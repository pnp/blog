---
title: "Office Add-ins developer platform community call – February 8th, 2023"
summary: "Topics include: Create a spreadsheet from your website by David Chesnut, Upcoming Preview Word APIs by Yun Wang, and Add-in Support for new Outlook by Nikita Mitta and Juan Balmori. The call was hosted by Preethika Kiruveedula. Recorded on February 8, 2023."
date: 2023-02-08T08:01:00-05:00
author: "Preethika Kiruveedula"
githubname: preethikakiru
categories: ["Office Add-ins community call"]
images:
- images/Session-Promo-Feb-2023.jpg
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/bUcpzn28VKs
draft: true
---

# Office Add-ins developer platform community call - February 8, 2023

## This month's agenda and presenters

The call was hosted by [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a148), Product Manager, Microsoft.

* **Demo on how to create a spreadsheet from your website .** [David Chesnut](https://twitter.com/davidchesnut), Senior Technical Writer, Microsoft. 
* **Update on upcoming Preview Word APIs.** [Yun Wang](https://www.linkedin.com/in/wang-yun-99370463/?originalSubdomain=cn), Principal Product Manager, Microsoft. 
* **Add-in Support for new Outlook** Nikita Mittal, Senior Product Manager, Microsoft and [Juan Balmori](http://twitter.com/juaneloBalmori), Principal Product Manager, Microsoft. 
* **Q&A.** See question and answers at end of call and in chat throughout call. [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a14), Product Manager, Microsoft.

{{< youtube bUcpzn28VKs >}}

## View video segments

* Introduction [00:00](https://youtu.be/MfEX1zdeQ3U?t=00)
* Demo - Create a spreadsheet from your website [00:53](https://youtu.be/bUcpzn28VKs?t=53)
* Upcoming Preview Word APIs coming in March 2023 [14:53](https://youtu.be/bUcpzn28VKs?t=883)
* Add-in Support for new Outlook [27:33](https://youtu.be/bUcpzn28VKs?t=1653)
* Q&A [40:38](https://youtu.be/bUcpzn28VKs?t=2438)
* Resources [41:45](https://youtu.be/bUcpzn28VKs?t=2505)
* Closing [42:35](https://youtu.be/bUcpzn28VKs?t=2555)

## Topic summaries

* **Create a spreadsheet from your website.** Walk through the tutorial document, solution architecture, and code sample for a solution that automatically generates a new spreadsheet with the requested data (data in table on a web page), uploads it to the initiator’s OneDrive, and opens it in Excel on a new browser tab. The action is initiated with a single click. Additionally, the pattern embeds your own Office Add-in inside the spreadsheet.      
* **Upcoming Preview Word APIs - March 2023.** Quick briefing on Word APIs that will Preview in March.  New/updated APIs include new insertFileFromBase64 API (insert content from source document into destination document), updated Style API (retrieve, show and insert other document’s styles in current document), Save / Close API (save/close new/existing documents), Fields API (more Field properties for selected types), and Content Control Events API (adding enter and exit events). Target mid-year GA.
* **Add-in Support for new Outlook.** Overview on new Outlook that’s available for Windows today and all platforms in time. What does this mean for developers? New Outlook is coming, web add-ins are going to be the main extensibility option for new Outlook, and the Microsoft team is super committed to add the richness needed to enable and support moving your existing COM add-in investments to web add-ins.

## Call to action

*•	Call to Action for Outlook Add-in Mobile Developers – provide feedback on Outlook add-in scenarios you are trying to support [Outlook Mobile Add-in Developer Survey](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRw5b9d2wAdRLj9NKAu1xfddUM1pW).
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
* [Join the next Office Add-ins community call](https://aka.ms/officeaddinscommunitycall) on March 8th at 8:00 AM Pacific Time.
* Please complete the [Office add-in developing experience survey](https://forms.office.com/r/wmzCgccbPa)


## Q&A (Question & Answers)

**Are there any plans to allow for add-ins to have limited functionality offline modes?**

We have a sample at https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/Excel.OfflineStorageAddin, that shows some techniques for working offline. However, it would be good to know what additional features you may need for your scenario. Please let us know more at https://aka.ms/m365dev-suggestions.

**Where can we find a roadmap regarding the future of Office Add-Ins using Office.JS?**

We are improving our processes, including adding API releases to the [Microsoft 365 Roadmap (MSRRP)](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=2&filters=). Periodically check this page for feature updates.

**Can an API function know what user uses the add-In to be able to retrieve the right information?**

Yes, the sample doesn't use auth, but you should set up auth on the Azure function so that it would have the user name. The [Azure Functions](https://learn.microsoft.com/en-us/azure/azure-functions/) documentation should have info on how to set this up. You can configure the parameters you pass to the function to pass any values you need.

**Any way to name the new workbook? (or Save As equivalent)?**

Yes, the uploadFile function in authPopup.js takes a name parameter. You can use any name you prefer.

**I am trying to work with shapes on an PowerPoint Web Add-in, on Visual Studio, using the PowerPoint JavaScript API, but I am not able to use the features shown on the Office Add-ins community call from August 2021. I get it to work on Script Lab, but not on Visual Studio (e.g. shape.textFrame.textRange.font.color = "purple";). How can I get help?**

Make sure that the template is referencing the CDN for Office.js. If you need further guidance, [open an issue on GitHub](https://github.com/OfficeDev/office-js/issues/new/choose). 

**Where can I get help/support to work out the Graph authentication for add-ins? I have not had any success to make the add-in and Graph authentication setup.**

Reach out to the [identity team](https://learn.microsoft.com/en-us/azure/active-directory/develop/developer-support-help-options) for further help.

**Will the other types than richText or ContentControls be supported in the next preview as well?**

PlainText CC will be supported in the preview as well.

**Are you going to retire the desktop Outlook application? Will a new Outlook be included to the Office package instead?**

This hasn't been determined yet.

**When will the support of shared mailboxes be made public? It's been in preview for months now.**

Support for shared mailbox scenarios will be made available mid-year.

**COM/VSTO add-ins does that also include VBA?**

Yes. COM and VSTO add-ins that include VBA will not be supported in the new Outlook on Windows.

**What is the likelihood/timing for a "New Excel" like the new Outlook? (Where COM/VSTO is not an option.)**

There are currently no plans to implement this for other Office applications other than Outlook.

**We are loving last month's announcement of the new Smart Alerts for Outlook!  Especially that they are allowed into AppSource (since on-send add-ins are not allowed). One of our financial clients would like an HTML form to be displayed before composing a new email, where the user must select from a pre-defined list of acceptable banks that they are allowed to email; the new Smart Alerts can help us to accomplish this, but how can we present an HTML input form with the list of banks to the user?  The Outlook compose event does not appear to allow us to present a form when first composing…**

You can use event-based activation to evaluate the preconditions of a task pane launch, add a notification message to determine if those checks pass, and instruct the user to click the task pane ribbon button. Auto-launching the task pane still isn't supported, but it can be pinned.

**How can I contribute the feature of encryption/decryption of messages?**

We would love to hear about your scenario for using encryption in the new Outlook on Windows. Please share your scenario for this feature by completing the form at [DevNewOutlook](https://aka.ms/DevNewOutlook).

**Was the DevNewOutlook just for VSO to new WebBased?**
Yes, [DevNewOutlook](https://aka.ms/DevNewOutlook) is a form where you can share your current VSTO and COM add-in solutions, so that we can further understand your scenario.

**PowerPoint.setSelectedSlides(slideIds) is throwing error as general exceptions.**

We're sorry to hear you're running into errors. Please [open an issue on GitHub](https://github.com/OfficeDev/office-js/issues/new/choose), so that we can troubleshoot this issue with you.



## Resources related to to this blog's content

* **Create a spreadsheet from your website**
    * [Documentation – Create an Excel spreadsheet from your web page, populate it with data, and embed your Office Add-in](https://learn.microsoft.com/office/dev/add-ins/excel/pnp-open-in-excel)
    * [Sample - Create a spreadsheet from your web site, populate it with data, and embed your Excel add-in](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/excel-create-worksheet-from-web-site)
    * [Identity Samples - Vanilla JavaScript single-page application using MSAL.js to authenticate users to call Microsoft Graph](https://github.com/Azure-Samples/ms-identity-javascript-tutorial/blob/main/2-Authorization-I/1-call-graph/README.md)
    * [Survey - Office Add-ins code sample survey](aka.ms/officesamplessurvey)
  **Upcoming Preview Word APIs - March 2023**
    * [Survey - Future Word API candidates](aka.ms/WordApiNext)
  **Add-in Support for new Outlook**
    *	[Documentation - Getting started with the new Outlook for Windows](aka.ms/AAjkfje)
    * [Issues – office-js issues](https://github.com/officedev/office-js/issues)
    * [Survey - Outlook Add-ins survey](aka.ms/DevNewOutlook)
    * [Documentation - Develop Outlook add-ins for the new Outlook on Windows (preview)](aka.ms/OutlookCOM2WebStatus)

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

* Follow our blog posts at [Microsoft 365 and Power Platform Community Blog](https://pnp.github.io/blog/)
* [Follow @microsoft365dev on Twitter](https://twitter.com/microsoft365dev)
* [Microsoft 365 Platform Community on YouTube](https://aka.ms/m365/videos)
* Invites to all [Microsoft 365 Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions about Office Add-ins development](https://aka.ms/officeaddinsform) for our next community call
* [Join us for our next community call](https://aka.ms/officeaddinscommunitycall) on March 8th at 8:00 AM PT

{{< attachments >}}
