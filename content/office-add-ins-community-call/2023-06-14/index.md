---
title: "Office Add-ins developer platform community call – June 14, 2023"
summary: "Topics include: Recap announcements made by the Add-ins org at Microsoft Build 2023 presented by Juan Balmori Labra, Principal Product Manager at Microsoft. Call hosted by Preethika Kiruveedula, Product Manager at Microsoft. Recorded on June 14, 2023."
date: 2023-06-14T08:01:00-05:00
author: "Preethika Kiruveedula"
githubname: preethikakiru
categories: ["Office add in developer community call"]
images:
- images/Session-Promo-June-2023.jpg
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/ACLYugQ6xgA
draft: false
---

# Office Add-ins developer platform community call - June 14, 2023

## This month's agenda and presenters

The call was hosted by [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a148), Product Manager, Microsoft.

* **Recap announcements made by the Add-ins org at Microsoft Build 2023.** The New Outlook and Outlook Add-ins, New features including Mailbox 1.13 and Smart Alerts learnings and best practices. Product demos delivered by partners – harman.ie and CodeTwo showing their products that incorporate Mailbox 1.13 features. Mailbox 1.13 is now in production, 7 features reviewed. Smart Alerts runs js-engine for Win32 and WebView for OWA.[Juan Balmori Labra](https://www.linkedin.com/in/juan-balmori-8443b532/), Principal Product Manager, Microsoft.

* **Q&A.** See question and answers at end of call and in chat throughout call. [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a14), Product Manager, Microsoft.

{{< youtube ACLYugQ6xgA >}}

## View video segments

* Introduction [00:00](https://youtu.be/P5DolLyE3E8?t=0)
* The New Outlook and Outlook Add-ins – overview [02:20](https://youtu.be/P5DolLyE3E8?t=53)
* Mailbox 1.13 rolling out to production – overview [11:05](https://youtu.be/P5DolLyE3E8?t=107)
* Mailbox 1.13 feature demo - Transition to New Outlook by using:  Item Multi Select + Context Free Commands – [harmin.ie](https://harman.ie)[13:10](https://youtu.be/P5DolLyE3E8?t=400)
* Mailbox 1.13 - features [16:26](https://youtu.be/P5DolLyE3E8?t=508)
* Mailbox 1.13 feature demo – Transition to New Outlook by using :  AutoLaunch Event including FromChanged Event – [CodeTwo](https://www.codetwo.com/)[22:19]()
* Smart Alerts Best Practices – recap [26:11](https://youtu.be/ACLYugQ6xgA?t=1571)
* Q&A [38:51](https://youtu.be/ACLYugQ6xgA?t=2331)
* Closing [40:28](https://youtu.be/ACLYugQ6xgA?t=2428)


## Call to action

* Fill out our Office Add-in Developer Experience Survey.
    * [Office Add-in Developer Experience Survey](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR-0oJqQ4NUVOo6aMB4pZ11dUOFhXOVFJU0ZaOERYMzI5VzBSS0RDQ0dCQS4u)
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
* [Next community call](https://aka.ms/officeaddinscommunitycall) on July 12th at 8:00 AM Pacific Time.
* Please complete the [Office add-in developing experience survey](https://forms.office.com/r/wmzCgccbPa).

## Q&A (Question & Answers)

**Will Sensitivity Labels eventually introduce built-in functionality with attachments, or is it only planned to have it operate on the message level? From my understanding it will not pick up on any labelled attachments at the moment.**

Regarding Sensitivity labels the understanding is correct. We don't currently pick up on any labeled attachments at the moment. This is not currently also not a part of our backlog/future plans either.

**Is "New Outlook" now the equivalent of the previously planned "One Outlook"?**

Yes, New Outlook (mentioned as One Outlook in previous calls) is an initiative to bring a  new modern and simplified design to your Outlook app.

**Regarding Message Encryption, what is the status exactly. Are you talking here about Smime? Also, is this to be supported on mobile form factor?**

We plan to add support for message encryption as part of our initiative to close the gaps for COM scenarios this year. You can refer the API to replace body on read which is already available for preview: [https://learn.microsoft.com/javascript/api/outlook/office.display?view=outlook-js-preview](https://learn.microsoft.com/javascript/api/outlook/office.display?view=outlook-js-preview). We don’t have timelines for mobile support yet.

**Will there be any support for mail sent/ receive events?**

We don’t have support for mail sent/ receive events yet. However, you can use onMessageSend to see if an email is being sent. Use Smart Alerts and the OnMessageSend and OnAppointmentSend events in your [Outlook add-in - Office Add-ins | Microsoft Learn](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Foffice%2Fdev%2Fadd-ins%2Foutlook%2Fsmart-alerts-onmessagesend-walkthrough%3Ftabs%3Dxmlmanifest&data=05%7C01%7Cpkiruveedula%40microsoft.com%7Ca0a5c45517fd4cf7ba0708db845c5b21%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C638249304497324540%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=TOufALi%2BqK1mMEQfOPkOfzUMacYJR8K5PSZgExzAf5E%3D&reserved=0).

**What are the APIs in Outlook for the CRM/Project management scenarios?**

We have recently listed and published all the supported and unsupported API's on Mobile [Outlook JavaScript APIs supported in Outlook on mobile devices - Office Add-ins | Microsoft Learn](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Foffice%2Fdev%2Fadd-ins%2Foutlook%2Foutlook-mobile-apis&data=05%7C01%7Cpkiruveedula%40microsoft.com%7Ca0a5c45517fd4cf7ba0708db845c5b21%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C638249304497168789%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=H5QqUUVNxmJEZfzXKyqUhiwjgVZqQta018ctADCAFFk%3D&reserved=0). 2.	CRM supported APIs are the ones that are supported on Appointment Read surface. There are six different apis available: [Get User Identity Token](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Fjavascript%2Fapi%2Foutlook%2Foffice.mailbox%3Fview%3Doutlook-js-preview%26preserve-view%3Dtrue%23outlook-office-mailbox-getuseridentitytokenasync-member(1)&data=05%7C01%7Cpkiruveedula%40microsoft.com%7Ca0a5c45517fd4cf7ba0708db845c5b21%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C638249304497168789%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=rJm6joLixuGqi9%2BrRPKUySx2JfFa2cgHQtcyxSsai%2Bs%3D&reserved=0), [CustomProperties - Load and Save](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Fjavascript%2Fapi%2Foutlook%2Foffice.customproperties%3Fview%3Doutlook-js-preview&data=05%7C01%7Cpkiruveedula%40microsoft.com%7Ca0a5c45517fd4cf7ba0708db845c5b21%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C638249304497168789%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=AiJF0dOdCEl%2Fx0wfrhB6oRsHXSmFkp82m2oToPPnR2k%3D&reserved=0), [Get callback token](https://learn.microsoft.com/javascript/api/outlook/office.mailbox?view=outlook-js-preview#outlook-office-mailbox-getcallbacktokenasync-member(1)), [Get body](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Fjavascript%2Fapi%2Foutlook%2Foffice.body%3Fview%3Doutlook-js-preview%23outlook-office-body-getasync-member(1)&data=05%7C01%7Cpkiruveedula%40microsoft.com%7Ca0a5c45517fd4cf7ba0708db845c5b21%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C638249304497168789%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=Y31bJ3aZrIFsxOkIKhTYrbtMBh58AGn1Ahp7Fx4IC1w%3D&reserved=0), [Close container](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Fjavascript%2Fapi%2Foffice%2Foffice.ui%3Fview%3Dcommon-js-preview%23office-office-ui-closecontainer-member(1)&data=05%7C01%7Cpkiruveedula%40microsoft.com%7Ca0a5c45517fd4cf7ba0708db845c5b21%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C638249304497168789%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=SW7UgpEFZ%2FWT9YwnNXoAvJdpfOm4kf22nfj8OY66K%2BU%3D&reserved=0), and [Event completed](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Fjavascript%2Fapi%2Foffice%2Foffice.addincommands.event%3Fview%3Dcommon-js-preview&data=05%7C01%7Cpkiruveedula%40microsoft.com%7Ca0a5c45517fd4cf7ba0708db845c5b21%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C638249304497168789%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=vLUp0OXLZEdOQxXmlwgcskrSCoQg%2FnyhVBGREJexAGk%3D&reserved=0).

**We are currently developing a spellchecker add-in for Word that targets minority languages. Our approach involves extracting text from the paragraphs, checking for spelling errors, and displaying them in a taskbar. However, we are facing a challenge in determining the position of a word in the document after a user has accepted a proposed change.We have attempted to keep track of the index of a paragraph, but this approach proves to be problematic as the index changes when the text at the beginning of the document is altered, rendering our stored information invalid. We also experimented with marking all issues with content controls, which are identifiable through an ID. However, this approach leaves fields in the document.What approach would you recommend for keeping track of the paragraphs or even the exact text positions in order to replace the word accurately?**

We need to get more information regarding your scenario, if possible would be great if you can provide us with your contact information. Ways to do this include submitting more info in a forms response or creatings a ticket at [Technical Questions about Office add-ins](https://aka.ms/office-addins-dev-questions).

**Do we have any API to extract a PowerPoint selected slides alone?**

We do have APIs to get selected slides of a presentation: [PowerPoint.Presentation class - Office Add-ins | Microsoft Learn](https://learn.microsoft.com/javascript/api/powerpoint/powerpoint.presentation?view=powerpoint-js-preview#powerpoint-powerpoint-presentation-getselectedslides-member(1)).
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
* [Next community call – July 12th at 08:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}
