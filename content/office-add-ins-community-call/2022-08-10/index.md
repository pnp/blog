---
title: "Office Add-ins developer platform community call – August 10, 2022"
summary: "Topics include Excel add-in user pattern Open in Excel, Linq to XML in Office.js, Office Add-ins developer platform community update, Outlook add-in API update, REST decommission, Mailbox 1.12 scope definition."
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

# Office Add-ins developer platform community call - August 10, 2022

## This month's agenda and presenters

The call was hosted by [David Chesnut](http://twitter.com/davidchesnut), Senior Technical Writer, Microsoft Office Developer Platform
* **Excel add-in user pattern – Open in Excel.** Export data from any system to Excel. [Yawei Zhu](https://www.linkedin.com/in/yaweizhu-henson/), Senior Product Manager, Microsoft. 
* **Use Linq to XML in Office.js Add-ins.** Two TypeScript libraries for dealing with Open XML markup. [Thomas Barnekow](https://www.linkedin.com/in/thomas-barnekow-2580b11), Senior Principal Software Architect, [Analog Devices](https://www.analog.com/en/index.html).
* **Office Add-ins community engagement update.** Help us select a single destination for product ideas and suggestions. [Linda Lu Cannon](https://www.linkedin.com/in/lindalu-msft/), Senior Content Project Manager Microsoft, Microsoft.
* **Outlook add-in API update: REST decommission and Mailbox 1.12 scope.** New event-based features in Mailbox v1.12 and REST decommission update. [Juan Balmori](http://twitter.com/juaneloBalmori), Principal Product Manager, Microsoft.
* **Q&A.** See question and answers at end of call and in chat throughout call.
{{< youtube COic6ghBWsU&t >}}
## View Video Segments

* Excel add-in user pattern: Open in Excel [1:12](https://youtu.be/KxaE0SLk-lM?t=72)
* Use Linq to XML in Office.js Add-ins [9:27](https://youtu.be/KxaE0SLk-lM?t=567)
* Office Add-ins community engagement update [31:00](https://youtu.be/KxaE0SLk-lM?t=1860)
* Outlook add-in API update: REST decommission and Mailbox v1.12 scope [42:05](https://youtu.be/KxaE0SLk-lM?t=2525)
* Q&A [59:17](https://youtu.be/KxaE0SLk-lM?t=3557)

## Topic summaries

* **Excel add-in user pattern – Open in Excel.** In the Open in Excel pattern, reduce steps for sourcing, installing, and using an add-in from 6 to 3. See when and how to use pattern along with benefits for users and developers. Users can export data from any system to Excel. The Excel JavaScript add-in integrates your service with Excel by maintaining a connection between system data and your add-in.
* **Use Linq to XML in Office Add-ins.** To support Office Add-ins, presenter has developed two TypeScript libraries (linq-to-xml and linq-to-ooxml) to handle Open XML markup. The code enables pure functional transformations of Office Open XML (OOXML) documents in Office Add-ins. In the Linq samples shown, see how to use capabilities from the libraries to transform a Word document that contains a massive number of content controls.
* **Office Add-ins community engagement update.** Pros/cons of locations to share your Office.js ideas, improvements, and feature suggestions. Linda had three asks: 1.) Provide feedback and other suggestions on using GitHub issues vs. discussions, 2.) Tag @lindalu-MSFT on your ideas previously submitted to [Tech Communities ideas forum](https://aka.ms/m365dev-suggestions) to ensure transfer, and 3.) Are you interested in participating in a User Research session about customer support channels? [Contact Linda](mailto:lindalu@microsoft.com).  
* **Outlook add-in API update: REST decommission and Mailbox 1.12 scope.** Updates since February regarding Outlook v2.0 REST API decommission. Mailbox v1.12 adds two big event-based features: Smart Alerts (onMessageSend and onAppointmentSend) and New Compose events (onMessageCompose and onAppointmentOrganizer). The features are available in preview for Windows and Outlook on the web. Q&A at end of demo addresses when you can still use the REST API, solution for mobile, and using REST in an on-premises Exchange environment.
  
## Call to action

* Give us feedback on what you need from Word APIs. [Complete the survey](aka.ms/WordAPI).
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
* [Join the next Office Add-ins community call](https://aka.ms/officeaddinscommunitycall) on September 14th at 8:00 AM Pacific Time.

## Q&A (Question & Answers)

**Is there a resource that shows speed parity issues between PC/Mac/Web? For text search and selection, we see much faster performance on PC than on Mac. It would be great to see best practices on how to keep performance consistent among platforms.**

In order to best answer your question we need further clarification. Does this performance issue occur with a particular set of Word APIs being introduced or is there a difference in performance for the host Word on PC and Mac? It would be great if you could log an issue and provide more context here on our [Office.js Github repo](https://github.com/OfficeDev/office-js). 


**Any timelines on when these Smart Alerts will be supported on Outlook Mobile?**

We currently don't have concrete plans on the roadmap. It would be great if you could create a feature request with more information at https://aka.ms/m365dev-suggestions.

**Will the APIs for opening a document be extended to allow for opening POTX files? It currently only allows for PPTX I believe. (Unless I've missed something.)**

This is a great feature to request, please go to the M365 developer platform and put in a new idea request with more information at https://aka.ms/m365dev-suggestions.

## Additional Resources

* **Excel add-in user pattern: Open in Excel**
    *[Open Excel from your web page and embed your Office Add-in](https://docs.microsoft.com/office/dev/add-ins/excel/pnp-open-in-excel)
    *[Deploy add-ins in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)
    *[Configure your Office Add-in to use a shared JavaScript runtime](https://docs.microsoft.com/office/dev/add-ins/develop/configure-your-add-in-to-use-a-shared-runtime)
    * Feedback - [Open in Excel pattern proposal feedback](https://forms.office.com/r/14KL0MjPfJ)
* **Use Linq to XML in Office Add-ins**
    * Github Sample repo - [OpenXmlDev/linq-to-xml](https://ineleccom-my.sharepoint.com/personal/andrb_inelec_com/Documents/Desktop/Office Videos/Add In Calls/2022-08-10-OfficeAdd-ins/OpenXmlDev / linq-to-xml)
    * npm - [LINQ to XML for TypeScript](https://www.npmjs.com/package/@openxmldev/linq-to-xml)
    * Github sample repo - [OpenXmlDev/linq-to-ooxml](https://github.com/OpenXmlDev/linq-to-ooxml)
    * npm - [OOXML Namespace-Related Classes for LINQ to XML for TypeScript](https://www.npmjs.com/package/@openxmldev/linq-to-ooxml)
    * Github sample repo- [OpenXmlDev/inq-add-in](https://github.com/OpenXmlDev/linq-add-in)
  **Outlook Add-in API update: REST decommission and Mailbox 1.12 scope **
    *[REST API Add-in verification request](https://aka.ms/RESTCheck)
    *[Use the Outlook REST APIs from an Outlook add-in](https://docs.microsoft.com/office/dev/add-ins/outlook/use-rest-api)
    *[Add-ins for Outlook mobile](https://docs.microsoft.com/office/dev/add-ins/outlook/outlook-mobile-addins)
    *[On-Premises Architectural Requirements for the REST API](https://techcommunity.microsoft.com/t5/exchange-team-blog/on-premises-architectural-requirements-for-the-rest-api/ba-p/605609)
    

## Stay connected

* See the full blog post at [Microsoft 365 platform community blog](https://aka.ms/m365pnp/blog)
* [Follow @microsoft365dev on Twitter](https://twitter.com/microsoft365dev)
* [Microsoft 365 Platform Community on YouTube](https://aka.ms/m365/videos)
* Invites to all [Microsoft 365 Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions about Office Add-ins development](https://aka.ms/officeaddinsform) for our next community call
* [Join us for our next community call](https://aka.ms/officeaddinscommunitycall) on September 14th at 8:00 AM PT

{{< attachments >}}