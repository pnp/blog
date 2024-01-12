---
title: "Office Add-ins developer platform community call – July 12, 2023"
summary: "Topics include: Recap announcements made by the Add-ins org at Microsoft Build 2023 presented by Juan Balmori Labra, Principal Product Manager at Microsoft. Call hosted by Preethika Kiruveedula, Product Manager at Microsoft. Recorded on July 12, 2023."
date: 2023-07-12T08:01:00-05:00
author: "Preethika Kiruveedula"
githubname: preethikakiru
categories: ["Office add in developer community call"]
images:
- images/Session-Promo-July-2023.jpg
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/ACLYugQ6xgA
draft: false
---

# Office Add-ins developer platform community call - July 12, 2023

## This month's agenda and presenters

The call was hosted by [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a148), Product Manager, Microsoft.

* **Top 5 AppSource Validation Errors March - May 2023.** Go over the top five most common appsource validation errors from the months of March to May 2023.[Elizabeth Samuel](https://github.com/elizabethsamuel-msft), Senior Technical Writer, Microsoft.

* **Q&A.** See question and answers at end of call and in chat throughout call. [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a14), Product Manager, Microsoft.

{{< youtube JGlF8yfrTlY >}}

## View video segments

* Introduction [00:00](https://www.youtube.com/watch?v=JGlF8yfrTlY)
* The New Outlook and Outlook Add-ins – overview [00:45](https://youtu.be/JGlF8yfrTlY?t=45)
* Q&A [09:08](https://youtu.be/JGlF8yfrTlY?t=547)
* Closing [15:06](https://youtu.be/JGlF8yfrTlY?t=908)


## Call to action

* Fill out our Office Add-in Developer Experience Survey.
* Join a community panel – product focused add-in discussion groups.
    * [Outlook add-ins panel](https://ux.microsoft.com/Panel/OutlookAddinDeveloper)
    * [Excel add-ins panel](https://ux.microsoft.com/Panel/ExcelAddinDeveloper)
    * [Word add-ins panel](https://ux.microsoft.com/Panel/WordAddinDeveloper)
    * [PowerPoint add-ins panel](https://ux.microsoft.com/Panel/PowerPointAddinDeveloper)
    * [Samples and docs](https://ux.microsoft.com/Panel/OfficeAddinImproveSamplesDocs)
* [Register for the PnP Recognition Program](https://pnp.github.io/recognitionprogram/) and earn contributor badges.
* Follow channels on Twitter to see call agendas, important updates, and release announcements.
    * [@microsoft365dev](https://twitter.com/microsoft365dev)
    * [@m365pnp](https://twitter.com/m365pnp)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free E5 developer tenant with instant availability and other assets.
* [Next community call](https://aka.ms/officeaddinscommunitycall) on August 9th at 8:00 AM Pacific Time.

## Q&A (Question & Answers)

**We are just starting to build our first Word add-on (a writing assistance tool) but already have requests for Outlook, Powerpoint. We saw that for Outlook a new Desktop client will be released next year. As such we are wondering about the roadmap in aligning API's potentially so that ideally for what we are trying to do a single API would support all Office 365 applications.**

Office 365 provides APIs which can be Application specific or Common across multiple applications. Please find more details here: [https://learn.microsoft.com/office/dev/add-ins/reference/javascript-api-for-office](https://learn.microsoft.com/office/dev/add-ins/reference/javascript-api-for-office) Any API which is built for existing Outlook clients would be available for new Outlook as well and there is no additional work needed.

**What is the status of pinning admin deployed add-ins to Outlook web as discussed in the Office Add-ins community call – March 2021.We need deployed add-ins to be immediately visible to users, not hidden requiring digging to find.**

We currently do not support pinning of admin deployed add-ins to Outlook Web but we acknowledge the request. We would get back with timelines on this one soon.

**Do we have any API to extract a PowerPoint selected slides alone?**

Need more context here. For example, what does extract mean here? We do have APIs to get selected slides of a presentation: PowerPoint.[Presentation class - Office Add-ins | Microsoft Learn](https://learn.microsoft.com/javascript/api/powerpoint/powerpoint.presentation?view=powerpoint-js-preview#powerpoint-powerpoint-presentation-getselectedslides-member(1))

**We are currently developing a text enhancement add-in for Word with the objective of offering it without any online account requirements. Our aim is to ensure that the add-in operates locally, thereby eliminating any concerns for professional and administrative users about their data being uploaded to an external server. However, in order to implement the add-in, we need to store some configuration information locally. This information should be independent of the document that the user is working on. We have explored the Settings and CustomXmlParts APIs, but unfortunately, they only save settings in the current document, which is not an optimal solution. Hence, we are inquiring about suggestions on how to store these settings.**

You should try the runtime api 1.1: [OfficeRuntime.Storage interface - Office Add-ins | Microsoft Learn](https://learn.microsoft.com/javascript/api/office-runtime/officeruntime.storage?view=word-js-preview) is asynchronous, global, and persistent key-value storage.

**Regarding Message Encryption, what is the status exactly. Are you talking here about Smime? Also, is this to be supported on mobile form factor?**

 We plan to add support for message encryption as part of our initiative to close the gaps for COM scenarios this year. You can refer the API to replace body on read which is already available for preview: [https://learn.microsoft.com/javascript/api/outlook/office.display?view=outlook-js-preview](https://learn.microsoft.com/javascript/api/outlook/office.display?view=outlook-js-preview). We don’t have timelines for mobile support yet.

**We are currently developing a spellchecker add-in for Word that targets minority languages. Our approach involves extracting text from the paragraphs, checking for spelling errors, and displaying them in a taskbar. However, we are facing a challenge in determining the position of a word in the document after a user has accepted a proposed change.We have attempted to keep track of the index of a paragraph, but this approach proves to be problematic as the index changes when the text at the beginning of the document is altered, rendering our stored information invalid. We also experimented with marking all issues with content controls, which are identifiable through an ID. However, this approach leaves fields in the document.What approach would you recommend for keeping track of the paragraphs or even the exact text positions in order to replace the word accurately?**

We need to get more information regarding your scenario, if possible would be great if you can provide us with your contact information. Ways to do this include submitting more info in a forms response or creatings a ticket at [Technical Questions about Office add-ins](https://aka.ms/office-addins-dev-questions).

**Will there be any support for mail sent/ receive events?**

We don’t have support for mail sent/ receive events yet. However, you can use onMessageSend to see if an email is being sent. [Use Smart Alerts and the OnMessageSend and OnAppointmentSend events in your Outlook add-in - Office Add-ins | Microsoft Learn](https://learn.microsoft.com/office/dev/add-ins/outlook/smart-alerts-onmessagesend-walkthrough?tabs=xmlmanifest).

**Is "New Outlook" now the equivalent of the previously planned "One Outlook"?**

Yes, New Outlook (mentioned as One Outlook in previous calls) is an initiative to bring a  new modern and simplified design to your Outlook app.

**We have a VSTO add-in deployed to 2000+ users. Now we built a office.js based add-in. How do we remove existing VSTO add-in after deploying new add-in? Is there any standard way?**

There is no particular standard way, but here is a good starting point you should try: [Manage add-ins in the admin center - Microsoft 365 admin | Microsoft Learn](https://learn.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center?view=o365-worldwide).

## Resources related to to this blog's content

* Feedback Repo: [Issues – OfficeDev/Office-js](https://github.com/OfficeDev/office-js/issues)
* Add-in: [Grammarly for Microsoft Word and Outlook](https://www.grammarly.com/office-addin)
* Community panels – discussion and feedback:
  * [Outlook add-ins](https://ux.microsoft.com/Panel/OutlookAddinDeveloper)
  * [Excel add-ins](https://ux.microsoft.com/Panel/ExcelAddinDeveloper)
  * [Word add-ins ](https://ux.microsoft.com/Panel/WordAddinDeveloper)
  * [PowerPoint add-ins](https://ux.microsoft.com/Panel/PowerPointAddinDeveloper)
  * [Samples and docs](https://ux.microsoft.com/Panel/OfficeAddinImproveSamplesDocs)

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
* [Technical Questions about Office add-ins](https://aka.ms/office-addins-dev-questions)
* [Stack Overflow Questions](https://stackoverflow.com). Use keywords **office-js**, **outlook-web-addins**, or **office-scripts**.
* [Github office-js issues](https://github.com/OfficeDev/office-js/issues)
* [Microsoft Tech Community – Submit Feature Requests](https://aka.ms/m365dev-suggestions)
* [Microsoft 365 Developer Program](https://aka.ms/M365devprogram)

## Stay connected

* See the full blog post for this call in the [Microsoft 365 platform community blog](https://aka.ms/m365pnp/blog)
* [Twitter](https://twitter.com/microsoft365dev)
* [Microsoft 365 Unified Sample gallery](https://aka.ms/community/samples)
* [Microsoft 365 Platform Community in YouTube](https://aka.ms/community/videos)
* [Microsoft 365 Platform Community](http://aka.ms/community/home)
* [Link to all Microsoft Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions for next community call](https://aka.ms/officeaddinsform)
* [Next community call – August 9th at 08:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}
