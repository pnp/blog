---
title: "Microsoft 365 & Power Platform Development Community call - 10th of November, 2022"
date: 2022-11-10T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-10th-november.png
tags: []
type: "regular"
summary: "Demos:  PowerShell predictors - PnP PowerShell and CLI for Microsoft 365 and Create an internal community for Power Platform users with Power Platform Communication Site Template.   Project releases PnP Framework, PnP Core SDK, Microsoft Teams Toolkit and Microsoft Graph Toolkit (MGT) plus 10 samples."
videos:
- https://www.youtube.com/watch?v=3Utq8ZVvOeE
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, November 15th, 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * **Brian Jackett & Jason Johnston** – Calling Microsoft Graph from .NET Interactive Notebooks
    * **Garry Trinder** - Add single sign-on to your Microsoft Teams bots using Teams Toolkit for Visual Studio Code
    * **Hugo Bernier** - Using list components in Power Pages for securely displaying data to end users
* Project releases
    * PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework) – v1.11.0 GA
    * PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev) – v1.8.0 GA
    * [Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx) – v4.1.1 GA (VS Code), v17.4 (VS)
    * [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit) – v2.7.1 GA
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) submissions
    * New – One-Time Secret - [Aldo Gillone](https://www.linkedin.com/in/aldogillone/)
    * New – Festivo – [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors) \| @troystaylor
    * New – QuickChart – [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors) \| @troystaylor
    * New – The SMS Works – [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors) \| @troystaylor
    * New – De Lijn - Lenard Schockaert
    * New – DeepLIP - Michal Romiszewski
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* [Script samples](https://pnp.github.io/script-samples/)
    * New - PnP PowerShell – [Download all the content type document templates files associated with a library](https://pnp.github.io/script-samples/spo-list-download-contenttype-documenttemplate/README.html?tabs=pnpps) - [Leon Armston](http://twitter.com/LeonArmston) \| @LeonArmston
    * New - PnP PowerShell – [Gets usage from a particular user(s) or site(s) from the Unified Audit Log](https://pnp.github.io/script-samples/spo-get-usage-from-audit-logs/README.html?tabs=pnpps) - [Russell Gove](http://twitter.com/russgove) (Tronox) \| @russgove
    * New - PnP PowerShell – [Copy the folder structure of a directory to a SharePoint List](https://pnp.github.io/script-samples/spo-copy-directory-structure-to-sharepoint-list/README.html?tabs=pnpps) - [Russell Gove](http://twitter.com/russgove) (Tronox) \| @russgove
    * [Extensions for PnP PowerShell and CLI for Microsoft 365](https://marketplace.visualstudio.com/publishers/adamwojcikit) – [Adam Wójcik](https://twitter.com/Adam25858782) \| @Adam25858782
    * [Good first issue asks](https://github.com/pnp/script-samples)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/)
    * [Adaptive Cards Search Tab](https://aka.ms/tab-adaptive-cards-graph-search) - [Ramin Ahmadi](https://twitter.com/raminahmadi1986)! \| @raminahmadi1986
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* Conversations
    * Microsoft 365 PnP Weekly – Episode 186 (November 7th) with US/India based Microsoft Principal Product Manager - [DC Padur](https://twitter.com/dcpadur) \| @dcpadur \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-186/) \| [podcast](https://www.podbean.com/media/share/pb-xyxgw-130a0da)
    * Microsoft 365 PnP Weekly – Episode 185 (October 31st) with Belgium based Microsoft 365 Development MVP and Consultant - Jasey Waegebaert (GMI group) \| @jwaegebaert. \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-185/) \| [podcast](https://pnpweekly.podbean.com/)

### Demos

* **PowerShell predictors - PnP PowerShell and CLI for Microsoft 365** – the team has created an extension that allows you to add PnP cmdlets to the open-source PSReadLine module that predicts or suggests PnP PowerShell and CLI for Microsoft 365 cmdlets when typing on the cmd line. The predictor capability in PowerShell 7 suggests recently used cmdlets (History) and now PnP cmdlets (PnP Predictor). Select a cmdlet and cycle through arguments.
* **Create an internal community for Power Platform users with Power Platform Communication Site Template** – This optimized template comes with a trove of supporting content for makers including learning, strategy (Center of Excellence Strategy), and best practices to help drive awareness, connection and adoption of Power Platform within an organization. The template, PowerShell scripts and guidance are available to download today. Walk through site and supporting materials for deploying site. Areas in template requiring customer input are highlighted.

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube 3Utq8ZVvOeE >}}

## Agenda items

* PnP .NET library updates - [Bert Jansen](http://twitter.com/O365bert) (Microsoft) @O365bert – [6:48](https://youtu.be/3Utq8ZVvOeE?t=408)
* PnP PowerShell updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [9:19](https://youtu.be/3Utq8ZVvOeE?t=559)
* yo Teams updates - [Thomy Gölles](https://twitter.com/thomyg) (Solvion) \| @thomyg – [10:35](https://youtu.be/3Utq8ZVvOeE?t=635)
* Microsoft Teams Toolkit updates - [John Miller](https://twitter.com/jmillerdev) (Microsoft) \| @jmillerdev – [12:28](https://youtu.be/3Utq8ZVvOeE?t=748)
* Microsoft Graph Toolkit updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [15:02](https://youtu.be/3Utq8ZVvOeE?t=902)
* Independent Publisher Connectors - [Jocelyn Panchal](https://twitter.com/JocelynP_PM) (Microsoft) \| @JocelynP_PM – [15:44](https://youtu.be/3Utq8ZVvOeE?t=944)
* Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock – [17:46](https://youtu.be/3Utq8ZVvOeE?t=1066)
* Microsoft Teams Samples – [Bob German](https://twitter.com/Bob1German) (Microsoft) @Bob1German – [19:26](https://youtu.be/3Utq8ZVvOeE?t=1166)
* Microsoft Power Platform Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [20:56](https://youtu.be/3Utq8ZVvOeE?t=1256)
* Demo – PowerShell predictors - PnP PowerShell and CLI for Microsoft 365 – [Anoop Tatti](https://twitter.com/anooptells) (Content + Cloud) \| @anooptells – [22:30](https://youtu.be/3Utq8ZVvOeE?t=1350)
* Demo – Create an internal community for Power Platform users with Power Platform Communication Site Template – [Daniel Laskewitz](https://twitter.com/laskewitz) (Microsoft) \| @laskewitz – [39:44](https://youtu.be/3Utq8ZVvOeE?t=2384)

## Together Mode

![together-221110.png](images/together-221110.png)

Thank you for joining this call today with your community mates. Your feedback is always welcome along with your passion for making a difference.

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Have you created a cool flow? Tell us about it so we can write about it. \#FlowOfTheWeek aka.ms/FlowOfTheWeekForm
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Maturity Model Practitioners \| Tuesday, November 15th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite).
    * Power Platform Samples Contributor \| Monday, November 28th, 11:30am PST - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
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

* **PowerShell predictors - PnP PowerShell and CLI for Microsoft 365**
    * Repo - [PowerShell predictors](https://github.com/pnp/predictors)
    * Documentation - [How to create a command-line predictor](https://learn.microsoft.com/powershell/scripting/dev-cross-plat/create-cmdline-predictor?view=powershell-7.2)
    * Library – [PnP PowerShell](https://pnp.github.io/powershell/)
* **Create an internal community for Power Platform users with Power Platform Communication Site Template**
    * Documentation - [Create an internal Microsoft Power Platform hub](https://learn.microsoft.com/power-platform/guidance/adoption/wiki-community?WT.mc_id=power-79474-dlaskewitz) | aka.ms/ppcst-docs
    * Issues - [Power Platform communication site template] Bug, question or feature ask report \| aka.ms/ppcst-issues
    * Download - [The Power Platform Hub template and scripts](https://aka.ms/ppcst-download) \| aka.ms/ppcst-download

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)

## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.11.0 GA|
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.8.0 GA|
[Microsoft 365 Assessment tool](https://docs.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.11.0 GA|Prepping v1.12.0 coming soon.  Nightly builds
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v4.0.1 GA|
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.8.0 GA
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.2.0 GA
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1 GA
[Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx)|v4.1.1 GA (VS Code), v17.4 (VS)|New builds daily
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.7.1 GA

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

* Microsoft 365 platform call \| Tuesday, November 15, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Power Platform monthly call \| Wednesday, November 16, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, November 17, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, November 17, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Microsoft 365 General Dev call \| Thursday, November 24, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Adaptive Cards monthly call \| Thursday, December 8, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Office add-in monthly call \| Wednesday, December 14, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 10th of November 2022*

{{< attachments >}}{{< /attachments >}}
