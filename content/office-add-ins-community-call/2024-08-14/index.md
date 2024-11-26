---
title: "Office Add-ins developer platform community call – August 14, 2024"
summary: "Topics include: Install add-ins with Deeplink by Skylar Pan, Product Manager2 at Microsoft, Equivalent web add-in install on switching to New Outlook for Windows by Akshayta Pulugurtha, Senior Product Manager at Microsoft, Custom Functions updates by Adrian Wu, Senior Product Manager at Microsoft, New timeline for legacy Exchange token deprecation by David Chesnut, Senior Technical Writer at Microsoft, Visual Studio Code extension for Office add-in update by Mingjia Liu, Product Manager at Microsoft.  Call hosted by Mingjia Liu, Product Manager at Microsoft. Recorded on August 14, 2024."
date: 2024-08-14T07:00:00-05:00
author: "Mingjia Liu"
githubname: MingjiaLiu1995
categories: ["Office add in developer community call"]
images:
- images/office-add-ins-community-call-2024-08-14.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/12mHuf7qAkg
draft: false
---

# Office Add-ins developer platform community call - August 14, 2024

## This month's agenda and presenters

The call was hosted by [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager, Microsoft.

* **Install add-ins with Deeplink.** [Skylar Pan](https://www.linkedin.com/in/skylar-pan-4566617b/), Product Manager2, Microsoft.
* **Equivalent web add-in install on switching to New Outlook for Windows.** [Akshayta Pulugurtha](https://in.linkedin.com/in/akshayta-rao-pulugurtha-07a387a7), Senior Product Manager at Microsoft.
* **Custom function update.** [Adrian Wu](https://www.linkedin.com/in/adrian-wu-53462582/), Senior Product Manager at Microsoft.
* **New timeline for legacy Exchange token deprecation.** [David Chesnut](https://www.linkedin.com/in/davidpchesnut), Senior Technical Writer at Microsoft.
* **Visual Studio Code extension for Office add-in update.** [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager at Microsoft.

* **Q&A.** [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager, Microsoft.

{{< youtube 12mHuf7qAkg >}}

## View video segments

* Introduction [00:00]( https://youtu.be/12mHuf7qAkg?t=0)
* Install add-ins with Deeplink [00:12]( https://youtu.be/12mHuf7qAkg?t=12)
* Equivalent web add-in install on switching to New Outlook for Windows [02:55]( https://youtu.be/12mHuf7qAkg?t=175)
* Custom function update [12:10]( https://youtu.be/12mHuf7qAkg?t=730)
* New timeline for legacy Exchange token deprecation [19:05]( https://youtu.be/12mHuf7qAkg?t=1145)
* Visual Studio Code extension for Office add-in update [27:30]( https://youtu.be/12mHuf7qAkg?t=1650)
* Q&A [35:24]( https://youtu.be/12mHuf7qAkg?t=2124)
* Resources [37:20]( https://youtu.be/12mHuf7qAkg?t=2240)

## Resources related to this blog's content
Install add-ins with Deeplink
* [Get the link for your add-in](https://github.com/OfficeDev/OfficeJSAddinWidget?tab=readme-ov-file)

Equivalent web add-in install on switching to New Outlook for Windows
* [Full list of COM add-ins which have equivalent web add-ins that are available today](https://aka.ms/newOutlookSettings)
* [Guidance on how to opt out of this feature via GPO and impact on end user experience for admins](https://learn.microsoft.com/microsoft-365-apps/outlook/get-started/install-web-add-ins)
* [Take the survey to onboard to this feature](https://forms.office.com/r/GXBUgzSCs4)

New timeline for legacy Exchange token deprecation
* [Update history for Microsoft 365 Apps](https://learn.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date)
* [NAA public preview blog](https://aka.ms/NAApreviewblog)
* [NAA docs to get started](https://aka.ms/NAAdocs)
* [NAA FAQ](https://aka.ms/NAAFAQ)
* [NAA Outlook sample](https://aka.ms/NAAsampleOutlook)
* [NAA Word Excel PowerPoint sample](https://aka.ms/NAAsampleOffice)
* For issues, find us on [Github](https://github.com/OfficeDev/office-js/issues) and put “NAA” in your issue title

## Q&A (Question & Answers)

**We are implementing NAA into our add-in that is reliant on graph calls, with NAA allowing for client-side graph calls what is the best way for fallback auth? Will we still have to have middle-tier server graph calls to work with a fallback? We‘re hoping this isn’t the case.**

NAA is designed for an SPA Office web add-in, so there is no need for a middle-tier server. MSAL-browser.js (3.15 and later) has a built-in fallback mechanism. If NAA is not detected in the Office host (such as Outlook) MSAL automatically falls back to sign in the user without using NAA. This means SSO will not happen, but the user can still be signed in. We'll be adding more detail about this to the NAA code samples soon. 

**What are the Office version requirements for using NAA?**

The Office version requirements for using NAA:
* Office on Windows: Version 2302 (Build 16130.20306) or later.
* Office on Mac: Version 16.70 or later.
* Office on iOS/Android: The latest version available through the app stores.
* Office on the Web: No specific version requirement; it is supported as long as the web client is up to date.

**If you send too many graph requests, you get sent a 429 response and a header that contains the time you should retry sending the request. If you attempt to make a request during this period, the call is still counted against throttling limits and the retry after gets extended. Though only used in rare situations, consistent calls while throttled will cause the app to get banned from accessing the tenant. However, for SharePoint, all the SharePoint driveItem throttling limits are defined per app per tenant, meaning if calls get throttled they are throttled for all users in a given tenant. The old suggested approach is to use a back off method, where the app sends no requests, until the header retry time, for all users. This was a lot easier when graph requests were made from a server and all graph request traffic was centralised. But having naa, all the graph calls are now in separate instances of the app, there is no way to coordinate a back-off method? Just wondering if the new NAA flow can acount for this? Or if this is even a problem at all?**

Authentication and authorization goes to eSTS service with login.microsoftonline.com  URL. This isn't a Graph API so it won't count towards Graph throttling limits which are different for different APIs see [Microsoft Graph service-specific throttling limits](https://learn.microsoft.com/graph/throttling-limits).

## Call to action

* Join a community panel – product focused add-in discussion groups.
    * [Outlook add-ins panel](https://ux.microsoft.com/Panel/OutlookAddinDeveloper)
    * [Excel add-ins panel](https://ux.microsoft.com/Panel/ExcelAddinDeveloper)
    * [Word add-ins panel](https://ux.microsoft.com/Panel/WordAddinDeveloper)
    * [PowerPoint add-ins panel](https://ux.microsoft.com/Panel/PowerPointAddinDeveloper)
    * [Samples and docs](https://ux.microsoft.com/Panel/OfficeAddinImproveSamplesDocs)
* [Register for the PnP Recognition Program](https://pnp.github.io/recognitionprogram/) and earn contributor badges.
* Follow channels on X (formerly Twitter) to see call agendas, important updates, and release announcements.
    * [@microsoft365dev](https://twitter.com/microsoft365dev)
    * [@m365pnp](https://twitter.com/m365pnp)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free E5 developer tenant with instant availability and other assets.
* Join the [next community call](https://aka.ms/officeaddinscommunitycall) on September 11th at 7:00 AM Pacific Time.

## General Resources

* [Documentation](https://aka.ms/office-add-ins-docs)
* Quick Starts:
    * [Outlook](https://learn.microsoft.com/office/dev/add-ins/quickstarts/outlook-quickstart)
    * [Excel](https://learn.microsoft.com/office/dev/add-ins/quickstarts/excel-quickstart-jquery)
    * [Word](https://learn.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart)
    * [PowerPoint](https://learn.microsoft.com/office/dev/add-ins/quickstarts/powerpoint-quickstart)
* [Script Lab](https://aka.ms/getscriptlab)
* [Samples](https://aka.ms/officeaddinsamples)
* [Microsoft 365 Developer Program](https://aka.ms/M365devprogram)
* [Office Scripts](aka.ms/office-scripts-docs)
* [Technical questions about Office add-ins](https://aka.ms/office-addins-dev-questions)
* [Stack Overflow questions](https://stackoverflow.com). Use keywords **office-js**, **outlook-web-addins**, or **office-scripts**.
* [Github office-js issues](https://github.com/OfficeDev/office-js/issues)
* [Microsoft Tech Community – Submit feature requests](https://aka.ms/m365dev-suggestions)
* [Microsoft 365 Developer Program](https://aka.ms/M365devprogram)

## Stay connected

* See the full blog post for this call in the [Microsoft 365 platform community blog](https://aka.ms/m365pnp/blog)
* [X (formerly Twitter)](https://twitter.com/microsoft365dev)
* [Microsoft 365 Unified Sample gallery](https://aka.ms/community/samples)
* [Microsoft 365 Platform Community in YouTube](https://aka.ms/community/videos)
* [Microsoft 365 Platform Community](https://aka.ms/community/home)
* [Link to all Microsoft Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions for next community call](https://aka.ms/officeaddinsform)
* [Next community call – September 11th at 07:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}
