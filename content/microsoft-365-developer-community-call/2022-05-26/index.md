---
title: "Microsoft 365 & Power Platform Development Community call - 26th of May, 2022"
date: 2022-05-27T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 Developer Community Call"]
images:
- images/recording-26th-may.png
tags: []
type: "regular"
summary: "Demos - Independent Publishing Connectors Case - Netherland Railroads, Data Loss Prevention (DLP) solution for emails with Microsoft Graph, and TeamsFx .NET - Use SQLite and generic forms for your next Teams Dev demo. Released MGT v2.5.2, 3 script samples."
videos:
- https://www.youtube.com/watch?v=Yx9-HUaJsak
draft: false
---


## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, May 31, 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * Microsoft Build 2022 - Recap of the key announcements
    * **David de Matheu** - Get started with UI Library for Azure Communication Services
    * **Luis Ramos Vea & Rabeb Othmani** - Latest on Microsoft Graph developer portal updates
* Project releases
    * [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit) - v2.5.2 GA
    * [PnP PowerShell](https://github.com/pnp/PnP-PowerShell) - released new Docker image, new commands, and bug fixes
* Script samples
    * New scenario - [Planner migration to SharePoint list](https://pnp.github.io/script-samples/planner-migration-spo-list/README.html?tabs=cli-m365-ps) - [Albert-Jan Schot](http://twitter.com/appieschot) \| @appieschot
    * 2 New scenarios - [SharePoint Online Hub Site Association *(SPO MS + PnP PS)*](https://pnp.github.io/script-samples/spo-hub-sites-association/README.html?tabs=pnpps) - [Chandani Prajapati](http://twitter.com/Chandani_SPD) \| @Chandani_SPD
* Microsoft 365 PnP Weekly – Episode 167 (May 23rd) with Helsinki-based software engineer, PowerShell maintainer and Office Apps and Services MVP Gautam Sheth (Valo Solutions) \| @gautamdsheth. \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-167/) \| [podcast](https://www.podbean.com/media/share/pb-2jtm9-1232f34)

### Demos

* **Introduction on getting stared on building Independent Publishing Connectors – Case Netherland Railroads** – Microsoft Teams app gets information on train arrivals, departures, stations, and station disruptions through connector accessing Dutch railway operator’s open API. Power Automate flow is triggered each afternoon to assess if commuter train is on time, notification delivered by a chatbot. See detailed [article](https://www.powerplatformchallenge.com/post/challenge-004) on creating a custom connector in Miguel’s blog. 128 certified Independent Publisher Connectors in production, 27 in pipeline today!
* **Data Loss Prevention (DLP) solution for emails with Microsoft Graph** – the new secure and customizable alternative to Microsoft Purview Insider Risk Management uses Microsoft Graph subscriptions for email (and other event) notifications and Azure.Messaging.EventHub as an incident reporting end-point. See how to create an EventHub and configure policies. Essentially 2 policies - Graph can only send to my EventHub and my custom code can only listen to my Event Hub! Solution uses an Azure Durable Function.
* **TeamsFx .NET - Use SQLite and generic forms for your next Teams Dev demo** – see use of TeamsFx for scaffolding a Teams Tab as a Blazor project, use Entity Framework Core to manage data in SQLite, use C\# Source Code Generators to auto create service classes, usage of Mezaiantou’s generic forms for Blazor, and use of the generators to also create razor components. This demo assumes familiarity of building TeamsFx apps, covered in previous PnP demos.

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII)
(Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the
call.

{{< youtube Yx9-HUaJsak >}}

## Agenda items

* PnP .NET library updates - [Paolo Pialorsi](http://twitter.com/paolopia) (PiaSys.com) \| @paolopia – [5:20](https://youtu.be/Yx9-HUaJsak?t=320)
* PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Valo Intranet) \| @gautamdsheth – [6:57](https://youtu.be/Yx9-HUaJsak?t=417)
* yo Teams updates - [Rick Van Rousselt](http://twitter.com/rickvanrousselt) (Advantive) \| @rickvanrousselt – [8:29](https://youtu.be/Yx9-HUaJsak?t=509)
* Microsoft Graph Toolkit updates - [Sébastien Levert](http://twitter.com/sebastienlevert) (Microsoft) \| @sebastienlevert – [9:25](https://youtu.be/Yx9-HUaJsak?t=565)
* Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock – [10:24](https://youtu.be/Yx9-HUaJsak?t=624)
* Microsoft Teams Samples - [Bob German](http://twitter.com/Bob1German) (Microsoft) \| @Bob1German – [12:06](https://youtu.be/Yx9-HUaJsak?t=726)
* Microsoft Power Platform Samples - [April Dunnam](http://twitter.com/aprildunnam) (Microsoft) \| @aprildunnam – [13:02](https://youtu.be/Yx9-HUaJsak?t=782)
* Demo - Introduction on getting stared on building Independent Publishing Connectors – Case Netherland Railroads – [Miguel Verweij](http://twitter.com/MiguelVerweij) (Sogeti) \| @MiguelVerweij & [Natalie Pienkowska](http://twitter.com/NataliePienkow1) (Microsoft) \| @NataliePienkow1 – [14:47](https://youtu.be/Yx9-HUaJsak?t=887)
* Dwmo - Data Loss Prevention (DLP) solution for emails with Microsoft Graph – [Rick Van Rousselt](http://twitter.com/RickVanRousselt) (Advantive) \| @RickVanRousselt – [22:36](https://youtu.be/Yx9-HUaJsak?t=1356)
* Demo - TeamsFx .NET - Use SQLite and generic forms for your next Teams Dev demo – [Thomy Gölles](http://twitter.com/thomyg) (Solvion) \| @thomyg – [39:02](https://youtu.be/Yx9-HUaJsak?t=2342)


## Together Mode

![220526-together-mode.gif](images/220526-together-mode.gif)

Awesome seeing everybody on the call today. Thank you everyone for being so collaborative. See you again.

## Actions

* Opt into PnP Recognition Program \| <https://aka.ms/m365pnp-recognition>
* Register for Sharing is Caring Events:
    * Power Platform Samples – First Time Contributor \| Monday, May 31, 9:30 am PT- [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN09VTVU2QzRLNE0yVERQMklHSDBMUTJGWC4u)
    * Writing for the Web \| Thursday, June 23, 12pm PT \| 3pm ET \| 9pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Writing for the Web \| Monday, June 27, 10am PT \| 1pm ET \| 7pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Maturity Model Practitioners \| [Register](https://aka.ms/mm4m365)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* What do you need from PnP Core SDK? Let us know and/or view the latest changes at [PnP Core SDK Changelog](https://github.com/pnp/pnpcore/blob/dev/src/sdk/CHANGELOG.md).
* PowerShell suggestions? Please visit [PnP.PowerShell Changelog](https://github.com/pnp/powershell/blob/dev/CHANGELOG.md)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Sign up to [Share your story](https://aka.ms/share-your-story) in the [Learn from the community](https://aka.ms/LearnFromTheCommunity/ThisWeek) series.
* Request a Demo spot on the call – <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call – <https://aka.ms/spdev-sig-call>

## Demo references

* **Introduction on getting stared on building Independent Publishing Connectors – Case Netherland Railroads**
    * Documentation - [Nederlandse Spoorwegen (Independent Publisher) (Preview)](https://docs.microsoft.com/connectors/nederlandsespoorweip/)
    * Repo - [Nederlandse Spoorwegen](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Nederlandse%20Spoorwegen)
    * Blog - [Power Platform Challenge 004](https://www.powerplatformchallenge.com/post/challenge-004)
    * Connectors - [Welcome to the Independent Publisher Connector Directory!](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Miro)
* **Data Loss Prevention (DLP) solution for emails with Microsoft Graph**
    * Documentation – [Get change notifications delivered in different ways](https://docs.microsoft.com/graph/change-notifications-delivery)
    * Documentation - [Send events to and receive events from Azure Event Hubs - .NET (Azure.Messaging.EventHubs)](https://docs.microsoft.com/azure/event-hubs/event-hubs-dotnet-standard-getstarted-send)
    * Documentation - [Azure Durable Functions documentation](https://docs.microsoft.com/azure/azure-functions/durable/)
* **TeamsFx .NET - Use SQLite and generic forms for your next Teams Dev demo**
    * Repo – [SQLiteStudio](https://github.com/pawelsalawa/sqlitestudio)
    * Forms - [Meziantou’s Blog](https://www.meziantou.net)


Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)


## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.9.0 GA|Prepping for v1.10.0
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.6.0 GA|Prepping for v1.7.0
[Microsoft 365 Assessment tool](https://docs.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool                                     
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.10.0 GA|Many bug fixes, also in progress: V2 POC - .NET 6.0 based, Requires PowerShell 7.2
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v3.5.0 GA,v4.0.0-preview.1|Version 4.0 is imminent – pending an issue with the new Teams JS SDK
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.6.0 GA, v1.7.0-preview.2
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.1.0 GA, v1.2.0-preview.2
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1 GA
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.5.2 GA|Working on v3.0.0 - Aligning all Toolkit components to Fluent UI Web Components

## General resources

*   Script Samples - [Getting started with PnP Script Samples](https://aka.ms/script-samples/getting-started) – aka.ms/script-samples/getting-started
*   Samples - [Power Platform Samples](https://aka.ms/powerplatform-samples) | [aka.ms/](https://aka.ms/powerplatform-samples)[powerplatform](https://aka.ms/powerplatform-samples)[\-samples](https://aka.ms/powerplatform-samples)
*   Microsoft 365 tenant – [Script Samples Gallery](https://aka.ms/script-samples) | aka.ms/script-samples
*   [Microsoft Teams Samples Gallery](https://pnp.github.io/teams-dev-samples/) | aka.ms/teams-samples
*   [Microsoft 365 Extensibility look book gallery](https://adoption.microsoft.com/extensibility-look-book?WT.mc_id=m365-24198-cxa) | aka.ms/m365/extensibility
*   Archives - Microsoft 365 PnP Weekly - [Videos](https://www.youtube.com/playlist?list=PLR9nK3mnD-OVYI-St_CBiFfuL4CZbBpkC), [Podcasts](https://pnpweekly.podbean.com/)  
*   PnP Teams Quickstart | [aka.ms/pnp-teams-quickstart](https://aka.ms/pnp-teams-quickstart)
*   Microsoft Teams Toolkit v3.x | [https://aka.ms/teams-toolkit](https://aka.ms/teams-toolkit)
*   [Microsoft 365 platform community blog](https://pnp.github.io/blog) | aka.ms/m365pnp/blog
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

* Microsoft 365 platform call \| Tuesday, May 31, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Viva Connections & SharePoint Framework call \| Thursday, June 2, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Office add-in monthly call \| Wednesday, June 8, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* M365 General Dev call \| Thursday, June 9, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Adaptive Cards monthly call \| Thursday, June 9, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Power Platform monthly call \| Wednesday, June 15, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, June 16, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 27th of May 2022*

{{< attachments >}}

