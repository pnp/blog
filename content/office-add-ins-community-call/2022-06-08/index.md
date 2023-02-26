---
title: "Office Add-ins community call – June 8, 2022"
summary: "Microsoft roadmap for One Outlook, Outlook Smart Alerts (Demo), Using Blazor in an Excel add-in. Q&A in chat and at end of call."
date: 2022-06-13T08:01:00-05:00
author: "Sam Ramon"
githubname: samantharamon
categories: ["Office Add-in developer community call"]
images:
- images/office-add-ins-call-june-2022-recording.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://www.youtube.com/watch?v=k9k70_QQZ-Q
draft: false
---

## Call Summary

This month's community call topics:

* **Microsoft roadmap for One Outlook** – Get to know more about One Outlook, including enabling support for web add-ins and the planned timeline for preview and release – [Nikita Mittal](https://www.linkedin.com/in/nikita-mittal-92536648) – Senior Product Manager (Microsoft)
* **Microsoft Outlook Smart Alerts** – Preview how to use Outlook Smart Alerts to enable your add-in to run logic when a user sends a message or appointment – [Sam Ramon](https://github.com/samantharamon) – Technical Writer (Microsoft)
* **Using Blazor in a Microsoft Excel add-in** – Step through creating a Blazor Webassembly Excel add-in – [Maarten van Stam](http://twitter.com/aafvstam) – MVP Office Add-ins | @aafvstam
* **Community spotlight** recognizes [Maarten van Stam](http://twitter.com/aafvstam)
* **Community panels** – Join us to share your feedback on how we can provide you with a better Office Add-ins development experience
* **Q&A** – See question and answers at end of call and in chat throughout call

The call was hosted by [David Chesnut](http://twitter.com/davidchesnut) (Microsoft) | @davidchesnut. Recorded June 8, 2022.

{{< youtube k9k70_QQZ-Q >}}

## Topic summaries

* **Microsoft roadmap for One Outlook** – One Outlook is a Microsoft initiative to unify our code base, increase engineering velocity, and deliver a consistent experience across all Outlook clients. One Outlook uses the Outlook on the web code in a native frame. Our team is currently working to support web add-ins in One Outlook and are tentatively planning to preview this in July. We're aiming to request for partner feedback from July through September.
* **Microsoft Outlook Smart Alerts (demo)** – Outlook Smart Alerts is an event-based activation capability in preview that allows an add-in to run logic after a user selects Send from a message or appointment. The demo showcases an add-in which verifies that correct color categories are applied to a message or appointment based on keywords found in the item's subject and body.
* **Using Blazor in a Microsoft Excel add-in (demo)** – Blazor Webassembly allows you to build Office Add-ins using .NET, C#, and JavaScript technologies. This demo walks through how to clone the Office Add-ins sample repository and build a Blazor Webassembly Excel add-in project to create tables and bubble charts.

## Agenda

* Update - Microsoft roadmap for One Outlook - Nikita Mittal - Senior Product Manager (Microsoft) – [1:23](https://youtu.be/k9k70_QQZ-Q?t=83)
* Demo - Microsoft Outlook Smart Alerts - [Sam Ramon](https://github.com/samantharamon) - Technical Writer (Microsoft) – [7:35](https://youtu.be/k9k70_QQZ-Q?t=455)
* Demo - Using Blazor in a Microsoft Excel add-in - [Maarten van Stam](http://twitter.com/aafvstam) - MVP Office Add-ins \| @aafvstam – [15:12](https://youtu.be/k9k70_QQZ-Q?t=912)
* Community Spotlight – [32:26](https://youtu.be/k9k70_QQZ-Q?t=1946)
* Community Panels announced – [33:10](https://youtu.be/k9k70_QQZ-Q?t=1990)
* Q&A – [David Chesnut](http://twitter.com/davidchesnut) (Microsoft) \| @davidchesnut – [36:26](https://youtu.be/k9k70_QQZ-Q?t=2186)

## Actions

* Give us feedback on what you need from code samples. Join the Teams call – [Office Add-ins samples discussion](https://aka.ms/officeaddinsamples-join) – June 15, 8:00 AM PT \| <https://aka.ms/officeaddinsamples-call>
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

**Is there a way to create spell checker add-ins? We are currently trying to create some spell checkers for small languages not supported officially by Microsoft. Is there a way to include them via office.js on all platforms and applications?**

This depends on what features you want to support. For example, you can't integrate with the built-in spell checker to scan as the user types, but you can read document content, spell check it, and write document content with corrections. You can create one add-in for Word, Excel, and PowerPoint. For more information on how to configure multiple hosts in the manifest, see [Specify Office applications and API requirements](https://docs.microsoft.com/office/dev/add-ins/develop/specify-office-hosts-and-api-requirements#specify-which-office-applications-can-host-your-add-in). Also take a look at the [Script Lab manifest](https://github.com/OfficeDev/script-lab/blob/master/manifests/script-lab-react-prod.xml) which supports multiple hosts. You'll need to create a separate add-in for Outlook.

If you need more information, please let us know more about your scenario at either [Microsoft Q&A](https://aka.ms/office-addins-dev-questions) (using the ​**office-js-dev** and **office-addins-dev** tags) or [Stack Overflow](https://stackoverflow.com) (using the **office-js**, **outlook-web-addins**, and **office-scripts** tags).

**What plan is there for additional Events in Excel that will substantially improve its potential as a development platform? For example, Hyperlink clicked, Defined Name changed, Shape on-hover, etc.**

These Excel events aren't on our roadmap. Please let us know more about your scenarios for these events by creating an idea request at <https://aka.ms/m365dev-suggestions>.

**Any update on improving the Office Add-in Ideas Management system?**

Yes, we are looking to move to GitHub, but the plan isn't finalized. For now, please continue submitting ideas at the current site at <https://aka.ms/m365dev-suggestions>. We'll provide an update on the next community call.

**Will One Outlook allow you to have multiple accounts at the same time (meaning, having folders on the left pane) like Outlook desktop does? Not having that capability in OWA is the biggest drawback of OWA.**

Yes, One Outlook will allow multiple accounts to be added. The team is working on enabling this as this feature isn't currently supported in Outlook on the web (OWA).

**Will harmon.ie add-in be supported in One Outlook?**

Yes, harmon.ie has a corresponding web add-in, so it'll be supported in the One Outlook client. The feature crew is working closely with the harmon.ie team on additional capabilities to better integrate their VSTO add-in in the web add-in model.

**We have an older product that is a VSTO COM add-in for Outlook. I'm assuming that the legacy Outlook will still be available for users. Is there some time frame when One Outlook will replace the legacy Outlook client?**

There are currently no plans for One Outlook to replace the current Outlook Windows client. One Outlook will be available alongside the existing Windows client.

**For One Outlook, does the July 2022 date mean it will be on by default in the beta channel in July? I already see the option available in the beta channel right now, but it isn't toggled on by default.**

There is currently no plan to turn on One Outlook by default. We don't have a date to share at this time.

**Can you speak as to how web add-ins are going to be extended to add more features to match COM add-ins? Samples include:**

* **COM add-in that decrypts encrypted messages being viewed in the client when the email is selected. This isn't possible using web add-ins as they lack the full control of message and activation time required to achieve this.**

* **COM add-in that, when the Exchange Server goes down, the add-in takes control of retrieving email from a backup email server and inserting that into the Outlook client until the server is available again. Again, going beyond what a web add-in can do.**

We're aware that there are gaps in the features supported by web add-ins versus those supported by COM add-ins. Rest assured that we're working on making the web add-ins model richer. Regarding your first point, enabling security scenarios, including encryption, is at the top of our list. The team is working on extending our event-based approach to support this scenario. The plan is to have an event that will work upon message selection and an API to replace the contents of the message with the decrypted version, if the user has privileges. Your second sample is a scenario we're interested in exploring more. Please let us know more about this scenario by creating an idea request at <https://aka.ms/m365dev-suggestions>.

**Can you please share your view on this limitation: <https://github.com/OfficeDev/office-js/issues/2613>. It might turn out to be a huge blocker for us.**

Thank you for bringing this to our attention. We will follow up on this with our engineers, so that they can assist you further.

**Which requirement sets of Outlook JavaScript API is One Outlook targeting, e.g. Mailbox 1.8, Identity API 1.3?**

We are looking to support all Outlook JavaScript APIs in One Outlook.

**Might be a bit too specific a question, but will One Outlook still use Cached Exchange Mode? We've had issues with Outlook Desktop not syncing drafts to the server quickly enough for the add-in to access them, so wondering if anything has changed in that area.**

Because One Outlook uses Outlook on the web code in a native frame, it may not use Cached Exchange Mode. That being said, we'll take this up with our feature crew to clarify this further. Stay tuned!

**We encountered a problem when we turn off events and calculations in Excel with Office Add-in, where VBA still handles events. It looks like turning off events in VBA or Office Add-in does not do it at the Excel application level but only at the Office Add-in or VBA level.**

We're sorry to hear you've encountered an issue. Please open a [GitHub issue](https://github.com/OfficeDev/office-js/issues/new/choose) with us, so that we can assist you further.

## References

* **Microsoft Outlook Smart Alerts**
    * Documentation – [Use Smart Alerts and the OnMessageSend and OnAppointmentSend events in your Outlook add-in (preview)](https://docs.microsoft.com/office/dev/add-ins/outlook/smart-alerts-onmessagesend-walkthrough)
    * Documentation - [LaunchEvent element](https://docs.microsoft.com/javascript/api/manifest/launchevent)
    * Documentation - [Configure your Outlook add-in for event-based activation](https://docs.microsoft.com/office/dev/add-ins/outlook/autolaunch)
    * Sample - [Use Outlook Smart Alerts (preview)](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/outlook-check-item-categories)

* **Using Blazor in a Microsoft Excel add-in**
    * Sample – [Create a Blazor Webassembly Excel add-in](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/blazor-add-in/excel-blazor-add-in)
    * Samples - [Office Add-ins code samples](https://github.com/OfficeDev/Office-Add-in-samples)
    * Documentation - [Office Add-ins platform overview](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)
    * Videos channel – [Maarten van Stam – Soft As In Software](https://www.youtube.com/SoftAsInSoftware)
    * Twitch – [Soft As In Software](https://www.twitch.tv/softasinsoftware)
    * Blog - [Soft As In Software blog](https://blog.softasinsoftware.com/)
    * Website - [Maarten van Stam – Soft As In Software](https://www.softasinsoftware.com/)

## General resources

* [Office developer center](https://developer.microsoft.com/office)

## Stay connected

* See the full blog post for this call in the Microsoft 365 and Power Platform Community Blog – <https://aka.ms/m365pnp/blog>
* Follow us on Twitter – <https://twitter.com/microsoft365dev>
* Microsoft 365 Platform Community on YouTube – <https://aka.ms/m365/videos>
* All Microsoft Developer Community calls – <https://aka.ms/M365DevCalls>
* Submit questions about add-ins development for our next community call – <https://aka.ms/officeaddinsform>
* Next community call – July 13th at 8:00 AM PT – <https://aka.ms/officeaddinscommunitycall>

{{< attachments >}}
