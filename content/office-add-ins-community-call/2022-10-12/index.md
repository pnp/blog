---
title: "Office Add-ins developer platform community call – Ocotober 12, 2022"
summary: "This month's community call topics include: Update the ASP.NET server in Visual Studio (update a task pane in an Excel add-in updating the sideloader project to point to an updated ASP.NET Core project) – David Chesnut (Microsoft) and Feedback request for Excel add-in auto install launch function (thoughts on making your office JS add-in discoverable and safely auto install and launch it) - Yawei Zhu (Microsoft),  Community spotlight – shines on Eric Legault (Eric Legault Consulting), and Q&A at end of call and in chat throughout call."
date: 2022-10-12T08:01:00-05:00
author: "Preethika Kiruveedula"
githubname: preethikakiru
categories: ["Office Add-in developer community call"]
images:
- images/office-add-ins-call-october-2022-recording.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/zdyWBTxtjF4
draft: true
---

# Office Add-ins developer platform community call - Ocotober 12, 2022

## This month's agenda and presenters

The call was hosted by [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a148), Product Manager, Microsoft  
* **Update the ASP.NET server in Visual Studio.** [David Chesnut](https://twitter.com/davidchesnut), Senior Technical Writer, Microsoft. 
* **Feedback request for Excel Add-in Auto install launch function.** [Yawei Zhu](https://www.linkedin.com/in/yaweizhu-henson/), Senior Product Manager, Microsoft. 
* **Community spotlight.** Recognizing [Eric Legault](https://twitter.com/elegault), Senior Principal Software Architect, Eric Legault Consulting.
* **Q&A.** See question and answers at end of call and in chat throughout call. [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a14), Product Manager, Microsoft.

{{< youtube zdyWBTxtjF4 >}}

## View video segments

* Demo - Update the ASP.NET server in Visual Studio [00:42](https://youtu.be/watch?v=zdyWBTxtjF4?t=42)
* Topic - Feedback request for Excel Add-in Auto install launch function [08:40] (https://www.youtube.com/watch?v=zdyWBTxtjF4&t=520s)
* Community spotlight [12:04] (https://www.youtube.com/watch?v=zdyWBTxtjF4&t=724s)
* Q&A [12:16](htthttps://www.youtube.com/watch?v=zdyWBTxtjF4&t=736s)

## Topic summaries

* **Update the ASP.NET server in Visual Studio.** Learn how to update a task pane in an Excel Add-in to use a new ASP.NET Core project. When you create a new project in Visual Studio and choose the Excel Web Add-in, actually two projects are created – a web ASP.NET server and a sideloader.  Configure the solution to add a new ASP.NET Core project, update the sideload project to point to it, and update your manifest.  Add additional capabilities to the index page in the new project.  
* **Feedback request for Excel add-in auto install launch function.** What if your office JS add-in can be discovered and safely auto installed and auto launched! Use scenario &mdash; one receives a file with elements created by an add-in used by the sender. We would greatly appreciate it if you would provide feedback about this proposed capability by selecting the survey link and answering three brief questions. Use it? Why? For what scenarios?  
  
## Call to action
* Share your feedback on how we can provide you with a better Office Add-ins development experience. Join a community panel. 
    * [Outlook add-ins panel](https://ux.microsoft.com/Panel/OutlookAddinDeveloper)
    * [Excel add-ins panel](https://ux.microsoft.com/Panel/ExcelAddinDeveloper)
    * [Word add-ins panel](https://ux.microsoft.com/Panel/WordAddinDeveloper)
    * [PowerPoint add-ins panel](https://ux.microsoft.com/Panel/PowerPointAddinDeveloper)
    * [Samples and docs](https://ux.microsoft.com/Panel/OfficeAddinImproveSamplesDocs)
* [Sign up for the PnP Recognition Program](https://pnp.github.io/recognitionprogram/) and earn contribution badges.
* Follow us on Twitter to see call agendas, important updates, and release announcements. 
    * [@microsoft365dev](https://twitter.com/microsoft365dev)
    * [@m365pnp](https://twitter.com/m365pnp)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free E5 developer tenant with instant availability and other assets.
* [Join the next Office Add-ins community call](https://aka.ms/officeaddinscommunitycall) on November 9th at 8:00 AM Pacific Time.
* Please complete the [Office add-in developing experience survey](https://forms.office.com/r/wmzCgccbPa)

## Q&A (Question & Answers)
**Regarding the need to register functions called by add-in manifest ExecuteFunction using Office.actions.associate, if we're using an older copy of the office-js library will the requirement for the function to have been registered still apply? e.g. there was a bug introduced in office.js back in 2020 so we stuck to a version of the library from before that change, will such an add-in be impacted by the need to register functions?**

Hello, please submit this question here https://github.com/OfficeDev/office-js. 

**Hi. Thanks for a good community! I especially enjoyed the April session where Onur Onder made a really good demonstration on some beta PowerPoint APIs and some nice features he developed in ScriptLab. I was just curious if these snippets were shared in a public gist to allow for a closer look. Would be really appreciated if that was the case. If I could make a wish for future content, I'm really curious to get some high-level pointers on how to develop a custom chart object. I'm inspired by ThinkCell (this is not Office.js as far as I understand) and MekkoChart (www.mekkographics.com) that have some nice chart elements and a few steps down the road I would like to make my own charts... Would be really good to go about it in the best way with some guidance from the real experts Thanks again!** 

They are in progress to be added to Script Lab soon. We'll update this blog here with updated information when they are published.

**When will Microsoft Word Forms API's will be added in office JS?**

We currently do not have plans to add Microsoft Word Forms apis to Office JS. Currently the best way to do this would be to use the Forms connector in Power Automate. 

**Hi! Is it possible to write Outlook add-in that will work with Gmail account to set email signature in Outlook using event-based activation as described in https://learn.microsoft.com/en-us/samples/officedev/pnp-officeaddins/outlook-add-in-set-signature/?**

This is a good question to ask here https://github.com/OfficeDev/office-js.

**Would you say what you just demonstrated with Visual Studio is the preferred approach for developing a web add-in vs. the Yeoman and Visual Studio Code approach?**

Either one works. If your background is in VSTO you may find that using the Visual Studio IDE a more familiar environment. But you probably also want to use a newer version of ASP.NET, which the demonstration shows. You may also be interested in the [Blazor Webassembly samples](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/blazor-add-in) which allow you to keep your task pane UI in C# as well.

**What is the Mac equivalent of the Wef folder to clear the cache?**

For instructions on how to clear the Office cache on Mac, see the "Clear the Office cache on Mac" section in [Clear the Office cache](https://learn.microsoft.com/office/dev/add-ins/testing/clear-cache#clear-the-office-cache-on-mac).

**I was just wondering if any of you are developing add-in for the IPAD since I am just experiencing an issue with the event handler on data changed in a worksheet. With the new Excel IPAD version (2.65.1) it seems that the event handler is not called any more while it was working with the previous versions. On Windows, Excel on the Web everything is working fine except with this new IPAD version and the issue is also that I can't revert back to a previous IPAD version :( Thanks in advance for any feedback or suggestion in reporting this issue to Microsoft!**

We're sorry to hear you're experiencing an issue with developing an add-in on an iPad. If you haven't already, please submit a [GitHub issue on office-js](https://github.com/OfficeDev/office-js/issues), so that we can escalate it to the Excel team for further investigation.


## Additional Resources

* **Update the ASP.NET server in Visual Studio**
    * Documentation - [Sideload an add-in on the web when using Visual Studion](https://learn.microsoft.com/en-us/office/dev/add-ins/testing/sideload-office-add-ins-for-testing#sideload-an-add-in-on-the-web-when-using-visual-studio)
    * Documentation - [Office Add-ins platform overview](https://learn.microsoft.com/en-us/office/dev/add-ins/overview/office-add-ins)
    * Samples - [Office Add-ins code samples](https://github.com/OfficeDev/Office-Add-in-samples)
* **Feedback request for Excel Add-in Auto install launch function**
    * Feedback - [What if your office JS add-in can be auto installed and auto launched](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxFri8-AP1RMhGrt_lYwo8BUMTcwNzBSU1dWM0paRE5HSTg1UkE4N1dMMS4u&wdLOR=c0D8EB527-F375-4499-8FE2-DA3B5029A060)
    * Demo - [Excel add-in User Pattern – Open in Excel - Yawei Zhu](https://www.youtube.com/watch?v=0OKULxfib44&feature=youtu.be) 
    

## Stay connected

* Follow our blog posts at [Microsoft 365 platform community blog](https://aka.ms/m365pnp/blog)
* [Follow @microsoft365dev on Twitter](https://twitter.com/microsoft365dev)
* [Microsoft 365 Platform Community on YouTube](https://aka.ms/m365/videos)
* Invites to all [Microsoft 365 Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions about Office Add-ins development](https://aka.ms/officeaddinsform) for our next community call
* [Join us for our next community call](https://aka.ms/officeaddinscommunitycall) on November 9th at 8:00 AM PT

{{< attachments >}}
