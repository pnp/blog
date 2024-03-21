---
title: "Office Add-ins developer platform community call – October 11, 2023"
summary: "Topics include: Top 5 AppSource Validation Errors June - August 2023 presented by Elizabeth Samuel, Senior Technical Writer at Microsoft. Call hosted by Preethika Kiruveedula, Product Manager at Microsoft. Recorded on October 11, 2023."
date: 2023-10-11T08:01:00-05:00
author: "Preethika Kiruveedula"
githubname: preethikakiru
categories: ["Office add in developer community call"]
images:
- images/Session-Promo-October-2023.jpg
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/c3aLpz3VEb4
draft: false
---

# Office Add-ins developer platform community call - October 11, 2023

## This month's agenda and presenters

The call was hosted by [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a148), Product Manager, Microsoft.

* **Top 5 AppSource Validation Errors June - August 2023**  Went over the top 5 validation errors in AppSource between June – August 2023 and shared how to avoid them. [Elizabeth Samuel](https://github.com/elizabethsamuel-msft), Senior Technical Writer, Microsoft.

* **Q&A.** See question and answers at end of call and in chat throughout call. [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a14), Product Manager, Microsoft.

{{< youtube c3aLpz3VEb4 >}}

## View video segments

* Introduction [00:00](https://youtu.be/c3aLpz3VEb4)
* Top 5 AppSource Validation Errors March - May 2023 [00:44](https://youtu.be/c3aLpz3VEb4?t=44)
* Q&A [08:38](https://youtu.be/c3aLpz3VEb4?t=517)
* Closing [11:23](https://youtu.be/c3aLpz3VEb4?t=683)


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
* [Next community call](https://aka.ms/officeaddinscommunitycall) on November 8th at 8:00 AM Pacific Time.

## Q&A (Question & Answers)

**We are currently working on a proof of concept to migrate (parts of) an existing COM add-in to Office.js. We make extensive use of a task pane that provides the user with ways to interact with the document. In Office Online, when the user clicks on a button in our task pane, the focus from the document is lost. The user needs to manually click into the document to continue working. Is there anyway to pass the focus back from the task pane to the document?**

Developers could try .select() of the object they operate. For example, rance.select(Word.SelectionMode.end) could help to switch the focus back to the end of the range. For more details, please visit: [Word.Range class - Office Add-ins | Microsoft Learn](https://learn.microsoft.com/en-us/javascript/api/word/word.range?view=word-js-preview) 

**Is improving Office.js performance a priority? Event handlers and interations with content controls can be quite slow, especially at scale. When can we expect improvements in these areas?**

We are working on some enhancements for content control performance. However, for this specific ask, we need to understand what specific performance issue here is. eg. What kind of interactions need to be improved. [https://github.com/OfficeDev/office-js](https://github.com/OfficeDev/office-js)




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
* [Next community call – November 8th at 08:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}
