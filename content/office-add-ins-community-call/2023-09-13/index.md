---
title: "Office Add-ins developer platform community call – September 13, 2023"
summary: "Topics include: Update on changes to app entry point and dev sideloading, writing assistance update from the Word Extensibility team, security enhancements to callback tokens for Office add-ins, and Word/Excel/PowerPoint add-in entrance has moved from Insert tab to Home tab and File menu. Call hosted by Preethika Kiruveedula, Product Manager at Microsoft. Recorded on September 13, 2023."
date: 2023-09-13T08:01:00-05:00
author: "Preethika Kiruveedula"
githubname: preethikakiru
categories: ["Office add in developer community call"]
images:
- images/Session-Promo-September-2023.jpg
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/XNykp7pLXgI
draft: true
---

# Office Add-ins developer platform community call - September 13, 2023

## This month's agenda and presenters

The call was hosted by [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a148), Product Manager, Microsoft.

* **Update on changes to app entry point and dev sideloading** Go over new updates to UI sideloading for Outlook add-ins and discuss potential delay in sideloading. [Kate Everitt](https://www.linkedin.com/in/kate-everitt-6aa69a3/), Principal Product Manager, Microsoft.

* **Writing assistance Update from the Word Extensibility team** Released a new feature called Writing Assistance for Word add-ins that will allow developers to leverage some of the on-canvas elements present in the editor in Word. Can begin testing feature now. [Yun Wang](https://www.linkedin.com/in/wang-yun-99370463/?originalSubdomain=cn), Principal Product Manager, Microsoft. [Ana Pegan](https://www.linkedin.com/in/anapegan/), Senior Product Manager, Microsoft.

* **Security enhancements to callback tokens for Office add-ins** Enhancements have been made to callback tokens to increase security, have released a new API that incorporates these changes. [Akhilesh Shah](https://www.linkedin.com/in/akhileshshah/), Senior Product Manager, Microsoft.

* **Add-in entrance moved from Insert Tab to Home Tab and File Menu** The add-in entrance for Word, Excel, and PowerPoint has moved from being under the Insert tab to being located on the Home tab and File menu. [Adrian Wu](https://www.linkedin.com/in/adrian-wu-53462582/?originalSubdomain=cn), Senior Product Manager, Microsoft.


* **Q&A.** See question and answers at end of call and in chat throughout call. [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a14), Product Manager, Microsoft.

{{< youtube XNykp7pLXgI >}}

## View video segments

* Introduction [00:00](https://youtu.be/XNykp7pLXgI?t=0)
* Update on changes to app entry point and dev sideloading [01:21](https://www.youtube.com/watch?v=XNykp7pLXgI&t=83s)
* Writing assistance Update from the Word Extensibility team [07:35](https://youtu.be/XNykp7pLXgI?t=455)
* Security enhancements to callback tokens for Office add-ins [14:50](https://youtu.be/XNykp7pLXgI?t=888)
* Add-in entrance moved from Insert Tab to Home Tab and File Menu [18:05](https://youtu.be/XNykp7pLXgI?t=1085)
* Q&A [25:26](https://youtu.be/XNykp7pLXgI?t=1525)
* Closing [26:09](https://youtu.be/XNykp7pLXgI?t=1567)


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
* [Next community call](https://aka.ms/officeaddinscommunitycall) on October 11th at 8:00 AM Pacific Time.

## Q&A (Question & Answers)

**A few months ago, Smart Alerts for Outlook were introduced. At the time, one of the slides said that Smart Alerts run in "js-engine" for Win32 and WebView for OWA. We are finding that there are limitations when using the "js-engine" runtime; the same code works when using WebView for OWA. Where can we find documentation on the "js-engine" features and limitations?**

Still investigating this question.


**Will the delay be removed for the centralized deployment as well? Admin deployed addins from the store?**

I don't have the answers to this but I hear the need for quick deployment across multiple surfaces.

**Does the pin feature still apply only for Outlook? Or also for other products?**

Right now we are doing pinning per client - so it would apply to Outlook only M365 Admin will be auto pinned. We aspire to have them have pin/unpin level of control but no timeline on that.

**"Customer is able to pin or un-pin" Does "customer" here refer to end user or M365 Admin?**

Customer refers to the end user.

**Will sideloading work the same way in Word and Excel as well?**

 The new Store provides a new view of AppSource to help you search and install add-ins for Outlook.

**Where would you go to rate or recommend an addin in this new experience?So the in app experience to rate an add-in is gone?Really? When I go to my add-ins in PowerPoint I can't see that option anymore. Am I missing something?**

You can rate the add-ins on the App Source website: [Business Apps – Microsoft AppSource](https://appsource.microsoft.com/en-US/marketplace/apps?page=1&product=excel%3Bpowerpoint%3Bword) You can still find the rating entry point from the in app store (My add-ins)


## Resources related to to this blog's content

* Feedback Repo: [Issues – OfficeDev/Office-js](https://github.com/OfficeDev/office-js/issues)
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
* [Microsoft 365 Platform Community](https://aka.ms/community/home)
* [Link to all Microsoft Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions for next community call](https://aka.ms/officeaddinsform)
* [Next community call – October 11th at 08:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}
