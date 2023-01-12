---
title: "Microsoft 365 & Power Platform Development Community call - 22nd of December, 2022"
date: 2022-12-22T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-22nd-dec.png
tags: []
type: "regular"
summary: "Demos:  Extend Microsoft Teams apps across Microsoft 365 (Outlook and Office) and Power Apps component library: Material design.  Releases for yo Teams (generator and build-core), Microsoft Teams Toolkit, Microsoft Graph Toolkit, plus 8 connectors, 6 samples and 1 conversation!"
videos:
- https://www.youtube.com/watch?v=ssgNG_mcKUE
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Join the next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, December 27th, 8:00 am PT.
    * Coffee & chat with Community - questions, feedback, discussions, employee reflections, ad hoc demos and good cheer. 
* Project releases
    * [Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams) – v4.1.0 GA
    * [Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core) – v1.9.0 GA
    * [Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx) – v4.2.0 GA (VS Code)
    * [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit) – [v2.9.0 GA](https://aka.ms/mgt/2.9.0), v3.0 Preview
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) submissions
    * Milestone achievement – \>900 Power Platform Connectors!
    * [DailyMed](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/DailyMed) – [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * Citymapper – [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * TheGoodAPI – [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * Holopin – [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * [FishWatch](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/FishWatch) – [Andras Fordos](https://github.com/fordosa90)
    * [Pixel Encounter](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Pixel%20Encounter) – [Andras Fordos](https://github.com/fordosa90)
    * Exchange Rate – [Andras Fordos](https://github.com/fordosa90)
    * [SMS Wireless Services](https://learn.microsoft.com/connectors/smswirelessserviceip/) – [ViaData](https://www.viadata.nl/)
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
    * Good Flow story? Tell us. [FlowOfTheWeek](https://aka.ms/FlowOfTheWeekForm) – aka.ms/FlowOfTheWeekForm
* [Script samples](https://pnp.github.io/script-samples/)
    * New - PnP PowerShell – [Extract the configuration of a PnP Modern Search results web part and apply it on another site collection](https://pnp.github.io/script-samples/spo-deploy-pnpmodernsearch-webpart/README.html?tabs=pnpps) - [Kasper Bo Larsen](http://twitter.com/kasperbolarsen) \| @kasperbolarsen
    * [Good first issue asks](https://github.com/pnp/script-samples)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/)
    * [Meeting tab that records names so everyone can pronounce them properly](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-meeting-record-name) - [Markus Moeller](https://twitter.com/moeller2_0) \| @moeller2_0
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* [Power Platform Samples](https://pnp.github.io/powerplatform-samples/)
    * Power Apps – Injured Body Part Selection Gallery App - [Mubarak Adeyemo](https://twitter.com/tMub365) (HCS Business Solutions) \| @tMub365
    * Power Apps – [Microsoft Graph toolkit People Picker](https://www.m365princess.com/blogs/microsoft-graph-people-picker-power-apps/) - [Luise Freese](https://twitter.com/LuiseFreese) \| @LuiseFreese
    * Power Automate – SharePoint copy pages between sites - [Thijs Hereygers](https://www.linkedin.com/in/thijs-hereygers-017267121/) (Capgemini)
    * Power Automate – Set Dataverse lookups - [Taylor Becktold](https://twitter.com/BecktoldTaylor) (RSM US LLP) \| @BecktoldTaylor
* Conversations
    * Microsoft 365 PnP Weekly – Episode 191 (December 12th) with Microsoft Redmond based Visual Studio Development Program Manager - [Julia Kasper](https://twitter.com/Jujujuliakasper) \| @Jujujuliakasper \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-191/) \| [podcast](https://www.podbean.com/media/share/pb-vp8k5-1338aee)

### Demos

* **Extend Microsoft Teams apps across Microsoft 365 (Outlook and Office)** - use the same Mail Storage app – a static Teams personal app, in Teams, Outlook and Office.com to store emails with attachments in (Teams, Outlook, OneDrive) based on host environment (detected) in which the personal app is running. Microsoft Graph open extensions detects and links to mails already saved. Requires [TeamsJS SDK 2.0](https://learn.microsoft.com/microsoftteams/platform/tabs/how-to/using-teams-client-sdk?view=msteams-client-js-latest&tabs=javascript%2Cmanifest-teams-toolkit#whats-new-in-teamsjs-version-20&WT.mc_id=M365-MVP-5004617) (SSO), yoTeams v4.0 (instance) and [Teams manifest 1.13](https://learn.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema&WT.mc_id=M365-MVP-5004617) or greater. Sample available now.
* **Power Apps component library: Material design** - overview on Design Toolkit Initiative - prescriptive guidance around UI principles for Power Apps. Review UI options for makers – ugly/bad/good, material design, what/why component libraries for Power Apps, and introduction to first library with 16 components, template, proper documentation and 5000 SVGs. Download component library and template app then build an app, use mix of standard and component library controls, change app style easily in OnStart Property.


The host of this call was [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube ssgNG_mcKUE >}}

## Agenda items

* [06:46](https://youtu.be/ssgNG_mcKUE?t=406) – PnP .NET library updates - [Bert Jansen](http://twitter.com/O365bert) (Microsoft) @O365bert
* [08:21](https://youtu.be/ssgNG_mcKUE?t=501) – PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Valo Intranet) \| @gautamdsheth
* [10:15](https://youtu.be/ssgNG_mcKUE?t=615) – yo Teams updates - [Rick Van Rousselt](http://twitter.com/rickvanrousselt) (Advantive) \| @rickvanrousselt
* [11:31](https://youtu.be/ssgNG_mcKUE?t=691) – Microsoft Teams Toolkit updates - [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen
* [12:36](https://youtu.be/ssgNG_mcKUE?t=756) – Microsoft Graph Toolkit updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII
* [13:21](https://youtu.be/ssgNG_mcKUE?t=801) – Independent Publisher Connectors - [Jocelyn Panchal](https://twitter.com/JocelynP_PM) (Microsoft) \| @JocelynP_PM
* [15:16](https://youtu.be/ssgNG_mcKUE?t=916) – Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock
* [16:44](https://youtu.be/ssgNG_mcKUE?t=1004) – Microsoft Teams Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII
* [17:14](https://youtu.be/ssgNG_mcKUE?t=1034) – Microsoft Power Platform Samples - [April Dunnam](http://twitter.com/aprildunnam) (Microsoft) \| @aprildunnam
* [18:29](https://youtu.be/ssgNG_mcKUE?t=1109) – Together mode picture
* [19:39](https://youtu.be/ssgNG_mcKUE?t=1179) – Extend Microsoft Teams apps across Microsoft 365 (Outlook and Office) - [Markus Möller](https://twitter.com/Moeller2_0) (Avanade) \| @Moeller2_0
* [35:01](https://youtu.be/ssgNG_mcKUE?t=2101) – Power Apps component library: Material design - [April Dunnam](https://twitter.com/aprildunnam) (Microsoft) \| @aprildunnam, [Luise Freese](https://twitter.com/LuiseFreese) \| @LuiseFreese & [Robin Rosengrün](https://twitter.com/power_r2) (EnBW) \| @power_r2

## Together Mode

![together-221222.png](images/together-221222.png)

Thank you for joining the call today. Great to see some of you are donning your holiday apparel. Thank you as well for being with us through 2022 and into 2023!

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Do you have a cool flow? Tell us about it so we can write about it. \#FlowOfTheWeek aka.ms/FlowOfTheWeekForm
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Power Platform Samples Contributor \| Tuesday, January 10th, 10:30am PST \| [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
    * First Time Contributor \| Thursday, January 12th, 10am PT \| 1pm ET \| 7pm CET – [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNjAwRVNETlA1MkxIR1MyTEs5STZFVVRJMC4u)
    * Maturity Model Practitioners \| Tuesday, January 17th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * Writing for the Web \| Monday, January 23rd, 10am PT \| 1pm ET \| 7:00pm CET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMFNPNFMyUk9CNFROUjJWTFFGSzdJV0czVC4u)
    * PnP SPFx Samples w/ NVM \| Wednesday, January 25th, 9am PT \| 12pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNEE2SUdTOU1UOEtCTFU3MlM1SERDMlNVNi4u)
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

* **Extend Microsoft Teams apps across Microsoft 365 (Outlook and Office)**
* Article - [Extend Teams apps to M365 with SSO the right way](https://mmsharepoint.wordpress.com/2022/08/31/extend-teams-apps-to-m365-with-sso-the-right-way/)
* Sample - [Tab Office Mail Storage - Microsoft Teams App](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-office-sso-mail-save)
* Documentation - [Extend Teams apps across Microsoft 365](https://learn.microsoft.com/microsoftteams/platform/m365-apps/overview)
* Article - [M365 Across App scenarios - Teams apps and SPFx](https://pnp.github.io/blog/post/microsoft-365-app-scenarios/)
* **Power Apps component library: Material design**
* Tool - [Material Design](https://m2.material.io/design)
* Tool - [Power Apps Design Toolkit](https://github.com/pnp/powerapps-designtoolkit)

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)

## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.11.0 GA| 
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.8.0 GA|
[Microsoft 365 Assessment tool](https://docs.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool                                     
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.12.0 GA|Prepping v1.12.0 coming soon.  Nightly builds
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v4.1.0 GA|
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.9.0 GA
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.2.0 GA
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1 GA
[Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx)|v4.2.0 GA (VS Code), v17.4 (VS)|New builds daily                          
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.9.0 GA, v3.0 Preview|<https://aka.ms/mgt/2.9.0> 

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

* Microsoft 365 platform call - **(Coffee & chat with Community)** \| Tuesday, December 27, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Viva Connections & SharePoint Framework call \| Thursday, December 29, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft 365 platform call - **(Coffee & chat with Community)** \| Tuesday, January 3, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Microsoft 365 General Dev call - \| Thursday, January 5, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Office add-in monthly call \| Wednesday, January 11, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Power Platform monthly call \| Wednesday, January 18, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, January 19, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 22nd of December 2022*

{{< attachments >}}
