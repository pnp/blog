---
title: "Microsoft 365 & Power Platform Development Community call - 23rd of June, 2022"
date: 2022-06-23T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-23rd-june.png
tags: []
type: "regular"
summary: "Demos - List Formatting - Tab and Percentage Chart, Tracking activities with Microsoft Lists and Power Automate, and Building your own Microsoft Teams using Microsoft Graph Toolkit and .NET Core API + Integrate using Web Components. Yo teams version releases + 9 scripts."
videos:
- https://www.youtube.com/watch?v=WZwg_Zo1ZL4
draft: false
---


## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, June 28, 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * **Rabeb Othmani** - Taking advantage of the Microsoft Graph postman collections
    * **Geeta Ramakrishnan, Divyanka Malik, Malabika Roy** - Introduction on the Microsoft Viva Learning extensibility
    * **Benjamin Olson** - Introduction to Virtual Appointment API
    * Note: **Last call before summer break 1st of July – 31st of August**
* Project releases
    * [Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams) - v4.0 GA
    * [Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core) - v1.7 GA
    * [Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy) - v1.2 GA
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors)
    * New - MS Graph Groups and Users - [Jay Jani](https://www.linkedin.com/in/jayjani03/)
    * New - RegEx Matching - Mitanshu Garg
    * New - Meme - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * New - Unofficial Netflix Search - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * Updated - [GoQR](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/GoQR) (originally built by Rui Santos) - [Woong Choi](https://www.linkedin.com/in/woongchoi/)
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* [Script samples](https://pnp.github.io/script-samples/)
    * New for CLI - [Install Solution and Deploy to the SharePoint site](https://pnp.github.io/script-samples/spo-install-deploy-spfx-solution/README.html?tabs=cli-m365-ps) - [Nanddeep Nachan](http://twitter.com/NanddeepNachan) \| @NanddeepNachan
    * Updated for Power Apps/Power Shell - [Add/Remove users (bulk from Power Apps from CSV file](https://pnp.github.io/script-samples/powerapps-bulk-useraccess/README.html?tabs=powerapps-ps) - [Luise Freese](https://twitter.com/LuiseFreese) \| @LuiseFreese
    * Updated for CLI - [Set Home site for SharePoint online tenant](https://pnp.github.io/script-samples/spo-set-home-site/README.html?tabs=pnpps) - [Smita Nachan](https://twitter.com/SmitaNachan) \| @SmitaNachan
    * Updated for CLI - [Bulk Create Teams with JSON File](https://pnp.github.io/script-samples/teams-bulk-create-teams/README.html?tabs=pnpps) - [Nanddeep Nachan](http://twitter.com/NanddeepNachan) \| @NanddeepNachan
    * Updated for CLI - [Export SharePoint List Data to CSV with attachments](https://pnp.github.io/script-samples/spo-export-sharepoint-list-items-to-csv/README.html?tabs=pnpps) - [Nanddeep Nachan](http://twitter.com/NanddeepNachan) \| @NanddeepNachan
    * Updated for CLI - [Create bulk dummy documents, including major/minor versions](https://pnp.github.io/script-samples/create-dummy-docs-versions-in-library/README.html?tabs=pnpps) - [Mathijs Verbeeck](https://www.linkedin.com/in/mathijsverbeeck/)
    * Updated for PowerShell - [Delete custom color themes from SharePoint](https://pnp.github.io/script-samples/spo-remove-custom-themes/README.html?tabs=cli-m365-ps) - [Leon Armston](http://twitter.com/LeonArmston) \| @LeonArmston
    * Updated for PowerShell - [Read SharePoint List Items Using CAML Query](https://pnp.github.io/script-samples/spo-list-items-with-caml-query/README.html?tabs=pnpps) - [Jago Pauwels](https://github.com/jagopauwels/)
    * [Good first issue asks](https://github.com/pnp/script-samples)
* [Teams samples](https://adoption.microsoft.com/sample-solution-gallery?sortby=creationDateTime-true&keyword=&product=Teams&action=ajax_plugin_call_sample_solution_gallery)
    * New - [Movie Vote - Tab meeting w/stageview](https://adoption.microsoft.com/sample-solution-gallery/pnp-sp-dev-teams-sample-tab-meeting-stageview-basic) - [Markus Moeller](http://twitter.com/Moeller2_0) \| @Moeller2_0
* Microsoft 365 PnP Weekly – Episode 171 (June 20th) with Germany based Teams/Power Apps Consultant, Partner Manager, MVP at Valo Solutions - [Edyta Gorzon](https://twitter.com/EdytaGorzon) \| @EdytaGorzon \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-171/) \| [podcast](https://www.podbean.com/media/share/pb-axtx9-1255b1a)

### Demos

* **List Formatting magic - Tab and Percentage Chart** – simple examples of formatting we can implement on a SharePoint page. Create tabs with associated content. Tabs sample allows you to add an icon or url to image displayed on each Tab. Percentage chart displays formatted chart row based on icon/emoji/svg and associated calculated numbers. Add new items to list in Property Pane on page. Edit dates and values alternatively on page or in list.
* **Keep track of your activities with Microsoft Lists and Power Automate** – create a custom list that captures notes and automatically highlights, groups and sorts by date, is flexible and easy to use, tracks information about activities as well as operations, and is Microsoft Teams ready. Keeps track of attachments (Power Automate) and can be customized further. Each list record has Title, writing box and a tool bar. Edit content in list or on page.
* **Build your own Microsoft Teams using Microsoft Graph Toolkit and .NET Core API and Integrate using Web Components** – why build your own version of Teams? Step through one business case and architecture. Uses a Graph Toolkit provider, mgt-get components, back-end implementation (.NET 5), Graph change subscription, SignalR implementation, client-side changes to get latest messages from Teams, and respond to all Graph calls (Proxy Provider). See demo of near instantaneous chat and notifications in the non-Teams app and Teams App side-by-side.

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII)
(Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the
call.

{{< youtube WZwg_Zo1ZL4 >}}

## Agenda items

* PnP .NET library updates - [Bert Jansen](http://twitter.com/O365bert) (Microsoft) @O365bert – [5:58](https://youtu.be/WZwg_Zo1ZL4?t=358)
* PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Valo Intranet) \| @gautamdsheth – [9:05](https://youtu.be/WZwg_Zo1ZL4?t=545)
* yo Teams updates - [Wictor Wilén](http://twitter.com/wictor) (Microsoft) @wictor – [11:09](https://youtu.be/WZwg_Zo1ZL4?t=669)
* Microsoft Graph Toolkit updates - [Sébastien Levert](http://twitter.com/sebastienlevert) (Microsoft) \| @sebastienlevert – [13:16](https://youtu.be/WZwg_Zo1ZL4?t=796)
* Independent Publisher Connectors - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [15:04](https://youtu.be/WZwg_Zo1ZL4?t=904)
* Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock – [15:25](https://youtu.be/WZwg_Zo1ZL4?t=925)
* Microsoft Teams Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [17:38](https://youtu.be/WZwg_Zo1ZL4?t=1058)
* Microsoft Power Platform Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [18:00](https://youtu.be/WZwg_Zo1ZL4?t=1080)
* Demo - List Formatting magic - Tab and Percentage Chart – [André Lage](https://twitter.com/aaclage) (Datalynx AG) \| @aaclage – [19:47](https://youtu.be/WZwg_Zo1ZL4?t=1187)
* Demo - Keep track of your activities with Microsoft Lists and Power Automate – Federico Sapia (ANPAL Servizi) – [28:17](https://youtu.be/WZwg_Zo1ZL4?t=1697)
* Demo - Build your own Microsoft Teams using Microsoft Graph Toolkit and .NET Core API and Integrate using Web Components – [Sohil Bhalla](https://twitter.com/SohilBhalla) (Codeless Technology) \| @SohilBhalla – [35:20](https://youtu.be/WZwg_Zo1ZL4?t=2120)

## Actions

* Opt into PnP Recognition Program \| <https://aka.ms/m365pnp-recognition>
* Attend the next [Power Platform LABs call](https://aka.ms/PowerPlatformIntegrationLABs), June 29, 8am PT \|11am ET at [aka.ms/](https://ineleccom-my.sharepoint.com/personal/andrb_inelec_com/Documents/Desktop/SharePoint%20Videos/June%2023%20-%20M365%20Gen%20Dev%20Call/aka.ms/PowerPlatformIntegrationLABs)[PowerPlatformIntegrationLABs](https://ineleccom-my.sharepoint.com/personal/andrb_inelec_com/Documents/Desktop/SharePoint%20Videos/June%2023%20-%20M365%20Gen%20Dev%20Call/aka.ms/PowerPlatformIntegrationLABs)
* Register for [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Writing for the Web \| Monday, July 11th, 10am PT \| 1pm ET \| 7pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Power Platform Samples Contributor \| Wednesday, June 29, 10:00 am PT - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN09VTVU2QzRLNE0yVERQMklHSDBMUTJGWC4u)
    * Maturity Model Practitioners \| [Register](https://aka.ms/mm4m365)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* What do you need from PnP Core SDK? Let us know and/or view the latest changes at [PnP Core SDK Changelog](https://github.com/pnp/pnpcore/blob/dev/src/sdk/CHANGELOG.md).
* PowerShell suggestions? Please visit [PnP.PowerShell Changelog](https://github.com/pnp/powershell/blob/dev/CHANGELOG.md)
* Ideas for Microsoft Lists? aka.ms/Feedback/Lists
* Create a connector – [Top Power Platform Independent Publisher Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Sign up to [Share your story](https://aka.ms/share-your-story) in the [Learn from the community](https://aka.ms/LearnFromTheCommunity/ThisWeek) series.
* Request a Demo spot on the call – <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call – <https://aka.ms/spdev-sig-call>

## Demo references

* **List Formatting magic - Tab and Percentage Chart**
    * Repo - [SharePoint List Formatting Samples](https://github.com/pnp/List-Formatting)
    * Feedback - [Microsoft Lists](https://feedbackportal.microsoft.com/feedback/forum/ab3ad59e-6dd1-ec11-a7b5-0022481f35a4) \| aka.ms/Feedback/Lists
    * Repo - [tabs format](https://github.com/pnp/List-Formatting/tree/master/view-samples/tabs-format)
    * Repo - [Percent chart format](https://github.com/pnp/List-Formatting/tree/master/view-samples/percent-chart-format)
* **Keep track of your activities with Microsoft Lists and Power Automate**
    * Article - [Keep track of your activities with Microsoft Lists and Power Automate](https://github.com/Fedes365/Microsoft-Lists-Templates/wiki/Keep-track-of-your-activities-with-Microsoft-Lists-and-Power-Automate)
    * Documentation - [Use column formatting to customize SharePoint](https://docs.microsoft.com/sharepoint/dev/declarative-customization/column-formatting)
* **Build your own Microsoft Teams using Microsoft Graph Toolkit and .NET Core API and Integrate using Web Components**
    * Article - [Build your own Microsoft Teams using Microsoft Graph Toolkit and .NET Core API and Integrate using Web Components](https://pnp.github.io/blog/post/build-teams-using-graph-toolkit/)

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)


## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.9.0 GA|Prepping for v1.10.0 (end of June)
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.6.0 GA|Prepping for v1.7.0 (end of June)
[Microsoft 365 Assessment tool](https://docs.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool                                     
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.10.0 GA|Bug fixes and improvements continue to 1.11 release (end of June)
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v4.0.0 GA
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.7.0 GA
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.2.0 GA
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

* Microsoft 365 platform call \| Tuesday, June 28, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Viva Connections & SharePoint Framework call \| Thursday, June 30, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* M365 & Power Platform Dev call \| Thursday, July 7, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Office add-in monthly call \| Wednesday, July 13, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Adaptive Cards monthly call \| Thursday, July 14, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Power Platform monthly call \| Wednesday, July 20, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, July 21, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 24th of June 2022*

{{< attachments >}}

