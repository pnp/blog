---
title: "Office Add-ins developer platform community call – May 10, 2023"
summary: "Topics include: Call hosted by Preethika Kiruveedula, Product Manager at Microsoft. Recorded on May 10, 2023."
date: 2023-05-10T08:01:00-05:00
author: "Preethika Kiruveedula"
githubname: preethikakiru
categories: ["Office add in developer community call"]
images:
- images/Session-Promo-May-2023.jpg
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/yvJ8n6GaO2s
draft: false
---

# Office Add-ins developer platform community call - May 10, 2023

## This month's agenda and presenters

The call was hosted by [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a148), Product Manager, Microsoft.

* **Office Add-in Developer Experience Survey.** Survey requesting developer input. [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a14), Product Manager, Microsoft.

* **Q&A.** See question and answers at end of call and in chat throughout call. [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a14), Product Manager, Microsoft.

{{< youtube P5DolLyE3E8 >}}

## View video segments

* Introduction [00:00](https://youtu.be/P5DolLyE3E8?t=0)
* Office Add-in Developer Experience Survey [00:53](https://youtu.be/P5DolLyE3E8?t=53)
* Q&A [01:47](https://youtu.be/P5DolLyE3E8?t=107)
* Resources [06:40](https://youtu.be/P5DolLyE3E8?t=400)
* Closing [08:28](https://youtu.be/P5DolLyE3E8?t=508)

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
* [Next community call](https://aka.ms/officeaddinscommunitycall) on June 14th at 8:00 AM Pacific Time.
* Please complete the [Office add-in developing experience survey](https://forms.office.com/r/wmzCgccbPa).

## Q&A (Question & Answers)

**In my Office Addin for PowerPoint I would like to provide a library of slides and custom shapes that the user can insert in the presentation through functions in the Addin. What would be the best solution for storing these slides and custom shapes after deployment to a wide group of users? Considering both response time and that I would like to be able to continuously update the content (the shapes and slides).**

Methods to store slides can be various. It quite depends on developers' choice. It could be sharepoint or users' own document library system. It would be great if you give us more context about what your goal is. For example, how does user want to store their shapes. By saying continuously update the content, does it mean update the content in the library or in ppt file? It would be great if you could resubmit this question with the answers to this question or answer in the chat etc. so we can find the best solution.

**The APIs for PowerPoint are quite limited. Is there a time plan for when there will be APIs to allow working closed with graphical shapes and text frames? Specifically being able to work with charts, tables, wider range of formatting for text frames, freeform shapes, adjustments points etc.**

Thanks for the question. Currently there is no plan to support these in short term. That being said we would like to continue hearing your feedback and user scenarios, so it would be great if you could submit a request here [m365dev-suggestions](https://aka.ms/m365dev-suggestions).

**I have been looking for a way to do a simple copy/paste of shapes in PowerPoint. The closest I could find was the setSelectedDataAsync and getSelectedDataAsync with CoercionType svg, but it is not really the same. Is there a better option available or any forecast when there might be something better available?**

Currently, we don't have a direct way to do this. You should take a look at Shape related APIs to see if you could read an existing Shape and its properties, andthen create a new Shape with those properties.

**I'm not able to find the PowerPoint files of previous calls when I go to the community blog. I know I was able to find it before can you inform where to find and download the ppt files? Thanks!**

Our blog was recently refactored to no longer post the powerpoint deck from the monthly call, but we do have a youtube video link in every blog which goes over the content of the call.

**I am looking at developing an add-in for Powerpoint. As the task pane and content add-in have different functions, are we able to essentially combine them into one add-in for the user? Or are there any issues with having two types of add-ins, with one add-in drawing information from the other? Would also like to know if there are any restrictions or security issues from developing the add-in this way.**

It is not currently possible to develop a taskpane and content add-in in one add-in project. If you would like to submit a feature request with more information about your specific scenario go here [m365dev-suggestions](https://aka.ms/m365dev-suggestions).

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
* [Microsoft 365 Platform Community](https://aka.ms/community/home)
* [Link to all Microsoft Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions for next community call](https://aka.ms/officeaddinsform)
* [Next community call – June 14th at 08:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}
