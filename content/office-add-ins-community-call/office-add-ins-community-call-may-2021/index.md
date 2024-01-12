---
title: "Office Add-ins community call -- May 2021"
date: 2021-05-19T01:37:00-04:00
author: "David Chesnut"
githubname: davidchesnut

categories: ["Office add-in developer community call"]
images:
- images/office-add-ins-call-recording-12th-may.png
tags: []
type: "regular"
---

## Agenda

May's call, hosted by **David Chesnut**, featured the following
presenters and topics:

-   **Abid Rahman** announced the GA of keyboard shortcuts and shared
    plans for the feature going forward. --
    [00:59](https://youtu.be/Y6nee7VQkFE?t=59)
-   **Sohail Zafar** announced the GA of contextual tabs and updates
    about the feature and plans going forward. --
    [11:03](https://youtu.be/Y6nee7VQkFE?t=663)
-   **Special guest presenter Damien Bird (DamoBird365)** demonstrated
    how to use Office Scripts with Power Automate to generate and fill
    in an invoice with data from SharePoint, and then save to a PDF.  --
    [19:57](https://youtu.be/Y6nee7VQkFE?t=1197)
-   **Juan Balmori** shared Outlook updates on event-based activation
    and announced new preview events. --
    [35:09](https://youtu.be/Y6nee7VQkFE?t=2109)





## Q&A (Question & Answers)


Unfortunately, we had some issues with the chat during the call. We
apologize to folks who were not able to ask a question. If you have a
question, you can reach out to us by using our short [survey
form](https://aka.ms/officeaddinsform). We'll address any questions in
the form during the next call.

**Is it possible to see a demonstration of debugging Outlook add-ins in
the Outlook application on mobile devices? Ideally for a local developer
instance of an add-in server rather than one publicly accessible (since
a hurdle is getting the mobile device to communicate successfully with
lab instance of add-in server). We've encountered issues on Android
with certificates running lab instances of add-ins so would like to see
a demonstration of recommended approach to testing on mobile devices.**

Thanks for this request! We're working to schedule this demo this on a
future call.
**When the Outlook REST API is decommissioned in November 2022, what API
should add-ins deployed to customer hosted Exchange Servers (2016/2019)
use for mobile support? Will the Outlook REST API remain active for
Exchange Server and just be decommissioned for O365 accounts?**

We're still working through details on this, and we plan to share more
guidance in the future.
**Is there any movement on supporting reading values, such as AppDomains
and custom properties, from the add-in manifest at runtime through
Office.js? The request has come up over the years on forums and been
raised on UserVoice. We would prefer to write a key and value to the
manifest, instead of passing values to URL endpoints, as this opens the
door to people injecting their own values outside of the manifest to
those endpoints.**

This feature is not on our backlog. We migrated UserVoice requests that
had over 100 votes to our new [Microsoft 365 Developer Platform Ideas
Forum](https://aka.ms/m365dev-suggestions). We'd ask that you **Submit
an Idea** on this page and recreate your request. If there's enough
interest from the community we'll definitely consider it. Thanks!
**What is the roadmap for Office.js for PowerPoint? When will it achieve
feature parity with VSTO APIs?**

VSTO is a huge API surface, which is why we approach building out the
Office JS API based on prioritized scenarios. It's tremendously helpful
to understand the scenarios you are trying to unlock and what API's you
need. That helps us prioritize. Please let us know which scenarios you
need enabled on our [Ideas
page](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform/label-name/office%20add-ins%20development)
and use the "Office Add-ins development" label. We're planning to
deliver increased API surface area for PowerPoint going forward.
**In Excel on the web, when you close an Office Add-In, it creates a bar
on the left side of Excel and puts an icon for the add-in on that bar,
allowing the user to quickly show or hide add-ins from there. Will this
be available in Excel on the desktop?**

Thanks for this feature request! Can you let us know more about this on
our [ideas
page](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform/label-name/office%20add-ins%20development)
and provide a screen shot to help us understand better?
**Will you support Excel.Range.Interior characters and the ability to
apply formatting at the character level?**

Thanks for this request! We're looking into supporting this. Can you
please create a request for this on our [ideas
page](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform/label-name/office%20add-ins%20development)?

## Resources

### Keyboard shortcuts

-   [Custom keyboard shortcuts in Office Add-ins - Office Add-ins |
    Microsoft
    Docs](https://learn.microsoft.com/office/dev/add-ins/design/keyboard-shortcuts)
-   [PnP sample: Use keyboard shortcuts for Office add-in
    actions](https://github.com/OfficeDev/PnP-OfficeAddins/tree/master/Samples/excel-keyboard-shortcuts)

### Custom contextual tabs

-   [Create custom contextual tabs in Office Add-ins - Office Add-ins |
    Microsoft
    Docs](https://learn.microsoft.com/office/dev/add-ins/design/contextual-tabs)
-   [PnP sample: Create custom contextual tabs on the
    ribbon](https://github.com/OfficeDev/PnP-OfficeAddins/tree/master/Samples/office-contextual-tabs)

### Office Scripts demo by Damien Bird

-   Excel demo: <https://damobird365.birdhoose.co.uk/exceldemo>
-   [DamoBird365 -
    YouTube](https://www.youtube.com/channel/UC-NCKrEw6CM8fidaIk-yrUQ)

### Outlook event-based activation

-   [Outlook add-ins overview - Office Add-ins | Microsoft
    Docs](https://learn.microsoft.com/office/dev/add-ins/outlook/outlook-add-ins-overview)
-   [Configure your Outlook add-in for event-based activation
    (preview) - Office Add-ins | Microsoft
    Docs](https://learn.microsoft.com/office/dev/add-ins/outlook/autolaunch)
-   PnP sample: [Use Outlook event-based activation to set the signature
    (preview)](https://github.com/OfficeDev/PnP-OfficeAddins/tree/master/Samples/outlook-set-signature)

### Office Add-ins community call

-   [Recurring, monthly community call calendar
    invite](https://aka.ms/officeaddinscommunitycall)
-   [Community call topic requests and
    questions](https://aka.ms/officeaddinsform)
-   Community call recordings on the [YouTube Office Dev
    channel](https://aka.ms/OfficeDevYouTube)

### Office Add-ins feedback

-   Technical questions -- Microsoft Q&A
    ([office-js-dev](https://learn.microsoft.com/answers/topics/office-js-dev.html)),
    ([office-addins-dev](https://learn.microsoft.com/answers/topics/office-addins-dev.html))
-   Issues -- [GitHub](https://github.com/OfficeDev/office-js/issues) 
-   Recommendations and suggestions -- [Microsoft 365 Developer Platform
    ideas](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform)
The next Office Add-ins community call is on **Wednesday, June 9, 2021**
at 8:00AM PDT. Get the calendar invite at
<https://aka.ms/officeaddinscommunitycall>.
