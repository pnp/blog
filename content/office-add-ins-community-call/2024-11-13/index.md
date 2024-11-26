---
title: "Office Add-ins developer platform community call – November 13, 2024"
summary: "Topics include: Word API Update​ by Yun Wang, Principal Product Manager​ at Microsoft, Excel API and Capability Update by Adrian Wu​, Senior Product Manager​ at Microsoft. Call hosted by Mingjia Liu, Product Manager2 at Microsoft. Recorded on November 13, 2024."
date: 2024-11-13T07:00:00-05:00
author: "Mingjia Liu"
githubname: MingjiaLiu1995
categories: ["Office add in developer community call"]
images:
- images/office-add-ins-community-call-2024-11-13.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/hJ8fY2IxJKU
draft: false
---

# Office Add-ins developer platform community call - November 13, 2024

## This month's agenda and presenters

The call was hosted by [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager2, Microsoft.

* **Word API Update.** [Wang Yun](https://www.linkedin.com/in/airwangyun/), Principal Product Manager at Microsoft.
* **Excel API and Capability Update.** [Adrian Wu](https://www.linkedin.com/in/adrian-wu-53462582/), Senior Product Manager at Microsoft.
* **Q&A.** [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager2, Microsoft.

{{< youtube hJ8fY2IxJKU >}}

## View video segments

* Introduction [00:00]( https://youtu.be/hJ8fY2IxJKU?t=0)
* Word API Update [00:50]( https://youtu.be/hJ8fY2IxJKU?t=50)
* Excel API and Capability Update [13:39]( https://youtu.be/hJ8fY2IxJKU?t=819)
* Q&A [23:56]( https://youtu.be/hJ8fY2IxJKU?t=1436)
* Resources [28:26]( https://youtu.be/hJ8fY2IxJKU?t=1706)

## Resources related to this blog's content
Word API Update
* [WordApiDesktop 1.1 requirement set​](https://learn.microsoft.com/en-us/javascript/api/requirement-sets/word/word-api-desktop-1.1-requirement-set?view=common-js-preview)

Excel API and Capability Update
* [COM/JS Add-in Fusion Mode Experiment Partner Registration Form](https://forms.office.com/r/URuLbXXtzT)

## Q&A (Question & Answers)

**We deploy office (Excel) JavaScript-based add-ins (and their updated manifests) using the "Integrated Apps" section in admin.microsoft.com (all of our users are signed in using their Entra ID credentials).​ Whenever we deploy a new version, it is unclear to us how/if we can have the updated add-in reflected on user's Excel client. We usually try one or more of these measure and the updated version eventually loads.​ 1. Close and re-open Excel. This can be really disruptive for users that have a number of documents open.​ 2. Refresh the add-ins from the "manage add-ins" section of Excel and re-add the add-in.​ This process is slow and non-deterministic for our many excel users. Some of the changes we push out are time sensitive and we'd like to get them to user's Excel clients much quicker.​What can we do to automate the process of getting the updated add-ins reflected on the user's Excel clients on Windows 11 and Office 365.​ We are on the Enterprise Monthly channel (currently on version 2408 Build 17928.20216 click-to-run)**

Currently, in our mechanism, all add-ins are loaded when the application starts, and due to resource management, the app would not continuously check for new add-ins, and it would also need careful consideration if we were to provide such an API capability for add-ins to update the add-in registry, as this would also terminate the current add-in session. But it's doable. So please help us raise a new feature request in [our tech community](https://techcommunity.microsoft.com/category/microsoft365/ideas/microsoft365developerplatform) so that we can put it in our backlog and prioritize it properly based on the vote numbers.​

**Does any documentation exist on the format/pattern used for MSGraph SharePoint IDs (Such as SiteId, DriveId, FolderId, etc). We want to be able to validate that given IDs are in the correct format and are valid IDs.**

Graph API related information can be found [here](https://learn.microsoft.com/graph/api/resources/sharepoint?view=graph-rest-1.0​), where there are examples of how to get specific IDs related to sharepoints, and also how to further use these IDs to get the data you need. ​

**We are developing an Outlook add-in that also must cover mobile devices.​The extension point MobileMessageReadCommandSurface exists on mobile, that results in apps/modern add-ins can be opened while reading an email.​To fulfill our requirements, it must be possible to open apps/modern add-ins while composing an email. E.g. with a new extension point MobileMessageComposeCommandSurface. MessageComposeCommandSurface is already available on the desktop and webmail.**

We have launched events on Mobile which run in [compose mode](https://learn.microsoft.com/office/dev/add-ins/outlook/mobile-event-based?tabs=jsonmanifest). You can check and see if it's related to your question. If not, please submit your question to GitHub so that we can understand more about your use case.

​**We have an Outlook add-in interacting with user on edit message. this is working well for Windows but Outlook Mobile it does not work, when do you support Dialogs Edit Message (New, Reply and Forward) for Outlook Mobile.**

We have some items in the backlog that might be related. Could you share more about your use case to help us understand? Please submit the question to GitHub so that the team can reach out to you.

**There are few Outlook performance issues / bugs open in Office.js and no answers on investigation or current status. Is Outlook team going to investigate the performance issues and how we should communicate these to our clients meanwhile?​ We hear (Forrester) how new Outlook saves energy, and some of these performance issues seems to stem from "energy saving" mode, Outlook energy conservation tactics, and related slowdown of core JS features (setTimeout). Are the efforts on energy saving and performance issues related?**

Is it possible to get a list of the open bugs/issues you are referring to? Our team frequently monitors GitHub for issues and triage bugs. In the meantime, here are some information you can stay current on what's coming in New Outlook. Check [Add-ins in the new Outlook for Windows](https://techcommunity.microsoft.com/blog/outlook/add-ins-in-the-new-outlook-for-windows/3954388) and  [What's new in new Outlook for Windows](https://support.microsoft.com/en-us/office/what-s-new-in-new-outlook-for-windows-c4c33813-1e9a-4304-8499-90fe7f164bd1)

**Centralized Deployment of add-ins - for customers using Microsoft 365 licenses it takes a very long time (24 to 48 hours) to install Outlook Addin through centralized deployment and it takes a very long time to remove such Addin. Customers have 48 hours on Azure Marketplace to test applications and if addin needed for using the application is not available in a short time (up to one hour) it might result in canceling subscription. It would be great if someone can address that issue and give best practice to shorten propagation time.​**

**Why does centralised deployment take up to 24 hours to deploy an add-in? In OWA I used to be able to sideload an add-in and it would immediately appear. Sideloading using the hidden https://aka.ms/officeaddinsform doesn't make the add-in show up under Apps any quicker.**

We haven't got an answer from the owner team till now. Please stay tuned for the update.

**I wanted to know whether there is any workshop by which we can understand the office.js flow and can contribute to the new features to office.js which can help us to maximize the productivity?**

We don't currently have a workshop. You can check all the resources we provide at the end of every month's community call to get started. For new feature requests, please submit them to [the channel](https://techcommunity.microsoft.com/category/microsoft365/ideas/microsoft365developerplatform) and the team will frequently monitor it.

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
* Join the [next community call](https://aka.ms/officeaddinscommunitycall) on December 11th at 7:00 AM Pacific Time.

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
* [Next community call – December 11th at 07:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}
