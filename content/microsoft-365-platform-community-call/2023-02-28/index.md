---
title: "Microsoft 365 & Power Platform Community Call - 28th of February, 2023"
summary: "Three demos: Dynamically Create a Microsoft Teams Meeting using Microsoft Graph, Teams Toolkit Learn Path - Build a bot using Teams Toolkit for Visual Studio Code, and Remotely debug your Microsoft Teams apps from any device using Vorlon.js."
date: 2023-02-28T04:00:00.000Z
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 platform call"]
images:
- images/recording-230228.png
tags: []
type: regular
videos:
- https://www.youtube.com/watch?v=77u73mD9MKE
draft: false
---

## Call summary

Welcome to the weekly call focused on capabilities of the Microsoft 365 platform.  In this call, we highlight recently announced and key existing developer resources, news, community events and three demos.

### New this week

* Announcements
    * Microsoft Graph and .NET – March Hack Together – March 1st to 15th - aka.ms/hack-together - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR0ktYAUCTtVIvJkJdFsfkalUMlM0SVBXRjIyTEFJQVFYOUMzTDE2SEY1WS4u)
    * Samples – [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) - aka.ms/m365/samples now with more than **1500+ samples** from Microsoft and community.
    * Agenda set for next [Microsoft 365 & Power Platform weekly call](https://aka.ms/m365-dev-call) - Tuesday, March 7th, 8:00 am PT.
        * Latest news from Microsoft engineering on Microsoft 365 topics
        * Demo - **Ayça Baş** – Dynamically Create an Azure Communication Services Identity and Token
        * Demo - **Garry Trinder** – Teams Toolkit Learn Path - Build a Microsoft Teams tab app using Teams Toolkit for Visual Studio Code
        * Demo - **Waldek Mastykarz** – Microsoft Graph Hackathon – Recap on the first week
    * Article – [Microsoft Graph Developer Proxy v0.5 with execution summary and recording mode](https://devblogs.microsoft.com/microsoft365dev/microsoft-graph-developer-proxy-v0-5/) - [Waldek Mastykarz](https://twitter.com/waldekm) (Microsoft) \| @waldekm and [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder
    * Article – [Introducing apps in Microsoft Teams channel meetings general availability](https://devblogs.microsoft.com/microsoft365dev/introducing-apps-in-microsoft-teams-channel-meetings-general-availability/) - Gino Buzzelli (Microsoft)
    * Article – [Microsoft Graph To Do API will be available for GCC High and DoD](https://devblogs.microsoft.com/microsoft365dev/microsoft-graph-to-do-api-will-be-available-for-gcc-high-and-dod/) - [Ashok Obhan](https://www.linkedin.com/in/ashokobhan/) (Microsoft)
    * Article – [New capabilities available in Microsoft Graph To Do APIs](https://devblogs.microsoft.com/microsoft365dev/new-capabilities-available-in-microsoft-graph-to-do-apis/) - Swapna Ninan (Microsoft)
    * Article – [Public preview of SharePoint Framework 1.17 – First release of upcoming features](https://devblogs.microsoft.com/microsoft365dev/public-preview-of-sharepoint-framework-1-17-first-release-of-upcoming-features/) - [Vesa Juvonen](https://twitter.com/VesaJuvonen) \| @VesaJuvonen (Microsoft)
    * Article – [Get ready for the first week of Hack Together: Microsoft Graph and .NET](https://devblogs.microsoft.com/microsoft365dev/get-ready-for-the-first-week-of-hack-together-microsoft-graph-and-net/) - [Ayça Baş](https://twitter.com/aycabs) (Microsoft) \| @aycabs and [Waldek Mastykarz](https://twitter.com/waldekm) (Microsoft) \| @waldekm
    * Article – [Modern Work Superheroes \| Viva Learning Video + February News](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/modern-work-superheroes-viva-learning-video-february-news/ba-p/3753974) - Steven Storey (Microsoft)
    * Article – [Answers in Viva: Understanding Time Saved & People Helped](https://techcommunity.microsoft.com/t5/microsoft-viva-blog/answers-in-viva-understanding-time-saved-amp-people-helped/ba-p/3744671) – kedieu (Microsoft)
* Teams Platform updates
    * Resource - [Changelog for Developer Portal](https://learn.microsoft.com/microsoftteams/platform/concepts/build-and-test/teams-developer-portal#changelog-for-developer-portal)
    * Enable SSO for Adaptive Cards Universal Actions in your bot
        * Documentation - Enable SSO for Adaptive Cards Universal Actions in your bot
        * Sample - [bot-sso-adaptivecard](https://github.com/OfficeDev/Microsoft-Teams-Samples/tree/main/samples/bot-sso-adaptivecard)
* Shows and Events
    * Microsoft 365 Conference – May 2 – 4. 2023, Las Vegas – m365Con.com - [Register](https://m365conf.com/)
    * European Collaboration Summit 2023 – May 24 – 26, 2023 – Düsseldorf – collabsummit.eu – [Register](https://www.collabsummit.eu/)
    * ACT NOW – save €300 on tickets for the [European Power Platform Conference](https://www.sharepointeurope.com/european-power-platform-conference) – Dublin, 20-23 June
    * 365 EduCon - Use promo code “Community” to save 25% off any pass type.
        * [Washington DC](https://techcon365.com/DC/) – June 12-16, 2023
        * [Seattle](https://techcon365.com/Seattle/) – August 21-25, 2023 & PWR EduCon
        * [Chicago](https://techcon365.com/Chicago/) – October 30 – November 3, 2023
    * Upcoming [Community Days](https://communitydays.org/) Events - aka.ms/communitydays
* Conversations
    * Microsoft 365 Developer Podcast – Partner showcase: Building nBold with Guillaume Meyer (February 26th) \| [podcast](https://m365devpodcast.com/e/partner-series-building-nbold-with-guillaume-meyer/)
    * Microsoft 365 Developer Podcast – Kiota and Microsoft Graph SDKs with Vincent Biret and Rabeb Othmani (February 21st) \| [podcast](https://m365devpodcast.com/e/kiota-and-microsoft-graph-sdks-with-vincent-biret-and-rabeb-othmani/)
    * Microsoft 365 PnP Weekly – Episode 199 (February 27th) with reflections from [Vesa Juvonen](http://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen and [Waldek Mastykarz](http://twitter.com/waldekm) (Microsoft) \| @waldekm \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-199/) \| [podcast](http://pnpweekly.podbean.com)
    * Microsoft 365 PnP Weekly – Episode 198 (February 21st) with Bosnia and Herzegovina-based Speaker, Author, Cloud Solutions Architect, Azure MVP at Devoteam M Cloud - [Mustafa Toroman](https://twitter.com/toromust) \| @toromust \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-198/) \| [podcast](https://www.podbean.com/eas/pb-hfy3i-13965d2)
    * Power Platform Connections - Power Platform Connections Ep 2 - Scott Durow (February 23rd) \| [video](https://www.youtube.com/watch?v=CINlK7F3Nhg)
    * Power Platform Connections - Hugo loves the Ribbon Workbench Tool! (February 23rd) \| [video](https://www.youtube.com/watch?v=wY1-gVy1Tvg)

### Demos

* **Dynamically Create a Microsoft Teams Meeting using Microsoft Graph** – leverage Microsoft Graph and Azure functions to automate the creation of a Teams meeting link rather than going to the calendar, creating an invite, copying/pasting link for ACS, etc. Ideal for customers using ACS in a custom app while customer service agent is using Teams – both parties use same URL to join meeting. Step through Microsoft Graph client (with authentication) setup and meeting creation code. Module 4 in this series.
* **Teams Toolkit Learn Path - Build a bot using Teams Toolkit for Visual Studio Code** – step through prerequisites to create a bot for Teams and understand functions of a proactive messaging (reminder) bot in your workflow. Bot architectural components include web server, Azure Bot Service, Azure AD app registration, HTTP tunnel, and Microsoft Teams app package. In Visual Studio Code, create a Notification bot using an HTTP trigger running on Azure Functions using JavaScript. On local machine, tour provisioned capabilities. Module 2 in a 5-part series.
* **Remotely debug your Microsoft Teams apps from any device using Vorlon.js** – develop and remotely debug (and make live updates) apps on Android or iPhone from a Windows PC using the Vorlon.js. Requires adding only a script to Teams web app running on these surfaces. The script monitors calls to console log that’s connected to PC via WiFi. See functionality in demo today. What can we build for you tomorrow? Envision a VS Code extension for Teams Toolkit.

The host of this call was [Vesa Juvonen](http://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen. Q&A takes place in chat throughout the call.

{{< youtube 77u73mD9MKE >}}

## Agenda items

[00:00](https://youtu.be/77u73mD9MKE?t=0) – Intro

[11:35](https://youtu.be/77u73mD9MKE?t=695) – Latest updates and news on the Microsoft 365 platform – [Vesa Juvonen](http://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[12:13](https://youtu.be/77u73mD9MKE?t=733) – Microsoft Teams Platform updates – Surbhi Gupta (Microsoft)

[13:18](https://youtu.be/77u73mD9MKE?t=798) – Together mode picture

[14:31](https://youtu.be/77u73mD9MKE?t=871) – Demo – Dynamically Create a Microsoft Teams Meeting using Microsoft Graph – [Ayça Baş](https://twitter.com/aycabs) (Microsoft) \| @aycabs

[28:31](https://youtu.be/77u73mD9MKE?t=1711) – Demo – Teams Toolkit Learn Path - Build a bot using Teams Toolkit for Visual Studio Code – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[46:29](https://youtu.be/77u73mD9MKE?t=2789) – Demo – Remotely debug your Microsoft Teams apps from any device using Vorlon.js – [David Rousset](https://twitter.com/davrous) (Microsoft) \| @davrous

[59:50](https://youtu.be/77u73mD9MKE?t=3590) – Closing

Thank you for your creativity and work execution. Samples are often showcased in Demos.

## Together Mode

![together-230228.png](images/together-230228.png)

Thanks everyone for joining the call today. Great to see many new and familiar faces.

## Actions

* [Request to Present a demo](https://aka.ms/community/request/demo) during Microsoft 365 & Power Platform community calls - aka.ms/community/request/demo
* [Register](http://www.communitydays.org) for an Upcoming Event around Microsoft 365 and Power Platform.
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

* **Dynamically Create a Microsoft Teams Meeting using Microsoft Graph**
    * Tutorial - [Audio/Video Calling from a Custom App into a Teams Meeting](https://microsoft.github.io/MicrosoftCloud/tutorials/docs/ACS-to-Teams-Meeting/) \| aka.ms/mscloud-acs-teams-tutorial
    * Integrations - [Microsoft Cloud Integration Scenarios](https://microsoft.github.io/MicrosoftCloud/?WT.mc_id=m365-80533-dwahlin) \| aka.ms/microsoft-cloud
    * Repo - [Microsoft Cloud Integrations (code samples, videos, documentation)](https://github.com/microsoft/MicrosoftCloud)
    * Library - [Azure Communication Services – UI Library](https://azure.github.io/communication-ui-library/?path=/story/overview--page) \| aka.ms/acs-ui-library
    * Documentation - [Azure Functions documentation](https://learn.microsoft.com/azure/azure-functions/) \| aka.ms/msazure-functions
    * Tool – [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer) \| [aka.ms/ge](https://aka.ms/ge)
* **Teams Toolkit Learn Path - Build a bot using Teams Toolkit for Visual Studio Code**
    * Learn - [Build a bot by using Teams Toolkit for Visual Studio Code](https://learn.microsoft.com/training/modules/teams-toolkit-vsc-create-bot/)
    * Learn - [Build and deploy apps for Microsoft Teams using Teams Toolkit for Visual Studio Code](https://learn.microsoft.com/training/paths/m365-teams-toolkit-vsc/) \| aka.ms/learn/teamstoolkit
    * Visual Studio Marketplace – [Teams Toolkit](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension)
* **Remotely debug your Microsoft Teams apps from any device using Vorlon.js**
    * Tool - [INTRODUCING VORLON.JS](https://www.vorlonjs.io/)

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

* Microsoft 365 General Dev call \| Thursday, March 2, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Microsoft 365 platform call \| Tuesday, March 7, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Office add-in monthly call \| Wednesday, March 8, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, March 9, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Power Platform monthly call \| Wednesday, March 15, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, March 16, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

Microsoft 365 Platform community call focuses on latest Microsoft 365 Platform updates and demos delivered by Microsoft presenters and takes place weekly on Tuesday.  The alternating Special Interest Group community calls each Thursday focus on SharePoint Framework (client-side development/implementation) and Microsoft 365 Platform (includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, PowerApps, Column Formatting, list formatting, etc. topics.) with demos commonly delivered by community members.

More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp).

You can download recurrent invite for this call from [https://aka.ms/m365-dev-call](https://aka.ms/m365-dev-call).  Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments to this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/sppnp).


&quot;_Sharing is caring&quot;_

_Microsoft 365 Platform Community team, Microsoft - 28th of February 2023_

{{< attachments >}}{{< /attachments >}}
