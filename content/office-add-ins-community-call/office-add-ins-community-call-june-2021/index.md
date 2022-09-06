---
title: "Office Add-ins community call -- June 2021"
date: 2021-06-16T08:33:00-04:00
author: "David Chesnut"
githubname: davidchesnut

categories: ["Office add-in developer community call"]
images:
- images/office-add-ins-call-recording-9th-june.png
tags: []
type: "regular"
---


## Call summary



This month's community call features presentations - Excel v1.13 API
updates (highlights 2 new APIs  **insertWorksheetFromBase64** and
**onFormulaChanged** event), Outlook Add-ins - Build 2021 recap (GA for
**Event- Driven Add-in with onCompose Event** and for **Mailbox 1.10 for
Outlook**), New Email Signature Add-in (Exclaimer's Outlook Add-in
product uses latest Outlook Add-ins capabilities), and PnP: Insert
template from external Excel file (insert external Excel file into the
open Excel worksheet and populate it with JSON data).  This month's
Community spotlight recognizes MVPs Damien Bird (DamoBird365) and
Maarten van Stam.  Thank you!    Q&A in chat throughout call.  The call
was hosted by David Chesnut (Microsoft) | @davidchesnut. Microsoft
Presenters: Raymond Lu and Juan Balmori | @juaneloBalmori.  Special
guest presenters James Wayne and Phillip Vetter from Exclaimer Cloud. 
Recorded on June 9, 2021.

## Agenda

June's call, hosted by **David Chesnut**, featured the following
presenters and topics:

-   **Excel API updates** -- Raymond Lu (Microsoft) -
    [1:31](https://youtu.be/934N5mZY_5M?t=91)
-   **Outlook API updates** - Juan Balmori (Microsoft) |
    @juaneloBalmori - [13:17](https://youtu.be/934N5mZY_5M?t=797)
-   **New Email Signature Add-in** - James Wayne (Exclaimer Cloud) -
    [21:27](https://youtu.be/934N5mZY_5M?t=1287)
-   **PnP: Insert template from external Excel file** - David Chesnut
    (Microsoft) | @davidchesnut -
    [37:12](https://youtu.be/934N5mZY_5M?t=2232)



## Q&A (Question & Answers) 

Unfortunately, we had some issues with the chat during the call. We
apologize to folks who were not able to ask a question. If you have a
question, you can reach out to us by using our short [survey
form](https://aka.ms/officeaddinsform). We'll address any questions in
the form during the next call.
**Can you fix Teams add-ins functionality for online meetings?
Association between Outlook events and online meetings is non-existent.
The Teams SDK currently works online with single instance meetings, but
there is no way to associate custom data with event instance and event
series. For example, the SDK does not let you get meeting instance start
time.**

We can help with Office Add-ins development, but this is a good question
for Microsoft Teams. We recommend asking this question on
[office-teams-app-dev - Microsoft
Q&A.](https://docs.microsoft.com/answers/topics/office-teams-app-dev.html)
Thanks!
**Are there plans to provide access to the Outlook auto-complete list
via office-js? The list is available in the UI on mobile, OWA and
desktop clients while entering recipients. It would be useful for us to
be able to access it (or a list of commonly used email addresses for the
user) via office-js to check the entered recipients.**

There are no plans at this time, but this sounds like a great idea!
Please create a feature request for this on our ideas page at
[https://aka.ms/m365dev-suggestions](https://aka.ms/m365dev-suggestions).
Thanks!


**There are many videos and articles about Single sign-on for Office
Add-ins. The Yeoman generator uses the NPM package "msal" but there is
also an NPM package called "@azure/msal-browser" and another one
called "@azure/msal-react". Can these all be used inside an Office
Add-in? Which ones are the recommended ones to use?**


 In general you can use most web libraries with an Office Add-in. For
SSO you don't need an authentication library to get the user identity
token, since you just call
[**getAccessToken**](https://docs.microsoft.com/javascript/api/office-runtime/officeruntime.auth?view=excel-js-preview#getAccessToken_options_)().
However, you should implement a fallback sign-in dialog for scenarios
where SSO will fail. In these cases using an authentication library
makes the process easier. There is no requirement to use MSAL, but if
you do, you should use the official MSAL package for the
framework/language of choice as recommended by Microsoft Azure. For more
information see [Enable single sign-on for Office Add-ins - Office
Add-ins | Microsoft
Docs](https://docs.microsoft.com/office/dev/add-ins/develop/sso-in-office-add-ins)


**I am attempting to implement the shared JavaScript runtime. However, I
get an error when adding the \<Runtimes> section. The error is: The
element 'Host' in namespace
'**[**http://schemas.microsoft.com/office/taskpaneappversionoverrides**](http://schemas.microsoft.com/office/taskpaneappversionoverrides)**'
has invalid child element 'Runtimes' in namespace
'**[**http://schemas.microsoft.com/office/taskpaneappversionoverrides**](http://schemas.microsoft.com/office/taskpaneappversionoverrides)**'.
List of possible elements expected: 'AllFormFactors,
DesktopFormFactor' in namespace
'**[**http://schemas.microsoft.com/office/taskpaneappversionoverrides**](http://schemas.microsoft.com/office/taskpaneappversionoverrides)**'.**

This error can occur if the \<Runtimes> section is not in the expected
location. Be sure to put the \<Runtimes> section just below the \<Host>
tag as follows:
\<Hosts>

  \<Host xsi:type="Workbook"\>

  \<Runtimes>

    \<Runtime resid="Taskpane.Url" lifetime="long" />

  \</Runtimes>
In general if you run into a manifest error, you can compare the
manifest to one that works and look for any significant differences. For
example you could compare against this [PnP sample
manifest](https://github.com/OfficeDev/PnP-OfficeAddins/blob/main/Samples/excel-shared-runtime-scenario/manifest.xml)
that uses a shared runtime.

You can also run [manifest
validation](https://docs.microsoft.com/office/dev/add-ins/testing/troubleshoot-manifest)
which can provide more information about the error.

## Resources

### Excel API updates 

-   insertWorksheetsFromBase64 - [Work with workbooks using the Excel
    JavaScript API - Office Add-ins | Microsoft
    Docs](https://docs.microsoft.com/office/dev/add-ins/excel/excel-add-ins-workbooks#insert-a-copy-of-an-existing-workbook-into-the-current-one-preview)
-   onFormulaChanged - [Work with worksheets using the Excel JavaScript
    API - Office Add-ins | Microsoft
    Docs](https://docs.microsoft.com/office/dev/add-ins/excel/excel-add-ins-worksheets#detect-formula-changes-preview)
-   getDirectDependents - [Work with formula precedents and dependents
    using the Excel JavaScript API - Office Add-ins |
    Micros\...](https://docs.microsoft.com/office/dev/add-ins/excel/excel-add-ins-ranges-precedents-dependents)
-   Workbook.onActivated - [Work with workbooks using the Excel
    JavaScript API - Office Add-ins | Microsoft
    Docs](https://docs.microsoft.com/office/dev/add-ins/excel/excel-add-ins-workbooks#detect-workbook-activation-preview)
-   Table.resize - [Work with tables using the Excel JavaScript API -
    Office Add-ins | Microsoft
    Docs](https://docs.microsoft.com/office/dev/add-ins/excel/excel-add-ins-tables#resize-a-table-online-only)

### Outlook add-ins Build conference recap 

-   Try out event-based activation -
    <https://aka.ms/LearnEventBasedAddIns>


### PnP: Insert an external Excel file and populate it with JSON data 

-   PnP sample: [Insert an external Excel file and populate it with JSON
    data](https://github.com/OfficeDev/PnP-OfficeAddins/tree/main/Samples/excel-insert-file)

### Office Add-ins community call 

-   [Recurring, monthly community call calendar
    invite](https://aka.ms/officeaddinscommunitycall)
-   [Community call topic requests and
    questions](https://aka.ms/officeaddinsform)
-   Community call recordings on the [YouTube Office Dev
    channel](https://aka.ms/OfficeDevYouTube)

### Office Add-ins feedback 

-   Technical questions -- Microsoft Q&A
    ([office-js-dev](https://docs.microsoft.com/answers/topics/office-js-dev.html)),
    ([office-addins-dev](https://docs.microsoft.com/answers/topics/office-addins-dev.html))
-   Issues -- [GitHub](https://github.com/OfficeDev/office-js/issues) 
-   Recommendations and suggestions -- [Microsoft 365 Developer Platform
    ideas](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform)

The next Office Add-ins community call is on **Wednesday, July 14,
2021** at 8:00AM PDT. Get the calendar invite at
<https://aka.ms/officeaddinscommunitycall>.

