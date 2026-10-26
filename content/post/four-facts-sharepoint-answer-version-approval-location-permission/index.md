---
title: "Four facts a SharePoint answer needs before you can trust it: version, approval status, location and permission"
date: 2026-10-19T00:00:00-00:00
author: "Kaspars Jurjāns"
githubname: jurjans
categories: ["Community post"]
images:
- images/thumbnail.png
tags: ["SharePoint Online", "Microsoft Graph", "Microsoft 365 Governance", "Copilot"]
type: "regular"
draft: false
---

## The problem

A document assistant over SharePoint rarely fails by saying nothing. The failure that hurts is a fluent answer taken from the wrong version of a procedure, from a draft that was never approved, or from a file the person asking should not have seen at all.

SharePoint already records everything needed to catch that. The work is to read those records and show them next to every answer. This post walks through the four facts we attach to each answer in our own assistant, which runs over about 400,000 documents in 865 sites for a construction company, and the Graph calls behind each one.

## 1. Which version was used

Libraries can keep major and minor versions. A major version (5.0) is a published milestone; a minor version (5.1) is a draft that not all site users are meant to see. The newest file content is therefore not always the valid one: 5.1 is newer than 5.0 and may be exactly the unfinished revision.

Microsoft Graph lists versions newest first:

```http
GET /drives/{drive-id}/items/{item-id}/versions
```

Each `driveItemVersion` carries `id`, `lastModifiedDateTime`, `lastModifiedBy` and a `publication` facet. Two things in that facet matter for a citation:

- `publication.level` is `published` or `checkout`.
- `publication.versionId` is "the unique identifier for the version that is visible to the current caller". Two people can be shown different versions of the same file, so the citation must name the version that was actually read, not just the file name.

The first entry in the list is the current version; its content comes from the usual `/content` endpoint, while `/versions/{id}/content` serves the earlier ones. One caveat from the docs: the `@microsoft.graph.downloadUrl` of a version does not require authentication and removing a user's permission "might not immediately invalidate the URL". Keep those URLs inside your service.

## 2. Was it approved

Content approval is a library setting ("Require content approval for submitted items"). When it is on, each item has a moderation status. In Graph it is exposed as the list item field `_ModerationStatus`:

```http
GET /sites/{site-id}/lists/{list-id}/items/{item-id}?$expand=fields($select=_ModerationStatus,_ModerationComments)
```

The values are integers:

| Value | Meaning |
|---|---|
| 0 | Approved |
| 1 | Rejected |
| 2 | Pending |
| 3 | Draft |
| 4 | Scheduled |

Three details we learned the hard way:

1. The field exists only in libraries where approval is enabled. If it is absent, say nothing rather than inventing "Approved".
2. When approval is switched on in a library that already has files, every existing file is marked Approved. "Approved" means the status field says so, not that someone reviewed it.
3. The approver's name is not stored in the standard item fields. If a customer needs it, it has to come from a column of their own.

So the answer shows the status word as it is, and the reader decides.

## 3. Where exactly

A link to a 200-page PDF is not a citation. The reader will not search it again; they will either trust the answer blindly or ignore the tool. We attach the page for PDF, the sheet and row range for Excel, and the slide number for PowerPoint. For spreadsheets the chunk also carries the sheet's header row, otherwise `45 | 1.2 | 2026-09-30` means nothing to the model or to a person.

This is cheap to implement and it is the check that makes the other three usable: if verification takes seconds, people actually verify.

## 4. Was this person allowed to see it

Permissions in SharePoint are inherited from site to library to folder to item unless inheritance is broken, and in a large tenant it is broken in thousands of places by years of ad hoc sharing. Do not rebuild that model in your own code.

The pattern that holds is the on-behalf-of flow: the API takes the signed-in user's token and calls Graph with delegated permissions, so every search and every file read is evaluated with that user's rights. The Microsoft Search API states this directly: results are trimmed, and a user cannot get more items through search than through a corresponding `GET` with the same permissions.

```http
POST /search/query
{ "requests": [ { "entityTypes": ["driveItem"], "query": { "queryString": "concrete tolerance" } } ] }
```

The opposite pattern, an application-only index that reads everything and filters afterwards, means a second copy of the permission model that must stay in sync. It will not.

## A short checklist

Before trusting any document assistant on your tenant, ask it:

- Which version did you use, and is it a major version or a draft?
- Where content approval is on, what is the status of the source?
- Which page, sheet and rows, or slide did this come from?
- Did you read this as me, or as an app that sees everything?

If an answer cannot show these four facts, treat it as a hint, not a fact.

---

*Kaspars Jurjāns is a SharePoint and Microsoft 365 architect in Latvia. The checks above are implemented in [Answergrove](https://ksj.lv/en/answergrove/), an assistant that answers from a company's own SharePoint documents and runs alongside Microsoft 365 Copilot. A longer version of this article, with references to the Microsoft documentation for each claim, is on [ksj.lv](https://ksj.lv/en/document-ai-answers-version-approval-page-permission/).*
