---
title: "Office Add-ins community call -- September 8, 2021"
date: 2021-09-16T10:45:00-04:00
author: "David Chesnut"
githubname: davidchesnut

categories: ["Office add-in developer community call"]
images:
- images/officeadd-ins.jpg
tags: []
type: "regular"
---


## ![officeadd-ins.jpg](images/officeadd-ins.jpg)



## Call summary

 

This month's community call features presentations - Word API updates
(preview of Footnote and Comment APIs for citation management and
content insertion), Excel API updats (preview Excel v1.14 API -
Worksheet Protection Changed event), Mocking Office.js for unit tests
(you are invited to provide feedback  around mocking and unit testing
with Office.js APIs.) and Community call feedback (live/chat discussion
on the merits of this monthly community call). This month's Community
spotlight recognizes MVP Maarten van Stam for his continued
contributions. Thank you again! Q&A in chat throughout call. The call
was hosted by David Chesnut (Microsoft) | @davidchesnut.

**Microsoft Presenters:**

-   Ruoying Liang - Senior Program Manager
-   Raymond Lu - Senior Program Manager
-   Igor Ribeiro - Software Engineer
-   David Chesnut - Senior Dev Writer

## Agenda 

-   Word API updates - Ruoying Liang, Senior Program Manager (Microsoft)
    -- [1:06](https://www.youtube.com/watch?v=MfHpw5Tzs30&t=66s)
-   Excel API updates - Raymond Lu, Senior Program Manager (Microsoft)
    -- [9:59](https://www.youtube.com/watch?v=MfHpw5Tzs30&t=599s)
-   Mocking Office.js for unit tests - Igor Ribeiro, Software Engineer
    (Microsoft) --
    [16:53](https://www.youtube.com/watch?v=MfHpw5Tzs30&t=1013s)
-   Community call feedback - David Chesnut, Senior Dev Writer
    (Microsoft) --
    [23:18](https://www.youtube.com/watch?v=MfHpw5Tzs30&t=1398s)
-   Community spotlight - Maarten van Stam --
    [46:15](https://www.youtube.com/watch?v=MfHpw5Tzs30&t=2775s)
-   Q&A -- [47:02](https://www.youtube.com/watch?v=MfHpw5Tzs30&t=2822s)

## Actions 

-   Provide input on Mocking Office.js for unit tests blog. [Standard
    way to unit test and mock office-js
    API](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/standard-way-to-unit-test-and-mock-office-js-api/idi-p/2718673 "Standard way to unit test and mock office-js API")
-   Follow channels in Twitter -- for call agendas and summaries,
    release announcements:
    -   <https://twitter.com/microsoft365dev>
    -   <https://twitter.com/m365pnp>
-   Become a community contributor and get a badge in the [PnP
    recognition
    program](https://aka.ms/m365pnp-recognition "PnP recognition program")

## Demo summaries 

-   **Preview on latest Microsoft Word API updates: Footnote and Comment
    APIs**.  The Footnote API enables users to insert searchable
    citations with reference marks into documents. Similar to how you
    add comments to a cell in Excel, the new Comments API allows users
    to add comments to a specified range, paragraph, table in Word. You
    can reply to, resolve, view and delete comments. Supports URL and
    rich text. Beta rollout presently, available on Word on the web
    (on-line) only.
-   **Microsoft Excel v1.14 preview API: Worksheet Protection Changed
    event.**  After a quick review of APIs releasing in Excel v1.14, we
    looked at the **WorksheetProtectionChangedEvent** APIs. Previously
    protected worksheets threw an error when access was attempted. Now
    add-in status can be controlled in event logic with a new event
    handler. The edit button will be grayed out when the worksheet is
    protected and fully visible, and enabled when the worksheet is
    unprotected.


## Q&A (Question & Answers) 


**Is there a way to "auto push" manifest updates?**
Updates for add-ins happen as follows.

**Line-of-business add-in:**  When an admin explicitly uploads a
manifest, the add-in requires that the admin upload a new manifest file
to support metadata changes. The next time the relevant Office
applications start, the add-in will update. The web application can
change at any time.
**Office Store add-in:**  When an admin previously selected an add-in
from the Office Store, if there is an update available, the next time
the relevant Office applications start, the add-in will update. The web
application can change at any time.
For more information, see [Test and deploy Microsoft 365 Apps by
partners in the Integrated apps
portal](https://docs.microsoft.com/microsoft-365/admin/manage/test-and-deploy-microsoft-365-apps?view=o365-worldwide#more-about-office-add-ins-security).
**Will the new Word APIs be available for all platforms?**
These Word API updates will be available in Preview for Word on the web
later this month (September 2021). Eventually, they will be available on
all platforms. We do not have a specific timeframe to offer.
**Is the bookmarks API for Word being promoted out of preview?**
Yes, the bookmarks API will be in GA soon.
**Are you going to cover inserting new content types for Word?**
We are considering Equation, and some level of support for Fields.
**We cannot control the size of icons used in the ribbon in Office
Online. It uses the larger icon, when we want to force use of the
smaller icon.**
We currently ask for different sizes for your icons since Office will
choose the size based on a variety of factors. The size can vary based
on the number of add-ins on the ribbon, screen resolution, whether the
user is using the single line ribbon or not, and more. We have some
ideas for enabling more control over icon size, but right now this is
not on our backlog.
**I am interested in the best practices for loading a Word document from
a base64 encoded string. We have a repository of documents and the
content is exposed via a RESTful endpoint. I am currently using
getSelection and insertFileFromBase64.**
Probably the best thing to be aware of is that you can use this method
on a variety of objects. For example, you can use
[Word.Body.InsertFileFromBase64](https://docs.microsoft.com/javascript/api/word/word.body?view=word-js-1.1#insertFileFromBase64_base64File__insertLocation_),
and
[Word.Paragraph.InsertFileFromBase64](https://docs.microsoft.com/javascript/api/word/word.paragraph?view=word-js-1.1#insertFileFromBase64_base64File__insertLocation_).
To see all the objects with this method, type "InsertFileFromBase64"
into the search box in the [reference section for the Word
API](https://docs.microsoft.com/javascript/api/word?view=word-js-1.1).

If you're looking for more specific guidance, please provide more
information on ask on the [Microsoft 365 Q&A
site](https://docs.microsoft.com/answers/topics/office-addins-dev.html?page=2&amp;pageSize=15&amp;sort=active&amp;filter=all),
or at <https://stackoverflow.com> using the \[**office-js**\] tag.
**When will we be able to use SPFX to create Office Addins?**
A couple of years ago, we released a preview for creating Outlook
add-ins using the SharePoint Framework. While the feedback on it was
positive, it was overshadowed by other feedback on the limitations. As a
result, we decided to pause that preview and focus on delivering new
scenarios such as online meetings integration, signature support and
other event-based add-in scenarios. Unfortunately, we don't have a plan
at this time for when or if we will resume work on the preview.


**When running a Word add-in within a Word Form document (i.e. has form
controls and document protection), when can we expect support for other
types of content controls such as Date, Plain Text, Checkbox, etc.?**
Other types of content controls are in our backlog. We don't have an
ETA we can share for when these will be available.


**Using SSO from a Word add-in in Teams desktop works if the Word file
opens from the "Files" position. However, if the same file is opened
via "Assignments", SSO stops working. Additionally in "Assignment",
the dialogue opens a browser from outside Teams desktop (and then there
is no communication between the browser and the add-in). How do we get
SSO to work in this situation?**
Currently, SSO is not supported when Teams is the host. You'll need to
catch the error when calling getAccessToken(), which should be a 13012
error, and use a fallback dialog to sign in the user. To see how to set
up the fallback dialog, see [Create a Node.js Office Add-in that uses
single sign-on - Office Add-ins | Microsoft
Docs](https://docs.microsoft.com/office/dev/add-ins/develop/create-sso-office-add-ins-nodejs)
which also uses the [Office Add-in Node.js code
sample](https://github.com/OfficeDev/PnP-OfficeAddins/tree/main/Samples/auth/Office-Add-in-NodeJS-SSO).

You shouldn't be running into issues opening a fallback dialog. If
you're still having issues with the browser opening in a separate
window, can you provide more information at
<https://github.com/OfficeDev/office-js/issues>? We can follow up and
see if we can resolve the issue.

**Back in the Office add-ins Community call (March 09, 2021), you
revealed that admin-deployed add-ins would be automatically pinned to
the ribbon in Outlook on the web starting April 21, 2021. We have many
customers who already had deployed our add-in before that date, but
would now like to have it auto-pinned. However, in our internal testing
and testing done by our customers, re-deployed (remove + add) add-ins
are not automatically pinned in Outlook on the web. In addition to lack
of auto-pinning, we are naturally not seeing the "nudge" notification.
Are we doing something wrong? Our add-in is private and not available
via AppSource. Tenants are pure Microsoft 365.**
Thanks for letting us know about this. It looks like it is probably a
product bug. Please help us out and provide information on how to
reproduce this bug at <https://github.com/OfficeDev/office-js/issues>.
That's where we track any product bugs and we can look into it in more
detail.

