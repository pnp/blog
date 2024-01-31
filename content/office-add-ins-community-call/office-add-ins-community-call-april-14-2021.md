---
title: "Office Add-ins community call -- April 14, 2021"
date: 2021-05-03T12:56:00-04:00
author: "David Chesnut"
githubname: davidchesnut

categories: ["Office add-in developer community call"]
images: []
tags: []
type: "regular"
---


## Call summary



April's call, hosted by **David Chesnut**, featured the following
presenters and topics:\
• **Richard Taylor** discussed different support options available on
Microsoft 365, and how to submit a new support ticket.
• **Sudhi Ramamurthy** shared news about updates to APIs, Recorder, and
Admin-control for Office Scripts.
• **Leslie Black (Analysis Cloud Limited)** demonstrated a TICTACUFO
application he created with Office Scripts.
• **David Chesnut** demonstrated a new PnP sample that shows how to
handle event-based activation and set the signature in Outlook.
To watch the call, tap the following link.
[Office Add-ins community call -- April 2021 -
YouTube](https://www.youtube.com/watch?v=hGVdftCzs20)


## Q&A (Question & Answers)


We welcome you to submit questions and topic suggestions prior to each
call by using our short [survey form](https://aka.ms/officeaddinsform).

### Support options

**When we try to open tickets in the admin center regarding SharePoint
Development they are getting immediately closed with the comment \"we
don't provide support for developer issues\". Is that different for
Office Add-ins?**
The comment you see applies if you don't have a Premier account, or
Enterprise SKU. If you do have a Premier account and are seeing this
comment, please reach out to us on the next community call web chat so
we can follow up with you.
**What level of support can I get for my tenant from the Microsoft 365
Developer Program?**\
The Microsoft 365 Developer Program provides standard Office 365
support, and does not include developer support. You can get help with
developer questions at Microsoft Q&A for Office Add-ins, or at Stack
Overflow \[office-js\].

### Office Scripts


**ServiceHub is not enabled for my Enterprise ID. Is it possible for an
admin to configure without admin access to rest of the Office 365
tenant?**\
If you have a Premier account, we can reach out to your ADC/TAM and
ensure you have access. If you just have an Enterprise subscription, use
the O365 admin instead. Either should work.
**Are Office Scripts for Excel on the web available to Microsoft 365
family accounts or just Enterprise?**\
Currently, Office Scripts are only available on Enterprise, though
we're exploring expanding availability to other licenses.

### Miscellaneous questions

**When will the current Outlook preview requirement set, including
event-based activation, be available in production?**\
We don't have a specific date yet, but we hope to make it available
soon.
**The Outlook REST API is going to be decommissioned. Is it safe to
continue using EWS (Exchange Web Services) with Outlook add-ins going
forward or is it also at risk of being decommissioned?**\
At present, there is no plan to decommission EWS.
**Is it possible to port Office.addin.showAsTaskpane common API function
to Outlook JS?**\
This is a great suggestion! Can you please provide more details on this
idea, and scenario at [Microsoft 365 Developer Platform - Microsoft Tech
Community](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform)?\
**One of our custom functions must access data (a table) not specified
in the arguments. We've noticed that calling Excel.run to request that
data through the Excel request context on every formula invocation leads
to concurrency issues (RichApi.Error: Wait until the previous call
completes.) Is there a flexible way to get this to work?**
There is a code approach used in [GitHub issue 483 in
office-js](https://github.com/OfficeDev/office-js/issues/483#issuecomment-490592291)
that may help you. If that doesn't work for your scenario, please post a
question with more information at [Microsoft Q&A: Office JavaScript
API](https://learn.microsoft.com/answers/topics/office-js-dev.html).
**In Excel custom functions, is there a way to pause the calculations
and resume later (other than setting calculation mode to manual)? End
users want to pass an additional flag to the custom function that
indicates if it should run or not run.**
We suggest switching to manual recalc mode, instead of using an argument
to the function. Our goal is for Excel custom functions to run using the
same paradigm as built-in functions. We don't have a design pattern
where we pause recalc based on an argument to a function. It's clearer
for users if you ask them to change to manual recalc, that you could
implement in the task pane UI. Then when completed, you can switch back
to automatic recalculation and the custom functions will run.
**In Excel custom functions, you can get the address of the calling cell
from the invocation object. Is there a way to get the current value from
the cell along with the address?**\
We suggest that you use the onCalculated event which is called when
custom functions are calculated. Here's an example:

```javascript
async function onCalculated(event) {
 await Excel.run(async (context) => {
        console.log(event.address);
        if (event.address == "A13") // “A13” here is an example of the cell that has the custom function. It can be replaced by a real cell address.
        {
           context.load (event.address, “values”);
           await context.sync();
          console.log(`The range value was "${cellC1.values}".`);
        }
      });
    }
```


**Can the Microsoft Graph API be used by an add-in without a dedicated
server to proxy requests to the Graph API? We're trying to replace the
usage of the Outlook REST API in an add-in that makes API calls from the
client-side. We are struggling to find tutorials covering that case.**\
If you're Outlook add-in is basically a single-page app (SPA) this
tutorial will help you call the Microsoft Graph API from the add-in:
[Tutorial: Create a JavaScript single-page app that uses auth code
flow - Microsoft identity
platform\...](https://learn.microsoft.com/azure/active-directory/develop/tutorial-v2-javascript-auth-code).
There are also additional Microsoft Graph samples at
[https://github.com/Azure-Samples/active-directory-aspnetcore-webapp-openidconnect-v2/tree/master/2-W\...](https://github.com/Azure-Samples/active-directory-aspnetcore-webapp-openidconnect-v2/tree/master/2-WebApp-graph-user)\
**When will Outlook sideload and debug from VS Code (as demoed in
November community call) be available?**\
This feature is available, but there is an issue that prevents it from
working in all scenarios. We're working to get a fix out soon.


## Resources

### Microsoft 365 support

-   [Premier Services in CSS Unified
    Support](https://serviceshub.microsoft.com/)
-   [Concierge Services in Office 365 Admin
    Portal](https://admin.microsoft.com/)
-   Community and Q+A Answer Forums
    -   <https://developer.microsoft.com/office/blogs/>
    -   <https://learn.microsoft.com/answers/topics/office-addins-dev.html>
    -   <https://stackoverflow.com>
-   [Troubleshoot development errors with Office
    Add-ins](https://learn.microsoft.com/office/dev/add-ins/testing/troubleshoot-development-errors)\
    [Troubleshoot user errors with Office
    Add-ins](https://learn.microsoft.com/office/dev/add-ins/testing/testing-and-troubleshooting)\
    [Resource limits and performance optimization for Office
    Add-ins](https://learn.microsoft.com/office/dev/add-ins/concepts/resource-limits-and-performance-optimization)

### Office Scripts demo by Leslie Black

-   Source for TICTACUFOGame:
    <https://github.com/MrAnalyticals/OfficeScripts/tree/main/TICTACUFOGame>
-   Short demo video: <https://youtu.be/FMOCPm1aV_Q>
-   Long demo video: <https://youtu.be/F49hwCzpygQ>
-   Office Scripts LinkedIn Group:
    <https://www.linkedin.com/groups/9016822/>
-   Analysis Cloud Limited, The Irish Cloud Company:
    [www.analysis.ie](http://www.analysis.ie)

### PnP: Outlook set signature

-   Sample code:
    <https://github.com/OfficeDev/PnP-OfficeAddins/tree/master/Samples/outlook-set-signature>
-   [Configure your Outlook add-in for event-based
    activation](https://learn.microsoft.com/office/dev/add-ins/outlook/autolaunch)

### Office Add-ins community call

-   [Recurring, monthly community call calendar
    invite](https://aka.ms/officeaddinscommunitycall)
-   [Community call topic requests and
    questions](https://aka.ms/officeaddinsform)
-   Community call recordings on [Microsoft 365
    developer YouTube](https://aka.ms/OfficeDevYouTube)

### Office Add-ins feedback

-   Technical questions -- Microsoft Q&A
    ([office-js-dev](https://learn.microsoft.com/answers/topics/office-js-dev.html)),
    ([office-addins-dev](https://learn.microsoft.com/answers/topics/office-addins-dev.html))
-   Issues -- [GitHub (office-js
    repo)](https://github.com/OfficeDev/office-js/issues)
-   Recommendations and suggestions -- [Microsoft 365 Developer Platform
    ideas](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform)

The next Office Add-ins community call is on **Wednesday, May 12, 2021**
at 8:00AM PDT. You can download the calendar invite at
<https://aka.ms/officeaddinscommunitycall>.
