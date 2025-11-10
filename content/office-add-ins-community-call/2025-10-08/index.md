---
title: "Office Add-ins developer platform community call – October 8, 2025"
summary: "Topics include: Inline images update for Outlook by Arpit Sangwan. Call hosted by David Chesnut, Technical writer at Microsoft. Recorded on October 8, 2025."
date: 2025-10-08T07:00:00-05:00
author: "David Chesnut"
githubname: davidchesnut
categories: ["Office add in developer community call"]
images:
- images/office-add-ins-community-call-2025-10-08.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/z-vYEb4N2go
draft: false
---

# Office Add-ins developer platform community call - October 8, 2025

## This month's agenda and presenters

* **Changes to inline image representation in Outlook on the web and new Outlook for Windows** Arpit Sangwan, Software Engineer at Microsoft.

{{< youtube z-vYEb4N2go >}}

## View video segments

* Introduction [00:00]( https://youtu.be/z-vYEb4N2go?t=0)
* Word API update [01:27]( https://youtu.be/z-vYEb4N2go?t=86)
* Q&A [08:49]( https://youtu.be/z-vYEb4N2go?t=529)
* Documentation updates [09:37]( https://youtu.be/z-vYEb4N2go?t=577)
* Resources [10:43]( https://youtu.be/z-vYEb4N2go?t=643)

## Resources related to this blog's content

Changes to inline image representation in Outlook
* [Changes to HTML for inline image representation in Outlook | Microsoft 365 Developer Blog​](https://devblogs.microsoft.com/microsoft365dev/changes-to-inline-images-in-outlook/). Stay informed about known issues affecting Office Add-ins.

Documentation updates
**General** 
- [Office Add-ins known issues](https://learn.microsoft.com/office/dev/add-ins/resources/resources-office-add-in-known-issues)

**Developer experience**
- [Persist add-in state and settings: Storage partitioning](https://learn.microsoft.com/office/dev/add-ins/develop/persisting-add-in-state-and-settings#storage-partitioning). Learn how to store private data in partitioned localStorage.
- [Best practices for add-in commands on the ribbon](https://learn.microsoft.com/office/dev/add-ins/design/add-in-commands#best-practices-for-add-in-commands-on-the-ribbon). Familiarize yourself with best practices for configuring add-in commands on the ribbon.

**Excel**
- [Excel JavaScript API 1.20](https://learn.microsoft.com/javascript/api/requirement-sets/excel/excel-api-1-20-requirement-set). Try out Excel 1.20 APIs to implement [undo support](https://devblogs.microsoft.com/microsoft365dev/excel-announces-undo-support-for-3rd-party-add-ins/) and controls to show and hide custom functions in Excel AutoComplete.
- [Excel JavaScript preview APIs](https://learn.microsoft.com/javascript/api/requirement-sets/excel/excel-preview-apis). Test Excel APIs that are currently in preview.

**Nested app authentication (NAA) and legacy token deprecation**
- [Nested app authentication and Outlook legacy tokens deprecation FAQ](https://learn.microsoft.com/office/dev/add-ins/outlook/faq-nested-app-auth-outlook-legacy-tokens). Familiarize yourself with the timeline for turning off legacy Exchange tokens and learn how to prepare for this change.

**Outlook**
- [Changes to inline image representation in Outlook on the web and new Outlook on Windows](https://devblogs.microsoft.com/microsoft365dev/changes-to-inline-images-in-outlook/). Learn about the update about inline image representation in the HTML body of emails in Outlook on the web and the
new Outlook on Windows, so that you can update your add-in's parsing logic if needed.

**PowerPoint**
- [PowerPoint JavaScript preview APIs](https://learn.microsoft.com/javascript/api/requirement-sets/powerpoint/powerpoint-preview-apis). Test PowerPoint APIs that are currently in preview.

**Word**
- [Word JavaScript API desktop-only requirement set 1.3](https://learn.microsoft.com/javascript/api/requirement-sets/word/word-api-desktop-1.3-requirement-set). Implement the Word desktop-only 1.3 APIs today.
- [Word JavaScript preview APIs](https://learn.microsoft.com/javascript/api/requirement-sets/word/word-preview-apis). Test Word APIs that are currently in preview.

## Q&A (Question & Answers)

Note that there are still some questions we are tracking down answers for and we will post them here soon, or follow up on the next community call during the Q&A session.

**Is there any updated on the ability for Smart Alerts to be supported in Outlook mobile?**

It's something that's on our radar and we expect work on this to start soon. It's a large, complex piece of work on Outlook mobile, so we do not have a definitive ETA yet. But the work is in progress to enable Smart Alerts on Outlook Mobile.

**The item change event in Outlook works in classic but on OWA and new Outlook it doesn't fire consistently. For details, see https://learn.microsoft.com/en-us/answers/questions/5537293/itemchanged-event-not-triggered-sometimes-on-chang?comment=answer-12261379&page=1#comment-2249453 and  https://github.com/OfficeDev/office-js/issues/6101 **

We have someone looking into this and we'll share more updates on the GitHub issue once we are able to reproduce the problem.

**What is the best place to ask about updates on issues/feature requests (I have the office bug#)?**

If there is a bug with Office.js APIs or Office Add-ins, please create an issue at [https://github.com/OfficeDev/Office-js](https://github.com/OfficeDev/Office-js).

**events around named items in Excel. The Excel-specific beta version of office.js has support for events around named items in Excel (see https://appsforoffice.microsoft.com/lib/beta/hosted/excel.js) for years, but it has not been added into the office.js build. Is there a specific reason?**

We looked into this and decided we'll work to include them in the next Excel Requirement set (likely 1.21). Thanks for bringing this to our attention!

## Call to action

* Join the [next community call](https://aka.ms/officeaddinscommunitycall) on November 12th at 7:00 AM Pacific Time.

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
* [Microsoft 365 Platform Community on YouTube](https://aka.ms/community/videos)
* [Microsoft 365 Platform Community](https://aka.ms/community/home)
* [Link to all Microsoft Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions for next community call](https://aka.ms/officeaddinsform)
* [Next community call – December 11th at 07:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}
