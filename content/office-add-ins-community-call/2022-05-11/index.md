---
title: "Office Add-ins community call – May 11, 2022"
summary: "Topics: AppSource Add-in Validation Improvements, Blazor in Office Add-ins (Demo), Add-in command changes (reminder to register add-ins commands that use ExecuteFunction by October 30) and Community ideas (feedback wanted). Q&A in chat and at end of call."
date: 2022-05-15T08:01:00-05:00
author: "David Chesnut"
githubname: davidchesnut
categories: ["Office add-in developer community call"]
images:
- images/office-add-ins-call-may-2022-recording.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://www.youtube.com/watch?v=_3rzh23TaH4
draft: true
---

## Call Summary

This month's community call topics:

1. **AppSource Add-in Validation Improvements** – including browser support update, top failure outcomes to avoid and communicating directly with your validation team - [Juan Balmori](http://twitter.com/juaneloBalmori) - Principal Product Manager (Microsoft) \| @juaneloBalmori
2. **Blazor in Office Add-ins** - step through creating a Blazor Webassembly Word add-in - [Maarten van Stam](http://twitter.com/aafvstam) - MVP Office Add-ins \| @aafvstam
3. **Add-in command changes** - how to update and register your add-ins commands that use ExecuteFunction, by October 30th deadline - [Abid Rahman](https://www.linkedin.com/in/abidrahman1/) - Product Manager (Microsoft)
4. **Community ideas** - help shape how we gather and prioritize Microsoft 365 development suggestions - [Linda Cannon](http://twitter.com/lindalu_MSFT) - Senior Content Product Manager (Microsoft) \| @lindalu_MSFT.
5. **Q&A** at end of call and in chat throughout call.

The call was hosted by [David Chesnut](http://twitter.com/davidchesnut) (Microsoft) \| @davidchesnut. Recorded May 11, 2022.

{{< youtube _3rzh23TaH4 >}}

## Topic summaries

* **AppSource Add-in Validation Improvements** – effective immediately, we (AppSource) will activate your add-in in IE (Trident). If your add-in fails to load in Trident, we will soft-fail it. Top failures when validating add-ins include no testing instructions, poor first run experience and external service experience, no additional charges disclosure, and more. Now you can engage directly with the Add-ins Validation Team in response to a validation report from team.
* **Blazor in Office Add-ins (Demo)** – initial Pull Request to bring in the Office Add-in based on Blazor Webassembly technologies using Blazor, .NET Core, C\# and JavaScript Interop. Blazor WASM will be handled just like any other Office JS Add-in on cross-platform environments that are compatible with WASM. See Blazor web assembly app in Word, add content controls and event handlers to the controls from the task pane.
* **Add-in command changes** – reinforcing our May 10th announcement regarding add-ins that use ExecuteFunction, if your handler function is not registered by October 30, 2022, it will fail to run! You do not need to resubmit your add-in, you are just making a change in the js function itself. See the one line of code you need to add after your function definitions and learn how to verify completeness.
* **Community ideas** – Door \#1, \#2, \#3? Sharing a transparent update on the quest to settle on the right and ONE home for your Office Add-ins related suggestions. What is the current state, our shared objectives, our technical challenges, and pros/cons for potential next steps? Please chime in and let us know what you think we should do on this front.

## Agenda

* AppSource Add-in Validation Improvements - [Juan Balmori](http://twitter.com/juaneloBalmori) - Principal Product Manager (Microsoft) \| @juaneloBalmori – [1:17](https://youtu.be/_3rzh23TaH4?t=77)
* Blazor in Office Add-ins (Demo) - [Maarten van Stam](http://twitter.com/aafvstam) - MVP Office Add-ins \| @aafvstam – [11:58](https://youtu.be/_3rzh23TaH4?t=718)
* Add-in command changes - [Abid Rahman](https://www.linkedin.com/in/abidrahman1/) - Product Manager (Microsoft) – [29:16](https://youtu.be/_3rzh23TaH4?t=1756)
* Community ideas - [Linda Cannon](http://twitter.com/lindalu_MSFT) - Senior Content Product Manager (Microsoft) \| @lindalu_MSFT – [35:09](https://youtu.be/_3rzh23TaH4?t=2109)
* Q&A – [David Chesnut](http://twitter.com/davidchesnut) (Microsoft) \| @davidchesnut - [47:15](https://youtu.be/_3rzh23TaH4?t=2835)

## Actions

* Join the Teams call – [Office Add-ins samples discussion](https://aka.ms/officeaddinsamples-call) – June 15, 8:00 am PT \| aka.ms/officeaddinsamples-call
* Earn contributor badges - sign up for the PnP Recognition program. - <https://pnp.github.io/recognitionprogram/>
* Follow channels in twitter – for call agendas and summaries, release announcements,…
    * <https://twitter.com/microsoft365dev>
    * <https://twitter.com/m365pnp>
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free E5 developer tenant with instant availability and other assets.
* Next community call – June 8th at 08:00am PT - <https://aka.ms/officeaddinscommunitycall>


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

* **AppSource Add-in Validation Improvements**
    * Documentation - [App validation documentation](https://ineleccom-my.sharepoint.com/personal/andrb_inelec_com/Documents/Desktop/Office%20Videos/Add%20In%20Calls/2022-05-11-OfficeAdd-ins/App%20validation%20documentation)
    * Documentation - [Microsoft AppSource submission FAQ](https://docs.microsoft.com/office/dev/store/appsource-submission-faq)
    * Article – [Announcing WebView2 for Office Add-ins Platform – Preview](https://devblogs.microsoft.com/microsoft365dev/announcing-webview2-for-office-add-ins-platform/)

* **Blazor in Office Add-ins (Demo)**
    * Sample - [Create a Blazor Webassembly Word add-in](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/word-blazor-add-in)
    * Videos channel – [Maarten van Stam - Soft As In Software](https://www.youtube.com/SoftAsInSoftware)
    * Twitch – [Soft As In Software](https://www.twitch.tv/softasinsoftware)

* **Add-in command changes**
    * Article - [Announcing changes to Office Add-ins’ ExecuteFunction commands](https://devblogs.microsoft.com/microsoft365dev/announcing-changes-to-office-add-ins-executefunction-commands/)
    * Samples - [Office Add-in commands](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/office-add-in-commands)
    * Documentation - [Create add-in commands in your manifest for Excel, PowerPoint, and Word](https://docs.microsoft.com/office/dev/add-ins/develop/create-addin-commands)
    * Issues – [Office Add-ins issues](https://github.com/OfficeDev/office-js/issues)

* **Community ideas**
    * Suggestions - [Microsoft 365 Developer Platform Ideas - Office Add-ins](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform) \| [aka.ms/m365dev-suggestions](https://aka.ms/m365dev-suggestions)
    * Issues - [OfficeDev/office-js/issues](https://github.com/OfficeDev/office-js/issues)
    * Forum - [Microsoft Ideas forum - Feedback Portal](https://feedbackportal.microsoft.com/feedback)
    * Feedback on Feedback – how should people contact you regarding our presentation today?

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

## Stay connected

* See the full blog post for this call in the Microsoft 365 platform community blog - <https://aka.ms/m365pnp/blog>
* Twitter - [https://twitter.com/microsoft365dev](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbkdvcDJHcGdzM2VIUkwzU3lOYkJaVFEzM0Q2QXxBQ3Jtc0ttM1NyaTQ2RjFSOFh3a0l4c1pralBRQVI1bDNSQ2RaVm9OdzJrRkdtV1Z1SW5VdmdwamNNLTBEaFdaSmZMc0lQNzdRZ2dDYV9WZVF1ZVIwc2dPQTZBRUZ3b3hoWUVJdDJoQWZUcWdCR2JKdmwtUU43RQ&q=https%3A%2F%2Ftwitter.com%2Fmicrosoft365dev)​
* Microsoft 365 Platform Community in YouTube - <https://aka.ms/m365/videos>
* Link to all Microsoft Developer Community calls - <https://aka.ms/M365DevCalls>
* Submit questions for next community call - <https://aka.ms/officeaddinsform>
* Next community call – June 8th at 08:00am PT - <https://aka.ms/officeaddinscommunitycall>

{{< attachments >}}
