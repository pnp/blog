---
title: "Office Add-ins community call – August 10, 2022"
summary: "Excel add-in User Pattern – Open in Excel, Using Linq to XML in Office.js Add-ins, Office Add-ins Community engagement update, Outlook Add-in API update - REST decommission and Mailbox 1.12 Scope definition."
date: 2022-08-10T08:01:00-05:00
author: "Preethika Kiruveedula"
githubname: preethikakiru
categories: ["Office Add-in developer community call"]
images:
- images/office-add-ins-call-august-2022-recording.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/KxaE0SLk-lM 
draft: true
---

## Call summary

* **Excel add-in User Pattern – Open in Excel.** export data from any system to Excel. [Yawei Zhu](https://www.linkedin.com/in/yaweizhu-henson/) Senior Product Manager (Microsoft) 
* **Using Linq to XML in Office.js Add-ins.** (2 TypeScript libraries for dealing with Open XML markup). [Thomas Barnekow](https://www.linkedin.com/in/thomas-barnekow-2580b11),Senior Principal Architect (Analog Devices)
* **Office Add-ins Community engagement update – August 2022.** help us select a single destination for developer feedback. [Linda Cannon](http://twitter.com/lindalu_MSFT), Senior Content Product Manager (Microsoft), @lindalu_MSFT
* **Outlook Add-in API update - REST decommission and Mailbox 1.12 Scope definition.** new event-based features in Mailbox v1.12 and REST decommission update. [Juan Balmori](http://twitter.com/juaneloBalmori), Principal Product Manager (Microsoft)
* **Community panels.** Join us to share your feedback on how we can provide you with a better Office Add-ins development experience
* **Q&A.** See question and answers at end of call and in chat throughout call

The call was hosted by [David Chesnut](http://twitter.com/davidchesnut) (Microsoft) | @davidchesnut. Recorded August 10, 2022.

{{< youtube COic6ghBWsU&t >}}
## Agenda

* Excel add-in User Pattern - Open in Excel. Yawei Zhu, Senior Product Manager (Microsoft) – [1:12] (https://youtu.be/KxaE0SLk-lM?t=72)
* Using Linq to XML in Office.js Add-ins. Thomas Barnekow, Senior Principal Architect (Analog Devices), [9:27] (https://youtu.be/KxaE0SLk-lM?t=567)
* Office Add-ins Community engagement update - August 2022. Linda Cannon, Senior Content Product Manager (Microsoft) | @lindalu_MSFT,  [31:00] (https://youtu.be/KxaE0SLk-lM?t=1860)
* Outlook Add-in API update - REST decommission and Mailbox 1.12 Scope definition. Juan Balmori, Principal Product Manager (Microsoft), @juaneloBalmor, [42:05] (https://youtu.be/KxaE0SLk-lM?t=2525)
* Q&A. David Chestnut, Senior Technical Writer (Microsoft), (http://twitter.com/davidchesnut), @davidchesnut, [59:17](https://youtu.be/KxaE0SLk-lM?t=3557)

## Topic summaries

* **Excel add-in User Pattern – Open in Excel .**  in the Open in Excel Pattern, reduce steps for sourcing, installing, and using an add-in from 6 to 3.  See when and how to use pattern along with benefits and value propositions to users and developers.  User can export data from any system to Excel.  The Excel JS add-in integrates your service with Excel by maintaining a connection between system data and your add-in.
* **Using Linq to XML in Office.js Add-ins.** to support Office.js add-ins, presenter has developed 2 TypeScript libraries (linq-to-xml and linq-to-ooxml) for dealing with Open XML markup.   The code enables pure functional transformations of Office Open XML documents in Office.js Add-ins.   In the linq-add-in sample shown, see code and how to use capabilities from the libraries to transform a Word document that contains a massive number of content controls. 
* **Office Add-ins Community engagement update – August 2022** help us identify the best location to capture your feedback, suggestions, and issues.  Pros/cons of location options shared.   Action:  Provide feedback by end of August on 3 items - use Feedback Portal or GitHub for feedback, is there feedback you submitted on Tech Communities site that needs to be kept, and are you interested in participating in a User Research session about customer support channels?      
* **Outlook Add-in API update - REST decommission and Mailbox 1.12 Scope definition** Mailbox v1.12 scope adds 2 big event-based features – Smart Alerts (onMessageSend & onAppointmentSend) and New Compose events (onMessageCompose & onAppointmentOrganizer).  The featuress are available in preview for Windows and OWA.   Updates since February regarding Outlook v2.0 REST API decommission.  Q&A addresses up to when you can still use the REST API, solution for mobile, and using REST in OnPrem.  Q&A at end of demo.
  



## Actions

* Give us feedback on what you need from code samples. Join the Teams call. [Office Add-ins samples discussion](https://aka.ms/officeaddinsamples-join), July 27th, 8:00 AM PT,  <https://aka.ms/officeaddinsamples-call>
* Share your feedback on how we can provide you with a better Office Add-ins development experience. Join a community panel. 
    * [Outlook add-ins panel](https://ux.microsoft.com/Panel/OutlookAddinDeveloper)
    * [Excel add-ins panel](https://ux.microsoft.com/Panel/ExcelAddinDeveloper)
    * [Word add-ins panel](https://ux.microsoft.com/Panel/WordAddinDeveloper)
    * [PowerPoint add-ins panel](https://ux.microsoft.com/Panel/PowerPointAddinDeveloper)
    * [Samples and docs](https://ux.microsoft.com/Panel/OfficeAddinImproveSamplesDocs)
* [Sign up for the PnP Recognition Program](https://pnp.github.io/recognitionprogram/) and earn contribution badges
* See call agendas and summaries, and release announcements. Follow us on Twitter. 
    * [@microsoft365dev](https://twitter.com/microsoft365dev)
    * [@m365pnp](https://twitter.com/m365pnp)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free E5 developer tenant with instant availability and other assets.
* [Join the next community call](https://aka.ms/officeaddinscommunitycall) on September 14th at 8:00 AM Pacific Time (PT)

## Q&A (Question & Answers)

**Is there a resource that shows speed parity issues between PC/Mac/Web? For text search and selection, for instance, we see much faster performance on PC than on Mac. It would be great to see best practices on how to keep performance consistent among platforms.**

In order to best answer your question we need further clarification, is this performance issue occurring with a particular set of word apis being introduced or is there an difference in performance for the host word on pc and mac? It would be great if you could log an issue and provide more context here at https://github.com/OfficeDev/office-js . 


**Any timelines on when these Smart Alerts will be supported on Outlook Mobile?**

We currently don't have concrete plans on the roadmap. It would be great if you could create a feature request with more information at https://aka.ms/m365dev-suggestions.

**Will the APIs for opening a document be extended to allow for opening POTX files? It currently only allows for PPTX I believe. (Unless I've missed something.)**

This is a great feature to request, please go to the M365 developer platform and put in a new idea request with more information at https://aka.ms/m365dev-suggestions.

## References

* **Excel add-in User Pattern – Open in Excel**
    * Documentation - [Open Excel from your web page and embed your Office Add-in](https://docs.microsoft.com/office/dev/add-ins/excel/pnp-open-in-excel)
    * Documentation - [Deploy add-ins in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)
    * Documentation - [Configure your Office Add-in to use a shared JavaScript runtime](https://docs.microsoft.com/office/dev/add-ins/develop/configure-your-add-in-to-use-a-shared-runtime)
    * Feedback - [Open in Excel pattern proposal feedback](Open in Excel pattern proposal feedback)
* **Using Linq to XML in Office.js Add-ins**
    * Repo - [OpenXmlDev / linq-to-xml](https://ineleccom-my.sharepoint.com/personal/andrb_inelec_com/Documents/Desktop/Office Videos/Add In Calls/2022-08-10-OfficeAdd-ins/OpenXmlDev / linq-to-xml)
    * npm - [LINQ to XML for TypeScript](https://www.npmjs.com/package/@openxmldev/linq-to-xml)
    * Repo - [OpenXmlDev / linq-to-ooxml](https://github.com/OpenXmlDev/linq-to-ooxml)
    * npm - [OOXML Namespace-Related Classes for LINQ to XML for TypeScript](https://www.npmjs.com/package/@openxmldev/linq-to-ooxml)
    * Sample- [OpenXmlDev / linq-add-in](https://github.com/OpenXmlDev/linq-add-in)
* **Office Add-ins Community engagement update – August 2022**
    * Feedback Portal - [Feedback Portal](https://feedbackportal.microsoft.com/feedback/search/?q=Add-ins)
    * Github - [Product Feature Request - OfficeDev/office-js](https://github.com/OfficeDev/office-js/issues?q=is%3Aissue+is%3Aopen+label%3A%22Type%3A+product+feature+request%22)
  **Outlook Add-in API update - REST decommission and Mailbox 1.12 Scope definition **
    * Participate - [REST API Add-in verification request](https://aka.ms/RESTCheck)
    * Documentation - [Add-ins for Outlook Mobile](https://docs.microsoft.com/office/dev/add-ins/outlook/outlook-mobile-addins)
    * Article - [On-Premises Architectural Requirements for the REST API](https://techcommunity.microsoft.com/t5/exchange-team-blog/on-premises-architectural-requirements-for-the-rest-api/ba-p/605609)
    

## General resources

* [Office developer center](https://developer.microsoft.com/office)

## Stay connected

* See the full blog post at [Microsoft 365 platform community blog](https://aka.ms/m365pnp/blog)
* [Follow @microsoft365dev on Twitter](https://twitter.com/microsoft365dev)
* [Microsoft 365 Platform Community on YouTube](https://aka.ms/m365/videos)
* Invites to all [Microsoft 365 Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions about Office Add-ins development](https://aka.ms/officeaddinsform) for our next community call
* [Join us for our next community call](https://aka.ms/officeaddinscommunitycall) on August 10th at 8:00 AM PT

{{< attachments >}}