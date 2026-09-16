---
title: "One Outlook edit became two Microsoft Graph events with no shared ID"
date: 2026-09-17T00:30:00+01:00
author: "Ahmed Tariq"
githubname: ahmedtariq01
categories: ["Community post"]
images:
  - images/fig1_one_intent_two_objects.png
tags: ["Microsoft Graph", "Outlook", "Microsoft 365", "DynamoDB", "Webhooks"]
type: "regular"
---
A user opened a recurring room booking in Outlook, chose **Edit this and all following events**, and changed the future part of the series. The booking integration then handled an update and a create as two unrelated actions.

That produced the wrong result in the connected reservation system. The shortened series updated one reservation group. The new future series created another group. A later attempt to cancel the booking could only see part of what the user still regarded as one series.

Both Microsoft Graph event handlers worked as designed on their own. The service had no state that carried the user's intent from one handler to the other.

![One Outlook action becomes an update to one series master and a create for another series master.](images/fig1_one_intent_two_objects.png)

*Figure 1. One user action reached the integration as two resource changes with separate identifiers.*

## The interface described an action while Graph exposed objects

Outlook offers an option to edit one occurrence, the full series, or the selected occurrence and all events that follow it. That third choice describes what the user wants to happen. It does not promise that an integration will receive one event object carrying that intent.

In this incident, inspection of the affected calendar records showed two recurring series masters:

- the original master had a shorter recurrence range
- a new master began at the edit point
- the masters had different event IDs
- the masters also had different `iCalUId` values

The Graph event resource includes both `iCalUId` and `seriesMasterId`. Those fields solve other identity problems. `seriesMasterId` connects an occurrence or exception to its current master. It does not connect an old master to the new master that replaced its future portion. In the records I inspected, neither field linked the two masters.

I treat this shape as an observed integration behaviour from this incident. Microsoft documents the Outlook editing choice and the Graph event fields, but I found no API contract that says every use of the interface must always produce this exact pair.

## The first useful test was a mutation matrix

The original client report described two symptoms. Future edits did not reach the reservation platform, and a series edited that way later failed to cancel cleanly. Reading the code suggested several possible paths, but it could not establish which Graph objects Outlook had created.

I wrote a probe that created a fresh weekly series for each of five scenarios:

1. extend the end date
2. shorten the end date
3. add another weekday
4. move the recurrence to another weekday
5. shorten one master and create another master at the cutoff

The fifth scenario acted as a known split. It gave the other mutations a concrete two-master shape to compare against.

The first probe inspected the organizer's calendar. Production notifications came from the room mailbox, so that result alone could not explain the integration. A second probe recorded the room calendar before the split, performed the two Graph mutations on the organizer calendar, waited for room processing, and counted the resulting room masters.

This controlled probe reproduced the two-object shape through explicit Graph operations. It did not automate a click in the Outlook interface. That distinction matters. The client incident connected the user action to the failure. The probe showed how the same old-master update and new-master create propagated to the mailbox that generated notifications.

## Event-level idempotency could not join the pair

The service subscribed to created, updated and deleted event changes in the room mailbox. It already stored an event mapping so a repeated notification for the same event would not create another reservation.

That protection stopped duplicates for one Graph ID. It could not help when Graph presented the future portion as a new master with a new ID.

The update path saw a valid series shortening. The create path saw a valid new series. If each handler committed its own interpretation, the reservation platform ended with two groups for one calendar action.

The service needed correlation across messages. It also needed to distinguish a split from an ordinary shortening where no replacement series would arrive.

## A short-lived marker joined the two messages

The first implementation used a 60 second marker in DynamoDB.

When the update handler found that the last cancelled occurrence ended after the last remaining occurrence, it treated the change as a possible truncation. It stored the earlier end point, the previous end point and an expiry time on the old master's mapping.

When a new series arrived for the same room, the create handler looked for an unexpired marker whose truncation point fell at or before the new series start. A match connected the two messages. The handler then cancelled the old reservation group, retired its mapping rows, cleared the marker and created a clean group for the new master.

```text
on old series update
  if the final active occurrence moved earlier
    store a truncation observation for 60 seconds

on new series create
  find an unexpired observation for the same room
  require the old cutoff to be at or before the new start
  cancel the old reservation group
  retire the old mappings
  clear the observation
  create the new reservation group
```

The expiry let a genuine shortening continue without later capturing an unrelated series. Clearing the marker stopped a retried create from cancelling the old group twice. Unit tests covered both branches: a matching candidate cancelled and retired the old group before the new create, while a create with no candidate left old groups alone.

![An update stages a short-lived truncation marker and a nearby create resolves the pair.](images/fig2_correlation_window.png)

*Figure 2. The marker carries user intent across two webhook handlers for a bounded time.*

## The lookup contained a DynamoDB trap

A later source review found a serious weakness in the marker lookup. The code used a table scan with a filter and `Limit: 5`.

```text
scan the mapping table
  limit evaluated items to 5
  filter for the same room
  filter for a live truncation marker
  filter for a compatible cutoff
```

DynamoDB applies a scan filter after it reads the items. The `Limit` value caps how many items DynamoDB evaluates before that filter. If the first five table items belong to other rooms, the call can return no match even when the correct marker sits later in the table.

The scan also uses eventually consistent reads unless the caller requests strong consistency. A create notification can therefore miss a marker that the update handler has just written.

The low number of active markers does not make this safe. Marker rarity actually makes a filtered scan more likely to examine unrelated items first. Pagination would eventually find the marker, but it would turn a latency-sensitive webhook path into a growing table walk.

![A DynamoDB scan stops after five evaluated items before the filter can reach the matching marker.](images/fig3_scan_limit_trap.png)

*Figure 3. `Limit` constrains evaluated items, so a filtered scan can return an empty result while a matching row exists.*

I would replace the scan with a queryable correlation record. One option uses a sparse secondary index with the room as its partition key and the truncation point plus master ID as its sort key. Only active observations enter the index. The create handler queries one room and a bounded time range, then checks expiry and ambiguity in application code.

Another option writes one dedicated correlation item per room. A conditional or transactional write can make the winner explicit when two truncations happen close together. Either design makes cost and correctness depend on candidates for one room rather than the size and physical order of the full mapping table.

## The cancellation must gate the replacement

The implementation had another unsafe edge. If cancellation of the old reservation group threw an error, the handler logged a warning and continued. It still retired the old mappings and created the replacement group.

That can preserve the very duplicate the correlation logic exists to remove. The old group may remain active while the service forgets its mappings and creates a new group.

A safer transition has a firm commit point:

1. record the matched pair with an idempotency key
2. cancel the old group
3. confirm that cancellation reached the required state
4. retire the old mappings and create the replacement
5. mark the pair resolved

If cancellation fails, the service keeps the old mappings and retries or sends the pair to a recovery queue. It does not move to a state that claims the old group has gone.

The handler should also support either arrival order. The initial design assumed that the old-master update would stage the marker before the new-master create searched for it. Webhook delivery and processing can race. Storing both halves as short-lived observations lets either handler complete the match when its counterpart already exists.

## Correlation needs an ambiguity rule

Room and time provide useful evidence, but they do not form a global identity. Two organizers could truncate two recurring bookings for the same room within the same minute.

The initial lookup selected the candidate with the truncation point closest to the new start. That produces a deterministic answer. It does not prove the answer is correct.

When several candidates remain plausible, the service should avoid a destructive guess. It can compare more non-sensitive context such as organizer identity, normalized subject, duration and recurrence pattern. If the candidates still tie, it should hold the change for reconciliation and raise an operational signal.

That rule turns uncertainty into a visible state. A quiet false match can cancel the wrong reservation group.

## Webhooks start reconciliation, they do not complete it

Microsoft Graph change notifications tell the service that an event changed. The handler still needs to fetch current state and apply idempotent business rules. A short outage, expired subscription or failed handler can leave a gap even when the correlation algorithm itself works.

Graph calendar delta queries provide a recovery path for added, updated and deleted events within a calendar view. A production design can keep a delta watermark per room, renew subscriptions through their lifecycle notifications, and run periodic reconciliation. The webhook keeps the common path fast. Delta processing repairs missed or partially processed changes.

For this split workflow, I would preserve these records for every decision:

- both Graph event IDs and their `iCalUId` values
- the old and new recurrence ranges
- room and organizer identifiers in protected logs
- notification receive and processing times
- the correlation candidates considered
- the cancellation result and final reservation-group state
- the idempotency key and resolution status

Those fields make the system explainable without storing full meeting content in routine logs.

## The boundary was the real bug

The integration handled an updated resource and a created resource correctly. It failed because one user action crossed the boundary between them.

The first correlation marker repaired the immediate path and proved the value of a bounded state machine. The later review also showed why correlation code deserves the same scrutiny as payment or deployment code. Storage access patterns, read consistency, delivery order and failure commits all affect whether two messages really become one operation.

Whenever an interface offers an action over “this and all following,” inspect the objects on both sides of the integration. The visible series may split at the API boundary, and no identifier may carry the user's intent across it.

## References

- [Microsoft Support: Change an appointment, meeting, or event in Outlook](https://support.microsoft.com/en-us/outlook/calendar/change-an-appointment-meeting-or-event-in-outlook)
- [Microsoft Graph: Event resource type](https://learn.microsoft.com/en-us/graph/api/resources/event?view=graph-rest-1.0)
- [Microsoft Graph: Outlook change notifications](https://learn.microsoft.com/en-us/graph/outlook-change-notifications-overview)
- [Microsoft Graph: Track incremental changes to events in a calendar view](https://learn.microsoft.com/en-us/graph/delta-query-events)
- [AWS: Working with scans in DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Scan.html)
