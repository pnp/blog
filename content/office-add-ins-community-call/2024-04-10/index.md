---
title: "Office Add-ins developer platform community call – April 10, 2024"
summary: "Topics include: Design Best Practices for Office Add-ins presented by Skylar Pan, Product Manager2 at Microsoft, Add-in authentication and access to Exchange APIs presented by Ben Siler, Senior Product Manager, and Implementing an integrated spam reporting add-in for Outlook presented by Eric Legault, Microsoft MVP. Call hosted by Mingjia Liu, Product Manager at Microsoft. Recorded on April 10, 2024."
date: 2024-04-10T07:00:00-05:00
author: "Mingjia Liu"
githubname: MingjiaLiu1995
categories: ["Office add in developer community call"]
images:
- images/office-add-ins-community-call-2024-04-10.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/vStXzijN-as
draft: true
---

# Office Add-ins developer platform community call - April 10, 2024

## This month's agenda and presenters

The call was hosted by [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager, Microsoft.

* **Design Best Practices for Office Add-ins.** [Skylar Pan](https://www.linkedin.com/in/skylar-pan-4566617b/), Product Manager2, Microsoft.

* **Add-in authentication and access to Exchange APIs.** [Ben Siler](https://www.linkedin.com/in/bensiler/), Senior Product Manager, Microsoft.

* **Implementing an integrated spam reporting add-in for Outlook.** [Eric Legault](https://www.linkedin.com/in/ericlegault/), Microsoft MVP.

* **Q&A.** [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager, Microsoft.

{{< youtube vStXzijN-as >}}

## View video segments

* Introduction [00:00](https://youtu.be/vStXzijN-as?t=0)
* Design Best Practices for Office Add-ins [1:08](https://youtu.be/vStXzijN-as?t=68)
* Add-in authentication and access to Exchange APIs [10:16](https://youtu.be/vStXzijN-as?t=616)
* Implementing an integrated spam reporting add-in for Outlook [33:10](https://youtu.be/vStXzijN-as?t=1990)
* Q&A [41:42](https://youtu.be/vStXzijN-as?t=2502)
* Resources [45:20](https://youtu.be/vStXzijN-as?t=2720)
* Closing [46:30](https://youtu.be/vStXzijN-as?t=2790)

## Resources related to this blog's content
Design Best Practices for Office Add-ins
* [Best practices for designing Word, Excel, and PowerPoint add-ins](https://devblogs.microsoft.com/microsoft365dev/best-practices-for-designing-word-excel-and-powerpoint-add-ins/)

Add-in authentication and access to Exchange APIs
* NAA public preview blog: https://aka.ms/NAApreviewblog​
* NAA docs to get started: https://aka.ms/NAAdocs​
* NAA FAQ: https://aka.ms/NAAFAQ​
* NAA Outlook sample: https://aka.ms/NAAsampleOutlook​
* NAA Word Excel PowerPoint sample: https://aka.ms/NAAsampleOffice​

## Q&A (Question & Answers)

**I missed my question regarding source code protection in the call March 13th. I have submitted the question for two meetings now without any answer. I would love to hear your views on how to best protect the source code for an Office Add-in (keeping it safe from someone copying it and selling it for their own). I know about code obfuscation, and I know some code can be put on the server side, but I would love to hear some best practice on this topic from the experts.**

Obfuscation and putting code on the server side (like Azure functions) are the fundamental ways to keep your code private. Since Office Add-ins are basically web applications; they are subject to the same code protection strategies as any web application.

**Is it a good, relevant, smart idea to deploy an Office Add-in as an Aspire application using Blazor? (https://learn.microsoft.com/en-us/dotnet/aspire/)**

We don’t have any specific guidance around using .NET Aspire with Blazor or Office Add-ins. Office Add-ins are basically web applications, so if a framework is designed to work with web applications, in general it should work for Office Add-ins. ​

**Deployment of Add-Ins to external users**

To learn about the several methods used to deploy your Office Add-in for distribution to users, see [Deploy and publish Office Add-ins](https://learn.microsoft.com/office/dev/add-ins/publish/publish).

**I would like to ask questions about word addin, we are developing an addin for word, excel and powerpoint online and desktop versions, we have taskpan addin working fine but we wanted to activate our addin on events such as save if it is on new outlook desktop version.**

Thank you very much for your request here. We currently don't have such event for Word document save operations. We'll keep you informed when we have updates on this. Please also submit a request and describe your use case on the [Microsoft 365 Developer Platform Ideas Forum]( https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform).

**Our Outlook add-in is using event-based activation (OnNewMessageCompose, OnMessageSend). Those events are not critical, therefore we use an unrestricted listing in AppSource. But we'd like to show an information inside the taskpane, if the add-in has been installed directly from AppSource by an user. So it's clear that event-based features of our add-ins won't work. Is there a way in Officejs to detect whether event-based activation is available or the add-in has been installed directly from AppSource by an user?**

Currently, within Office.js, there isn’t a direct method to determine whether event-based activation is supported or if the add-in was installed directly via AppSource by an end user. Additionally, our messaging to users on Office clients does not reflect/call out the installation source of the add-in. Our team is exploring potential workarounds for this situation. We'll keep you informed with updates once we have thoroughly tested any proposed solutions. 

**Does Microsoft have any plans to add compose mode support for Outlook Mobile, and on-send event support (not Smart Alerts because the APIs are too limiting) to show a custom dialog and modify the item's subject, body and internet headers? These features have been requested for years but ISVs are still waiting. Outlook on Windows and Mac for M365 are around requirement set 1.13 but Outlook Mobile is still just a subset of 1.5 - a huge disparity.**

Thank you for your request here. Currently we don't have such support for Outlook Mobile. We'll keep you informed when we have an update.​

**Is it possible to communicate from document context to task pane with use of function file / execute the function from manifest for task pane?**

We might need more information to understand which part of the functionality you are interested in, but the short answer is yes, you can communicate between the document context and the task pane using our APIs enabled in an add-in. If you're specifically talking about "Excel custom function", such communication is also possible. You can check out the following links for a quick overview of what JS add-ins or Excel custom functions can do. 

* [Office Add-ins platform overview - Office Add-ins | Microsoft Learn](https://learn.microsoft.com/en-us/office/dev/add-ins/overview/office-add-ins)
* [Create custom functions in Excel - Office Add-ins | Microsoft Learn](https://learn.microsoft.com/en-us/office/dev/add-ins/excel/custom-functions-overview)
* [Tutorial: Share data and events between Excel custom functions and the task pane - Office Add-ins | Microsoft Learn](https://learn.microsoft.com/en-us/office/dev/add-ins/tutorials/share-data-and-events-between-custom-functions-and-the-task-pane-tutorial)

**Hi Team, We are trying to review and compile the list of Office addins from Office 365 Admin center. The goal is to review the addins that are being reported and then have those packaged up in Intune for better management (from an Enterprise POV). We have combo of 64 and 86 Office architecture. Any inputs on best practice methods available out there to Manage Office addins will be greatly appreciated. Thank you.**

Thanks for your question. To better help, our team would like to understand more details of your scenario. Would you please go  [Issues · OfficeDev/office-js (github.com)](https://github.com/officedev/office-js/issues) to submit your question there so that the team can engage with you? 

**I have pushed add-in for my organization through Azure portal, How should I show the message / page if user don't have access to add-in? currently it show yellow page that add-in not loaded successfully. When I try with other office store add-in it show me the link for redirection when it is not installed**

Thanks for your question. To better help, our team would like to understand more details of your scenario. Would you please go  [Issues · OfficeDev/office-js (github.com)](https://github.com/officedev/office-js/issues) to submit your question there so that the team can engage with you? 

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
* Join the [next community call](https://aka.ms/officeaddinscommunitycall) on May 8th at 7:00 AM Pacific Time.

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
* [Next community call – May 8th at 07:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}
