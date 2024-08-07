---
title: "Office Add-ins developer platform community call – June 12, 2024"
summary: "Topics include: Catch up Microsoft Build 2024​ by Mingjia Liu, Product Manager at Microsoft, Dev tools update for WXP add-ins​ by Wang Yun, Principal Product Manager​ at Microsoft and Mingjia Liu, Product Manager at Microsoft, Word add-ins update​ by Wang Yun, Principal Product Manager​ at Microsoft, Excel add-ins update by Adrian Wu, Senior Product Manager​ at Microsoft. Call hosted by Mingjia Liu, Product Manager at Microsoft. Recorded on June 12, 2024."
date: 2024-06-12T07:00:00-05:00
author: "Mingjia Liu"
githubname: MingjiaLiu1995
categories: ["Office add in developer community call"]
images:
- images/office-add-ins-community-call-2024-06-12.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/kwq58iURZjo
draft: false
---

# Office Add-ins developer platform community call - June 12, 2024

## This month's agenda and presenters

The call was hosted by [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager, Microsoft.

* **Catch up Microsoft Build 2024.** [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager at Microsoft.
* **Dev tools update for WXP add-ins.** [Wang Yun](https://www.linkedin.com/in/airwangyun/), Principal Product Manager at Microsoft and [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager at Microsoft.
* **Word add-ins update.** [Wang Yun](https://www.linkedin.com/in/airwangyun/), Principal Product Manager at Microsoft.
* **Excel add-ins update.** [Adrian Wu](https://www.linkedin.com/in/adrian-wu-53462582/), Senior Product Manager at Microsoft.

* **Q&A.** [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager, Microsoft.

{{< youtube kwq58iURZjo >}}

## View video segments

* Introduction [00:00]( https://youtu.be/kwq58iURZjo?t=0)
* Catch up Microsoft Build 2024 [00:45]( https://youtu.be/kwq58iURZjo?t=45)
* Dev tools update for WXP add-ins [04:30]( https://youtu.be/kwq58iURZjo?t=270)
* Word add-ins update [15:40]( https://youtu.be/kwq58iURZjo?t=940)
* Excel add-ins update [20:30]( https://youtu.be/kwq58iURZjo?t=1230)
* Q&A [28:45]( https://youtu.be/kwq58iURZjo?t=1725)
* Resources [31:27]( https://youtu.be/kwq58iURZjo?t=1887)

## Resources related to this blog's content
Catch up Microsoft Build 2024
* [General info](https://build.microsoft.com/)
* [Unleash AI-powered Extensibilities in Word/Excel/PowerPoint](https://youtu.be/I44RtBr01Lw)
* [Outlook Add-ins Transformed](https://youtu.be/5NKLh9D1Z3Q?si=HQous-VY_jfsGcWK)
* [Blog: What’s new for Office Add-ins at Build 2024](https://devblogs.microsoft.com/microsoft365dev/whats-new-for-office-add-ins-at-build-2024)

Dev tools update for WXP add-ins
* [Register for GitHub Copilot Extension for Office Add-ins early preview](https://forms.office.com/r/X40i91QN4u)
* [Get examples and inspirations from Office Add-in Prompt library](aka.ms/OfficeAddinsPromptLibrary)
* [Microsoft's free learning course: Get Started Building with Generative AI](https://github.com/microsoft/generative-ai-for-beginners)

## Q&A (Question & Answers)

**Is it possible to start talking about Copilot for MS Office. Copilot can be customised for clients and it would be great to know what resources are available to help get started.**

We have two sessions on Build for [WXP](https://aka.ms/OD506) and [Outlook add-ins](https://aka.ms/OD507) that both mentioned Copilot topic. You can also check [here](aka.ms/copilot_extensibility) for general information about Copilot extensions. 

**Are there any plans on allowing POTX files to be used when using the createPresentation function in the PowerPoint APIs? Also can you give us any more information on what PowerPoint APIs might be coming in the near future?**

Thank you for the feature request. This functionality is not currently supported nor in our backlog. We will consider it for future rounds of planning and keep you informed when we have updates.

**Is there a way to allow two separate instances of office applications to communicate via Office.js?**

Could you please clarify whether you are referring to an application-specific or a cross-application scenario? You can check Persist add-in state and settings - Office Add-ins | Microsoft Learn to see if it is useful for your use case. If you have further questions, you can go to https://stackoverflow.com [office-js] and submit a question.

**We’re currently using Exchange tokens and Outlook REST API in our event-based add-in within the OnMessageSend event. Will NAA support event-based add-ins?**

Yes, it will support event-based add-ins. We are working to bring support to win32 Outlook in the coming few weeks in insiders channel.

**Will we see the Critiques, Annotations and Highlighting APIs that are in currently in the Word API sets be available in PowerPoint's APIs?**

Thank you for the feature request. This functionality is not currently supported nor in our backlog. We will consider it for future rounds of planning and keep you informed when we have updates.


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
* Join the [next community call](https://aka.ms/officeaddinscommunitycall) on July 12th at 7:00 AM Pacific Time.

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
* [Next community call – July 12th at 07:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}
