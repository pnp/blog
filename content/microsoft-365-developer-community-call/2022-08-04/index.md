---
title: "Microsoft 365 & Power Platform Development Community call - 4th of August, 2022"
date: 2022-08-04T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 Developer Community Call"]
images:
- images/recording-4th-august.png
tags: []
type: "regular"
summary: "Demos: ProvisionGenie v.3.0 – focus on Localization and Accessability and List formatting backgrounds and borders using new isSelected placeholder. Delivered 8 new/updated Power Platform Independent Publisher Connectors along with 5 script, and 2 Power Platform samples."
videos:
- https://www.youtube.com/watch?v=yZ-dJvmt8Zo
draft: false
---


## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) submissions
    * New – [Microsoft Partner Center](https://github.com/microsoft/PowerPlatformConnectors/pull/1834/commits) - [Oleksii Skirko](https://www.linkedin.com/in/oleksii-skirko/)
    * New – [Snowflake](https://github.com/microsoft/PowerPlatformConnectors/pull/1840) - [Rene Koch](https://github.com/rekodus)
    * New – Datamuse - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * New – Moosend - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * New – Shadify - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * Updated – [Notion](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Notion) - [Chandra Sekhar Malla](https://twitter.com/ChandraSMalla) \| @ChandraSMalla
    * Updated – [Quickbase](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Quickbase) - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * Updated – [SchoolDigger](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/SchoolDigger) - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* [Script samples](https://pnp.github.io/script-samples/)
    * New PowerShell – [Update web part properties on modern pages](https://pnp.github.io/script-samples/spo-update-modern-webpart-properties/README.html?tabs=pnpps) - [Ramin Ahmadi](https://twitter.com/raminahmadi1986) \| @raminahmadi1986
    * New PowerShell – [Export SharePoint Term Store terms to CSV](https://pnp.github.io/script-samples/spo-export-termstore-terms-to-csv/README.html?tabs=pnpps) - [Ramin Ahmadi](https://twitter.com/raminahmadi1986) \| @raminahmadi1986
    * New CLI – [List external users across all sites and in what site groups](https://pnp.github.io/script-samples/spo-list-site-externalusers-in-groups/README.html?tabs=cli-m365-ps) - [Martin Lingstuyl](https://github.com/martinlingstuyl)
    * Updated CLI – [List all external users in all site collections](https://pnp.github.io/script-samples/spo-list-site-externalusers/README.html?tabs=cli-m365-ps) - [Martin Lingstuyl](https://github.com/martinlingstuyl)
    * Updated Power App PowerShell – [Copy Planner plan](https://pnp.github.io/script-samples/planner-copy-planner-plan/README.html?tabs=cli-m365-ps) - [Reshmee Auckloo](http://twitter.com/ReshmeeAuckloo) \| @ReshmeeAuckloo
    * [Good first issue asks](https://github.com/pnp/script-samples)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/)
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
    * Documentation – [Microsoft Teams JavaScript client SDK](https://docs.microsoft.com/javascript/api/overview/msteams-client) \| aka.ms/TeamsSDK-v2
    * Documentation – [Microsoft 365 Platform Community Call – 7th of June, 2022](https://www.youtube.com/watch?v=B4F0KY-qCUU&t=1202s) \| aka.ms/TeamsSDK-v2-Community-Call
* [Power Platform Samples](https://pnp.github.io/powerplatform-samples/)
    * New – [Progress-Bar Components](https://www.m365princess.com/blogs/build-powerapps-progressbar-component/) - [Luise Freese](https://twitter.com/LuiseFreese) \| @LuiseFreese
    * New – Get terms from Term Store - [Ramin Ahmadi](https://twitter.com/raminahmadi1986) \| @raminahmadi1986
* The MGT samples repository is now live! \| aka.ms/mgt/samples


### Demos

* **ProvisionGenie v.3.0 – focus on Localization and Accessibility** – newly released v3.0 delivers Localization - UI in 12 languages. Languages are easily added – upload from spreadsheet to localization table in Microsoft Dataverse. Admins can limit language options presented for user to choose. Accessibility options include Theming, Screen reader and Keyboard-only support, and language availability. Call to action is to translate ProvisionGenie into more languages to enable more people to benefit from this application.
* **List formatting backgrounds and borders using new isSelected placeholder** – isSelected is used with classes found on formatting samples site, applies formatting (backgrounds, borders) to selected row or changes image in column of selected row. Classes used ms-bgColor- applies a background color, sp-field-border sets border-width and border-style. Two Bonus on-the-fly demos show new “customRowAction” to expose a context menu and new expression called “split” for formatting text and borders around text.

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII)
(Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube yZ-dJvmt8Zo >}}

## Agenda items

* Microsoft Graph Toolkit updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [6:10](https://youtu.be/yZ-dJvmt8Zo?t=370)
* Independent Publisher Connectors - [Natalie Pienkowska](http://twitter.com/NataliePienkow1) (Microsoft) \| @NataliePienkow1 – [6:39](https://youtu.be/yZ-dJvmt8Zo?t=399)
* Microsoft Script Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [8:05](https://youtu.be/yZ-dJvmt8Zo?t=485)
* Microsoft Teams Samples - [Bob German](https://twitter.com/Bob1German) (Microsoft) @Bob1German – [8:46](https://youtu.be/yZ-dJvmt8Zo?t=526)
* Microsoft Power Platform Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [10:30](https://youtu.be/yZ-dJvmt8Zo?t=630)
* Demo - ProvisionGenie v.3.0 – focus on Localization and Accessability – [Luise Freese](https://twitter.com/LuiseFreese) \| @LuiseFreese – [11:51](https://youtu.be/yZ-dJvmt8Zo?t=711)
* Demo - List formatting backgrounds and borders using new isSelected placeholder – [Chris Kent](https://twitter.com/theChrisKent) (DMI) \| @theChrisKent – [28:42](https://youtu.be/yZ-dJvmt8Zo?t=1722)


## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Power Platform Samples Contributor \| Wednesday, August 17th, 9:30am PT \| 12:30pm ET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN09VTVU2QzRLNE0yVERQMklHSDBMUTJGWC4u)
    * Writing for the Web \| Tuesday, September 6th, 9:30am PT \| 12:30pm ET \| 6:30pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Maturity Model Practitioners \| Tuesday, September 20th, 7am PST - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* What do you need from PnP Core SDK? Let us know and/or view the latest changes at [PnP Core SDK Changelog](https://github.com/pnp/pnpcore/blob/dev/src/sdk/CHANGELOG.md).
* PowerShell suggestions? Please visit [PnP.PowerShell Changelog](https://github.com/pnp/powershell/blob/dev/CHANGELOG.md)
* Ideas for Microsoft Lists? aka.ms/Feedback/Lists
* Create a connector – [Top Power Platform Independent Publisher Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Request a Demo spot on the call – <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call – <http://aka.ms/spdev-sig-call>

## Demo references

* **ProvisionGenie v.3.0 – focus on Localization and Accessability**
    * Documentation – [ProvisionGenie – Dataverse vs Dataverse for Teams](https://provisiongenie.com/architecturedecisions/#dataverse-vs-dataverse-for-teams)
    * Tool – [ProvisionGenie](https://github.com/ProvisionGenie)
    * Documentation - [Release notes](https://provisiongenie.com/about/releasenotes/)
* **List formatting backgrounds and borders using new isSelected placeholder**
    * List Formatting Samples - [Samples by Class: ms-bgColor-\*](https://pnp.github.io/List-Formatting/groupings/classes/ms-bgColor/)
    * List Formatting Samples - [Samples by Class: sp-field-border\*](https://pnp.github.io/List-Formatting/groupings/classes/sp-field-border/)
    * Documentation - [Use column formatting to customize SharePoint](https://docs.microsoft.com/sharepoint/dev/declarative-customization/column-formatting) \| [aka.ms/spdev-column-formatting](https://aka.ms/spdev-column-formatting)
    * Icons - [Flicon.io](https://flicon.io/)
    * Repo - Farrier [Community-tooling](https://github.com/pnp/community-tooling)
    * Samples - [SharePoint List Formatting Samples](https://github.com/pnp/List-Formatting)

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)


## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.10.0 GA|Prepping 1.11.0 (after summer break)
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.7.0 GA|Prepping for 1.8.0 (after summer break)
[Microsoft 365 Assessment tool](https://docs.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool                                     
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.11.0 GA|
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v4.0.0 GA
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

* Office add-in monthly call \| Wednesday, August 10, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, August 11, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Adaptive Cards monthly call \| Thursday, August 11, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Power Platform monthly call \| Wednesday, August 17, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft 365 General Dev call \| Thursday, August 18, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, August 18, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Microsoft 365 platform call \| Tuesday, September 6, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 4th of August 2022*

{{< attachments >}}

