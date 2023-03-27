---
title: "Office Add-ins developer platform community call – March 8th, 2023"
summary: "Topic: March 2023 Word Extensibility APIs (preview) presented by Yun Wang, Principal Product Manager at Microsoft. The call was hosted by Preethika Kiruveedula. Recorded on March 8, 2023."
date: 2023-03-08T08:01:00-05:00
author: "Preethika Kiruveedula"
githubname: preethikakiru
categories: ["Office Add-ins community call"]
images:
- images/Session-Promo-Mar-2023.jpg
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/gmNSqNIG_SY
draft: true
---

# Office Add-ins developer platform community call - March 8, 2023

## This month's agenda and presenters

The call was hosted by [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a148), Product Manager, Microsoft.

* **Word Extensibility APIs (Preview) - March 2023.** [Yun Wang](https://www.linkedin.com/in/wang-yun-99370463/?originalSubdomain=cn), Principal Product Manager, Microsoft. 
* **Q&A.** See question and answers at end of call and in chat throughout call. [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a14), Product Manager, Microsoft.

{{< youtube gmNSqNIG_SY >}}

## View video segments

* Introduction [00:00](https://youtu.be/gmNSqNIG_SY?t=0)
* Upcoming Preview Word APIs coming in March 2023 [00:32](https://youtu.be/gmNSqNIG_SY?t=32)
* Q&A [10:59](https://youtu.be/gmNSqNIG_SY?t=659)
* Resources [13:37](https://youtu.be/gmNSqNIG_SY?t=817)
* Closing [14:52](https://youtu.be/gmNSqNIG_SY?t=892)

## Topic summaries

* **Word Extensibility APIs (preview) - March 2023.** Five Word desktop APIs reviewed in last month’s call plus three new features (Application.retrieveStylesFromBase64, recognize deleted content controls and plain text content control support), are available now for you to test.  Requires running desktop version 16.0.16130.20218 and above.  Hear about all eight desktop features plus one new Word online feature “Track changes for content controls” is now in production. Targeting mid-year GA on features.

## Call to action

* Call to Action for Outlook Add-in Mobile Developers – provide feedback on Outlook add-in scenarios you are trying to support [Outlook Mobile Add-in Developer Survey](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRw5b9d2wAdRLj9NKAu1xfddUM1pW).
* Join a Community panel – product focused add-in discussion groups 
    * [Outlook add-ins panel](https://ux.microsoft.com/Panel/OutlookAddinDeveloper)
    * [Excel add-ins panel](https://ux.microsoft.com/Panel/ExcelAddinDeveloper)
    * [Word add-ins panel](https://ux.microsoft.com/Panel/WordAddinDeveloper)
    * [PowerPoint add-ins panel](https://ux.microsoft.com/Panel/PowerPointAddinDeveloper)
    * [Samples and docs](https://ux.microsoft.com/Panel/OfficeAddinImproveSamplesDocs)
* [Register for the PnP Recognition Program](https://pnp.github.io/recognitionprogram/) and earn contributor badges.
* •	Follow channels in twitter to see call agendas, important updates, and release announcements. 
    * [@microsoft365dev](https://twitter.com/microsoft365dev)
    * [@m365pnp](https://twitter.com/m365pnp)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free E5 developer tenant with instant availability and other assets.
* [Next community call ](https://aka.ms/officeaddinscommunitycall) on April 12th at 8:00 AM Pacific Time.
* Please complete the [Office add-in developing experience survey](https://forms.office.com/r/wmzCgccbPa).

## Q&A (Question & Answers)

**How long does it take to reflect the changes made in app registration inside azure portal to the development?**

Need Answer.

**What's the timeframe for providing feedback from the "Auto install and auto launch add-ins for Word, Excel and PowerPoint" survey?**

Thank you for sharing great feedback. We are planning to present the survey results in the next community call.

**Are the functions in the demo still in beta?**

Yes, the functions demoed are currently in preview.

**Is there any documentation page about all this new Word API?**

To learn more about the Word JavaScript API in preview, see [Word JavaScript preview APIs](https://learn.microsoft.com/en-us/javascript/api/requirement-sets/word/word-preview-apis?view=powerpoint-js-preview).

**Last month, you asked for missing Outlook events so that ISVs can migrate their existing Outlook COM add-ins to the new web based add-ins. With that in mind, we are looking for the following: 1. The ability to display a dialog when a Compose, Reply, Reply All, or Forward is clicked. The customers want to either display a warning or in some cases (like the Compose) they want to force the user to select from a list of pre-defined subjects (this is for a help desk scenario). Other (mostly legal) customers want to see a very prominent prompt show up when clicking on Reply All. 2. The ability to support on-send Outlook events (or Smart Alerts) in iPhone or Android. This is a frequent request from our customers and we need a roadmap from the Office team to know whether this is a planned feature or not, and what to tell our customers.**

1. We already have the events you need. The way we recommend handling this is case is the following:
  Using Event based add-ins and subscribe the OnCOmpose events. This will trigger an event you can handle when folks create new messages or reply/reply all/fwd. As part of the handler of that event you can pop a notification bar to that the user can select from the pre-defined list of subjects.  Upon clicking that notification bar you can open a taskpane from which the user can select and insert. To make sure that the user is actually changing the subject add an OnSend event handler, so after the user clicks “send” you can validate if the subject is compliant and stop the send until the user changes it.
2. The ability to support on-send Outlook events (or Smart Alerts) in iPhone or Android. This is in our backlog and  been currently planned for implementation. 

**I am looking at developing an add-in for PowerPoint. As the task pane and content add-in have different functions, are we able to essentially combine them into one add-in for the user? Or are there any issues with having two types of add-ins, with one add-in drawing information from the other? Would also like to know if there are any restrictions or security issues from developing the add-in this way.**

It isn't currently possible to develop a task pane and content add-in in a single add-in project. To submit a feature request with more information about your specific scenario, see [https://aka.ms/m365dev-suggestions](https://aka.ms/m365dev-suggestions).

**Will task pane in Outlook add-in support change default width?**

We don't have any plans to support this in the near future.

## Resources related to to this blog's content

* Feedback Repo: [Issues – OfficeDev/Office-js](https://github.com/OfficeDev/office-js/issues)
* Add-in: [Grammarly for Microsoft Word and Outlook](https://www.grammarly.com/office-addin)
* Community panels – discussion and feedback 
  * [Outlook add-ins](https://ux.microsoft.com/Panel/OutlookAddinDeveloper)
  * [Excel add-ins](https://ux.microsoft.com/Panel/ExcelAddinDeveloper)
  * [Word add-ins ](https://ux.microsoft.com/Panel/WordAddinDeveloper)
  * [PowerPoint add-ins](https://ux.microsoft.com/Panel/PowerPointAddinDeveloper)
  * [Samples and docs](https://ux.microsoft.com/Panel/OfficeAddinImproveSamplesDocs)

## General Resources

* [Documentation](https://aka.ms/office-add-ins-docs)
* Quick Starts: [Outlook](https://docs.microsoft.com/office/dev/add-ins/quickstarts/outlook-quickstart), [Excel](https://docs.microsoft.com/office/dev/add-ins/quickstarts/excel-quickstart-jquery), [Word](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart), and [PowerPoint](https://docs.microsoft.com/office/dev/add-ins/quickstarts/powerpoint-quickstart)
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

* See the full blog post for this call in the Microsoft 365 platform community blog [https://aka.ms/m365pnp/blog](https://aka.ms/m365pnp/blog)
* [Twitter](https://twitter.com/microsoft365dev)
* [Microsoft 365 Unified Sample gallery](https://aka.ms/community/samples)
* [Microsoft 365 Platform Community in YouTube](https://aka.ms/community/videos)
* [Microsoft 365 Platform Community](http://aka.ms/community/home)
* [Link to all Microsoft Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions for next community call](https://aka.ms/officeaddinsform)
* [Next community call – April 12th at 08:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}
