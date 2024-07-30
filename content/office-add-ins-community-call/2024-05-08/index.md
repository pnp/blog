---
title: "Office Add-ins developer platform community call – May 08, 2024"
summary: "Topics include: Outlook Add-ins Updates​ by Rashi Jindal, Senior Product Manager at Microsoft, Word Add-ins Updates​ by Steve Jin, Senior Product Manager at Microsoft, Nested App Auth: A Simpler SSO Solution for WXP Add-ins​ by Steve Jin, Senior Product Manager at Microsoft and David Chesnut, Senior Technical Writer​ at Microsoft. Call hosted by Mingjia Liu, Product Manager at Microsoft. Recorded on May 08, 2024."
date: 2024-05-08T07:00:00-05:00
author: "Mingjia Liu"
githubname: MingjiaLiu1995
categories: ["Office add in developer community call"]
images:
- images/office-add-ins-community-call-2024-05-08.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/LKf73ZEa_yY
draft: true
---

# Office Add-ins developer platform community call - May 08, 2024

## This month's agenda and presenters

The call was hosted by [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager at Microsoft.

* **Outlook Add-ins Updates.** [Rashi Jindal](https://www.linkedin.com/in/jindalrashi), Senior Product Manager at Microsoft.
* **Word add-ins update.** [Steve Jin](https://www.linkedin.com/in/steve-jin-61b08011), Senior Product Manager at Microsoft.
* **Nested App Auth: A Simpler SSO Solution for WXP Add-ins.** [Steve Jin](https://www.linkedin.com/in/steve-jin-61b08011), Senior Product Manager at Microsoft and [David Chesnut](https://www.linkedin.com/in/davidpchesnut) Senior Technical Writer​ at Microsoft.
* **Q&A.** [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager at Microsoft.

{{< youtube LKf73ZEa_yY >}}

## View video segments

* Introduction [00:00]( https://youtu.be/LKf73ZEa_yY?t=0)
* Outlook Add-ins Updates [01:54]( https://youtu.be/LKf73ZEa_yY?t=114)
* Word add-ins update [19:12]( https://youtu.be/LKf73ZEa_yY?t=1152)
* Nested App Auth: A Simpler SSO Solution for WXP Add-ins [31:30]( https://youtu.be/LKf73ZEa_yY?t=1890)
* Q&A [40:16]( https://youtu.be/LKf73ZEa_yY?t=2416)
* Resources [41:48]( https://youtu.be/LKf73ZEa_yY?t=2508)

## Resources related to this blog's content
Outlook Add-ins Updates
* [Office Add-ins with the unified app manifest for Microsoft 365](https://learn.microsoft.com/en-us/office/dev/add-ins/develop/unified-manifest-overview)
* [Build an Outlook add-in with the unified manifest](https://learn.microsoft.com/en-us/office/dev/add-ins/quickstarts/outlook-quickstart-json-manifest)
* [Create Office Add-in projects using Teams Toolkit](https://learn.microsoft.com/en-us/office/dev/add-ins/develop/teams-toolkit-overview)
* [Convert xml to json manifest](https://learn.microsoft.com/en-us/office/dev/add-ins/develop/convert-xml-to-json-manifest)

Dev tools update for WXP add-ins
* [Share insights and experiences on autorun user scenarios for Word JS Add-ins](https://aka.ms/WordJSAutorun)

Nested App Auth: A Simpler SSO Solution for WXP Add-ins
* [Preview documentation on NAA](https://aka.ms/NAADocs)

## Q&A (Question & Answers)

**Is there any way to check no of user installed the office.js PowerPoint admin-managed add-in which is deployed using Integrated apps deployment? If we don't have option in Office 365 admin center, can you recommend some way to check this in machine level (mac) through script?**

We do not have any dashboards to track which users are acquiring the apps for themselves. However, admin can run following cmdlet on all user mailbox to get list of add-in deployed for the user. This will help admins get list of which apps are deployed and to which users. [Get-App (ExchangePowerShell) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/exchange/get-app?view=exchange-ps) 

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
* Join the [next community call](https://aka.ms/officeaddinscommunitycall) on June 10th at 7:00 AM Pacific Time.

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
* [Next community call – JUne 10th at 07:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}
