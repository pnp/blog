---
title: "Microsoft 365 & Power Platform Development Community call - 13th of October, 2022"
date: 2022-10-13T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-13th-oct.png
tags: []
type: "regular"
summary: "Demos: Introduction to Fantasy Premier League Independent Power Platform Connector and Create a better version of HTML Text component using PCF components in Power Apps.  Project updates - Yo teams build core and Microsoft Teams Toolkit. Released 14 samples."
videos:
- https://www.youtube.com/watch?v=SoJ7uYg6iPg
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, October 18th, 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * **Brian T. Jackett** and **Cameron Parker** – Introduction to Microsoft Graph Search APIs
    * **Ayca Bas** – Build your first Command bot in C\# for Microsoft Teams with Teams Toolkit for Visual Studio
* Project releases
    * [Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core) - v1.8.0 GA
    * [Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx) - v4.0.6 GA, v4.0.7 (Preview)
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) submissions
    * New – [Checkly](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Checkly) – [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors) \| @troystaylor
    * New – [Did You Mean This](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Did%20You%20Mean%20This) – [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors) \| @troystaylor
    * New – [DynamicDocs](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/DynamicsDocs) – [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors) \| @troystaylor
    * New – [Replicate](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Replicate) – [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors) \| @troystaylor
    * New – [Synthesia](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Synthesia) – [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors) \| @troystaylor
    * New – [Focusmate](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Focusmate) – [Phil Cole](https://github.com/filcole)
    * New – [Working Days](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Working%20days) – [Tomasz Poszytek](https://twitter.com/TomaszPoszytek) \| @TomaszPoszytek
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* [Script samples](https://pnp.github.io/script-samples/)
    * New - PnP PowerShell – [Update content type of files in folder with system update](https://pnp.github.io/script-samples/spo-list-update-contenttype-systemupdate/README.html?tabs=pnpps) – [Reshmee Auckloo](http://twitter.com/ReshmeeAuckloo) \| @ReshmeeAuckloo
    * New - PnP PowerShell – [Change the Placeholder text in SharePoint Search Box](https://pnp.github.io/script-samples/spo-search-change-placeholder-text/README.html?tabs=pnpps) – [Ganesh Sanap](http://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * New - PnP PowerShell – [Activate a site feature in SharePoint Online](https://pnp.github.io/script-samples/spo-activate-site-feature/README.html?tabs=pnpps) – [Ganesh Sanap](http://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * New - PnP PowerShell – [Disable SharePoint List Commenting at Tenant Level](https://pnp.github.io/script-samples/spo-disable-list-comments-tenant/README.html?tabs=pnpps) – [Ganesh Sanap](http://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated - CLI for Microsoft 365 – [Export Term Store terms to CSV](https://pnp.github.io/script-samples/spo-export-termstore-terms-to-csv/README.html?tabs=cli-m365-ps) – [Reshmee Auckloo](http://twitter.com/ReshmeeAuckloo) \| @ReshmeeAuckloo
    * [Good first issue asks](https://github.com/pnp/script-samples)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/)
    * Updated Sample - [Tab Meeting StageView Vote Movie Fluid - Microsoft Teams App](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-meeting-stageview-vote-movie-fluid) - [Markus Möller](https://twitter.com/Moeller2_0) (Avanade) \| @Moeller2_0
    * New resource site - [Microsoft Teams App camp](https://aka.ms/app-camp) \| aka.ms/app-camp – Securely migrate applications to Microsoft Teams – Hands on labs and samples.
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* [Power Platform Samples](https://pnp.github.io/powerplatform-samples/)
    * Convert a DOC file to PDF - [Chandani Prajapati](https://twitter.com/Chandani_SPD) \| @Chandani_SPD
* Microsoft 365 PnP Weekly – Episode 182 (October 10th) with Netherlands based Microsoft 365 Architect [Martin Lingstuyl](https://twitter.com/martinlingstuyl) (I4-YOU Business Solutions) \| @martinlingstuyl \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-182/) \| [podcast](https://www.podbean.com/media/share/pb-6kawv-12e502f)

### Demos

* **Introduction to Fantasy Premier League Independent Power Platform Connector** – step through the process - Power Automate Independent Connector requests information, FPL responds to the request passing back JSON, Power Automate Independent Connector receives data & sends to Microsoft Teams, and Microsoft Teams receives data and displays message to users. Go deep on organizing and manipulating returned data and then call a Microsoft Teams action to render standings in a Teams chat or channel.
* **Create a better version of HTML Text component using PCF components in Power Apps** – this PCF HTML Template component allows you to create new controls, with behaviors and internal state, using only HTML and a Json string! So you can create a static HTML Text component in Power Apps Canvas or now you may create a dynamic HTML text component using the Power Apps Component Framework (PCF). Step through proof of concept of the template component.

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube SoJ7uYg6iPg >}}

## Agenda items

* PnP .NET library updates - [Bert Jansen](http://twitter.com/O365bert) (Microsoft) @O365bert – [8:13](https://youtu.be/SoJ7uYg6iPg?t=493)
* PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Valo Intranet) \| @gautamdsheth – [9:50](https://youtu.be/SoJ7uYg6iPg?t=590)
* yo Teams updates - [Stephan Bisser](https://twitter.com/stephanbisser) (Solvion) \| @stephanbisser – [12:22](https://youtu.be/SoJ7uYg6iPg?t=742)
* Microsoft Teams Toolkit updates - [Vesa Juvonen](https://twitter.com/VesaJuvonen) (Microsoft) \| @VesaJuvonen – [13:23](https://youtu.be/SoJ7uYg6iPg?t=803)
* Microsoft Graph Toolkit updates - [Sébastien Levert](http://twitter.com/sebastienlevert) (Microsoft) \| @sebastienlevert – [14:35](https://youtu.be/SoJ7uYg6iPg?t=875)
* Independent Publisher Connectors - [Jocelyn Panchal](https://twitter.com/JocelynP_PM) (Microsoft) \| @JocelynP_PM – [16:10](https://youtu.be/SoJ7uYg6iPg?t=970)
* Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock – [18:26](https://youtu.be/SoJ7uYg6iPg?t=1106)
* Microsoft Teams Samples – [Bob German](https://twitter.com/Bob1German) (Microsoft) @Bob1German – [20:13](https://youtu.be/SoJ7uYg6iPg?t=1213)
* Microsoft Power Platform Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [21:02](https://youtu.be/SoJ7uYg6iPg?t=1262)
* Demo – Introduction to Fantasy Premier League Independent Power Platform Connector – [Joe Unwin](https://twitter.com/Flow_Joe_) (Hitachi Solutions) \| @Flow_Joe\_ – [22:32](https://youtu.be/SoJ7uYg6iPg?t=1352)
* Demo - Create a better version of HTML Text component using PCF components in Power Apps – [Fabio Franzini](https://twitter.com/franzinifabio) (Apvee Solutions) \| @franzinifabio – [42:57](https://youtu.be/SoJ7uYg6iPg?t=2577)

## Together Mode

![together-221013.png](images/together-221013.png)

This thriving community, depth of knowledge and this photo are not possible without you! Thank you for making this the best community in tech.

## Actions

* [Register](https://aka.ms/TeamsAppCamp) for Teams App Camp Online event – October 20th - Register at aka.ms/TeamsAppCamp
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

* **Introduction to Fantasy Premier League Independent Power Platform Connector**
    * Documentation - [Fantasy Premier League (Independent Publisher) (Preview)](https://learn.microsoft.com/connectors/fantasypremierleagueip/)
    * Repo - [Fantasy Premier League Independent Connector](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Fantasy%20Premier%20League)
    * Article - [Fantasy Premier League (FPL), Power Automate & Microsoft Teams](https://www.flowjoe.io/2022/10/13/fantasy-premier-league-fpl-power-automate-microsoft-teams/)
* **Create a better version of HTML Text component using PCF components in Power Apps**
    * Documentation – [HTML text control in Power Apps](https://learn.microsoft.com/power-apps/maker/canvas-apps/controls/control-html-text)
    * Documentation – [Create and build a code component](https://learn.microsoft.com/power-apps/developer/component-framework/create-custom-controls-using-pcf)
    * Documentation – [Templates in the Microsoft Graph Toolkit](https://learn.microsoft.com/graph/toolkit/customize-components/templates)
    * CSS – [tailwindcss](https://tailwindcss.com/)
    * Handbook - [\#Twind Guide](https://twind.dev/handbook/introduction.html)

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)

## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.10.0 GA|Prepping 1.11.0
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.7.0 GA|Prepping for 1.8.0
[Microsoft 365 Assessment tool](https://docs.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.11.0 GA|Nightly builds
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v4.0.1 GA|Release in approximately 2 weeks
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.8.0 GA
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.2.0 GA
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1 GA
[Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx)|v4.0.6 GA, v4.0.7 (Preview)| New builds daily
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

* Microsoft 365 platform call \| Tuesday, October 18, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Power Platform monthly call \| Wednesday, October 19, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, October 20, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, October 20, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Microsoft 365 General Dev call \| Thursday, October 27, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Office add-in monthly call \| Wednesday, November 9, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Adaptive Cards monthly call \| Thursday, November 10, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 13th of October 2022*

{{< attachments >}}{{< /attachments >}}
