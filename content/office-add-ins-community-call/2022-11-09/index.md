---
title: "Office Add-ins developer platform community call – November 9, 2022"
summary: "This month's community call topics include Working with Partial Documents in PowerPoint (Large files are broken up for faster downloading) by John Teichman - Principal Product Manager(Microsoft) and Onur Onder - Senior Software Engineer (Microsoft), Content control enhancements in Word Online (what’s new and in the works) by Maja Damjanić - Senior Product Manager (Microsoft) and Search Bar for Office Add-ins (Help users find their add-ins) by Adrian Wu: Senior Product Manager (Microsoft), and Q&A at end of call and in chat throughout call. The call was hosted by Preethika Kiruveedula (Microsoft)."
date: 2022-11-09T08:01:00-05:00
author: "Preethika Kiruveedula"
githubname: preethikakiru
categories: ["Office Add-in developer community call"]
images:
- images/Session-Promo-Nov-2022.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/6hC4YJLlfi0
draft: false
---

# Office Add-ins developer platform community call - November 9, 2022

## This month's agenda and presenters

The call was hosted by [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a148), Product Manager, Microsoft.

* **Working with Partial Documents in PowerPoint.** [John Teichman](https://www.linkedin.com/in/john-teichman-04b3581/), Principal Product Manager, Microsoft [Onur Onder](https://www.linkedin.com/in/onur-onder-5b315311/), Senior Software Engineer, Microsoft.
* **Content control enhancements in Word Online.** [Maja Damjanić](https://www.linkedin.com/in/majadamjanic/), Senior Product Manager, Microsoft. 
* **Search Bar for Office Add-ins.** [Adrian Wu](https://www.linkedin.com/in/adrian-tsung-han-wu-53462582/), Senior Product Manager, Microsoft.
* **Q&A.** See question and answers at end of call and in chat throughout call. [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a14), Product Manager, Microsoft.

{{< youtube 6hC4YJLlfi0 >}}

## View video segments

* Update - Working with Partial Documents in PowerPoint [00:47](https://youtu.be/6hC4YJLlfi0?t=472)
* Update - Content control enhancements in Word Online [10:18](https://youtu.be/6hC4YJLlfi0?t=618)
* Announcing - Search Bar for Office Add-ins [18:31](https://youtu.be/6hC4YJLlfi0?t=1111)
* Q&A [23:13](https://youtu.be/6hC4YJLlfi0?t=1393)

## Topic summaries

* **Work with partial documents in PowerPoint.** Large files laden with graphics and videos are often broken up for faster download. This presentation explains capabilities and implications for add-ins developers working with partial documents including error handling, impacted APIs, and office.js API calls that may return errors. In Preview.     
* **Content control enhancements in Word Online.** This presentation covers new and upcoming enhancements to content controls in Word including those created via UI and programmatically (Word for Windows) and those created with Rich Text in Office.js (Word Online). What’s new and in the pipeline.   
* **Search Bar for Office Add-ins.** Learn how users can use TellMe to search for installed add-ins from the search box in Word, Excel and PowerPoint documents. Supports user installed add-ins and admin deployed add-ins.

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
* [Join the next Office Add-ins community call](https://aka.ms/officeaddinscommunitycall) on December 14th at 8:00 AM Pacific Time.
* Please complete the [Office add-in developing experience survey](https://forms.office.com/r/wmzCgccbPa)

## Q&A (Question & Answers)
**We'd also love an update on [GitHub issue](https://github.com/OfficeDev/office-js/issues/2955) - Outlook OWA UI has been updated for some users and there is no way for them to open add-ins in compose mode. Major issue.**

We've assigned the issue to the Outlook team for further investigation. 

**Hi, anyone working on Outlook add-in - SSO with .Net Core - adding Authentication in Middleware. and adding redirect URI? This works in Outlook on Windows but fails in Outlook on the web.**

We usually debug SSO issues with the browser dev tools. If you haven't already, please submit a [GitHub issue](https://github.com/OfficeDev/office-js/issues), so that we can assist you further.

**Any one working on Excel add-in pivot table function and connect with external data source mainly cube in pivot table inside add-in?**

If you're experiencing issues with developing an Excel add-in, please submit a [GitHub issue](https://github.com/OfficeDev/office-js/issues), so that we can assist you further.

**For PowerPoint, it would be interesting if the app asked the user if they wanted to compress the embedded video. I have done this on my decks, but it is kind of buried for the average user.**

We will pass on this feedback to the team.

**Why rich text for Word Online content controls? Plain text is so much more useful for integration because there's no formatting jargon**

We are planning to roll out support for Plain Text content controls editing soon.

**To be clear, we are still not able to create the Content Controls in Word Online?** 

That's correct. Creating content controls in Word on the web still isn't possible. They need to be created with via the Word desktop client or the JS API.

**Has anyone had challenges with Outlook Add-ins when using the "Microsoft 365 Features - Shared calendar improvements" setting in Outlook Windows Desktop? Our Outlook add-in sets extended properties with Graph (public and private) for meetings on shared/delegate calendars.When the setting is on, the meeting won't send. When we turn it off, everything works as expected.**

We're sorry to hear you're experiencing challenges with developing your Outlook add-in. If you haven't already, please submit a [GitHub issue](https://github.com/OfficeDev/office-js/issues), so that we can assist you.

**Would the search work only by the add-in name, or use some additional descriptions? In other words, how do you match the Office Add-in to the user search phrase in the new search functionality?**

We continuously improve the matching logic, but the most effective way today would be to match the add-in titles directly.


**How about data-bound content controls?**

This is one of the things we are considering. We would love to hear more of your use case via [https://aka.ms/WordAPI](https://aka.ms/WordAPI).


## Additional Resources

* **Working with partial documents in PowerPoint**
    * Documentation - [Work with partial documents](https://learn.microsoft.com/office/vba/powerpoint/how-to/work-with-partial-documents)
    * Documentation - [Presentation.IsFullyDownloaded property (PowerPoint)](https://learn.microsoft.com/office/vba/api/powerpoint.presentation.isfullydownloaded)
    * Documentation - [getFileAsync(fileType, options, callback)](https://learn.microsoft.com/javascript/api/office/office.document?view=common-js-preview#office-office-document-getfileasync-member(1))
    * Mail Feedback - [PowerPoint Partial Documents Feedback](pptpartialdocsfdbk@microsoft.com)
* **Content control enhancements in Word Online**
    * Survey - [Let us know what you'd want to see next in this area](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR6n1U-1y30dHploxSapt6sxUMEdRQUMyU1kzSExENUI1WTIzN1k1WlMxQy4u)
* **Search Bar for Office Add-ins**
   * Documentation - [Automatically open a task pane when an add-in is installed](https://learn.microsoft.com/office/dev/add-ins/develop/automatically-open-on-installation#configure-default-task-pane)

    

## Stay connected

* Follow our blog posts at [Microsoft 365 platform community blog](https://aka.ms/m365pnp/blog)
* [Follow @microsoft365dev on Twitter](https://twitter.com/microsoft365dev)
* [Microsoft 365 Platform Community on YouTube](https://aka.ms/m365/videos)
* Invites to all [Microsoft 365 Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions about Office Add-ins development](https://aka.ms/officeaddinsform) for our next community call
* [Join us for our next community call](https://aka.ms/officeaddinscommunitycall) on December 14th at 8:00 AM PT

{{< attachments >}}
