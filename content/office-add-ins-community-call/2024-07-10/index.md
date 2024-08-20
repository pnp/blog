---
title: "Office Add-ins developer platform community call – July 10, 2024"
summary: "Topics include: An overview of the Microsoft 365 App Compliance Program by Leana Gerrard, Senior Product Manager at Microsoft and Sreekanth Thirthala Venkata, Principal Product Manager at Microsoft. Call hosted by Mingjia Liu, Product Manager at Microsoft. Recorded on July 10, 2024."
date: 2024-07-10T07:00:00-05:00
author: "Mingjia Liu"
githubname: MingjiaLiu1995
categories: ["Office add in developer community call"]
images:
- images/office-add-ins-community-call-2024-07-10.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/h4p8rbZOIms
draft: false
---

# Office Add-ins developer platform community call - July 10, 2024

## This month's agenda and presenters

The call was hosted by [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager, Microsoft.

* **An overview of the Microsoft 365 App Compliance Program.** [Leana Gerrard](https://www.linkedin.com/in/leanagerrard), Senior Product Manager at Microsoft and Sreekanth Thirthala Venkata, Principal Product Manager at Microsoft.

* **Q&A.** [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager, Microsoft.

{{< youtube h4p8rbZOIms >}}

## View video segments

* Introduction [00:00](https://youtu.be/h4p8rbZOIms?t=0)
* An overview of the Microsoft 365 App Compliance Program [01:10](https://youtu.be/h4p8rbZOIms?t=70)
* Q&A [37:02](https://youtu.be/h4p8rbZOIms?t=2222)
* Resources [40:20](https://youtu.be/h4p8rbZOIms?t=2420)

## Resources related to this blog's content
An overview of the Microsoft 365 App Compliance Program
* [Watch the App Compliance Program Video to learn more](https://youtu.be/Aff_35f10B8)
* [Learn more at the M365 App Compliance docs pages](https://learn.microsoft.com/en-us/microsoft-365-app-certification)
* [Begin the Microsoft 365 App](https://partner.microsoft.com/)
* [Compliance Program on Partner Center](https://partner.microsoft.com/)
* [View the getting started guide for Office, Teams, and SharePoint apps](https://docs.microsoft.com/en-us/microsoft-365-app-certification/docs/userguide)

## Q&A (Question & Answers)

**I had a question responded to in the June 2024 call and I was asked to clarify my scenario. Old question: Is there a way to allow two separate instances of office applications to communicate via Office.js? New question: If I have two Office.js task panes; one running in an instance of Word and another running in an instance of Excel on the same machine, is there a way I can obtain a reference to the running Excel application from the Word task pane (or vice versa) to emulate a temporary communication layer between the two running applications?
To clarify, this would be a cross-application scenario. It is not necessary (but ideal) for the two task panes to communicate, but the ability to, for example, get the selected data in Excel from a user's actions in the Word task pane would be invaluable.**

You can use Graph api to get access to Excel application data in your Word add-in: [Excel workbooks and charts API overview - Microsoft Graph | Microsoft Learn](https://learn.microsoft.com/en-us/graph/excel-concept-overview). However, this doesn’t work if you want to get access to Word data from Excel, so you may consider using a server to communicate between. 

**Is there a way to use Microsoft Playwright (https://playwright.dev/) to test desktop add-ins?**

For Office add-in testing, we recommend you use the [Office-Addin-Mock](https://www.npmjs.com/package/office-addin-mock) library with JavaScript unit testing framework. You can find more examples here: [Unit testing in Office Add-ins - Office Add-ins | Microsoft Learn](https://learn.microsoft.com/en-us/office/dev/add-ins/testing/unit-testing).

**Not related to compliance or certification but my question relates to Copilot for M365 and the new Add in platform: Will the new Add in platform allow customisations to Copilot or are the two completely different things. If so, how can we work with Copilot in our Add-ins.**

We are investigating scenarios for how Copilot and Office Add-ins could work together, but have no public plans to share at this time.  If there are scenarios or functionality you'd like to suggest, please let us know through the [feedback channel](https://aka.ms/m365dev-suggestions).

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
* Join the [next community call](https://aka.ms/officeaddinscommunitycall) on August 14th at 7:00 AM Pacific Time.

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
* [Next community call – Auguest 14th at 07:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}
