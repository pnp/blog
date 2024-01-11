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
draft: false
---

## Call Summary

This month's community call topics:

1. **AppSource Add-in Validation Improvements** – See the latest browser support update, top failure outcomes to avoid, and see how to communicate directly with your validation team – [Juan Balmori](http://twitter.com/juaneloBalmori) – Principal Product Manager (Microsoft) \| @juaneloBalmori
2. **Blazor in Office Add-ins** – Step through creating a Blazor Webassembly Word add-in – [Maarten van Stam](http://twitter.com/aafvstam) – MVP Office Add-ins \| @aafvstam
3. **Add-in command changes** – Update and register your add-in commands that use ExecuteFunction, by October 30th deadline – [Abid Rahman](https://www.linkedin.com/in/abidrahman1/) – Product Manager (Microsoft)
4. **Community ideas** – Shape how we gather and prioritize Microsoft 365 development suggestions – [Linda Cannon](http://twitter.com/lindalu_MSFT) – Senior Content Product Manager (Microsoft) \| @lindalu_MSFT.
5. **Q&A** – See question and answers at end of call and in chat throughout call.

The call was hosted by [David Chesnut](http://twitter.com/davidchesnut) (Microsoft) \| @davidchesnut. Recorded May 11, 2022.

{{< youtube _3rzh23TaH4 >}}

## Topic summaries

* **AppSource add-in validation improvements** – Effective immediately, we (AppSource) no longer require IE (Trident) support. If your add-in fails to load in Trident, we'll soft-fail it. Top failures when validating add-ins include: no testing instructions, poor first run and external service experiences, missing additional charges disclosures, and more. Now you can engage directly with the Add-ins Validation Team in response to a validation report from team.
* **Blazor in Office Add-ins (demo)** – We viewed a demo of the initial pull request to bring in the Office Add-in based on Blazor WebAssembly technologies using Blazor, .NET Core, C\#, and JavaScript Interop. Blazor WASM is handled just like any other Office JS add-in on cross-platform environments that are compatible with WASM. See the Blazor WebAssembly app in Word to add content controls and event handlers to the controls from the task pane.
* **Add-in command changes** – On May 10th, 2022, we announced changes to add-ins that use ExecuteFunction. If your handler function is not registered by October 30, 2022, it will fail to run! You don't need to resubmit your add-in; you're just making a change in the js function itself. See the one line of code you need to add after your function definitions and learn how to verify completeness.
* **Community ideas** – Door \#1, \#2, \#3? We shared a transparent update on the quest to settle on the correct and final home for your Office Add-ins related suggestions and ideas. What is the current state, our shared objectives, our technical challenges, and pros/cons for potential next steps? Please chime in and let us know what you think we should do on this front.

## Agenda

* AppSource Add-in Validation Improvements – [Juan Balmori](http://twitter.com/juaneloBalmori) – Principal Product Manager (Microsoft) \| @juaneloBalmori – [1:17](https://youtu.be/_3rzh23TaH4?t=77)
* Blazor in Office Add-ins (Demo) – [Maarten van Stam](http://twitter.com/aafvstam) – MVP Office Add-ins \| @aafvstam – [11:58](https://youtu.be/_3rzh23TaH4?t=718)
* Add-in command changes – [Abid Rahman](https://www.linkedin.com/in/abidrahman1/) – Product Manager (Microsoft) – [29:16](https://youtu.be/_3rzh23TaH4?t=1756)
* Community ideas – [Linda Cannon](http://twitter.com/lindalu_MSFT) – Senior Content Product Manager (Microsoft) \| @lindalu_MSFT – [35:09](https://youtu.be/_3rzh23TaH4?t=2109)
* Q&A – [David Chesnut](http://twitter.com/davidchesnut) (Microsoft) \| @davidchesnut – [47:15](https://youtu.be/_3rzh23TaH4?t=2835)

## Actions

* Give us feedback on what you need from code samples. Join the Teams call – Office Add-ins samples discussion – June 15, 8:00 am PT
* Sign up for the PnP Recognition Program and earn contribution badges – <https://pnp.github.io/recognitionprogram/>
* See call agendas and summaries, and release announcements. Follow us on Twitter –
    * <https://twitter.com/microsoft365dev>
    * <https://twitter.com/m365pnp>
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free E5 developer tenant with instant availability and other assets.
* Join the next community call on June 8th at 08:00am Pacific Time (PT) – <https://aka.ms/officeaddinscommunitycall>

## Q&A (Question & Answers)

**I'd love to follow-up on this feature request: [Office JS Save and Close methods for Word, Excel, and PowerPoint](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/office-js-save-and-close-methods-for-word-excel-and-powerpoint/idi-p/2800214). Apologies for my persistence, but this is literally the only blocking issue for us to move from the old add-ins to the Office web Add-ins platform. We would really appreciate if you could push this into the roadmap. We represent hundreds of users and the deployments of the old add-ins and updates are not ideal. Thank you so much.**

Thanks for your persistence! We're sorry you're blocked by this. Unfortunately, we can't add this to the roadmap at this time, but we'll continue to keep an eye on the request. Consider asking the [Office JS developer community](https://stackoverflow.com/questions/tagged/office-js) on Stack Overflow how others have addressed this issue.

As a workaround you may want to explore continuing to use your COM add-in for full functionality while adding partial functionality in the web add-in for cross-platform support. For more information, we recommend exploring [Make your Office Add-in compatible with an existing COM add-in](https://docs.microsoft.com/office/dev/add-ins/develop/make-office-add-in-compatible-with-existing-com-add-in).

**Open the Outlook mobile API to allow compose scenarios to insert attachments in emails. Currently, third-party cloud storage companies cannot integrate directly into Outlook mobile. With this API, we would be able to click a button and insert files from private cloud storage providers into emails.**

We'd like to know more about this scenario. Can you please create a feature request with more information at [https://aka.ms/m365dev-suggestions](https://aka.ms/m365dev-suggestions)? Thanks!

**How can you communicate from a Word add-in to an Office JS task pane? For example, OnContentEnter, highlight one HTML control in the task pane.**

We see this question was also [posted to the Q&A site](https://docs.microsoft.com/answers/questions/827167/how-to-call-office-js-function-hosted-in-taskpane.html). You should be able to use the [onSelectionChanged](https://docs.microsoft.com/javascript/api/word/word.contentcontrol?view=word-js-preview#word-word-contentcontrol-onselectionchanged-member) event. If not, can you please follow up with more information on the Q&A site? Thanks!

**During the last call, one of my questions was is possible to programmatically let the compose window disappear after the user clicks a custom "Encrypt and Send" button, as the mail already is encrypted. Then send the email as a MIME payload via the send message Graph API. You suggested to use smart alerts to handle the send event. However, this is not ideal for our use case. The on-send event is triggered on each email, but we want the user to deliberately decide via the custom button if they want to encrypt the email or not. Also, encrypting "on the fly" via OnMessage events is not on option as not every mail should be encrypted. Also, it does not work well with our custom encryption protocol. Hence, a feature request could be to programmatically discard the current composed mail, and subsequently close the compose form.**

We are not planning to override or suppress the native send button, nor to expose a cancel composition API. This can cause user confusion and could be used maliciously in some conditions. The scenario can still be solved with smart alerts. The key here is to combine the following things.

* Custom properties
* LaunchEvents (attachmentsChanges particularly)
* Smart Alerts

Pre-conditions: we cannot override the “send” button in Outlook. This is also not a recommended experience for Outlook users who expect to send an item using the native “send” option. So, the ability to encrypt and send UEX-wise is not possible.

1. Indeed the user needs to take an explicit action to encrypt the content. So there needs to be an “Encrypt Message” button. The button needs to open a task pane and ask the user what they want to encrypt (should the add-in encrypt the message? the attachments? all?) Also, the task pane can configure other settings or rules. For example, a rule like “always encrypt when sending messages to this particular customer”. Those can be stored as a mailbox setting, so that afterwards the setting can be honored when running the on-send event.
2. When the user chooses the “Encrypt Message” button and configures what to encrypt, they can also create a custom property that serves as a flag for the onSend event. (i.e. pleaseEncrypt=true)
3. Then in the onSend event, the first thing to do is to check the pleaseEncrypt custom property. If it does not exist it means the event needs to do nothing and just send the email.
4. To avoid a heavy onSend management logic, consider encrypting attachments as they are added using the AttachmentAdd event.

**Do you plan to upgrade the Visual Studio Web Add-in templates to ASP.NET Core?**

We are looking into some updates to the Visual Studio Office Add-in templates, but don't have anything on the roadmap at this time. Please let us know more about what you'd like to see in these templates by posting a request at [https://aka.ms/m365dev-suggestions](https://aka.ms/m365dev-suggestions).

**Has the PowerPoint API 1.3 been officially released to all platforms?**

The PowerPoint JavaScript API 1.3 requirement set is supported on Windows, Mac, and the web (but not iOS or mobile at this time.) See [PowerPoint JavaScript API requirement sets](https://docs.microsoft.com/javascript/api/requirement-sets/powerpoint/powerpoint-api-requirement-sets?view=powerpoint-js-preview) for complete details.

**If the task pane is specified in the add in manifest.xml that is installed by an admin, it will always show in Excel files. Is there a way for Excel add-ins that are installed by an admin to appear for a user or group only when the Excel file is created by the SaaS application, and not for existing or new Excel files created by the user?**

The **Show Taskpane** commands appear in all Excel workbooks once an add-in is deployed. To hide a custom tab, certain properties on the workbook must be present. See the [visible property](https://docs.microsoft.com/javascript/api/office/office.tab?view=common-js-preview#office-office-tab-visible-member) for more information.

**The manifest validation service continues to fail for the Outlook add-in ItemSend event (see https://github.com/OfficeDev/Office-Addin-Scripts/issues/613). Our organization wants to use our build pipeline as we did in the past for admin deployed add-ins.**

Thanks for pinging us on this. It's possible that the PowerShell command is using the store validation that ACCEPTS launch event annotations causing it to fail erroneously. We'll investigate more and follow up on the original GitHub issue.

**Regarding Trident support, just for clarification, "support" could mean a friendly screen telling the user that Trident is not supported. Is that correct? "Not supporting" would mean some form of error and blank screen without any notification of what happens.**

Supporting really implies that your add-in provides some functionality in Trident. We know that for some customers this is not required so the bare minimum we are asking is to "fail gracefully", which is basically the friendly screen you are referring to. We have some folks who only show a blank page, so that was not good and we used to reject on that situation. We have some guidance on how to fail gracefully at [Determine at runtime if the add-in is running in Internet Explorer](https://docs.microsoft.com/office/dev/add-ins/develop/support-ie-11#determine-at-runtime-if-the-add-in-is-running-in-internet-explorer)

**Could AppSource submission provide a testing notes field with the submission that gets submitted with the app submission? Current testing notes always get lost between submissions! This might help get rid of the number one validation failures!**

You can attach a PDF to your submission that will stay for the lifetime of the validation even on subsequent submissions.

**Comment on AppSource: After submitting an update to an add-in, if the add-in is distributed to employees through Microsoft Admin Center, or Integrated apps, the add-in is never updated for the end-users (employees). Please could you review this issue?**

This should not be the case; this could happen within 72 hours in the worst case. Depending on the type of add-in, there are a few conditions that require an admin to approve the update (i.e. if your add-in was updated to support SSO, or event-based in Outlook). If you can provide more details we can definitely help you (what type of add-in is this). Please let us know more at [office-js on Stack Overflow](https://stackoverflow.com) or the [Q&A forum](https://aka.ms/office-addins-dev-questions).

**Regarding the add-in commands, there is noticeable lag between clicking a button and seeing the result. That lag does not exist when performing the exact same action from a task pane. Is there a reason for this, and a way around it?**

When these commands are invoked, we start the runtime that is required to execute the action. This may result in the delay that you are experiencing. A work around is to use the shared runtime in your add-in. The shared runtime starts the same runtime as the task pane and it continues to run in the background even when the task pane is closed. This avoids having to start the runtime every time a ribbon button is invoked for an action. For more information, see [Configure your Office Add-in to use a shared JavaScript runtime](https://docs.microsoft.com/office/dev/add-ins/develop/configure-your-add-in-to-use-a-shared-runtime).

**For Ribbon commands, is it ever going to be possible to have multiple add-ins appear in the same group?**

This is not something we are currently focused on. Please let us know more about this scenario at https://aka.ms/m365dev-suggestions.

**Will Office.actions.associate be recognized by the Intellisense in VS Code similar to CustomFunctions.associate?**

Yes, the associate API should be recognized by Intellisense. Please be sure to have the latest [office-js type library](https://www.npmjs.com/package/@types/office-js).

**Is the new Answers Q&A forum just for users to ask questions about existing functionality?**

You can ask any technical question you need help with. We monitor both [office-js questions on Stack Overflow](https://stackoverflow.com) and the [Q&A forum](https://aka.ms/office-addins-dev-questions).

**Is it recommended to post to this newer feedback portal, stick to the M365 developer tools, or post on GitHub?**

That is exactly what we're trying to determine. If we're going to ask customers to move yet again to a new forum, we want to be sure we're going to support it! Stay tuned, we'll get there. For the moment, we're using https://aka.ms/m365dev-sugggestions.

**Will Office.auth.getAccessToken ever return a Graph API compatible token?**

We're investigating this. Ideally, we want to allow the same operations that we allow on Exchange Web Services (EWS). But there's a lot of complexity to solve to allow this. We'll let you know if we have updates. In the meantime, the recommended flow is that the server should get the Graph token using the [OAuth 2.0 On-Behalf-Of flow (OBO)](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-on-behalf-of-flow).

**This might have come up before but since mobile add-ins only support the REST API, and REST is being decommissioned this year, any Outlook add-in on mobile that relies on REST API functionality with getAccessToken is going to break when REST API goes away right? There's no support for IdentityAPI 1.3 on mobile so no getAccessToken for Graph so no auth path it can take yeah?**

For mobile, the alternative is to use Exchange Web Services (EWS). You can also request an exception at [https://aka.ms/RESTCheck](https://aka.ms/RESTCheck) that also applies to mobile. If your add-in is using REST before the November 2022 decommission date, it will be allowed to work until we end support for Office 2019.

**Does the add-in's getCallbackTokenAsync work on mobile to get a token that can be used against EWS on the server for authentication as the add-in user?**

Yes, this should work. We do have customers who have implemented a service middle tier to call EWS on environments not supporting REST (like Exchange 2013 on premise). You can also use that technique to use Microsoft Graph. This is all valid if your add-in is accessing Exchange 2013 on premise.

## References

* **AppSource Add-in Validation Improvements**
    * Documentation – [Test your Office Add-in on Internet Explorer](https://docs.microsoft.com/office/dev/add-ins/testing/ie-11-testing)
    * Documentation – [Microsoft AppSource submission FAQ](https://docs.microsoft.com/office/dev/store/appsource-submission-faq)
    * Article – [Announcing WebView2 for Office Add-ins Platform – Preview](https://devblogs.microsoft.com/microsoft365dev/announcing-webview2-for-office-add-ins-platform/)

* **Blazor in Office Add-ins (Demo)**
    * Sample – [Create a Blazor Webassembly Word add-in](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/word-blazor-add-in)
    * Videos channel – [Maarten van Stam – Soft As In Software](https://www.youtube.com/SoftAsInSoftware)
    * Twitch – [Soft As In Software](https://www.twitch.tv/softasinsoftware)

* **Add-in command changes**
    * Article – [Announcing changes to Office Add-ins’ ExecuteFunction commands](https://devblogs.microsoft.com/microsoft365dev/announcing-changes-to-office-add-ins-executefunction-commands/)
    * Samples – [Office Add-in commands](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/office-add-in-commands)
    * Documentation – [Create add-in commands in your manifest for Excel, PowerPoint, and Word](https://docs.microsoft.com/office/dev/add-ins/develop/create-addin-commands)
    * Issues – [Office Add-ins issues](https://github.com/OfficeDev/office-js/issues)

* **Community ideas**
    * Suggestions – [Microsoft 365 Developer Platform Ideas – Office Add-ins](https://aka.ms/m365dev-suggestions) \| [aka.ms/m365dev-suggestions](https://aka.ms/m365dev-suggestions)
    * Issues – [OfficeDev/office-js/issues](https://github.com/OfficeDev/office-js/issues)
    * Forum – [Microsoft 365 Developer Ideas forum](https://feedbackportal.microsoft.com/feedback)
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

* See the full blog post for this call in the Microsoft 365 and Power Platform Community Blog – <https://aka.ms/m365pnp/blog>
* Twitter – [https://twitter.com/microsoft365dev](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbkdvcDJHcGdzM2VIUkwzU3lOYkJaVFEzM0Q2QXxBQ3Jtc0ttM1NyaTQ2RjFSOFh3a0l4c1pralBRQVI1bDNSQ2RaVm9OdzJrRkdtV1Z1SW5VdmdwamNNLTBEaFdaSmZMc0lQNzdRZ2dDYV9WZVF1ZVIwc2dPQTZBRUZ3b3hoWUVJdDJoQWZUcWdCR2JKdmwtUU43RQ&q=https%3A%2F%2Ftwitter.com%2Fmicrosoft365dev)​
* Microsoft 365 Platform Community in YouTube – <https://aka.ms/m365/videos>
* Link to all Microsoft Developer Community calls – <https://aka.ms/M365DevCalls>
* Submit questions for next community call – <https://aka.ms/officeaddinsform>
* Next community call – June 8th at 08:00am PT – <https://aka.ms/officeaddinscommunitycall>

{{< attachments >}}{{< /attachments >}}
