---
title: "Office Add-ins community call – July 13, 2022"
summary: "Word update, updates on Outlook Add-ins (REST decommission, Shared Folders support, Item multiselect), and on SSO samples update.  This month’s Community Spotlight recognizes Maarten van Stam.  Covered Community panels plus Q&A in chat and at end of call. "
date: 2022-07-22T08:01:00-05:00
author: "Preethika Kiruveedula"
githubname: pkiruveedula
categories: ["Office Add-in developer community call"]
images:
- images/office-add-ins-call-july-2022-recording.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://www.youtube.com/watch?v=COic6ghBWsU
draft: true
---

## Call Summary

This month's community call topics:

* **Updates on Word** – JavaScript API online-only GA features, Fields API preview, and 6-month roadmap – [Yun Wang] - Principal Product Manager (Microsoft) 
* **Updates on Outlook Add-ins** – REST decommission, Shared Folders support, and pre-beta look at Item Multi-Select capability – [Juan Balmori] - Principal Product Manager (Microsoft) | @juaneloBalmor & [Victoria Iannotti] - Software Engineer (Microsoft) 
* **SSO samples update** – SSO NodeJS sample token handling has been updated – learn what and why – [David Chesnut] - Senior Technical Writer (Microsoft) | @davidchesnut
* **Community spotlight** recognizes [Maarten van Stam](http://twitter.com/aafvstam)
* **Community panels** – Join us to share your feedback on how we can provide you with a better Office Add-ins development experience
* **Q&A** – See question and answers at end of call and in chat throughout call

The call was hosted by [David Chesnut](http://twitter.com/davidchesnut) (Microsoft) | @davidchesnut. Recorded July 13, 2022.

{{< youtube COic6ghBWsU&t >}}

## Topic summaries

* **Microsoft Word update** – specifically, Word JavaScript API online-only requirement set - GA feature areas available only for Word on the web.  Feature areas include support for footnotes and endnotes (insert, get collections, navigate and operate footnotes/endnotes), comments and track changes.  Additionally, Fields APIs (web-only Preview) to Get collections of fields, Paragraph, Range, Table and TableRow objects and Navigate fields.  Feature candidates for next GA release.  
* **Outlook Add-ins Update (REST decommission, Shared Folders support, Item Multi-Select)** – Outlook add-in news.  1) REST Decommission update - APIs impacted, key dates for add-ins using REST and Microsoft Graph calls plus issues reporting; 2) Support for Shared Folders - Delegates and Shared Mailbox in Exchange OnPrem is in beta! (win32 16.0.15505.20000), and 3) Support for Item Multi-Select (Beta coming soon).  For example select 3 e-mails and retrieve information from all three simultaneously.  
* **SSO samples update** – token handling in SSO NodeJS sample has been updated to not return a middle-tier token back to the client.   Step through the logic of the three scenarios addressed in this sample.  SSO with OBO (successful flow), SSO fails and must use MSAL (fallback flow) and the SSO token expired flow.   Tips on extending this sample along with security notes.

## Agenda

* Word update – [Yun Wang] - Principal Product Manager (Microsoft) – [1:21](https://www.youtube.com/watch?v=COic6ghBWsU&t=81s)
* Outlook Add-ins Update – [Juan Balmori] - Principal Product Manager (Microsoft) | @juaneloBalmor & - [Victoria Iannotti] - Software Engineer (Microsoft) – [6:11](https://www.youtube.com/watch?v=COic6ghBWsU&t=371s) 
* SSO samples update – [David Chesnut] - Senior Technical Writer (Microsoft) | @davidchesnut – [23:38] (https://www.youtube.com/watch?v=COic6ghBWsU&t=1418s)
* Community spotlight – [42:40](https://www.youtube.com/watch?v=COic6ghBWsU&t=2560s)
* Community panels – [43:14](https://www.youtube.com/watch?v=COic6ghBWsU&t=2594s)
* Q&A – (http://twitter.com/davidchesnut) – Senior Technical Writer (Microsoft) \| @davidchesnut – [44:34](https://www.youtube.com/watch?v=COic6ghBWsU&t=2674s)

## Actions

* Give us feedback on what you need from code samples. Join the Teams call – [Office Add-ins samples discussion](https://aka.ms/officeaddinsamples-join) – July 27th, 8:00 AM PT \| <https://aka.ms/officeaddinsamples-call>
* Share your feedback on how we can provide you with a better Office Add-ins development experience. Join a community panel –
    * [Outlook add-ins panel](https://ux.microsoft.com/Panel/OutlookAddinDeveloper)
    * [Excel add-ins panel](https://ux.microsoft.com/Panel/ExcelAddinDeveloper)
    * [Word add-ins panel](https://ux.microsoft.com/Panel/WordAddinDeveloper)
    * [PowerPoint add-ins panel](https://ux.microsoft.com/Panel/PowerPointAddinDeveloper)
    * [Samples and docs](https://ux.microsoft.com/Panel/OfficeAddinImproveSamplesDocs)
* [Sign up for the PnP Recognition Program](https://pnp.github.io/recognitionprogram/) and earn contribution badges
* See call agendas and summaries, and release announcements. Follow us on Twitter – 
    * [@microsoft365dev](https://twitter.com/microsoft365dev)
    * [@m365pnp](https://twitter.com/m365pnp)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free E5 developer tenant with instant availability and other assets.
* [Join the next community call](https://aka.ms/officeaddinscommunitycall) on July 13th at 8:00 AM Pacific Time (PT)

## Q&A (Question & Answers)

**What can you tell us about the approach and timing of the upcoming integration of Loop components with Excel?**

There isn't anything on the roadmap to share at this time. If you have ideas or requests please create a feature request with more information at https://aka.ms/m365dev-suggestions.


**Is there a way we can create desktop shortcuts for MS Office Add-ins (specifically for Word)?**

If you are referring to keyboard shortcuts, yes, but this is only available in Excel today. You can find more information in https://docs.microsoft.com/office/dev/add-ins/design/keyboard-shortcuts. If you are looking for keyboard shortcut support in Word, please let us know more about your scenario in a feature request at https://aka.ms/m365dev-suggestions.

**I have two questions both relating to getAccessToken

(1) Can you clarify which namespace we should be using to access the getAccessToken method please ?
The Microsoft answer to this post says that we should be using the OfficeRuntime.Auth.getAccessToken.
https://stackoverflow.com/questions/66776046/whats-the-different-about-office-context-auth-getaccesstokenasync-vs-officerun
but the third sentence on this page says that the "Office.auth.getAccessToken" will be the one to receive updates in the future.
https://docs.microsoft.com/en-us/javascript/api/office-runtime/officeruntime.auth?view=common-js-preview

(2) Why does the documentation refer to "Office.auth" when the full namespace is "Office.context.auth" ?
Could you confirm that the full namespace is actually
Office.context.auth.getAccessToken
and not Office.auth.getAccessToken
**

1. You can use either namespace. They call the same code as one just maps to the other. However, for consistency throughout the docs and samples, we are updating to always use Office.auth.getAccesstoken. It is possible that if a change were made in the future (like adding a new method) it may not appear on the original OfficeRuntime namespace. However any code using OfficeRuntime will not break. So if you are already using OfficeRuntime, you do not need to rewrite your code.
2. The correct namespace is Office.auth.getAccessToken.

**Is there a way for admin to install Excel add-in for the user or group that will show only for some Excel files generated by our application and not when user creates new Excel file or some other Excel files opened by the user?**

It isn't possible to conditionally install an add-in based on various conditions about the opened file. You can however enable functionality in your add-in based on the conditions you want to detect. For more information see https://docs.microsoft.com/en-us/office/dev/add-ins/develop/run-code-on-document-open. You can also show the task pane or hide the task pane based on conditions you define. For more information see https://docs.microsoft.com/en-us/office/dev/add-ins/develop/show-hide-add-in. You can also embed your add-in into an Excel spreadsheet if opening the file from your service. For more information, see https://docs.microsoft.com/en-us/office/dev/add-ins/excel/pnp-open-in-excel
If you need more capabilities, please create an idea request with more details about your scenario at https://aka.ms/m365dev-suggestions

**While we are waiting; we are considering dropping support for our COM addin for 32-bit Office; do you have any data, what percentage of users is still using 32-bit office, as opposed to 64-bit office (say since Excel 2013...) ?

we have a Web Addin as well, which is backed/interacts with a server, but we are not yet in a position to completely switch away from COM; we use 3rd party DLLs, which are getting harder and harder to come by in 32-bit format.**

We unfortunately cannot disclose user information regarding bitness. That being said for a modern add-in the users using 32 bit office may not make a heavy impact. 


**Can someone speak to support for Visio?**

We would love to get more context on the type of support you are looking for. Please contact prateek.sharma@microsoft.com.

**I sent this question a few weeks ago. Any chance you can include a compare API? Basically sending 2 files to Word Online to make a comparison and see the compared file.**

We would love to discuss your use case with you further. Please contact Yun Wang at wyun@microsoft.com.

**Is there planned support for onSelectionChanged() for the Word API in Content Controls? I am curious about when it will work with the production release of the API.**

There will be more content control support going forward, but there are currently no production plans for it this year. However, we would like to further discuss your use case with you to help us reprioritize and see if we could push forward for another release. Please contact Yun Wang (wyun@microsoft.com) and Maja Damjanic (maja.damjanic@microsoft.com).

**Any idea if "run on startup" will be available in all platforms for Word API? I see it depends on shared execution which is broken in Word?**

This is coming soon for Word. To discuss your use case further, please connect with Yung Wang at wyun@microsoft.com.

**Is there any update on whether the OfficeJS API will provide a method for generating a Graph API token vs using SSO (which is not supported in all cases) or requiring a user to login again?**

There are currently no plans to release an API for this. However, the identity and authentication teams are working on a new way to authenticate. Stay tuned!

**Any ETA on when track changes will be available for all platforms?**

By the end of this year or early next year. We encourage you to try this feature on the online version first, then have your users try it in production before the features is supported on all platforms. To see a demo of this feature, see Office Add-ins community call – February 9, 2022 (pnp.github.io).

**Graph-compatible tokens are really easy to get when using TeamsFX. Are you considering replicating that very nice user experience for Office.js as well?**

Yes, we are looking to unify these concepts for Office.js.

**Public folders are basically shared mailboxes (folders). They are special shared mailboxes for public folders. Are they supported?**

Public folders should be supported. We invite you to try out this feature in beta and welcome your feedback.

**Are you going to provide an API that lets Office.js add-ins create comparison documents, which is possible with VSTO add-ins, for example?**

We currently don't have this on our list. However, we would love to know more about your use case to help us understand. Please connect with Yung Wang at wyun@microsoft.com.

**Maybe I missed something, but I was not able to get types working when I was trying the JS API in Word. I ended up with a pile of ts-ignores. Is there a better way? I am using WebStorm, but I would be happy to use VS Code if that solves it. My hope would be to use imports like import {OfficeStuff} from 'officesdk'.**

Using the Node.js environment to create your add-in could help. For further guidance with setting up your environment, see Set up your development environment - Office Add-ins | Microsoft Docs.

**Did I read correctly from the Q&A slides that you can embed add-ins in an Excel workbook?**

Yes, you can embed add-ins in an Excel workbook. For guidance, see Open Excel from your web page and embed your Office Add-in. 
For the technique to embed an add-in Excel using open in Teams approach, see Office-Add-in-samples/Samples/excel-open-in-teams at main · OfficeDev/Office-Add-in-samples (github.com).

**Via the GraphAPI it is possible to add an attachment to an email object (https://docs.microsoft.com/en-us/graph/api/message-post-attachments?view=graph-rest-1.0&tabs=http), however, I cannot specify metadata such as Content-Type, name, or Content-Transfer-Encoding. Will it be supported in the future or is there another way to add this information?**

We currently do not have concrete plans on the roadmap. It would be great if you could create a feature request with more information at https://aka.ms/m365dev-suggestions.

**Thank you for the great APIs! My company is developing a suite of Office Add-ins and from time to time runs into API limitations and/or feature parity issues across different applications. What would be the best way to bring these to the attention of Office Add-ins team? Do you have an email address for a developer liaison? techcommunity.microsoft.com can sometime feel like a black hole.**

The Office Add-ins platform team engages at the following locations.

For Q&A (either location works):
https://aka.ms/office-addins-dev-questions
Tags: [office-js-dev] [office-addins-dev]
https://stackoverflow.com 
Tags: [office-js] [outlook-web-addins] [office-scripts]

For any products please create an issue at:
https://github.com/OfficeDev/office-js 

**Thank you for the PowerPoint preview APIs and the progress being made there! Are there plans to continue extending the functionality such that eventually everything on a slide can be read and updated?**
We encourage the users to try and test the current preview APIs and provide us the feedbacks. If the users have specific requirements other than those listed in the preview, they need to go to where to submit office proposal - Search (aka.ms) to submit new proposals.

**Any plans to support the onSelectionChanged event in the Outlook Javascript Add-in APIs? In our Word and Excel Add-ins we have buttons that dynamically update according to user selection, but we can't do this in Outlook yet.**

There currently aren't any plans on our roadmap to support this event in our Outlook Javascript apis. It would be great if you could go add this feature as a new feature request so we can do further investigation into this. 
Microsoft 365 Developer Platform - Microsoft Tech Community

## References

* **Word Update**
    * Documentation - [Word JavaScript API online-only requirement set](https://docs.microsoft.com/en-us/javascript/api/requirement-sets/word/word-api-online-requirement-set?view=common-js-preview)
* **Outlook Add-ins Update (REST decommission, Shared Folders support, Item multiselect)**
    * Verification Form - [REST API Add-in verification request](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxxP2zxSbypLp5NxVTGn_ONUN0JVQ1Y5NlVEUUU4Uk5DSkVYR01KVElVVC4u)
* **SSO samples update**
    * Documentation - [Microsoft identity platform and OAuth 2.0 On-Behalf-Of flow](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-oauth2-on-behalf-of-flow)
    * Documentation - [Middle-tier access token request](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-oauth2-on-behalf-of-flow#middle-tier-access-token-request)
    * Debugging tool for examining tokens - [jwt.ms](https://jwt.ms/)
    * SSO NodeJS walkthrough - [Create a Node.js Office Add-in that uses single sign-on](https://docs.microsoft.com/en-us/office/dev/add-ins/develop/create-sso-office-add-ins-nodejs)
    * SSO NodeJS sample repo - [Office Add-in that supports Single Sign-on to Office, the Add-in, and Microsoft Graph](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/auth/Office-Add-in-NodeJS-SSO)
    * Documentation - [Microsoft identity platform documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/)
## General resources

* [Office developer center](https://developer.microsoft.com/office)

## Stay connected

* See the full blog post for this call in the Microsoft 365 platform community blog – <https://aka.ms/m365pnp/blog>
* Follow us on Twitter – <https://twitter.com/microsoft365dev>
* Microsoft 365 Platform Community on YouTube – <https://aka.ms/m365/videos>
* All Microsoft Developer Community calls – <https://aka.ms/M365DevCalls>
* Submit questions about add-ins development for our next community call – <https://aka.ms/officeaddinsform>
* Next community call – July 13th at 8:00 AM PT – <https://aka.ms/officeaddinscommunitycall>

{{< attachments >}}
