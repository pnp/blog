---
title: "Microsoft 365 & Power Platform Community Call - 28th of March, 2023"
summary: "Demos: SPFx v1.17 release - what's new and what's there, Kiota SDK generator is now available - What you need to know!, Deploy a Microsoft Teams app to Azure using Teams Toolkit for Visual Studio Code, plus 16 docs, 3 conversations."
date: 2023-03-29T02:00:00.000Z
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 platform call"]
images:
- images/recording-28th-march.png
tags: []
type: regular
videos:
- https://www.youtube.com/watch?v=5YfG-9pjiic
draft: false
---

## Call summary

Welcome to the weekly call focused on capabilities of the Microsoft 365 and Power Platform.  In this call, we highlight recently announced and key existing developer resources, news, community events and three demos.

### New this week

* Announcements
    * Agenda set for next [Microsoft 365 & Power Platform weekly call](https://aka.ms/m365-dev-call) - Tuesday, April 4th, 8:00 am PT.
        * Latest news from Microsoft engineering on Microsoft 365 topics
        * **Bob German** – Build a Teams Meeting app with Live Share SDK - Who's Next sample
        * **Rajdeep Chanda, Harshit Kumar** and **Mahesh Singhania** – Latest on the Microsoft Graph Connectors
        * **To be announced** – Microsoft Graph Hackathon - Winner demo \#1
    * Article – [Introducing Microsoft 365 Copilot—A whole new way to work](https://www.microsoft.com/microsoft-365/blog/2023/03/16/introducing-microsoft-365-copilot-a-whole-new-way-to-work) - Colette Stallbaumer (Microsoft)
    * Article – [Microsoft Business Applications Launch Event, April 4](https://msbizappslaunchevent.eventcore.com/home) - Microsoft
    * Article – [Announcing SharePoint Framework 1.17 release candidate](https://devblogs.microsoft.com/microsoft365dev/announcing-sharepoint-framework-1-17-release-candidate/) - [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen
    * Article – [Build custom communication experiences with Azure Communication Services UI Library for Microsoft Teams users](https://devblogs.microsoft.com/microsoft365dev/build-custom-communication-experiences-with-azure-communication-services-ui-library-for-microsoft-teams-users/) - [David de Matheu](https://twitter.com/ddematheu) (Microsoft) \| @ddematheu
    * Article – [Teams Toolkit for Visual Studio Code update – March 2023](https://devblogs.microsoft.com/microsoft365dev/teams-toolkit-for-visual-studio-code-update-march-2023/) - Junjie Li (Microsoft)
    * Article – [Updated public preview of SharePoint Framework 1.17 – Preview on upcoming features](https://devblogs.microsoft.com/microsoft365dev/updated-public-preview-of-sharepoint-framework-1-17-preview-on-upcoming-features/) - [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen
    * Article – [Avatars for Microsoft Teams in Public Preview](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/avatars-for-microsoft-teams-in-public-preview/ba-p/3774421) - Avery Salumbides (Microsoft)
    * Article – [Introducing the new Microsoft Teams, now in preview](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-the-new-microsoft-teams-now-in-preview/ba-p/3774406) - [Anupam Pattnaik](https://twitter.com/pattnaikanupam) (Microsoft) \| @pattnaikanupam
    * Article – [What’s New in Microsoft Teams at Enterprise Connect 2023](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/what-s-new-in-microsoft-teams-at-enterprise-connect-2023/ba-p/3774374) - Steven Stein (Microsoft)
    * Article – [Microsoft Teams: Advantages of the new architecture](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-advantages-of-the-new-architecture/ba-p/3775704) - Sumi Singh (Microsoft)
    * Article – [The business value of investing in employee growth](https://techcommunity.microsoft.com/t5/microsoft-viva-blog/the-business-value-of-investing-in-employee-growth/ba-p/3775929) - Andrea Lum (Microsoft)
    * Article – [Viva Sales at Teleperformance](https://techcommunity.microsoft.com/t5/microsoft-viva-blog/viva-sales-at-teleperformance/ba-p/3770091) - Smita Shrivastava (Microsoft)
    * Article – [What's New in Viva Sales – March 2023](https://techcommunity.microsoft.com/t5/microsoft-viva-blog/what-s-new-in-viva-sales-march-2023/ba-p/3775271) - David Shin (Microsoft)
    * Article – [What’s Next for SharePoint](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/what-s-next-for-sharepoint/ba-p/3776866) - [Adam Harmetz](https://twitter.com/adamharmetz) (Microsoft) \| @adamharmetz
    * Article – [The SharePoint storage platform supports the Loop app - Components, pages, and workspaces](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/the-sharepoint-storage-platform-supports-the-loop-app-components/ba-p/3772852) - [Zach Rosenfield](https://twitter.com/Zrosenfield) (Microsoft) \| @Zrosenfield
    * [Microsoft 365 Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery/) has 1527 samples now! aka.ms/m365/samples
* Shows and Events
    * Build once, deploy efficiently, connect across Microsoft 365 – Virtual event. March 29, 2023, 9:00AM PST. [Register](https://aka.ms/BuildwithTeams)
    * Microsoft 365 Conference – May 2 – 4. 2023, Las Vegas – m365Con.com - [Register](https://m365conf.com/)
    * European Collaboration Summit 2023 – May 24 – 26, 2023 – Düsseldorf – collabsummit.eu – [Register](https://www.collabsummit.eu/)
    * ACT NOW – save €300 on tickets for the [European Power Platform Conference](https://www.sharepointeurope.com/european-power-platform-conference) – Dublin, 20-23 June
    * 365 EduCon - Use promo code “Community” to save 25% off any pass type.
        * [Washington DC](https://techcon365.com/DC/) – June 12-16, 2023
        * [Seattle](https://techcon365.com/Seattle/) – August 21-25, 2023 & PWR EduCon
        * [Chicago](https://techcon365.com/Chicago/) – October 30 – November 3, 2023
    * Upcoming [Community Days](https://communitydays.org/) Events - aka.ms/communitydays
* Conversations
    * Microsoft 365 PnP Weekly – Episode 203 with by Germany-based Microsoft MVP, Developer, Consultant - [Luise Freese](https://twitter.com/LuiseFreese) \| @LuiseFreese (March 27th) \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-203/) \| [podcast](https://www.podbean.com/eas/pb-e56dm-13ca5ec)
    * Microsoft 365 Developer Podcast – User Interfaces and Accessibility with Stefan Bauer (March 21st ) \| [podcast](https://m365devpodcast.com/e/user-interfaces-and-accessibility-with-stefan-bauer/)
    * Power Platform Connections - Power Platform Connections Ep 6 - Shane Young (March 24th) \| [video](https://www.youtube.com/watch?v=v6mifi35_SQ)

### Demos

* **SPFx v1.17 release - what's new and what's there** – a direction update on SPFx and extensibility platform for Microsoft 365. SPFx v1.17 capabilities reviewed include: Use TeamsJS SDK v2.9.1, OS variable now in serve.json configuration, web part TopActions, Sync to Teams, Action handler for ACE, focus parameters in ACE quick view, and Adaptive Cards v1.5 schema support. Beyond v1.17 capabilities also described.
* **Kiota SDK generator is now available - What you need to know!** – Kiota is GA. It is presently being rolled into Graph Explorer and into a VS Code Extension. Kiota enables you to create and add a powerful, super specific API client to work inside your application. See how a package is created and added to your solution by stepping through a scenario to sync PRs from GitHub (a single endpoint) right into your Microsoft ToDo app.
* **Deploy a Microsoft Teams app to Azure using Teams Toolkit for Visual Studio Code** – you’ve built an awesome app on your local machine, now it’s time to move it to a remote environment to validate and share with others. The move is streamlined with 3 Toolkit features - provision to cloud, deploy to cloud, and publishing to your organization. In this example a simple tab app makes its way to the Teams admin portal and can be added to Teams.

The host of this call was [Vesa Juvonen](http://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen. Q&A takes place in chat throughout the call.

{{< youtube 5YfG-9pjiic >}}

## Agenda items

[00:00](https://youtu.be/5YfG-9pjiic?t=0) – Intro

[10:08](https://youtu.be/5YfG-9pjiic?t=608) – Latest updates – news across the Microsoft blogs – [Vesa Juvonen](http://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[11:33](https://youtu.be/5YfG-9pjiic?t=693) – Together mode picture

[12:58](https://youtu.be/5YfG-9pjiic?t=778) – Demo – SPFx v1.17 release - what's new and what's there – Luca Bandinelli (Microsoft) & [Alex Terentiev](https://twitter.com/alexaterentiev) (Microsoft) \| @alexaterentiev

[28:12](https://youtu.be/5YfG-9pjiic?t=1692) – Demo – Kiota SDK generator is now available - What you need to know! – [Sébastien Levert](https://twitter.com/sebastienlevert) (Microsoft) \| @sebastienlevert

[43:27](https://youtu.be/5YfG-9pjiic?t=2607) – Demo – Deploy a Microsoft Teams app to Azure using Teams Toolkit for Visual Studio Code – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[54:46](https://youtu.be/5YfG-9pjiic?t=3286) – Closing

Thank you for your creativity and work execution. Samples are often showcased in Demos.

## Together Mode

![together-230328.png](images/together-230328.png)

As always, it's awesome to have you on the call.  Idyllic - seated in the virtual amphitheater on a nice sunny day, birds chirping, smiling faces and much waving.

## Actions

* March 29, 2023, 9:00AM PST. Build once, deploy efficiently, connect across Microsoft 365 – Virtual event. [Register](https://aka.ms/BuildwithTeams)
* [Request to Present a demo](https://aka.ms/community/request/demo) during Microsoft 365 & Power Platform community calls - aka.ms/community/request/demo
* [Register](http://www.communitydays.org) for an Upcoming Event around Microsoft 365 and Power Platform advertised on the Community Days site.
* Community call agendas are published each week at aka.ms/community/meetup
* Opt into PnP Recognition Program – aka.ms/m365pnp-recognition
* Register for upcoming [Sharing Is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Power Platform Samples Contributor \| Monday, April 10th, 11:00am PT \| 2:00pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
    * Maturity Model Practitioners \| Tuesday, April 18th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) with more than 1400 samples from Microsoft and community.
* Download the recurrent invite for this call – aka.ms/m365-dev-call

## Demo references

* **SPFx v1.17 release - what's new and what's there**
    * Article – [Announcing SharePoint Framework 1.17 release candidate](https://devblogs.microsoft.com/microsoft365dev/announcing-sharepoint-framework-1-17-release-candidate/) - [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen
* **Kiota SDK generator is now available - What you need to know!**
    * Repo – [Project Kiota](https://github.com/microsoft/kiota) \| aka.ms/kiota
    * Documentation - [Welcome to Kiota](https://learn.microsoft.com/openapi/kiota/) \| <https://learn.microsoft.com/openapi/kiota/>
    * Documentation - [Get started with Kiota](https://learn.microsoft.com/openapi/kiota/) \| aka.ms/get/kiota
    * APIs – [APIs.guru](https://apis.guru/) \| <https://apis.guru/>
* **Deploy a Microsoft Teams app to Azure using Teams Toolkit for Visual Studio Code**
    * Training - [Build and deploy apps for Microsoft Teams using Teams Toolkit for Visual Studio Code](https://learn.microsoft.com/training/paths/m365-teams-toolkit-vsc/) \| aka.ms/learn/teamstoolkit
    * Documentation – [Teams Toolkit Overview](https://learn.microsoft.com/microsoftteams/platform/toolkit/teams-toolkit-fundamentals?pivots=visual-studio-code) \| <https://learn.microsoft.com/microsoftteams/platform/toolkit/teams-toolkit-fundamentals?pivots=visual-studio-code>
    * Documentation – [Teams JavaScript client library](https://learn.microsoft.com/microsoftteams/platform/tabs/how-to/using-teams-client-library) \| <https://learn.microsoft.com/microsoftteams/platform/tabs/how-to/using-teams-client-library>
    * Documentation - [people module](https://learn.microsoft.com/javascript/api/@microsoft/teams-js/people) \| <https://learn.microsoft.com/javascript/api/@microsoft/teams-js/people>
    * Documentation - [chat module](https://learn.microsoft.com/javascript/api/@microsoft/teams-js/chat) \| <https://learn.microsoft.com/javascript/api/@microsoft/teams-js/chat>
    * Previous demos in this series
        * Demo 4 - [Add chat capability to Microsoft Teams app using Teams JavaScript client library](https://youtu.be/FWRTaK_wAhs?t=2405) – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder (3/21)
        * Demo 3 - [Teams Toolkit Learn Path - Build a Microsoft Teams tab app using Teams Toolkit for Visual Studio Code](https://youtu.be/ZkD768EM-J4?t=1646) – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder (3/7)
        * Demo 2 – [Teams Toolkit Learn Path - Build a bot using Teams Toolkit for Visual Studio Code](https://youtu.be/77u73mD9MKE?t=1711) - [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder - (2/28)
        * Demo 1 – [Teams Toolkit Learn Path – Get started building apps for Microsoft Teams using Teams Toolkit for Visual Studio Code](https://youtu.be/yIm_rsKt4kE?t=1864) - [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder – (2/21)

## General resources

* Archives - Microsoft 365 PnP Weekly - [Videos](https://www.youtube.com/playlist?list=PLR9nK3mnD-OVYI-St_CBiFfuL4CZbBpkC), [Podcasts](https://pnpweekly.podbean.com/)
* Microsoft Teams Toolkit | [https://aka.ms/teams-toolkit](https://aka.ms/teams-toolkit)
* Microsoft Graph Toolkit in Microsoft Learn | [https://aka.ms/learn-mgt](https://aka.ms/learn-mgt)
* Viva Connections [https://aka.ms/VivaConnections](https://aka.ms/VivaConnections)
* [SharePoint look book](https://lookbook.microsoft.com/?WT.mc_id=m365-24198-cxa)
* [Yo Teams video training package](https://aka.ms/yoteams-training)
* [.NET Standard 2.0 version of SharePoint Online CSOM API](https://developer.microsoft.com/microsoft-365/blogs/net-standard-version-of-sharepoint-online-csom-apis?WT.mc_id=m365-24198-cxa)
* [Microsoft 365 Platform Community (PnP) videos](https://aka.ms/m365/videos) | aka.ms/m365/videos
* [Microsoft Teams Toolkit for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension)
* [yo Teams](https://aka.ms/yoteams) | aka.ms/yoteams
* [SPFx Developer documentation](https://aka.ms/spfx) | <https://aka.ms/spfx>
* [Microsoft 365 developer program site](https://developer.microsoft.com/office/dev-program?WT.mc_id=m365-24198-cxa) - Need to become a Tenant Admin to test look book capabilities? Get a Microsoft 365 E5 developer subscription - free tenant for 90 days with automatic renewal if used for dev purposes

## Upcoming Calls | Recurrent Invites

* Microsoft 365 & Power Platform Dev call \| Thursday, March 30, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Microsoft 365 platform call \| Tuesday, April 4, 8:00 am PT - <https://aka.ms/m365-dev-call> (weekly)
* Viva Connections & SharePoint Framework call \| Thursday, April 6, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Office add-in monthly call \| Wednesday, April 12, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Power Platform monthly call \| Wednesday, April 19, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, April 20, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

Microsoft 365 Platform community call focuses on latest Microsoft 365 Platform updates and demos delivered by Microsoft presenters and takes place weekly on Tuesday.  The alternating Special Interest Group community calls each Thursday focus on SharePoint Framework (client-side development/implementation) and Microsoft 365 Platform (includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, PowerApps, Column Formatting, list formatting, etc. topics.) with demos commonly delivered by community members.

More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp).

You can download recurrent invite for this call from [https://aka.ms/m365-dev-call](https://aka.ms/m365-dev-call).  Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments to this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/sppnp).


&quot;_Sharing is caring&quot;_

_Microsoft 365 Platform Community team, Microsoft - 28th of March 2023_

{{< attachments >}}{{< /attachments >}}
