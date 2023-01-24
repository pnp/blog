---
title: "Office Add-ins developer platform community call – January 11, 2023"
summary: "Topics include: Deploy Office Add-in that uses SSO to Azure App Service demo and walk-through new topic by David Chestnut, Feedback for Word, Excel or PowerPoint add-ins: user scenarios survey by Yun Wang, and Outlook add-in preview API prependOnSendAsync demo by Yashvardan Joshi. The call was hosted by Preethika Kiruveedula. Recorded on January 11, 2023."
date: 2023-01-11T08:01:00-05:00
author: "Preethika Kiruveedula"
githubname: preethikakiru
categories: ["Office Add-ins community call"]
images:
- images/Session-Promo-Jan-2023.jpg
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/MfEX1zdeQ3U
draft: true
---

# Office Add-ins developer platform community call - January 11, 2023

## This month's agenda and presenters

The call was hosted by [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a148), Product Manager, Microsoft.

* **Deploy Office Add-in that uses SSO to Azure App Service.** [David Chesnut](https://twitter.com/davidchesnut), Senior Technical Writer, Microsoft. 
* **Feedback for WXP (Word, Excel or PowerPoint) add-ins.** [Yun Wang](https://www.linkedin.com/in/wang-yun-99370463/?originalSubdomain=cn), Principal Product Manager, Microsoft. 
* **Outlook add-in preview API - prependOnSendAsync.** Yashvardan Joshi, Senior Product Manager, Microsoft.
* **Q&A.** See question and answers at end of call and in chat throughout call. [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a14), Product Manager, Microsoft.

{{< youtube MfEX1zdeQ3U >}}

## View video segments

* Introduction [00:00](https://youtu.be/MfEX1zdeQ3U?t=00)
* Deploy Office Add-in that uses SSO to Azure App Service [00:40](https://youtu.be/MfEX1zdeQ3U?t=40)
* Feedback for WXP (Word, Excel or PowerPoint) add-ins  [17:35](https://youtu.be/MfEX1zdeQ3U?t=1055)
* Outlook add-in preview API - prependOnSendAsync [20:10](https://youtu.be/MfEX1zdeQ3U?t=1210)
* Q&A [26:38](https://youtu.be/MfEX1zdeQ3U?t=1598)
* Resources [29:38](https://youtu.be/MfEX1zdeQ3U?t=1778)
* Closing [30:24](https://youtu.be/MfEX1zdeQ3U?t=1824)

## Topic summaries

* **Deploy Office Add-in that uses SSO to Azure App Service.** Follow the steps outlined in a recent article to create and deploy a single sign-on (SSO) Office Add-in to Microsoft Azure App Service. Create project, configure it to run SSO, app registration, install an Azure Extension in VS Code, create a new app service, update the manifest and package JSON, deploy the web app, create a new workbook in Excel, and test your new add-in.       
* **Feedback for WXP (Word, Excel or PowerPoint) add-ins.** Help us prioritize our work to make Office Add-ins better. Tell us about your user scenarios of Word, Excel, or PowerPoint add-ins. Review existing extensibility surveys on Auto install and auto launch add-ins for Word, Excel, and PowerPoint (to be done in a future call) and on Structured document content usage in Word add-ins.
* **Outlook add-in preview API - prependOnSendAsync.** What is the Prepend on-Send API? Use cases (legal statements, images), API details (prepend text in html and plain text emails and in event invites), API parameters, manifest changes (permissions), demo (show photo inserted above text in sent mail, and in meeting invite) and documentation. In Preview for Win32 presently and coming soon for MAC and Outlook for Web.

## Call to action

* Please let us know more about your user scenarios for Word, Excel, and PowerPoint add-ins so we can prioritize our work by completing our [Survey](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR5oYVeF9pExPnSjEMUhVOIdUQTY1NFU4TEFQMUxRSE1VRlVDNUhXU1AwTy4u).
* If you're interested in participating in a future User Research session about customer support channels, please let us know. Email [lindalu@microsoft.com](mailto:lindalu@microsoft.com?subject=[GitHub]%20Office%20Add-ins%20Developer%20User%20Research) with "Office Add-ins Developer User Research" as email subject.
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
* [Join the next Office Add-ins community call](https://aka.ms/officeaddinscommunitycall) on January 11th at 8:00 AM Pacific Time.


## Q&A (Question & Answers)

**Outlook Mobile (on iOS and Android) still only generally supports message read mode. When is compose mode and the on-send event going to be supported? This feature difference between the Outlook variants has been present for many years and remains a major barrier to customer adoption of our Outlook add-in. It is an [open issue in GitHub](https://github.com/OfficeDev/office-js/issues/1455).**

We currently do not have a roadmap for this feature. This feature request has been submitted to [aka.ms/m365dev-suggestions](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/support-for-addin-taskpane-activation-when-composing-messages-in/idi-p/3615686). Please go there to upvote and provide more details about your add-in and your exact requirements for compose on Mobile.

**We would like to enter our Outlook add-in into AppSource, but it is blocked because it is an on-send add-in. When will AppSource accept on-send add-ins? What is the roadmap regarding adding on-send functionality to phones (both iPhone and Android)?**

This is still not allowed. We recently shipped Smart alerts which has relatively the same functionality and is allowed in the store. For more information see [Smart Alerts Walkthrough](https://learn.microsoft.com/office/dev/add-ins/outlook/smart-alerts-onmessagesend-walkthrough?tabs=xmlmanifest). Please note that SendMode=Block is still not allowed in the store.

**What is the timeline for upcoming features in PowerPoint? There’s a lot in Excel but can’t be done in Word or PowerPoint. The developer feedback and ideas forum doesn’t get much attention. Could there be more effort in this review?**


Thank you for that feedback. There are currently a number of features currently being worked on in PowerPoint, if you have an feature requests you would like to see soon please fill out this [survey](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR5oYVeF9pExPnSjEMUhVOIdUQTY1NFU4TEFQMUxRSE1VRlVDNUhXU1AwTy4u)

**Is there a timeline for when Outlook Mobile (on iOS and Android) will support compose mode for Office add-ins, and further when the on-send event will be supported? Currently only read-mode is supported for Outlook add-ins and this has been the state for many years now, but our add-in is essentially for compliance measures to ensure all sent messages include some extra input/metadata from the sender.**

We have been getting questions on on-send support for mobile quite frequently now. This feature will be looked into once we are able to finish delivering other features that on-send would build upon. 

**Is there an API or access point where we can call how many seats have been provisioned for an Office Add-in by the 365 Administrator? Say a company has 25 seats but authorizes only 5 for my add-in - is there a way for the add-in developer to know that? Please note that we do not have a SaaS application, just an Office Store add-in.**

Still tracking down answer. 

**We just saw that PowerPoint desktop client now supports PowerPoint API1.5 with the semi-annual channel. We tried the PowerPoint web client and it still does not.  Will that be rolling out soon to keep up with desktop client?**

PowerPoint 1.5 support for PowerPoint Online web app is being rolled out, you should see it being available soon. The functionality should also work even if the supported requirement still returns 1.4 at this time.

**I am in need of information on how to list our Outlook add-in as an MSI, inside Microsoft AppSource to run in the Outlook desktop app. The Microsoft support people referred us here. Could someone please take our case and help us? Maybe an email address to contact me?**

AppSource only supports web add-ins and not COM add-ins. To distribute COM add-ins, use Azure Marketplace or any third-party digital delivery system or e-commerce solution. For guidance with publishing to Azure Marketplace, see [What is the Microsoft commercial marketplace?](https://learn.microsoft.com/en-us/azure/marketplace/overview).

**We tried the setSelectedShapes() example in Script Lab and it did select the first two shapes as advertised.  But when we modified the example to pass in an empty array, it did not unselect the shapes as the doc indicates it should (and how it works on desktop).**

This is a known bug. You can [see the issue on GitHub](https://github.com/OfficeDev/office-js/issues/3102) and track the issue there. Please provide more info if necessary.

**Does deployment of an SSO add-in work with PowerShell? When we try it through PowerShell, it fails and gives an error message. We tried it through the Exchange admin center, not from the Azure CLI.**

Deployment of an SSO add-in many not work with PowerShell under certain conditions. For example when using the Powershell cmdlet, there isn't the ability to grant admin consent which then causes an error to be thrown. 

**Is anyone aware of the Excel Range Top and Left attribute errors?**
So that we could help you further, please [open an issue on GitHub](https://github.com/OfficeDev/office-js/issues/new?assignees=&labels=&template=bug_report.md&title=). You can also follow [this topic](https://answers.microsoft.com/msoffice/forum/all/vba-in-excel-using-rangetop-rangeleft-to-get-cell/72f2276f-9d96-43c3-8e7b-c09e99a3988d) on Microsoft Community Answers forum.




## Resources related to to this blog's content

* **Deploy Office Add-in that uses SSO to Azure App Service**
    * [Documentation – Deploy a single sign-on (SSO) Office Add-in to Microsoft Azure App Service](https://learn.microsoft.com/office/dev/add-ins/publish/deploy-office-add-in-sso-to-azure)
    * [Article - Single Sign-on service for Office Add-ins rolls out in Office on the web](https://devblogs.microsoft.com/microsoft365dev/new-single-sign-on-service-for-office-add-ins-rolling-out-in-office-on-the-web/)
    * [Documentation - Enable single sign-on (SSO) in an Office Add-in](https://learn.microsoft.coms/office/dev/add-ins/develop/sso-in-office-add-ins)
    * [Documentation - Publish an (static) add-in developed with Visual Studio Code](https://learn.microsoft.com/office/dev/add-ins/publish/publish-add-in-vs-code)
    * [Documentation - Create Office Add-in projects using the Yeoman Generator](https://learn.microsoft.com/office/dev/add-ins/develop/yeoman-generator-overview)
  **Feedback for WXP (Word, Excel or PowerPoint) add-ins**
    * [Survey](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR5oYVeF9pExPnSjEMUhVOIdUQTY1NFU4TEFQMUxRSE1VRlVDNUhXU1AwTy4u)
  **Outlook add-in preview API – prependOnSendAsync**
    *	[Documentation - prependOnSendAsync(data, options, callback)](https://learn.microsoft.com/javascript/api/outlook/office.body?view=outlook-js-preview#outlook-office-body-prependonsendasync-member(1))
    * [Snippet - prepend-text-on-send.yaml](https://github.com/OfficeDev/office-js-snippets/blob/main/samples/outlook/99-preview-apis/prepend-text-on-send.yaml)
    * [Documentation - Outlook add-in API preview requirement set](aka.ms/OutlookPreviewAPI)
    * [Documentation - On-send feature for Outlook add-ins](https://learn.microsoft.com/office/dev/add-ins/outlook/outlook-on-send-addins)
    * [Documentation - Implement append-on-send in your Outlook add-in](https://learn.microsoft.com/office/dev/add-ins/outlook/append-on-send)

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

* Follow our blog posts at [Microsoft 365 platform community blog](https://pnp.github.io/blog/)
* [Follow @microsoft365dev on Twitter](https://twitter.com/microsoft365dev)
* [Microsoft 365 Platform Community on YouTube](https://aka.ms/m365/videos)
* Invites to all [Microsoft 365 Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions about Office Add-ins development](https://aka.ms/officeaddinsform) for our next community call
* [Join us for our next community call](https://aka.ms/officeaddinscommunitycall) on February 8th at 8:00 AM PT

{{< attachments >}}
