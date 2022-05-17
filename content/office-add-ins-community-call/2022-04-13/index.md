---
title: "Office Add-ins community call – April 13, 2022"
date: 2022-05-10T08:01:00-05:00
author: "David Chesnut"
githubname: davidchesnut
categories: ["Office add-in developer community call"]
images:
- images/office-add-ins-call-april-2022-recording.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://www.youtube.com/watch?v=ik9yBecsF3A
---

## Call Summary

This month's community call features demos on **Ribbon API updates** (previewing enable/disable ribbon buttons and contextual tabs for PowerPoint and Word) – Abid Rahman, Program Manager (Microsoft) & Preethika Kiruveedula, Program Manager (Microsoft), **PowerPoint selection APIs** (previewing 17 new APIs for getting and setting slides, shapes and text range in PowerPoint) – Onur Onder, Senior Software Engineer (Microsoft) & Camille Birch, Product Manager (Microsoft), and **Add-ins on Appointment read surface on Outlook Mobile** (previewing appointment organizer APIs for logging event details to 3rd party applications) – Jatin Guptam, Program Manager (Microsoft). There was Q&A at end of call and in chat throughout call. The call was hosted by [David Chesnut](https://twitter.com/davidchesnut) Senior Dev Writer (Microsoft) \| @davidchesnut. Recorded April 13, 2022.

{{< youtube ik9yBecsF3A  >}}

## Demos

* **Ribbon API updates** – previewing 2 capabilities – Enable/disable ribbon buttons and contextual tabs, along with timelines for their inclusion in PowerPoint and Word by platform. Enable/disable APIs used to set default state of your add-in command, change state of your add-in command programmatically, and change state in response to an event. Contextual tabs APIs used to create new tabs and show/hide existing tabs.
* **PowerPoint selection APIs** – 17 new APIs focused on how to get and set selected information for slides, shapes, and text range in PowerPoint. Reviewed concepts of slide and shape scoped collections along with text range selection and showed functionality delivered by the APIs. The beta APIs are available now for you to trial and provide feedback.
* **Add-ins on Appointment read surface on Outlook Mobile** – latest appointment organizer APIs now in preview. Delivering a new extension point with the ability to log event details to a 3rd party application, support for UI-less and task pane add-ins, semi-Contextual entry, discoverability, native UI, and status change from logging to viewing. Currently in preview on Android, GA by next month. We will share the timeline for iOS soon.

## Agenda

* **Ribbon API updates** – Abid Rahman, Program Manager (Microsoft) & Preethika Kiruveedula, Program Manager (Microsoft) – [1:19](https://youtu.be/ik9yBecsF3A?t=79)
* **PowerPoint selection APIs** – Onur Onder, Senior Software Engineer (Microsoft) & Camille Birch, Product Manager (Microsoft) – [7:20](https://youtu.be/ik9yBecsF3A?t=440)
* **Add-ins on Appointment read surface on Outlook Mobile** – Jatin Guptam, Program Manager (Microsoft) – [14:11](https://youtu.be/ik9yBecsF3A?t=851)
* **Q&A** – [18:57](https://youtu.be/ik9yBecsF3A?t=1137)

## Actions

* Earn contributor badges! Sign up for the PnP Recognition program at <https://pnp.github.io/recognitionprogram/>.
* Follow channels in Twitter – for call agendas and summaries, release announcements, and more.
    * <https://twitter.com/microsoft365dev>
    * <https://twitter.com/m365pnp>
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free E5 developer tenant with instant availability and other assets.
* Next community call May 11th at 08:00am PT. Add call to your calendar: <https://aka.ms/officeaddinscommunitycall>.


## Q&A (Question & Answers)

**When Microsoft deprecated User Voice there were a large number of great ideas lost. The replacement Microsoft 365 Developer Platform Ideas platform currently has New ideas = 535, Working on it = 2 and Need more information = 0 and Completed = 2! Even the most upvoted idea shows no responses from Microsoft. What value is there to posting ideas in this forum?**

Unfortunately, we were unable to preserve all ideas when we moved from UserVoice to the new ideas site. We did get a capture of all ideas with more than 100 votes and those were migrated to the new forum which we do use internally for planning. We definitely need improve this experience for better engagement and transparency into our planning process. There's currently a significant effort underway to reevaluate our community engagement on idea suggestions. We hope to share more details soon in an upcoming community call. Please understand that we absolutely value your suggestions and take them seriously. And thank you for raising this important issue!

**When can we expect "insertWorksheetsFromBase64" completely supported for Excel on the web? Currently Excel on the web doesn't support source worksheets with PivotTable, Chart, Comment, or Slicer elements."**

We don't have a plan to implement **insertWorksheetsFromBase64** for Excel on the web at this time. There's a dependency on a feature we require that is not yet in Excel on the web. There's an [existing idea request](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/add-full-support-for-insertworksheetsfrombase64-method-for-excel/idi-p/3255216) to implement 
**insertWorksheetsFromBase64**. We ask that any developers affected by this please upvote it. If you can provide comments, especially if you are blocked, this would be helpful to bump up the priority on this.

**I'm trying to use the Shape API. In Script Lab, when I run the "Insert shape, line, and text box" sample code, some things work (e.g., insert hexagon) and others don't (e.g., create shape with text). When I change the code on Script Lab, I'm able to play with position, dimensions, shape type, etc. but I can't change colors, text, line weight and style, etc. Can you confirm whether all of this should work?**

There was a bug in the "Insert shape, line, and text box" sample that we fixed based on this question. See the [issue on GitHub](https://github.com/OfficeDev/office-js-snippets/issues/618) for more details. If you're still seeing issues, can you please create report them [in the GitHub office-js-snippets repo](https://github.com/officedev/office-js-snippets)? We can follow up there.

**I have some questions about the Outlook add-ins and Outlook REST V2 decommission. We provide our customers with Outlook add-ins that use the On-send feature. We are wondering if it will be extended only to existing customers or to new customers as well.**

The exemption for Outlook add-ins using Outlook REST V2 applies to any add-ins created before November 2022.

Case:

* Tenant A has Outlook Add-in X using the On-send feature that was deployed before November 2022.
    * If you request an exemption for Outlook Add-in X before November 2022 it will continue to work.
* After November 2022, what happens if we delete the add-in X and then register it again?
    * It will continue to work. You only need to register once at <https://aka.ms/RESTCheck>.
* After November 2022, what happens if we register the add-in X for a new tenant B?
    * Registrations at <https://aka.ms/RESTCheck> will not be accepted after November 2022. Be sure to register your add-in before then if you need to continue using the Outlook REST APIs
* Is there any difference between registration by side-loading or by centralized deployment?
    * We use the App ID that you register at <https://aka.ms/RESTCheck> to track apps and provide the exemption. Once registered your add-in will continue to work regardless of the deployment method you choose.

**We develop an Office.js add-in for Outlook that can encrypt/decrypt emails. We'd like the compose window to disappear after our "Encrypt and Send" button is clicked. Or we need a toggle such that a user can enable/disable encryption, and subsequently, our encryption process is done after the user clicks on the Send button (thus, an extended on-send feature, not only for validation purposes). Is one of those two features planned to be implemented anytime soon, or is it wise to consider developing our addin within VSTO?**

You can accomplish this scenario using web add-ins and smart alerts. We recommend you combine this handling of the send event with event-based add-ins so you can encrypt the attachments as they are added on the email while composing, so that your on-send processing takes less time. We have a sample that shows how to do this at [https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/outlook-encrypt-attachments.](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/outlook-encrypt-attachments)

**Why is it not possible to use the mail in MIME format as payload in the request when trying to create a message within a mailFolder (via "POST /me/mailFolders/{id}/messages"), as it seems that only JSON is accepted here? But via /me/messages I can use MIME format.**

The best place to ask Microsoft Graph questions is at <https://aka.ms/askgraph>. When creating a draft email, it is typically created in the Drafts folder using “POST /me/messages”. This supports the MIME format. You can use “POST /me/mailFolders/{id}/messages” to create messages in any folder, although they will always be in draft mode. This did not seem like a likely scenario to support MIME. If there is a need for this please let us know more about your scenario at <https://aka.ms/askgraph>.

**In Word desktop, with WebView2, if I reject the consent for audio/video recording for the first time, how can I change it or raise this question again? And a similar question, how can I disable or change the spellcheck settings in WebView2 in Word desktop?**

If consent was rejected, you need to clear the Office cache to raise the question again. For more information, see [Clear the Office cache - Office Add-ins \| Microsoft Docs](https://docs.microsoft.com/office/dev/add-ins/testing/clear-cache).

Spellcheck settings are controlled at the webview level. For example, `\<div id="content" spellcheck="true"`.

**Where can I go to request feature enhancements for outlook, such as controlling the width of an Outlook add in?**

Please let us know about any feature enhancements or suggestions at the Microsoft 365 developer platform ideas site <https://aka.ms/m365dev-suggestions>.

**Are there any plans to have contextual tabs available for PowerPoint?**

We currently don’t have plans to extend to PPT, if you would like to have contextual tabs in PPT, please post more information around your scenario at <https://aka.ms/m365dev-suggestions>.

**Are you planning to make the Mail Compose Surface available on mobile?**

Yes, we're planning to support it and are exploring various scenarios. We don't have a timeline to share yet.

**Is it possible to customize the save dialog in Office (PPT, Word)?**

We don’t have any way to customize the save dialog with Office Add-ins. If you could post an idea request at <https://aka.ms/m365dev-suggestions> we'd like to learn more about the scenarios where you would need to customize the save dialog.

**What's the best place to store an "access token" in the Excel add-in? The access token is received by third-party app.**

In general it's not a good idea to store, or cache access tokens. You have to be very careful not to accidentally store the token in a way where malicious software could obtain it. Most libraries and APIs have a caching mechanism that you can take advantage of. For example, when calling the **getAccessToken** API in your Office Add-in, we recommend you call **getAccessToken** again whenever you need the token. Office caches it for you. If you are using the Microsoft Authentication Library, it also has caching that you can take advantage of. See [Acquire and cache tokens with Microsoft Authentication Library (MSAL) - Microsoft identity platform ...](https://docs.microsoft.com/azure/active-directory/develop/msal-acquire-cache-tokens), and [Enable single sign-on (SSO) in an Office Add-in - Office Add-ins \| Microsoft Docs](https://docs.microsoft.com/office/dev/add-ins/develop/sso-in-office-add-ins) for more details.

**When creating an office-js add-in in the context of a larger solution that also integrates with Teams, which UI package is recommended: Fluent UI React or Fluent UI React Northstar? Would either of those be fine with a view to getting those apps accepted in the store? I would like to develop a solution for both Office (Word and Excel) and Teams, so the question is what the best starting point would be. I would like to avoid having to use two libraries.**

[Fluent UI v8](https://developer.microsoft.com/fluentui#/controls/web) is the current look of Office and other apps. Northstar is the system used by Microsoft Teams. We are building out Fluent UI v9 as a new system for both Teams and Office. v9 is still pretty early on, and still in release candidate for the initial base controls. For now, we recommend using Fluent UI v8.

**Is there a roadmap for future PowerPoint APIs beyond the preview API sets?**

We'll be posting roadmaps for PowerPoint APIs and other features to the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap) soon.

## References

* **Ribbon API updates (Demo)**

    * Documentation – Enable and Disable Add-in Commands \| <https://docs.microsoft.com/office/dev/add-ins/design/disable-add-in-commands>
    * Documentation – Create custom contextual tabs in Office Add-ins \| <https://docs.microsoft.com/office/dev/add-ins/design/contextual-tabs>
    * Sample – Create custom contextual tabs on the ribbon \| <https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/office-contextual-tabs>

* **PowerPoint selection APIs (Demo)**

    * Documentation – PowerPoint.Shape class
    * Documentation – PowerPoint.TextRange class
    * Documentation – PowerPoint.Slide class
    * Documentation – PowerPoint.Presentation class
    * Preview Office library - <https://appsforoffice.microsoft.com/lib/beta/hosted/office.js>

* **Add-ins on Appointment read surface on Outlook Mobile (Demo)**

    * Documentation – Office.RoamingSettings interface
    * Documentation – Office.AddinCommands.Event interface
    * Documentation – [Use the Office dialog API in Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/dialog-api-in-office-add-ins)
    * Documentation – Office.AppointmentRead interface
    * Documentation – Office.AppointmentRead interface
    * Documentation – [Use the Office dialog API in Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/dialog-api-in-office-add-ins)

* **Office Add-ins community call**

    * [Upcoming agenda and previous call resources](https://aka.ms/officeaddinsagenda)
    * [Recurring, monthly community call calendar invite](https://aka.ms/officeaddinscommunitycall)
    * [Community call topic requests and questions](https://aka.ms/officeaddinsform)
    * Community call recordings on the [YouTube Microsoft 365 community channel](https://www.youtube.com/channel/UC_mKdhw-V6CeCM7gTo_Iy7w)

* **Office Add-ins feedback**

    * Technical questions – Microsoft Q&A ([office-js-dev](https://docs.microsoft.com/answers/topics/office-js-dev.html)), ([office-addins-dev](https://docs.microsoft.com/answers/topics/office-addins-dev.html))
    * Issues – [GitHub](https://github.com/OfficeDev/office-js/issues)
    * Recommendations and suggestions – [Microsoft 365 Developer Platform ideas](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform)

## General resources

* [Office developer center](https://developer.microsoft.com/office)
