---
title: "Microsoft 365 & Power Platform Community Call - 4th of April, 2023"
summary: "Demos: Build a Teams Meeting app with Live Share SDK - Who's Next sample, Latest on the Microsoft Graph Connectors, and Contributing to Microsoft Graph .NET SDK for improved batching, plus 10 articles, 3 conversations."
date: 2023-04-04T02:00:00.000Z
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 platform call"]
images:
- images/recording-4th-april.png
tags: []
type: regular
videos:
- https://www.youtube.com/watch?v=1rnspoFtjt4
draft: false
---

## Call summary

Welcome to the weekly call focused on capabilities of the Microsoft 365 and Power Platform.  In this call, we highlight recently announced and key existing developer resources, news, community events and three demos.

### New this week

* Announcements
    * Agenda set for next [Microsoft 365 & Power Platform weekly call](https://aka.ms/m365-dev-call) - Tuesday, April 11th, 8:00 am PT.
        * Latest news from Microsoft engineering on Microsoft 365 topics
        * **Ayca Bas & Garry Trinder** – Announcing Teams toolkit cloud skill challenge
        * **To be announced** – Microsoft Graph Hackathon - Winner demo \#2
        * **John Miller** – Latest on the Microsoft Teams Toolkit
    * Article - [Announcing SharePoint Framework 1.17 with updates for Microsoft Teams, Microsoft Viva and SharePoint](https://devblogs.microsoft.com/microsoft365dev/announcing-sharepoint-framework-1-17-with-updates-for-microsoft-teams-microsoft-viva-and-sharepoint/) – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen
    * Article – [Skype for Business usage reports deprecation in Microsoft Graph production and beta endpoints](https://devblogs.microsoft.com/microsoft365dev/skype-for-business-usage-reports-deprecation-in-microsoft-graph-production-and-beta-endpoints/) – Microsoft Graph Team
    * Article – [Top five AppSource validation errors for Office Add-ins submissions – March 2023](https://devblogs.microsoft.com/microsoft365dev/top-five-appsource-validation-errors-for-office-add-ins-submissions-march-2023/) - Microsoft
    * Article – [Announcing the Hack Together: Microsoft Graph and .NET winners](https://devblogs.microsoft.com/microsoft365dev/announcing-the-hack-together-microsoft-graph-and-net-winners/) - [Ayça Baş](https://twitter.com/aycabs) (Microsoft) \| @aycabs & [Waldek Mastykarz](https://twitter.com/waldekm) (Microsoft) \| @waldekm
    * Article – [Microsoft Graph Developer Proxy v0.6 with monitoring, rate limiting and paging guidance](https://devblogs.microsoft.com/microsoft365dev/microsoft-graph-developer-proxy-v0-6-monitoring-rate-limiting-paging-guidance/) - [Sébastien Levert](https://twitter.com/sebastienlevert) (Microsoft) \| @sebastienlevert & [Waldek Mastykarz](https://twitter.com/waldekm) (Microsoft) \| @waldekm
    * Article – [Build once, deploy efficiently, connect across Microsoft 365](https://devblogs.microsoft.com/microsoft365dev/build-once-deploy-efficiently-connect-across-microsoft-365/) - [Daniel Carrasco](https://twitter.com/danielserver) (Microsoft) \| @danielserver
    * Article – [Create a Teams tab and Outlook Add-in with a Hello World project](https://devblogs.microsoft.com/microsoft365dev/create-a-teams-tab-and-outlook-add-in-with-a-hello-world-project/) - [Rabia Williams](https://twitter.com/williamsrabia) (Microsoft) \| @williamsrabia
    * Article – [SharePoint Roadmap Pitstop: March 2023](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/sharepoint-roadmap-pitstop-march-2023/ba-p/3785694) - [Mark Kashman](https://twitter.com/mkashman) (Microsoft) \| @mkashman
    * Article – [The Service That SharePoint Built – a cumulative evolution story](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/the-service-that-sharepoint-built-a-cumulative-evolution-story/ba-p/3780245) - [Mark Kashman](https://twitter.com/mkashman) (Microsoft) \| @mkashman
    * Article – [Microsoft 365 Conference event guide to keynotes, AMA, sessions, and more](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/microsoft-365-conference-event-guide-to-keynotes-ama-sessions/ba-p/3780314) - [Mark Kashman](https://twitter.com/mkashman) (Microsoft) \| @mkashman
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
    * Microsoft 365 PnP Weekly – Episode 204 (April 3rd) with by Sweden-based Microsoft MVP and CTO at Rencore - [Erwin van Hunen](https://twitter.com/erwinvanhunen) \| @erwinvanhunen \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-204/) \| [podcast](https://www.podbean.com/eas/pb-2jgsw-13d3aee)
    * Microsoft 365 Developer Podcast – Partner showcase: Syskit with Hrvoje Bagaric (April 3rd) \| [podcast](https://m365devpodcast.com/e/partner-showcase-syskit-with-hrvoje-bagaric/)
    * Power Platform Connections - Power Platform Connections Ep 7 - Dian Taylor (March 31st) \| [video](https://www.youtube.com/watch?v=5GEEhSSgMDo&t=65s)

### Demos

* **Build a Teams Meeting app with Live Share SDK - Who's Next sample** – a simple Tab app solution that uses Live Share SDK, Teams Toolkit and Fluid UI. When in a meeting, any participant can (in side panel) add/delete themselves to the who’s next to speak queue, that immediately renders (Fluid) on all other participants screens. Low/no permissions requirement to use. Step through code – manifest, React app, the fluidLiveShare component, and the connection to the LiveShare SDK/host.
* **Latest on the Microsoft Graph Connectors** – get a brief introduction to Microsoft Search & Graph connectors, latest GA and Preview releases from Graph connectors, content through Cloud SSA to Graph connectors (cloud hybrid search), and the availability of Graph connectors in Teams mobile and iOS devices. Viewers views on Cloud SSA and on how Teams content can be brought into Microsoft Search from Teams mobile devices is requested.
* **Contributing to Microsoft Graph .NET SDK for improved batching** – preface from Waldek Mastykarz on this Hackathon entry that no less than improved the Graph SDK itself! Author’s approach: Extend the SDK so everyone can start using the new batching endpoint and at the same time, fix Blazor web assembly templates to get along with the Graph SDK for .NET v5. See measurable performance improvements adding/deleting 10 items to a ToDo task list with and without batching.

The host of this call was [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen. Q&A takes place in chat throughout the call.

{{< youtube 1rnspoFtjt4 >}}

## Agenda items

[00:00](https://youtu.be/1rnspoFtjt4?t=0) – Intro

[11:18](https://youtu.be/1rnspoFtjt4?t=678) – Latest updates – news across the Microsoft blogs – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[13:18](https://youtu.be/1rnspoFtjt4?t=798) – Together mode picture

[14:25](https://youtu.be/1rnspoFtjt4?t=865) – Demo – Build a Teams Meeting app with Live Share SDK - Who's Next sample – [Bob German](https://twitter.com/Bob1German) (Microsoft) \| @Bob1German

[27:30](https://youtu.be/1rnspoFtjt4?t=1650) – Demo – Latest on the Microsoft Graph Connectors – Rajdeep Chanda (Microsoft)

[37:57](https://youtu.be/1rnspoFtjt4?t=2277) – Demo – Contributing to Microsoft Graph .NET SDK for improved batching – [Stephan van Rooij](https://twitter.com/svrooij) (Smartersoft B.V.) \| @svrooij

[50:57](https://youtu.be/1rnspoFtjt4?t=3057) – Closing

Thank you for your creativity and work execution. Samples are often showcased in Demos.

## Together Mode

![together-230404.png](images/together-230404.png)

A lot of familiar faces, the room is packed, great smiles, thank you for joining, awesome seeing you today.

## Actions

* [Request to Present a demo](https://aka.ms/community/request/demo) during Microsoft 365 & Power Platform community calls - aka.ms/community/request/demo
* [Register](https://www.communitydays.org) for an Upcoming Event around Microsoft 365 and Power Platform advertised on the Community Days site.
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

* **Build a Teams Meeting app with Live Share SDK - Who's Next sample**
    * Sample Repo - [How to use this Who's Next In-meeting app](https://github.com/OfficeDev/TeamsFx-Samples/tree/dev/whos-next-meeting-app) \| aka.ms/who-is-next
    * Article – Build a "Who's Next" Teams meeting app with Fluid Framework and the Live Share SDK \| aka.ms/who-is-next-article
    * Video - [Build a "Who's Next" Teams Meeting app](https://www.youtube.com/watch?v=rHnd4g8uLTA) \| aka.ms/who-is-next-video
    * Documentation - [Live Share SDK](https://learn.microsoft.com/microsoftteams/platform/apps-in-teams-meetings/teams-live-share-overview?tabs=javascript)
* **Latest on the Microsoft Graph Connectors**
    * Survey - [Cloud SSA](https://forms.office.com/r/FQs5XaMrmG)
* **Contributing to Microsoft Graph .NET SDK for improved batching**
    * Live Tool - [Blazor Graph Explorer](https://blazor-explorer.svrooij.io/)
    * Repo – [BlazorGraphExplorer](https://github.com/svrooij/BlazorGraphExplorer)
    * Hackathon Entry - [SvRooij.Graph.Batching](https://github.com/svrooij/msgraph-sdk-dotnet-batching)
    * Article - [Batching with Microsoft Graph](https://svrooij.io/2023/03/03/batching-in-microsoft-graph/)
    * Documentation - [Combine multiple requests in one HTTP call using JSON batching](https://learn.microsoft.com/graph/json-batching)
    * SDK - [Microsoft Graph .NET Core Client Library](https://github.com/microsoftgraph/msgraph-sdk-dotnet-core)

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

* Viva Connections & SharePoint Framework call \| Thursday, April 6, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft 365 platform call \| Tuesday, April 11, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Office add-in monthly call \| Wednesday, April 12, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Microsoft 365 & Power Platform Dev call \| Thursday, April 13, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Power Platform monthly call \| Wednesday, April 19, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, April 20, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

Microsoft 365 Platform community call focuses on latest Microsoft 365 Platform updates and demos delivered by Microsoft presenters and takes place weekly on Tuesday.  The alternating Special Interest Group community calls each Thursday focus on SharePoint Framework (client-side development/implementation) and Microsoft 365 Platform (includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, PowerApps, Column Formatting, list formatting, etc. topics.) with demos commonly delivered by community members.

More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp).

You can download recurrent invite for this call from [https://aka.ms/m365-dev-call](https://aka.ms/m365-dev-call).  Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments to this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/sppnp).


&quot;_Sharing is caring&quot;_

_Microsoft 365 Platform Community team, Microsoft - 4th of April 2023_

{{< attachments >}}{{< /attachments >}}
