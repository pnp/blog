---
title: "Microsoft 365 & Power Platform Community Call - 7th of March, 2023"
summary: "Demos: Microsoft Graph Hackathon – first week recap, Dynamically Create an Azure Communication Services Identity and Token, and Teams Toolkit Learn Path - Build a Microsoft Teams tab app using Teams Toolkit for Visual Studio Code, plus 10 articles, 2 conversations."
date: 2023-03-07T03:00:00.000Z
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 platform call"]
images:
- images/recording-7th-mar.png
tags: []
type: regular
videos:
- https://www.youtube.com/watch?v=ZkD768EM-J4
draft: false
---

## Call summary

Welcome to the weekly call focused on capabilities of the Microsoft 365 platform.  In this call, we highlight recently announced and key existing developer resources, news, community events and three demos.

### New this week

* Announcements
    * **Join the fun** - Microsoft Graph and .NET – March Hack Together – March 1st to 15th - aka.ms/hack-together - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR0ktYAUCTtVIvJkJdFsfkalUMlM0SVBXRjIyTEFJQVFYOUMzTDE2SEY1WS4u)
    * Agenda set for next [Microsoft 365 & Power Platform weekly call](https://aka.ms/m365-dev-call) - Tuesday, March 14th, 8:00 am PT.
        * Latest news from Microsoft engineering on Microsoft 365 topics
        * Demo - **Waldek Mastykarz** – Microsoft Graph Hackathon – Recap on the second week
        * Demo - **Gary Pretty**– Power Virtual Agents – latest features and capabilities to get started within Microsoft Teams
        * Demo - **Dan Wahlin** – Deploying the Azure Communications Services Application to Azure
        * Article – [Microsoft Graph Developer Proxy v0.5 with execution summary and recording mode](https://devblogs.microsoft.com/microsoft365dev/microsoft-graph-developer-proxy-v0-5/) - [Waldek Mastykarz](https://twitter.com/waldekm) (Microsoft) \| @waldekm and [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder
    * Article – [Hack Together: Microsoft Graph and .NET week 1 recap and what’s coming](https://devblogs.microsoft.com/microsoft365dev/hack-together-microsoft-graph-and-dotnet-week-1-recap/) - [Waldek Mastykarz](https://twitter.com/waldekm) (Microsoft) \| @waldekm
    * Article – [Teams Toolkit for Visual Studio Code v5.0 pre-release](https://devblogs.microsoft.com/microsoft365dev/teams-toolkit-for-visual-studio-code-v5-0-prerelease/) – Ji Dong (Microsoft)
    * Article – [New Microsoft Graph Planner API capabilities now available](https://devblogs.microsoft.com/microsoft365dev/new-microsoft-planner-api-capabilities-now-available-in-microsoft-graph/) - Andrew Friedman (Microsoft), Brijesh Bharadwaj (Microsoft), and Tarkan Sevilmis (Microsoft)
    * Article – [Introducing apps in Microsoft Teams channel meetings general availability](https://devblogs.microsoft.com/microsoft365dev/introducing-apps-in-microsoft-teams-channel-meetings-general-availability/) – Gino Buzzelli (Microsoft)
    * Article – [Introducing Closed Captions in PowerPoint Live for Microsoft Teams Meetings](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-closed-captions-in-powerpoint-live-for-microsoft/ba-p/3759269) - Alexis Johnston (Microsoft)
    * Article – [Rapidly deploy Microsoft Teams at scale to empower your frontline workforce](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rapidly-deploy-microsoft-teams-at-scale-to-empower-your/ba-p/3755253) - Rahul Dey (Microsoft)
    * Article – [What’s New in Microsoft Teams \| February 2023](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/what-s-new-in-microsoft-teams-february-2023/ba-p/3755049) – Steven Stein (Microsoft)
    * Article – [SharePoint Roadmap Pitstop: February 2023](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/sharepoint-roadmap-pitstop-february-2023/ba-p/3755315) – [Mark Kashman](https://twitter.com/mkashman) (Microsoft) \| @mkashman
    * Article – [Build solutions faster with Microsoft Power Platform and next-generation AI](https://cloudblogs.microsoft.com/powerplatform/2023/03/06/build-solutions-faster-with-microsoft-power-platform-and-next-generation-ai) - Richard Riley (Microsoft)
    * Training next week - Power Platform Samples Contributor \| Wednesday, March 15th, 10:00am PT \| 1:00pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
* Teams Platform updates
    * Documentation - [Five steps to drive adoption of your app](https://learn.microsoft.com/microsoftteams/platform/promote-app-adoption)
* Shows and Events
    * Microsoft 365 Conference – May 2 – 4. 2023, Las Vegas – m365Con.com - [Register](https://m365conf.com/)
    * European Collaboration Summit 2023 – May 24 – 26, 2023 – Düsseldorf – collabsummit.eu – [Register](https://www.collabsummit.eu/)
    * ACT NOW – save €300 on tickets for the [European Power Platform Conference](https://www.sharepointeurope.com/european-power-platform-conference) – Dublin, 20-23 June
    * 365 EduCon - Use promo code “Community” to save 25% off any pass type.
        * [Washington DC](http://www.365educon.com/dc) – June 12-16, 2023
        * [Seattle](http://www.365educon.com/seattle) – August 21-25, 2023 & PWR EduCon
        * [Chicago](http://www.365educon.com/chicago) – October 30 – November 3, 2023
    * Upcoming [Community Days](https://communitydays.org/) Events - aka.ms/communitydays
* Conversations
    * Microsoft 365 PnP Weekly – Episode 200 (March 6th) with hossts [Sébastien Levert](https://twitter.com/sebastienlevert) (Microsoft) \| @sebastienlevert, [Vesa Juvonen](http://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen and [Waldek Mastykarz](http://twitter.com/waldekm) (Microsoft) \| @waldekm \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-200/) \| [podcast](https://www.podbean.com/eas/pb-cuzet-13ad58a)
    * Power Platform Connections - Power Platform Connections Ep 3 - Heidi Jordan (March 2nd) \| [video](https://www.youtube.com/watch?v=2kKFDT9aw5w&t)

### Demos

* **Microsoft Graph Hackathon – Recap of the first week** – launched on March 1st – this 15-day virtual hackathon includes training, keynote speakers, ask the experts, and an opportunity to submit an app built using Microsoft Graph, .NET and the Microsoft Graph .NET SDK, to qualify for prizes and a Credly badge. You or your team (up to 4 persons) are invited to participate. You have until March 15th to submit your app.
* **Dynamically Create an Azure Communication Services Identity and Token** – understand how does my external customer get a token that enables them to join my Teams meeting through ACS? Learn about the integrations between ACS, Teams and Azure functions. Use an Azure function (ACSTokenFunction) called from client’s React app, to make a dynamic ACS identity and token. Walk through the code and see the result in action. This is the 5th demo in this series.
* **Teams Toolkit Learn Path - Build a Microsoft Teams tab app using Teams Toolkit for Visual Studio Code** – create a new Teams app that contains a tab. The Teams Toolkit enables you to build a half dozen different tab experiences with React based project templates. Covered in this session – tabs and Toolkit overviews, themes, router, app manifest, Toolkit installation, configuration, app and tab template selection. Walk through the scaffolded project code. This is the 3rd demo in this series.

The host of this call was [Vesa Juvonen](http://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen. Q&A takes place in chat throughout the call.

{{< youtube ZkD768EM-J4 >}}

## Agenda items

[00:00](https://youtu.be/ZkD768EM-J4?t=0) – Intro

[08:02](https://youtu.be/ZkD768EM-J4?t=482) – Latest updates - events and news on the Microsoft 365 platform – [Vesa Juvonen](http://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[10:54](https://youtu.be/ZkD768EM-J4?t=654) – Microsoft Teams Platform updates – [Wajeed Shaikh](https://twitter.com/Wajeed_Shaikh) (Microsoft) \| @Wajeed_Shaikh

[12:15](https://youtu.be/ZkD768EM-J4?t=735) – Together mode picture

[13:18](https://youtu.be/ZkD768EM-J4?t=798) – Demo –Microsoft Graph Hackathon – Recap of the first week – [Waldek Mastykarz](https://twitter.com/waldekm) (Microsoft) \| @waldekm

[16:33](https://youtu.be/ZkD768EM-J4?t=993) – Demo – Dynamically Create an Azure Communication Services Identity and Token – [Ayça Baş](https://twitter.com/aycabs) (Microsoft) \| @aycabs

[27:26](https://youtu.be/ZkD768EM-J4?t=1646) – Demo –Teams Toolkit Learn Path - Build a Microsoft Teams tab app using Teams Toolkit for Visual Studio Code – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[48:36](https://youtu.be/ZkD768EM-J4?t=2916) – Closing

Thank you for your creativity and work execution. Samples are often showcased in Demos.

## Together Mode

![together-230307.png](images/together-230307.png)

Thanks everyone for joining the call once again today. Great to see many new and familiar faces. Keep the feedback coming.

## Actions

* [Request to Present a demo](https://aka.ms/community/request/demo) during Microsoft 365 & Power Platform community calls - aka.ms/community/request/demo
* [Register](http://www.communitydays.org) for an Upcoming Event around Microsoft 365 and Power Platform.
* Community call agendas are published each week at aka.ms/community/meetup
* Opt into PnP Recognition Program – aka.ms/m365pnp-recognition
* Register for upcoming [Sharing Is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Power Platform Samples Contributor \| Wednesday, March 15th, 10:00am PT \| 1:00pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
    * Maturity Model Practitioners \| Tuesday, March 21st, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) with more than 1400 samples from Microsoft and community.
* Download the recurrent invite for this call – aka.ms/m365-dev-call

## Demo references

* **Microsoft Graph Hackathon – Recap of the first week**
    * Repo - [Hack Together: Microsoft Graph and .NET](https://github.com/microsoft/hack-together) \| aka.ms/hack-together
    * Register - [Hack Together: Microsoft Graph and .NET](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR0ktYAUCTtVIvJkJdFsfkalUMlM0SVBXRjIyTEFJQVFYOUMzTDE2SEY1WS4u)
    * Article – [Hack Together: Microsoft Graph and .NET week 1 recap and what’s coming](https://devblogs.microsoft.com/microsoft365dev/hack-together-microsoft-graph-and-dotnet-week-1-recap/) - [Waldek Mastykarz](https://twitter.com/waldekm) (Microsoft) \| @waldekm
* **Dynamically Create an Azure Communication Services Identity and Token**
    * Tutorial - [Audio/Video Calling from a Custom App into a Teams Meeting](https://microsoft.github.io/MicrosoftCloud/tutorials/docs/ACS-to-Teams-Meeting/) \| aka.ms/mscloud-acs-teams-tutorial
    * Integrations - [Microsoft Cloud Integration Scenarios](https://microsoft.github.io/MicrosoftCloud/?WT.mc_id=m365-80533-dwahlin) \| aka.ms/microsoft-cloud
    * Repo - [Microsoft Cloud Integrations (code samples, videos, documentation)](https://github.com/microsoft/MicrosoftCloud)
    * Library - [Azure Communication Services – UI Library](https://azure.github.io/communication-ui-library/?path=/story/overview--page) \| aka.ms/acs-ui-library
    * Documentation - [Azure Functions documentation](https://learn.microsoft.com/azure/azure-functions/) \| aka.ms/msazure-functions
    * Tool – [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer) \| [aka.ms/ge](https://aka.ms/ge)
    * Previously delivered demos in this series
        * Demo 4 – [Dynamically Create a Microsoft Teams Meeting using Microsoft Graph](https://youtu.be/77u73mD9MKE?t=1711) - [Ayça Baş](https://twitter.com/aycabs) (Microsoft) \| @aycabs - (2/28)
        * Demo 3 – [Integrate Azure Communication Services Calling into a React App](https://youtu.be/yIm_rsKt4kE?t=844) - [Dan Wahlin](https://twitter.com/DanWahlin) (Microsoft) \| @DanWahlin – (2/21)
        * Demo 2 – [Create an Azure Communication Services Resource](https://www.youtube.com/watch?v=NC1bGG_gUPE&t=766) – [Dan Wahlin](https://twitter.com/DanWahlin) (Microsoft) \| @DanWahlin (2/14)
        * Demo 1 – [Getting Started with Azure Communication Services, Microsoft Graph, and Microsoft Teams](https://www.youtube.com/watch?v=xDXS9muZ0DI&t=718) – [Dan Wahlin](https://twitter.com/DanWahlin) (Microsoft) \| @DanWahlin (2/7)
        * Demo 0 – [Introduction to Azure Communication Services](https://www.youtube.com/watch?v=fHy1K0MRUiY&t=2001) – [Tomas Chladek](https://twitter.com/tomaschladek2) (Microsoft) \| @tomaschladek2 (1/31)
* **Teams Toolkit Learn Path - Build a Microsoft Teams tab app using Teams Toolkit for Visual Studio Code**
    * Training - [Build and deploy apps for Microsoft Teams using Teams Toolkit for Visual Studio Code](https://learn.microsoft.com/training/paths/m365-teams-toolkit-vsc/) \| aka.ms/learn/teamstoolkit
    * Documentation – [Teams Toolkit Overview](https://learn.microsoft.com/microsoftteams/platform/toolkit/teams-toolkit-fundamentals?pivots=visual-studio-code)
    * Documentation – [Create a new Teams project](https://learn.microsoft.com/microsoftteams/platform/toolkit/create-new-project?pivots=visual-studio-code)
    * Documentation – [Build tabs for Teams](https://learn.microsoft.com/microsoftteams/platform/tabs/what-are-tabs)
    * Documentation – [Add single sign-on to Teams app](https://learn.microsoft.com/microsoftteams/platform/toolkit/add-single-sign-on?pivots=visual-studio-code)
    * Previously delivered demos in this series
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

* Office add-in monthly call \| Wednesday, March 8, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, March 9, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft 365 platform call \| Tuesday, March 14, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Power Platform monthly call \| Wednesday, March 15, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft 365 General Dev call \| Thursday, March 16, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, March 16, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

Microsoft 365 Platform community call focuses on latest Microsoft 365 Platform updates and demos delivered by Microsoft presenters and takes place weekly on Tuesday.  The alternating Special Interest Group community calls each Thursday focus on SharePoint Framework (client-side development/implementation) and Microsoft 365 Platform (includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, PowerApps, Column Formatting, list formatting, etc. topics.) with demos commonly delivered by community members.

More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp).

You can download recurrent invite for this call from [https://aka.ms/m365-dev-call](https://aka.ms/m365-dev-call).  Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments to this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/sppnp).


&quot;_Sharing is caring&quot;_

_Microsoft 365 Platform Community team, Microsoft - 7th of March 2023_

{{< attachments >}}{{< /attachments >}}
