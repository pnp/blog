---
title: "Office Add-ins developer platform community call – September 14, 2022"
summary: "This month's community call topics include Microsoft Word Extensibility Update – September 2022 (four topics covered:  Embed an Add-in into a Word document, shared runtime support, structured document survey result, and Word panel introduction) – Yun Wang, Principal Product Manager (Microsoft) and Microsoft Outlook Add-in Blazer Sample Update – September 2022 (Step through setting up Blazor environment and sample project) – Eric Legault (Eric Legault Consulting) | @elegault,  Community spotlight – shines on Thomas Barnekow for samples submissions, and Q&A at end of call and in chat throughout call."
date: 2022-09-14T08:01:00-05:00
author: "Preethika Kiruveedula"
githubname: preethikakiru
categories: ["Office Add-in developer community call"]
images:
- images/office-add-ins-call-september-2022-recording.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/KKAGvdh1Jfk
draft: true
---

# Office Add-ins developer platform community call - September 14, 2022

## This month's agenda and presenters

The call was hosted by [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a148), Product Manager, Microsoft  
* **Microsoft Word Extensibility Update.** Four topics covered:  Embed an Add-in into a Word document, shared runtime support, structured document survey result, and Word panel introduction. [Yun Wang](), Principal Product Manager, Microsoft. 
* **Microsoft Outlook Add-in Blazer Sample Update.** Step through setting up Blazor environment and sample project. [Eric Legault](https://twitter.com/elegault).
* **Community spotlight.** recognizes [Thomas Barnekow](https://www.linkedin.com/in/thomas-barnekow-2580b11), Senior Principal Software Architect, [Analog Devices](https://www.analog.com/en/index.html).
* **Q&A.** See question and answers at end of call and in chat throughout call. [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a14), Product Manager, Microsoft.

{{< youtu.be/KKAGvdh1Jfk >}}

## View Video Segments

* Microsoft Word Extensibility Update [00:54] (https://youtu.be/KKAGvdh1Jfk?t=54)
* Demo - Microsoft Outlook Add-in Blazer Sample Update [9:22] (https://youtu.be/KKAGvdh1Jfk?t=562)
* Community spotlight [23:44] (https://youtu.be/KKAGvdh1Jfk?t=1424)
* Q&A [23:56](https://youtu.be/KKAGvdh1Jfk?t=1436)

## Topic summaries

* **Microsoft Word Extensibility Update.** Four topics covered with UI demos and use scenarios for first two topics.  1) Embed an Add-in into a Word document (using Open in Word Pattern), 2) shared runtime support, 3) structured document survey result, and 4) Word panel (user research community focus group) introduction.  
* **Microsoft Outlook Add-in Blazer Sample Update.** Get started using the Blazor Web framework to build an Office Add-in using C# in addition to .NET and JavaScript.  Practical review of Blazor capabilities and incompatibilities, tips for setting up project environment and Blazor project.  Learn about using the Blazor client template in Visual Studio and the Office Web Add-in template to add the sideloader project.  Walk through sample reference project. 
  
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
* [Join the next Office Add-ins community call](https://aka.ms/officeaddinscommunitycall) on October 12th at 8:00 AM Pacific Time.
* Please complete the [Office add-in developing experience survey](https://forms.office.com/r/wmzCgccbPa)

## Q&A (Question & Answers)

**Our add-in needs the MIME representation of an e-mail message, the conversationId and the internetMessageId. Would it be possible to add support for these properties to office.js? Currently we need to use Outlook REST API (or MS-Graph in the future) to get these values** 

We currently support these properties. For guidance with using these properties, see the Office.MessageRead API at https://learn.microsoft.com/en-us/javascript/api/outlook/office.messageread?view=outlook-js-preview.


**Consideration for existing add-ins that use the Outlook REST API is very helpful. Eventually, will all add-ins (existing and new add-ins) be able to use the Outlook REST API until Office 2019 support? I think this is very important, so could you please announce the decision on a dedicated page?**

Yes, both new and existing add-ins will be able to use the Outlook REST API until support ends for Office 2019 on October 14, 2025. This announcement has been posted to Use the Outlook REST APIs from an Outlook add-in at https://learn.microsoft.com/en-us/office/dev/add-ins/outlook/use-rest-api .

**Will the 'auto-launch' of an add-in from a Word document also apply to add-ins that are not acquired from the Office Store, but are deployed by an administrator internally as one of the admin-managed add-ins?**

Add-ins that are centrally deployed by an administrator are currently supported by auto-launch.


**This embedding is nice to have (if it works correctly), but are you considering to come up with the more traditional way, i.e. possibility to 'install/enable' the add-in for application level, not per the document? Or is it totally out of scope?**

Great and valuable point. We received similar requests, but can't provide a plan for it right now. It is something that we are also interested in.

**The auto launch feature is great! One thing that Word add-ins are missing (still) is the ability to listen for save events (and intercept those).**

Thanks for the suggestion. This is great requirement. Unfortunately this is not in our recent plan. You could submit a requirement at https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform to help us understand more of your user scenarios.

**Which version of Word will support the embedded add-ins? What will happen, if a document with an embedded add-in is opened from an old Word version?**

Office 2016, Version 1705, build 16.0.8122.1000 Click-to-Run, or later. For those old versions, the task pane will not show.

**Does Blazor support async/await?**

Yes, you can write c# code and use async/await. However Blazor WebAssembly runs in the JavaScript runtime, and therefore runs single-threaded. Be careful not to call .Result, or Wait() as this can block the thread and lead to a deadlock. For more details, and patterns to consider, see https://github.com/dotnet/aspnetcore/issues/14253

**Bumping the One Outlook topic and wondering about improved Mac Outlook support. We still continue to face edge cases and inconsistencies on Mac surrounding writing base64 attachments, as well as inline images.**

We're sorry to hear you're experiencing issues in Outlook on Mac. If you haven't already, please submit a GitHub issue, so that we can escalate it to the Outlook team for further investigation.


## Additional Resources

* **Microsoft Word Extensibility Update **
    *Sample - [Web application that uses Open XML SDK to configure Office documents to automatically open a specified add-in](https://github.com/OfficeDev/Office-OOXML-EmbedAddin)
    *Documentation - [Configure your Office Add-in to use a shared runtime](https://docs.microsoft.com/office/dev/add-ins/develop/configure-your-add-in-to-use-a-shared-runtime)
    *Survey - [Structured document content usage in Word add-ins](https://aka.ms/WordAPI)
    *Community Panel - [Improve Word add-ins](https://ux.microsoft.com/Panel/WordAddinDeveloper?utm_campaign=community_call&&utm_source=community_call&&utm_medium=qrcode)
* **Blazer Sample Update**
    * Repo - [Office Add-ins code samples](https://github.com/OfficeDev/Office-Add-in-samples)
    * Sample - [Create a Blazor Webassembly Outlook add-in](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/blazor-add-in/outlook-blazor-add-in) 
    * Developer sandbox - [Join the Microsoft 365 Developer Program today!](https://developer.microsoft.com/microsoft-365/dev-program) 
    * Website – [Blazor - Build client web apps with C#](https://dotnet.microsoft.com/apps/aspnet/web-apps/blazor)
    * Documentation - [ASP.NET Core Blazor fundamentals](https://docs.microsoft.com/aspnet/core/blazor/fundamentals) 
    * Documentation - [Tooling for ASP.NET Core Blazor](https://docs.microsoft.com/aspnet/core/blazor/tooling)
    * Documentation - [ASP.NET Core Blazor project structure](https://docs.microsoft.com/aspnet/core/blazor/project-structure) 
    * Documentation - [ASP.NET Core Blazor hosting models](https://docs.microsoft.com/aspnet/core/blazor/hosting-models)
    * Documentation - [ASP.NET Core Blazor JavaScript interoperability (JS interop)](https://docs.microsoft.com/aspnet/core/blazor/javascript-interoperability)
    * Documentation - [Host and deploy ASP.NET Core Blazor](https://docs.microsoft.com/aspnet/core/blazor/host-and-deploy) 
    * Documentation - [ASP.NET Core Razor component lifecycle](https://docs.microsoft.com/aspnet/core/blazor/components/lifecycle)
    * Documentation - [Debug ASP.NET Core Blazor WebAssembly](https://docs.microsoft.com/aspnet/core/blazor/debug)
    * Documentation - [ASP.NET Core Blazor dependency injection](https://docs.microsoft.com/aspnet/core/blazor/fundamentals/dependency-injection)
  **Q&A**
    * Documentation - [Office.MessageRead interface](https://learn.microsoft.com/javascript/api/outlook/office.messageread?view=outlook-js-preview)
    * Documentation - [Use the Outlook REST APIs from an Outlook add-in ](https://learn.microsoft.com/office/dev/add-ins/outlook/use-rest-api)
    

## Stay connected

* Follow our blog posts at [Microsoft 365 platform community blog](https://aka.ms/m365pnp/blog)
* [Follow @microsoft365dev on Twitter](https://twitter.com/microsoft365dev)
* [Microsoft 365 Platform Community on YouTube](https://aka.ms/m365/videos)
* Invites to all [Microsoft 365 Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions about Office Add-ins development](https://aka.ms/officeaddinsform) for our next community call
* [Join us for our next community call](https://aka.ms/officeaddinscommunitycall) on October 12th at 8:00 AM PT

{{< attachments >}}
