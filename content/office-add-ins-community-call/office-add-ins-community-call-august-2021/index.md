---
title: "Office Add-ins community call -- August 2021"
date: 2021-08-22T08:43:00-04:00
author: "David Chesnut"
githubname: davidchesnut

categories: ["Office add-in developer community call"]
images:
- images/office-add-ins-august-agenda.png
tags: []
type: "regular"
---


## Call summary


This month's community call features presentations - **Dialog API
security updates** (recent changes to dialog API that address a security
vulnerability requires action from you IF your add-in uses cross-domain
communication between the dialog and taskpane.  Requirements and
timeline with grace period),
**PowerPoint API update: Shape object**
(preview the new Shape APIs -- insertion APIs along with ability to
manipulate basic, line & fill, text frame & range properties of these
objects.), and
**PnP: Open in Teams** (access data hosted on a website
inside a Microsoft Teams channel for purposes of collaborating on the
data).  This month's Community spotlight recognizes MVP Maarten van Stam
for his continued contributions.  Thank you!   Q&A in chat throughout
call.  The call was hosted by David Chesnut (Microsoft) |
@davidchesnut. Microsoft Presenters: Lillian Liu - Senior Program
Manager and Onur Onder, Senior Software Engineer.   Recorded August 11,
2021.

## Agenda

-   Dialog API security updates - Lillian Liu, Senior Program Manager
    (Microsoft) -- [01:00](https://youtu.be/UflCQGPjz14?t=60)
-   PowerPoint API update: Shape object - Onur Onder, Senior Software
    Engineer (Microsoft) -- [05:02](https://youtu.be/UflCQGPjz14?t=302)
-   PnP: Open in Teams - David Chesnut, Senior Dev Writer (Microsoft) |
    @davidchesnut -- [13:08](https://youtu.be/UflCQGPjz14?t=788)
-   Q&A -- [28:15](https://youtu.be/UflCQGPjz14?t=1695)

![office-add-ins-august-agenda.png](images/office-add-ins-august-agenda.png)

## Demo Summaries

-   **PowerPoint API update: Shape object** -- overview and live demo of
    the new Shape APIs -- insertion APIs (Geometric Shapes, Lines, Text
    Boxes) along with ability to manipulate properties of these
    objects.  Some of these API's are available now on PowerPoint
    Online.  APIs to be released in Windows Desktop and MAC builds in
    September - October.  User customized shapes may be saved, applied
    to master slide view.  
-   **PnP: Open in Teams --** access data hosted on a website inside a
    Microsoft Teams channel for purposes of collaborating on the data. 
    Teams detects the web-based data set on site, prompts viewer to
    open.  If opened, then data (in memory using OOXML) is written to a
    spreadsheet and saved in OneDrive via Graph.   Code sample
    available.   Script Lab add-in uses Graph APIs and  ASP.NET.


## Q&A (Question & Answers)


**In response to your post about runtimes and XML errors - I am also
having the same issue. It appears to be a bug in Visual Studio 2019
(<https://github.com/OfficeDev/office-js/issues/1756>). I've not worked
out how to get around it just yet. Any advice would be welcome please.**
We recently added some guidance about how to update the XSD files in
Visual Studio to solve this problem. For full details, see [Troubleshoot
development errors with Office Add-ins - Manifest schema validation
errors in Visual
St\...](https://learn.microsoft.com/office/dev/add-ins/testing/troubleshoot-development-errors#manifest-schema-validation-errors-in-visual-studio-projects).


**When is the GA for custom contextual tab on Mac?**
We don't have an ETA on this yet but hope to provide an update soon.
**When can we expect addSvg method to be officially released and can you
please provide us with a working example of this method? My attempts
keep erroring with \"this picture can't be displayed\"!**
There are some issues holding us back from releasing the **addSvg** API
to general availability. We'll update you as soon as we have a
definitive timeline for when it will go to GA.

Here is a sample that you can paste into Script Lab. It will insert a
yellow circle into the spreadsheet.
 
```javascript
$("#run").click(() => tryCatch(run));

async function run() {
    await Excel.run(async (context) => {
        const sheet = context.workbook.worksheets.getActiveWorksheet();
        sheet.shapes.addSvg("<svg width='100' height='100' xmlns='http://www.w3.org/2000/svg'><circle cx='50' cy='50' r='40' stroke='green' stroke-width='4' fill='yellow' /></svg>");
        await context.sync();
    });
}

/** Default helper for invoking an action and handling errors. */
async function tryCatch(callback) {
    try {
        await callback();
    }
    catch (error) {
// Note: In a production add-in, you'd want to notify the user through your add-in's UI.
        console.error(error);
    }
}
```
 
Note that in Script Lab you need to go to the libraries tab and use
<https://appsforoffice.microsoft.com/lib/beta/hosted/office.js> since
this is a preview API.

**When will it be possible to change text on slides and slide masters?**

As Onur showed in his demo on the community call, these features will be
coming out sometime in the next few months.

**When is the Word API going to be updated?**

We are looking to share some more information on the Word APIs around
the September timeframe.
**Is there a known bug or lack of support for insertFileFromBase64()
with Word 97-2003 documents?**
The **insertFileFromBase64** API does not support Word 97-2003 document
formats. This is primarily a design artifact of supporting Word on the
web, which only supports .docx and .dotx formats.
**Will you support manipulating the Tags property of Shape objects (as
well as Slide and Presentation objects)? Developers REALLY like to store
information in Tags objects.**
Yes, tag support is currently in preview -
<https://learn.microsoft.com/office/dev/add-ins/reference/requirement-sets/powerpoint-preview-apis> 

**How do I add an officeGroup to my CustomTab for my Word add-in? I
can't seem to find much info on this.**

**officeGroup** is currently only supported for PowerPoint. We plan to
support Word and Excel in the future but we don't have an ETA just yet.

**Could we manage the shape object in a different slide?**

Yes.

**context.presentation.slides** has a collection of slides. Use the
**slide.shapes** collection to access a shape on another slide.

**Do the shape APIs work with placeholder shapes, both in Normal and
Slide Master view?**
Yes. Shape APIs work with placeholder shapes, both in Normal and Slide
Master view.

**Can we change a shape's alt text?**

Unfortunately alt text editing is not supported at this time with this
set of APIs.

**When will the shape APIs be available in Excel?**

For Excel support, more information is in the article, [Work with shapes
using the Excel JavaScript
API](https://learn.microsoft.com/office/dev/add-ins/excel/excel-add-ins-shapes).

**Will the shapes API also include things like pictures and tables?**

The Shapes collection will have information about the shape type. This
means you can differentiate between pictures and other shapes. Some of
the fill and line properties also applies to pictures, so those can be
updated too. But there won't be more picture specific APIs in this
update.

**Can the shapes API be used to copy existing shapes between slides?**

Not yet. We are looking to provide this capability in a future update.

We're trying out the beta of shared/delegated mailbox support and
finding that in OWA, we still can't open a shared mailbox. We get the
error: \"The operation on mailbox failed because it's out of the
current user's write scope.\" There are more details
here([https://learn.microsoft.com/answers/questions/506662/outlook-owa-addin-installation-permission-\...](https://learn.microsoft.com/answers/questions/506662/outlook-owa-addin-installation-permission-issue-de.html)).
Is this something we can expect to work in the release?**

This is a known outcome and you can find more information, including how
to set up the mailboxes to work, in this GitHub issue:
<https://github.com/OfficeDev/office-js/issues/1877#issuecomment-897097347>

**Does SSO (getAccessToken) work for an add-in online inside of Word
inside of Teams?**

Using SSO from Word inside of Microsoft Teams is not supported today.
But we are working on enabling this in the near future and hope to share
some more information soon.

**Say a user has an Office 365 license, but has only ever used Excel for
Windows. They also have access to Teams. If we open an Excel workbook in
Teams, will they always be able to see and work with it? Are there any
Office licensing issues?**

There shouldn't be any licensing issues, as long as they are licensed
for Microsoft 365 (the new name for Office 365).

**Last month I asked about the ability to change the width of a task
pane in Outlook.

Can someone update me or share a link to the response
from last month?**
Thanks for asking about this again. We unfortunately lost some of the
Q&A from the last chat.

Currently the user can change the task pane width in Word, Excel, and
PowerPoint. However you can't set the task pane width programmatically.
That is on our backlog but we don't have an ETA for when we'll
implement this feature.

Outlook on the web does not support task pane resizing, and setting task
pane width is not on the backlog for Outlook. Outlook scenarios can be
slightly different, so if you want to create a feature request with more
details, that would be helpful. You can create a feature request at
[Microsoft 365 Developer Platform - Microsoft Tech
Community](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform).

**In the Word API, is there a way to restrict the document editing with
Office.JS? I'm looking at document level editing control, not content
controls.**

Right now, restricting document editing is not part of the Word APIs.
However this sounds like a great feature request to make at [Microsoft
365 Developer Platform - Microsoft Tech
Community](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform).

\
**Can you recommend any books, training or certification courses for
development in Office.JS?**


For books you might take a look at [Building Office Add-ins Using
Office.js](https://learn.microsoft.com/office/dev/add-ins/develop/develop-overview).
There isn't a specific certification for Office Add-in development, but
there is a [Microsoft 365 Certified: Developer
Associate](https://learn.microsoft.com/learn/certifications/m365-developer-associate/)
certification. There is an Office Add-in specific learning at [Extend
Office clients with Office add-ins -- Associate - Learn | Microsoft
Docs](https://learn.microsoft.com/learn/paths/m365-office-add-in-associate/).

**Does anyone know when VSTO will reach official end of life?**

We continue to support the VSTO and VBA technologies and keep them
healthy and secure.

**Is there way to retrieve the previous value of a cell from inside of a
custom function?**


We don't have official support for custom functions to share previous
values. But there are mechanisms available that let you enable this. You
need to [configure your add-in to use the shared
runtime](https://learn.microsoft.com/office/dev/add-ins/develop/configure-your-add-in-to-use-a-shared-runtime).
Cache the results back from your custom function, and use the
**caller.address** parameter so you know where the custom function was
being called from (where you can get the old value from your cache).

**Is supporting encrypted S/MIME messages and compose mode on Outlook
for mobile on the road map?**


This is on our backlog but we don't yet have an ETA for when this could
be available.

## Resources

### Dialog API security updates

-   [Cross-domain messaging to the host
    runtime](https://learn.microsoft.com/office/dev/add-ins/develop/dialog-api-in-office-add-ins#cross-domain-messaging-to-the-host-runtime)
-   [Cross-domain messaging to the dialog
    runtime](https://learn.microsoft.com/office/dev/add-ins/develop/dialog-api-in-office-add-ins#cross-domain-messaging-to-the-dialog-runtime)

### PowerPoint new Shape APIs

-   npm
    package: [<https://www.npmjs.com/package/@microsoft/office-js/v/1.1.71-custom.37>]
-   [CDN URLs for direct consumption:]
    -  <https://unpkg.com/@microsoft/office-js@1.1.71-custom.37/dist/office.js>]
    -  <https://unpkg.com/@microsoft/office-js@1.1.71-custom.37/dist/office.d.ts>
-   Add a simple shape with some
    properties: <https://gist.github.com/ononder/3f8986126d07a3f81d7fc36af80dbe72>

### PnP open in Microsoft Teams sample

-   Readme and
    sample: <https://github.com/OfficeDev/PnP-OfficeAddins/tree/davech-open-in-teams/Samples/excel-open-in-teams>. 
-   Pull
    request: <https://github.com/OfficeDev/PnP-OfficeAddins/pull/197>. 

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

The next Office Add-ins community call is on Wednesday, September 8,
2021 at 8:00AM PDT. Get the calendar invite at
<https://aka.ms/officeaddinscommunitycall>.
