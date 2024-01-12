---
title: "Office Add-ins developer platform community call – December 14, 2022"
summary: "Topics include: Marketplace leads for Office plugins are now becoming available in the Referrals Workspace: consent to access valuable leads and metrics by Sudha Padmanabhan, Add-in Auto Open for Word and Excel: requirements gathering for additional auto launch/open capabilities by Yun Wang, Top 5 AppSource Validation Errors hit by Office Add-ins' submissions: tips to expedite marketplace certification by Elizabeth Samuel. and 4 topics formally addressed in this month’s Q&A, other topics addressed in chat throughout the call. The call was hosted by Preethika Kiruveedula. Recorded on December 14, 2022."
date: 2022-12-14T08:01:00-05:00
author: "Preethika Kiruveedula"
githubname: preethikakiru
categories: ["Office Add-in developer community call"]
images:
- images/Session-Promo-Dec-2022.jpg
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/oaYIy8kdVRU
draft: false
---

# Office Add-ins developer platform community call - December 14, 2022

## This month's agenda and presenters

The call was hosted by [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a148), Product Manager, Microsoft.

* **Marketplace leads for Office plugins are now becoming available in the Referrals Workspace.** [Sudha Padmanabhan](https://www.linkedin.com/in/sudha-padmanabhan-29832a70/), Senior Product Manager, Microsoft.
* **Add-in Auto Open for Word and Excel.** [Yun Wang](https://www.linkedin.com/in/wang-yun-99370463/?originalSubdomain=cn), Principal Product Manager, Microsoft.
* **Top 5 AppSource Validation Errors hit by Office Add-ins' submissions.** [ELizabeth Samuel](https://github.com/elizabethsamuel-msft), Senior Technical Writer, Microsoft.
* **Q&A.** See question and answers at end of call and in chat throughout call. [Preethika Kiruveedula](www.linkedin.com/in/preethika-kiruveedula-529b7a14), Product Manager, Microsoft.

{{< youtube oaYIy8kdVRU >}}

## View video segments

* Marketplace leads for Office plugins are now becoming available in the Referrals Workspace [00:41](https://youtu.be/oaYIy8kdVRU?t=41)
* Add-in Auto Open for Word and Excel [05:02](https://youtu.be/oaYIy8kdVRU?t=302)
* Top 5 AppSource Validation Errors hit by Office Add-ins' submissions [17:44](https://youtu.be/oaYIy8kdVRU?t=1064)
* Q&A [28:00](https://youtu.be/oaYIy8kdVRU?t=1680)

## Topic summaries

* **Marketplace leads for Office plugins are now becoming available in the Referrals Workspace.** In June 2022, Microsoft started delivering office plugin (Add-in) leads into Partner center – your one stop shop for leads! Information and filtering include:  Company name, customer name, title, address, validated e-mail and phone. In January 2023, the group is rolling out Lead enrichment – lead rating (probability), # interactions with Microsoft, events attended and product usage metrics. You are invited to consent to get access to these leads.
* **Add-in Auto Open for Word and Excel.** Recap existing behavior for auto open – capabilities, limitations, user or administrator control, then evaluate partner suggested auto open user requirements. Level set on definition for auto launch/auto open vs auto install with auto open capabilities. Please complete the survey to confirm requirements, modify or add new requirements that would address your auto open and auto install needs.
* **Top 5 AppSource Validation Errors hit by Office Add-ins' submissions.** Wouldn’t it be nice if your add-in sailed right through the Microsoft AppSource certification process? Learn about the top 5 certification show-stoppers - undisclosed charges, unclear first run experience, missing links for sign in/sign out/sign up, mismatch between provider and publisher name, inadequate testing instructions.  See the key marketplace certification policies related to Office Add-ins validations in this session.

## Call to action

* Please evaluate the review the Excel Add-in Auto install launch function and [provide feedback](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxFri8-).
* Please provide feedback in this survey  [Consent - Office add-in Leads](https://aka.ms/OfficeLeadsConsent)
* If you have any suggestions that you submitted to the current forum on Tech Communities, please @lindalu-msft in the comments so I can prioritize triaging your submission!
* If you are interested in participating in a future User Research session about customer support channels, please let me know. Email me lindalu@microsoft with "Office Add-ins Developer User Research" as email subject.
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
**When using SSO, the samples use a .ENV file to contain the secret. Are there any links on where to put the secret when you release to production?**

We recommend you use something like Azure Key Vault for securely storing and accessing secrets on your production app service.
[Azure Key Vault Overview - Azure Key Vault | Microsoft Learn](https://learn.microsoft.com/en-us/azure/key-vault/general/overview)


**We are Scribe an email signature management software. We developed an Outlook Addin with an event base integration to insert the signature on the "OnNewMessageCompose" event. But, we have users that have aliases and when they change the "From" address we would like to be able to re-trigger the Addin script to insert the alias signature. Is there a way to do that? If not, is there a possibility to implement a new event for that in the future?**

This feature is actually going to be delivered in the near future, stay tuned for an update on the release date.

**Can we add custom tab in outlook 365 web app and can it be viewable in Notes section?**

We do support Custom Tabs, but not in the Notes section. Add-ins are currently supported in Mail and Calendar items.


**Can you automatically open an add-in in Outlook 365??**

In Outlook we do not currently support automatically opening a task pane. It's a user driven experience and is accomplished via pinning taskpane. [Implement a pinnable task pane in an Outlook add-in - Office Add-ins | Microsoft Learn](https://learn.microsoft.com/en-us/office/dev/add-ins/outlook/pinnable-taskpane?tabs=xmlmanifest)


**Is the auto open feature is available also for the IPAD platform?**

I don't think office for IPAD is supported for the current autoopen feature. Office for web does support this. Please go to this link for further information.  [Automatically open a task pane with a document - Office Add-ins | Microsoft Learn](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform)


**I can see that the Graph API is available https://graph.microsoft.com/v1.0/me/MailFolders/notes/messages, how can we add our add-in or any other UI so that the Notes can be accessed? Can we pin the task pane and see it in the Notes section?**

Unfortunately, again, add-ins are not supported in Notes. Please add a new feature request to our team so we can consider supporting it in the future. [Microsoft 365 Developer Platform - Microsoft Community Hub](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform)

**How would trust be configured, i.e. to prohibit auto-loading arbitrary or malicious add-ins? Or will this work only for add-ins already installed?**

Great question. It depends on the different use cases. In many cases, we still need to have the user's consent to, eg. share a file to others. However, there could be other cases that consent 'might' be skipped. E.g. A user tries to install a trusted application bundled with add-in.

**For Js add-ins, we are facing problems with the cache. When new manifests are pushed it is not refreshing well on all machines. Is there a way to do that in code or the settings? Due to this it breaks and throws errors.**

Theoretically, any update made to the add-in's manifest should be updated to all users.Can you please share more details on what types of updates your are doing into the manifest? Also is this for admin deployed add-ins or add-ins installed from the store? Also is this for Word, Excel, PPT, or Outlook? If you can share more details that would be great. Please post this issue with all the details here so we can follow up: [Issues · OfficeDev/office-js](https://github.com/OfficeDev/office-js/issues)

**How do we test SSO from the Office UI?**

Typically you just sign in to Office, then when your add-in calls getAccessToken() it should get the token from Office. Is there something specific you are trying to test in your scenario? Although note it can get more complicated, for example if you are testing fallback, then you need to modify your code to not call getAccessToken and instead call your MSAL backup auth code. If you are calling Graph APIs, you'll need to use the UI in your add-in that calls Graph.

**We use SSO, but our clients provide their own IDP URL.  Is there a way to allow SSO without putting all of the IDP urls in the manifest AppDomain sections?**

Unfortunately there is not. They need to get into the appDomains.



## Resources related to to this blog's content

* **Feedback Repo**
    * [Issues – OfficeDev/Office-js](https://github.com/OfficeDev/office-js/issues)
  **Grammarly Add-in**
    * [Grammarly for Microsoft Word and Outlook](https://www.grammarly.com/office-addin)
  **Community Panels– discussion and feedback**
    * [Outlook add-ins](https://ux.microsoft.com/Panel/OutlookAddinDeveloper)
    * [Excel add-ins](https://ux.microsoft.com/Panel/ExcelAddinDeveloper)
    * [Word add-ins](https://ux.microsoft.com/Panel/WordAddinDeveloper)
    * [PowerPoint add-ins](https://ux.microsoft.com/Panel/PowerPointAddinDeveloper)
    * [Samples and Docs](https://ux.microsoft.com/Panel/OfficeAddinImproveSamplesDocs)

## General Resources

* [Documentation](https://aka.ms/office-add-ins-docs)
* Quick Starts: [Outlook](https://learn.microsoft.com/office/dev/add-ins/quickstarts/outlook-quickstart),[Excel](https://learn.microsoft.com/office/dev/add-ins/quickstarts/excel-quickstart-jquery),[Word](https://learn.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart),[PowerPoint](https://learn.microsoft.com/office/dev/add-ins/quickstarts/powerpoint-quickstart)
* [Script Lab](https://aka.ms/getscriptlab)
* [Samples](https://aka.ms/officeaddinsamples)
* [Microsoft 365 Developer Program](https://aka.ms/M365devprogram)
* [Office Scripts](aka.ms/office-scripts-docs)
* [Technical Questions about Office add-ins](https://aka.ms/office-addins-dev-questions)
* [Stack Overflow Questions](https://stackoverflow.com). Use keywords: (office-js, outlook-web-addins, office-scripts)
* [Github(issues)](https://github.com/OfficeDev/office-js )
* [Microsoft Tech Community – Submit Feature Requests](https://aka.ms/m365dev-suggestions)
* [Microsoft 365 Developer Program](https://aka.ms/M365devprogram)

## Stay connected

* Follow our blog posts at [Microsoft 365 and Power Platform Community Blog](https://aka.ms/m365pnp/blog)
* [Follow @microsoft365dev on Twitter](https://twitter.com/microsoft365dev)
* [Microsoft 365 Platform Community on YouTube](https://aka.ms/m365/videos)
* Invites to all [Microsoft 365 Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions about Office Add-ins development](https://aka.ms/officeaddinsform) for our next community call
* [Join us for our next community call](https://aka.ms/officeaddinscommunitycall) on January 11th at 8:00 AM PT

{{< attachments >}}{{< /attachments >}}
