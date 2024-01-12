---
title: "Microsoft 365 & Power Platform Development Community call - 29th of September, 2022"
date: 2022-09-29T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-29th-sep.png
tags: []
type: "regular"
summary: "Demos: How to build a good vibes generator bot for Microsoft Teams and Building a movie voting experience as Microsoft Teams meeting app. MGT v2.6.1 released along with 6 Independent Publisher Connector, 4 script, and 1 Microsoft Teams samples."
videos:
- https://www.youtube.com/watch?v=H3YNMCIi3xw
draft: false
---


## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, October 4th, 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * **Brian T. Jackett** and **Cameron Parker** – Introduction to Privacy APIs on Microsoft Graph
    * **Garry Trinder** – Build your first Notification bot for Microsoft Teams with Teams Toolkit for Visual Studio Code
    * **Bob German** and **Aditya Challapally** - Account Linking for Teams apps
* Project releases
    * [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit) – v2.6.1 GA
    * Referenced
        * Article (Tutorial) - [Build a productivity dashboard with Microsoft Teams Toolkit for Visual Studio](https://devblogs.microsoft.com/microsoft365dev/build-a-productivity-dashboard-with-microsoft-teams-toolkit-for-visual-studio) \| [Ayça Baş](https://twitter.com/aycabs) (Microsoft) \| @aycabs
        * Demo - [Build a productivity dashboard by using Teams Toolkit for Visual Studio](https://youtu.be/kedQTfnLetk?t=978) – [Ayça Baş](https://twitter.com/aycabs) (Microsoft) \| @aycabs
    * Much work being done on all projects as highlighted in this call. As well all the project teams are keen on receiving your input.
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) submissions
    * Updated – [Badgr](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Badgr) – [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors) \| @troystaylor
    * Updated – [GitLab](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/GitLab) – [Roy Paar](https://twitter.com/RoyPaar) (Microsoft) \| @RoyPaar
    * New – [Connpass](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Connpass) – [Miyake Hideo](https://github.com/Miyake-Mito)
    * New – [Fantasy Premier League](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Fantasy%20Premier%20League) – [Joe Unwin](https://twitter.com/flow_joe_) \| @flow_joe\_
    * New – [You Need A Budget](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/You%20Need%20A%20Budget) – [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors) \| @troystaylor
    * New – Proposal for Open Trivia DB – [Kiveshan](https://github.com/Kiveshan)
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* [Script samples](https://pnp.github.io/script-samples/)
    * New - PnP PowerShell – [Get all files in a Document Library along with Created By and Modified By](https://pnp.github.io/script-samples/spo-get-files-and-creators-modifiers/README.html?tabs=pnpps) – [Todd Klindt](https://twitter.com/ToddKlindt) (Sympraxis Consulting) \| @ToddKlindt
    * New - PnP PowerShell – [Create a Quick Links web part with items defined in a datasource](https://pnp.github.io/script-samples/spo-quicklink-wp-creator/README.html?tabs=pnpps) – [Kasper Larsen](http://twitter.com/kasperbolarsen) \| @kasperbolarsen
    * New - PnP PowerShell – [Add Content Type Hub with calendar format field to List](https://pnp.github.io/script-samples/spo-add-contenttypehub-format-field-to-List/README.html?tabs=pnpps) – [André Lage](https://twitter.com/aaclage) (Datalynx AG) \| @aaclage
    * New - Graph Power shell SDK – [Get users by license and review last signed in](https://pnp.github.io/script-samples/graph-get-license-and-signins/README.html?tabs=graphps) – [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock
    * [Good first issue asks](https://github.com/pnp/script-samples)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/)
    * Sample – [Tab Office Mail Storage - Microsoft Teams App](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-office-sso-mail-save) - [Markus Möller](https://twitter.com/Moeller2_0) (Avanade) \| @Moeller2_0
    * New resource site - [Microsoft Teams App camp](https://aka.ms/app-camp) \| aka.ms/app-camp – Securely migrate applications to Microsoft Teams – Hands on labs and samples.
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* Microsoft 365 PnP Weekly – Episode 180 (September 26th) with UK based Independent consultant and Microsoft MVP - [Chirag Patel](https://twitter.com/techChirag) (Patel Consulting) \| @techChirag \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-180/) \| [podcast](https://www.podbean.com/media/share/pb-9cb9v-12d3268)

### Demos

* **How to build a good vibes generator bot for Microsoft Teams –** send positive affirmations to Teams’ users. Design goals: Secret-less (uses managed identity), server-less (Azure cloud), and open source. Architecture – uses Azure Functions, a bot, assembles vibe from phrases stored in Cosmos DB, and sends as Adaptive Card into a Teams conversation. 2 types of interactions (entry points) for bot to get vibes (listening to messages (@mention) or based on a schedule (durable function).
* **Building a movie voting experience as Microsoft Teams meeting app –** using Teams stageView and real-time collaboration based on FluidFramework. Scenario: Vote on movies, identify audience favorite, and watch it in stageView. Meeting owner Schedules a Teams meeting, adds the “Tab Meeting Vote Movie Fluid” app, and inserts up to 3 movie options in app. Meeting participants see movie options in right sidebar. Voting results are updated nearly instantaneously. Better synchronization to come with Teams Live Share.

The host of this call was [Vesa Juvonen](https://twitter.com/VesaJuvonen)<http://twitter.com/DavidWarnerII> (Microsoft) \| @VesaJuvonen. Q&A takes place in chat throughout the call.

{{< youtube H3YNMCIi3xw >}}

## Agenda items

* PnP .NET library updates - [Bert Jansen](http://twitter.com/O365bert) (Microsoft) @O365bert – [7:31](https://youtu.be/H3YNMCIi3xw?t=451)
* PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Valo Intranet) \| @gautamdsheth – [9:34](https://youtu.be/H3YNMCIi3xw?t=574)
* yo Teams updates - [Stephan Bisser](https://twitter.com/stephanbisser) (Solvion) \| @stephanbisser – [11:21](https://youtu.be/H3YNMCIi3xw?t=681)
* Microsoft Graph Toolkit updates - [Sébastien Levert](http://twitter.com/sebastienlevert) (Microsoft) \| @sebastienlevert – [12:35](https://youtu.be/H3YNMCIi3xw?t=755)
* Independent Publisher Connectors - [Jocelyn Panchal](https://twitter.com/JocelynP_PM) (Microsoft) \| @JocelynP_PM – [14:47](https://youtu.be/H3YNMCIi3xw?t=887)
* Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock – [16:07](https://youtu.be/H3YNMCIi3xw?t=967)
* Microsoft Teams Samples – [Vesa Juvonen](https://twitter.com/VesaJuvonen) (Microsoft) \| @VesaJuvonen – [18:21](https://youtu.be/H3YNMCIi3xw?t=1101)
* Microsoft Power Platform Samples - [April Dunnam](http://twitter.com/aprildunnam) (Microsoft) \| @aprildunnam – [18:57](https://youtu.be/H3YNMCIi3xw?t=1137)
* Demo – How to build a good vibes generator bot for Microsoft Teams – [Lee Ford](https://twitter.com/lee_ford) (Symity) \| @lee_ford and [Luise Freese](https://twitter.com/LuiseFreese) \| @LuiseFreese – [20:46](https://youtu.be/H3YNMCIi3xw?t=1246)
* Demo – Building a movie voting experience as Microsoft Teams meeting app – [Markus Möller](https://twitter.com/Moeller2_0) (Avanade) \| @Moeller2_0 – [33:00](https://youtu.be/H3YNMCIi3xw?t=1980)

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Maturity Model Practitioners \| Tuesday, October 18th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite).
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* What key scenarios are missing from the PnP Core SDK? Let us know and/or view the latest changes at [PnP Core SDK Changelog](https://github.com/pnp/pnpcore/blob/dev/src/sdk/CHANGELOG.md).
* PowerShell – The team is thinking of dropping support for PS 5, any strong objections? Suggestions in general? Please visit [PnP.PowerShell Changelog](https://github.com/pnp/powershell/blob/dev/CHANGELOG.md)
* Ideas for Microsoft Lists? aka.ms/Feedback/Lists
* Suggestions for yo teams? [Discussions](https://github.com/pnp/generator-teams/discussions)
* Create a connector – [Top Power Platform Independent Publisher Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* Wish list for [Microsoft Teams](https://github.com/pnp/teams-dev-samples/issues/new/choose)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Request a Demo spot on the call – <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call – <http://aka.ms/spdev-sig-call>

## Demo references

* **How to build a good vibes generator bot for Microsoft Teams**
    * Repo - [Good Vibes generator](https://github.com/working-on-it/good-vibes-generator)
    * Guidance - [Deployment guide](https://github.com/working-on-it/good-vibes-generator/blob/main/docs/deploymentGuide.md)
    * Documentation - [What are Durable Functions?](https://learn.microsoft.com/azure/azure-functions/durable/durable-functions-overview)
* **Building a movie voting experience as Microsoft Teams meeting app**
    * Article - [Teams Meeting apps – A sample for in-Meeting experience and stageView (Vote Movies)](https://mmsharepoint.wordpress.com/2022/05/26/teams-meeting-apps-a-sample-for-in-meeting-experience-and-stageview-vote-movies/)
    * Article - [Use FluidFramework in a Microsoft Teams app](https://mmsharepoint.wordpress.com/2022/06/25/use-fluidframework-in-a-microsoft-teams-app/)
    * Sample - [Tab Meeting Vote Movie - Microsoft Teams App](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-meeting-stageview-vote-movie)
    * Sample - [Tab Meeting StageView Vote Movie Fluid - Microsoft Teams App](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-meeting-stageview-vote-movie-fluid)
    * Documentation - [Live Share SDK](https://learn.microsoft.com/microsoftteams/platform/apps-in-teams-meetings/teams-live-share-overview)

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)

## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.10.0 GA|Prepping 1.11.0
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.7.0 GA|Prepping for 1.8.0
[Microsoft 365 Assessment tool](https://learn.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.11.0 GA|Nightly builds
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v4.0.1 GA|Release in approximately 2 weeks
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.7.0 GA
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.2.0 GA
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1 GA
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.6.1 GA

## General resources

*   Script Samples - [Getting started with PnP Script Samples](https://aka.ms/script-samples/getting-started) – aka.ms/script-samples/getting-started
*   Samples - [Power Platform Samples](https://aka.ms/powerplatform-samples) | [aka.ms/](https://aka.ms/powerplatform-samples)[powerplatform](https://aka.ms/powerplatform-samples)[\-samples](https://aka.ms/powerplatform-samples)
*   Microsoft 365 tenant – [Script Samples Gallery](https://aka.ms/script-samples) | aka.ms/script-samples
*   [Microsoft Teams Samples Gallery](https://pnp.github.io/teams-dev-samples/) | aka.ms/teams-samples
*   [Microsoft 365 Extensibility look book gallery](https://adoption.microsoft.com/extensibility-look-book?WT.mc_id=m365-24198-cxa) | aka.ms/m365/extensibility
*   Archives - Microsoft 365 PnP Weekly - [Videos](https://www.youtube.com/playlist?list=PLR9nK3mnD-OVYI-St_CBiFfuL4CZbBpkC), [Podcasts](https://pnpweekly.podbean.com/)
*   PnP Teams Quickstart | [aka.ms/pnp-teams-quickstart](https://aka.ms/pnp-teams-quickstart)
*   Microsoft Teams Toolkit v3.x | [https://aka.ms/teams-toolkit](https://aka.ms/teams-toolkit)
*   [Microsoft 365 and Power Platform Community Blog](https://pnp.github.io/blog) | aka.ms/m365pnp/blog
*   Microsoft Graph Toolkit in Microsoft Learn | [https://aka.ms/learn-mgt](https://aka.ms/learn-mgt)
*   Viva Connections [https://aka.ms/VivaConnections](https://aka.ms/VivaConnections)
*   [SharePoint look book](https://lookbook.microsoft.com/?WT.mc_id=m365-24198-cxa)
*   [Yo Teams video training package](https://aka.ms/yoteams-training)
*   [.NET Standard 2.0 version of SharePoint Online CSOM API](https://developer.microsoft.com/microsoft-365/blogs/net-standard-version-of-sharepoint-online-csom-apis?WT.mc_id=m365-24198-cxa)
*   [Microsoft 365 community (PnP) videos](https://aka.ms/m365pnp-videos) | aka.ms/m365pnp-videos
*   [Microsoft Teams Toolkit for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension)
*   [yo Teams](https://aka.ms/yoteams) | aka.ms/yoteams
*   Video - [Getting started using yo Teams](https://youtu.be/w0OrFkzNC10) | [Wictor Wilén](https://twitter.com/wictor) (Microsoft)| @wictor
*   [Build a crisis management site to connect people and information](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/build-a-crisis-management-site-to-connect-people-and-information/ba-p/1216791?WT.mc_id=m365-24198-cxa)
*   [Developer documentation](https://aka.ms/spdev-docs) | [https://aka.ms/spdev-docs](https://aka.ms/spdev-docs)
*   [PnP Power Shell](https://aka.ms/sppnp-powershell)
*   [SharePoint Modernization Partner Guidance](https://aka.ms/sppnp-modernization-partnerguidance) \- Feedback welcome
*   Solution - [Building a modern search experiences with SharePoint Framework web parts](https://aka.ms/pnp-modern-search)
*   [Page transformation guidance](https://aka.ms/sppnp-pagetransformation)
*   [Page transformation videos](https://aka.ms/sppnp-pagetransformationvideos)
*   [Modernization scanner](https://aka.ms/sppnp-modernizationscanner)
*   [Microsoft 365 developer program site](https://developer.microsoft.com/office/dev-program?WT.mc_id=m365-24198-cxa) \- Need to become a Tenant Admin to test look book capabilities? Get a Microsoft 365 E5 developer subscription (free tenant for 90 days)
*   [SharePoint Page Transformation webcast series](https://developer.microsoft.com/sharepoint/blogs/sharepoint-page-transformation-webcast-series?WT.mc_id=m365-24198-cxa)
*   [PnP PowerShell](https://aka.ms/sppnp-powershell)
*   [SharePoint Modernization Tools](https://github.com/SharePoint/sp-dev-modernization/tree/dev/Tools)

## Upcoming calls | Recurrent invites

* Microsoft 365 platform call \| Tuesday, October 4, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Viva Connections & SharePoint Framework call \| Thursday, October 6, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Office add-in monthly call \| Wednesday, October 12, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Microsoft 365 General Dev call \| Thursday, October 13, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Adaptive Cards monthly call \| Thursday, October 13, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Power Platform monthly call \| Wednesday, October 19, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, October 20, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 29th of September 2022*

{{< attachments >}}{{< /attachments >}}
