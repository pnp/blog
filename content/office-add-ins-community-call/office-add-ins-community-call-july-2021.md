---
title: "Office Add-ins community call -- July 2021"
date: 2021-07-22T10:22:00-04:00
author: "David Chesnut"
githubname: davidchesnut

categories: ["Office add-in developer community call"]
images: []
tags: []
type: "regular"
---

## Call summary



This month's community call features presentations - **Shared mailboxes
in Outlook** (Shared Mailbox vs Delegate Access/Shared Folder, Shared
Mailbox design considerations and add-ins) and **PnP: Message recipients
changed event (Outlook)** (If external recipients are detected in an
e-mail's list of recipients, than the message is automatically tagged as
External and optionally a disclaimer is appended to message).  This
month's Community spotlight recognizes James Wayne (Exclaimer) for his
continued contributions.  Thank you!   Q&A in chat throughout call.  The
call was hosted by David Chesnut (Microsoft) | @davidchesnut.
Microsoft Presenters: Juan Balmori | @juaneloBalmori, Ankush Oberoi,
and Elizabeth Samuel.   Recorded July 14, 2021.

## Agenda

-   Shared mailboxes in Outlook -- Juan Balmori (Microsoft) |
    @juaneloBalmori -- [00:50](https://youtu.be/zZpelH7CxJ8?t=50)
-   PnP: Message recipients changed event (Outlook) - Elizabeth Samuel,
    Sr. Dev Writer (Microsoft) --
    [11:13](https://youtu.be/zZpelH7CxJ8?t=673)
-   Shared mailboxes Demo - Ankush Oberoi (Microsoft) --
    [22:37](https://youtu.be/zZpelH7CxJ8?t=1357)
-   Q&A -- [26:45](https://youtu.be/zZpelH7CxJ8?t=1605)

## Demo Summaries

This month's community call featured presentations:

-   **Shared mailboxes in Outlook** - Juan Balmori (Microsoft) and
    Ankush Oberoi (Microsoft) discussed shared mailboxes and shared
    folders. [Shared
    mailbox](https://learn.microsoft.com/microsoft-365/admin/email/about-shared-mailboxes)
    is now in preview and we encourage you to try it out and give us
    feedback at <https://github.com/OfficeDev/office-js/issues>.
-   **Message recipients changed event for Outlook** - Elizabeth Samuel
    (Microsoft) shared a new PnP sample demonstrating how to use the
    Recipients Changed event to tag an email when there are external
    recipients.


## Q&A (Question & Answers)


\
Due to the technical difficulties we had on this call, we could not
access the chat to read your questions and provide follow-up. If you had
a question that did not get answered during the call, or in this blog,
please reach out to us by using our short [survey
form](https://aka.ms/officeaddinsform). We'll address any questions you
have during the next call.

**Can you add some additional error handling around failure cases for an
Outlook add-in that uses the On-send event? We have a scenario where if
an On-send add-in fails due to service outage users are unable to send
emails unless an admin performs a companywide deactivation of the
add-in. It would be helpful to let end-users still send their emails if
the On-send add-in fails to load or throws an unhandled exception.**

\
That's by design for the On-send event when we released the 1.8
requirement set. The good news is that the team is working on enabling a
new version of this event that will deal with the "add-in unavailable"
cases. We are working to get this into preview soon, so please keep an
eye out on future community calls.

\
**On the iOS and Android platforms, you only support Outlook API 1.5. Do
you think we will see support for 1.6+ before 2022?**

\
We have this in our backlog, but we don't yet have an ETA.

\
**Outlook on mobile still does not support compose mode add-ins, or the
On-send event. This was a highly requested feature on the UserVoice
system. When will Outlook on mobile support both of these? How did the
'Exclaimer' add-in from June 2021's community call work on Outlook
mobile without support for compose mode add-ins?**

\
We have this in our backlog, but we don't yet have an ETA. The
Exclaimer add-in isn't designed for use on Outlook on mobile.

\
**Is there a way to write a CSV file to the local computer's storage
where the add-in is running?**

\
Office Add-ins run in a browser runtime and only have the capabilities
of any web app running in a browser. It's not possible to write
directly to disk from the browser in any way that works cross-platform.
A recommended approach to write to a CSV file is to [write to files
using Microsoft Graph and
OneDrive](https://learn.microsoft.com/graph/api/resources/onedrive?view=graph-rest-1.0).

## Resources

### Outlook shared mailbox

-   [Create a shared mailbox - Microsoft 365 admin | Microsoft
    Docs](https://learn.microsoft.com/microsoft-365/admin/email/create-a-shared-mailbox)

-   [Remove automapping for a shared mailbox - Outlook | Microsoft
    Docs](https://learn.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)

-   [Enable shared folders and shared mailbox scenarios in an Outlook
    add-in | Microsoft
    Docs](https://learn.microsoft.com/office/dev/add-ins/outlook/delegate-access?tabs=windows)

### PnP: Use Outlook event-based activation to tag external recipients (preview)

-   PnP sample: [Use Outlook event-based activation to tag external
    recipients
    (preview)](https://github.com/OfficeDev/PnP-OfficeAddins/tree/main/Samples/outlook-tag-external)

### Office Add-ins community call

-   [Recurring, monthly community call calendar
    invite](https://aka.ms/officeaddinscommunitycall)
-   [Community call topic requests and
    questions](https://aka.ms/officeaddinsform)
-   Community call recordings on the [YouTube Microsoft 365 community
    channel](https://www.youtube.com/channel/UC_mKdhw-V6CeCM7gTo_Iy7w)

### Office Add-ins feedback

-   Technical questions -- Microsoft Q&A
    ([office-js-dev](https://learn.microsoft.com/answers/topics/office-js-dev.html)),
    ([office-addins-dev](https://learn.microsoft.com/answers/topics/office-addins-dev.html))
-   Issues -- [GitHub](https://github.com/OfficeDev/office-js/issues)
-   Recommendations and suggestions -- [Microsoft 365 Developer Platform
    ideas](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform)

\
The next Office Add-ins community call is on Wednesday, August 11, 2021
at 8:00AM PDT. Get the calendar invite at
<https://aka.ms/officeaddinscommunitycall>.

 
