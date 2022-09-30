---
title: "Microsoft 365 & Power Platform Development Community call - 15th of September, 2022"
date: 2022-09-15T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 Developer Community Call"]
images:
- images/recording-15th-sep.png
tags: []
type: "regular"
summary: "Demos: List formatting magic - neomorphic design for polished UX and Using Mockaroo Independent Publisher Connectors to automatically generate sample data. Delivered 5 Independent Publisher Connector, 2 script, and 1 Microsoft Teams samples. Check out Microsoft Teams App camp."
videos:
- https://www.youtube.com/watch?v=q5C2cOPMuqs
draft: false
---


## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, September 6th, 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * **Adriana Wood, Liam Fernandez** - Introduction to SharePoint Online Admin APIs on Microsoft Graph
    * **Garry Trinder** - Getting started with Teams Toolkit for Visual Studio
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) submissions
    * Updated - [VIES by European Commission](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/VIES%20by%20European%20Commission) - [Tomasz Poszytek](https://twitter.com/TomaszPoszytek) \| @TomaszPoszytek
    * New - Connpass - Miyake Hideo
    * New - Working days - [Tomasz Poszytek](https://twitter.com/TomaszPoszytek) \| @TomaszPoszytek
    * New - HTTP Garden - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors) \| @troystaylor
    * New - Proposal for NFT Mania - Shreyan Fernandes (Welcome!)
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
    * Welcome to [Jocelyn Panchal](https://twitter.com/JocelynP_PM) (Microsoft) \| @JocelynP_PM, the new leader of the Independent Publisher & Verified Publisher program.
* [Script samples](https://pnp.github.io/script-samples/)
    * New - Graph Power shell SDK - [Microsoft Graph PowerShell SDK for Common Operations](https://pnp.github.io/script-samples/graph-common-operations/README.html?tabs=graphps) - [Nik Charlebois](https://twitter.com/NikCharlebois) (Microsoft) \| @NikCharlebois
    * New - PnP PowerShell - [SPO Recover Deleted Meeting Recordings](https://pnp.github.io/script-samples/spo-recover-meeting-recordings/README.html?tabs=pnpps) - [Jason Baxter](https://github.com/jasonwbaxter)
    * [Good first issue asks](https://github.com/pnp/script-samples)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/)
    * Sample X – a sample-in-progress that works in Teams and Outlook and stores emails in OneDrive - [Markus Möller](https://github.com/jMoeller2_0) (Avanade) \| @Moeller2_0
    * New resource site - [Microsoft Teams App camp](https://aka.ms/app-camp) \| aka.ms/app-camp – Securely migrate applications to Microsoft Teams – Hands on labs and samples.
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* The [MGT samples repository](https://aka.ms/mgt/samples) is now live! \| aka.ms/mgt/samples
* Microsoft 365 PnP Weekly – Episode 178 (September 12th) with UK-based [Paul Hunt](https://twitter.com/cimares), Microsoft MVP \| @cimares\| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-178/) \| [podcast](https://www.podbean.com/media/share/pb-h8ads-12c134e)

### Demos

* **List formatting magic - neomorphic design for polished UX** – what? A minimalist design style - 3D look and feel for buttons and graphics applied to 7 newly created JSON neomorphic list formatting controls – Buttons, Options, Rate, Image, Doughnut, Bars, Calendar. The sample controls can be implemented on list columns and views. Create a neomorphic list and distribute it using PowerShell for consistent usage and management across organization. This work inspired by Kristine Kolodziejski.
* **Using Mockaroo Independent Publisher Connectors to automatically generate sample data** – step through Mockaroo features (customized schemas, datasets, mock APIs and grouped schemas/datasets). Connector accesses Mockaroo APIs for two scenarios: 1) Repeatable Test Data - use Power Automate to load contacts (basic flow) and to load contacts and accounts (advanced flow). 2) Speed up UI/UX development – see 2 methods (classic and using experimental ParseJSON (function), for automatically importing simulated data into a Canvas app.

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII)
(Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube q5C2cOPMuqs >}}

## Agenda items

* PnP .NET library updates - [Bert Jansen](http://twitter.com/O365bert) (Microsoft) @O365bert – [6:23](https://youtu.be/q5C2cOPMuqs?t=383)
* PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Valo Intranet) \| @gautamdsheth – [8:00](https://youtu.be/q5C2cOPMuqs?t=480)
* yo Teams updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [9:37](https://youtu.be/q5C2cOPMuqs?t=577)
* Microsoft Graph Toolkit updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [9:58](https://youtu.be/q5C2cOPMuqs?t=598)
* Independent Publisher Connectors - [Natalie Pienkowska](http://twitter.com/NataliePienkow1) (Microsoft) \| @NataliePienkow1 & [Jocelyn Panchal](https://twitter.com/JocelynP_PM) (Microsoft) \| @JocelynP_PM – [10:48](https://youtu.be/q5C2cOPMuqs?t=648)
* Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock – [13:24](https://youtu.be/q5C2cOPMuqs?t=804)
* Microsoft Teams Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [15:31](https://youtu.be/q5C2cOPMuqs?t=931)
* Microsoft Power Platform Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [16:06](https://youtu.be/q5C2cOPMuqs?t=966)
* Demo - List formatting magic - neomorphic design for polished UX – [André Lage](https://twitter.com/aaclage) (Datalynx AG) \| @aaclage – [18:27](https://youtu.be/q5C2cOPMuqs?t=1107)
* Demo - Using Mockaroo Independent Publisher Connectors to automatically generate sample data – [Richard A. Wilson](https://twitter.com/PowerAppsRAW) (Microsoft) \| @PowerAppsRAW – [34:07](https://youtu.be/q5C2cOPMuqs?t=2047)

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Maturity Model Practitioners \| Tuesday, September 20th, 7am PST - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    * LIVE at the Power Platform Conference - Power Platform Samples Contributor \| Wednesday, September 21st, 9:15 am ET, Pacifica 8
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

* **List formatting magic - neomorphic design for polished UX**
    * Samples - [List Formatting Samples](https://pnp.github.io/List-Formatting/) \| aka.ms/list-formatting
    * Video - [Taking your Power Apps mobile navigation UI to the next level!](https://youtu.be/BjhsmcaV2TM) – [Kristine Kolodziejski](https://twitter.com/kristinekk94) (Computacenter) \| @kristinekk94
    * Videos - [Kristine Kolodziejski](https://www.youtube.com/c/KristineKolodziejski/videos) (channel)
    * Sample - [Doughnut Chart](https://github.com/pnp/List-Formatting/tree/master/column-samples/number-doughnut-chart)
* **Using Mockaroo Independent Publisher Connectors to automatically generate sample data**
    * Connector - [Mockaroo (Independent Publisher) (Preview)](https://docs.microsoft.com/connectors/mockarooip/)
    * Repo – [Mockaroo](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Mockaroo)
    * Article - [Power Fx: Introducing ParseJSON](https://powerapps.microsoft.com/blog/power-fx-introducing-parsejson/)
    * Data mocking library – [mockaroo.com](https://www.mockaroo.com/)
    * Documentation - [Independent publisher certification process](https://docs.microsoft.com/connectors/custom-connectors/certification-submission-ip)
    * Video - [Independent Publisher connectors step by step](https://www.youtube.com/watch?v=wGFWZqsxIBQ) - [Tomasz Poszytek](https://twitter.com/TomaszPoszytek) \| @TomaszPoszytek
    * Video - [Power Platform Connectors (Visual Studio Code Extension)](https://www.youtube.com/watch?v=IyZ1jD_XPas&list=PLWGhKdEl5HpqPW49b2HlApEobW6MF2rD7&index=13) - [Daniel Laskewitz](https://twitter.com/laskewitz) (Microsoft) \| @laskwitz
    * Session - [Build and Submit an Independent Publisher Connector in Under 60 Minutes](https://powerplatformconf.com/#!/session/Build%20and%20Submit%20an%20Independent%20Publisher%20Connector%20in%20Under%2060%20Minutes/5434) – [Troy Taylor](https://twitter.com/troystaylor) (Hitachi Solutions) \| @troystaylor


Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)

## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.10.0 GA|Prepping 1.11.0 
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.7.0 GA|Prepping for 1.8.0 
[Microsoft 365 Assessment tool](https://docs.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool                                     
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.11.0 GA|Nightly builds
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v4.0.1 GA
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.7.0 GA
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.2.0 GA
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1 GA
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.6.0 GA

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

* Microsoft 365 platform call \| Tuesday, September 20, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Power Platform monthly call \| Wednesday, September 21, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, September 22, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft 365 platform call \| Tuesday, September 27, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Microsoft 365 General Dev call \| Thursday, September 29, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Office add-in monthly call \| Wednesday, October 12, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Adaptive Cards monthly call \| Thursday, October 13, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Microsoft Identity Platform call \| Thursday, October 20, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 15th of September 2022*

{{< attachments >}}

