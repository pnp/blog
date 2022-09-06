---
title: "Microsoft 365 & Power Platform Development Community call - 1st of September, 2022"
date: 2022-09-01T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 Developer Community Call"]
images:
- images/recording-1st-september.png
tags: []
type: "regular"
summary: "Demos: Independent Publisher Connector - OpenAI connector on using AI for content creation and interactions AND How to animate SVGs in Adaptive Cards. Delivered 5 Independent Publisher Connectors, 2 script and 3 Power Platform samples. Released Microsoft Teams App camp."
videos:
- https://www.youtube.com/watch?v=Yt4QcHjNr6A
draft: false
---


## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, September 6th, 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * **Brian Jackett & Cameron Parker** - Latest on eDiscovery Premium APIs on Microsoft Graph
    * **Alex Terentiev & Vesa Juvonen** - SPFx feature demo/preview
    * **Merill Fernando** - Introduction to Graph X-Ray
* Project releases
    * Yo teams - generator-teams – v4.0.1 GA (Fixed an issue with tab configuration)
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) submissions
    * New - Fantasy Premier League – [Joe Unwin](https://twitter.com/flow_joe_) \| @flow_joe\_
    * New - Mockaroo – [Richard Wilson](https://twitter.com/PowerAppsRAW) (Welcome!) \| @PowerAppsRAW
    * New - Mapbox – Simone Lin (Welcome!)
    * New - Near Earth Object Web Service – [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * New - USGS Earthquake Hazards – [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* [Script samples](https://pnp.github.io/script-samples/)
    * New CLI for Microsoft 365 – [Get notified in Microsoft Teams about SharePoint health incidents](https://pnp.github.io/script-samples/tenant-health-notify-teams/README.html?tabs=cli-m365-ps) – [Martin Lingstuyl](https://github.com/martinlingstuyl)
    * Updated CLI for Microsoft 365 – [Ensure the Site Assets Library is created](https://pnp.github.io/script-samples/spo-ensure-siteassets-library/README.html?tabs=cli-m365-ps) – [Martin Lingstuyl](https://github.com/martinlingstuyl)
    * Site update: Now filter scripts used for security and permissions
    * [Good first issue asks](https://github.com/pnp/script-samples)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/)
    * New resource site - [Microsoft Teams App camp](https://aka.ms/app-camp) \| aka.ms/app-camp – Securely migrate applications to Microsoft Teams – Hands on labs and samples.
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* [Power Platform Samples](https://pnp.github.io/powerplatform-samples/)
    * Email Translation - [Lama Alluwaymi](https://github.com/Lama-alluwaymi)
    * PDF Converter - [Lama Alluwaymi](https://github.com/Lama-alluwaymi)
    * Weather Sample - [Lama Alluwaymi](https://github.com/Lama-alluwaymi)
* The [MGT samples repository](https://aka.ms/mgt/samples) is now live! \| aka.ms/mgt/samples
* Microsoft 365 PnP Weekly – Episode 176 (August 29th) with Netherlands-based [Daniel Laskewitz](https://twitter.com/laskewitz), Microsoft Senior Cloud Developer Advocate – Power Platform \| @laskewitz \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-176/) \| [podcast](https://www.podbean.com/media/share/pb-dc4ui-12aef1a)

### Demos

* **Independent Publisher Connector - OpenAI connector on using AI for content creation and interactions** – through connector, access OpenAI’s Generative Pre-trained Transformer 3 (GPT-3), an autoregressive language model that uses deep learning to produce human-like text. To access GPT-3, you will need an OpenAI account. Connector exposes available GPT-3 List engines and responses to your questions (prompts) in any language. Familiarize yourself with OpenAI’s capabilities in Playground then build an instant cloud flow with an OpenAI step to access APIs via connector.
* **How to animate SVGs in Adaptive Cards** – see how to animate a basic SVG and add the animated file to an Adaptive Card. Why use animation, structure of an SVG, SVG animation options. The mechanics of adding an SVG to an Adaptive Card, limitations, and workarounds. In demo, animate with CSS keyframes because supported by every browser. Encode SVG in Adaptive Cards Designer or host it on site like svgur.com.

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII)
(Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube Yt4QcHjNr6A >}}

## Agenda items

* PnP .NET library updates - [Paolo Pialorsi](http://twitter.com/paolopia) (PiaSys.com) \| @paolopia – [7:26](https://youtu.be/Yt4QcHjNr6A?t=446)
* PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Valo Intranet) \| @gautamdsheth – [8:40](https://youtu.be/Yt4QcHjNr6A?t=520)
* yo Teams updates - [Stephan Bisser](https://twitter.com/stephanbisser) (Solvion) \| @stephanbisser – [10:16](https://youtu.be/Yt4QcHjNr6A?t=616)
* Microsoft Graph Toolkit updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [11:31](https://youtu.be/Yt4QcHjNr6A?t=691)
* Independent Publisher Connectors - [Natalie Pienkowska](http://twitter.com/NataliePienkow1) (Microsoft) \| @NataliePienkow1 – [12:07](https://youtu.be/Yt4QcHjNr6A?t=727)
* Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock – [13:57](https://youtu.be/Yt4QcHjNr6A?t=837)
* Microsoft Teams Samples - [Bob German](https://twitter.com/Bob1German) (Microsoft) @Bob1German – [15:58](https://youtu.be/Yt4QcHjNr6A?t=958)
* Microsoft Power Platform Samples - [April Dunnam](http://twitter.com/aprildunnam) (Microsoft) \| @aprildunnam – [17:26](https://youtu.be/Yt4QcHjNr6A?t=1046)
* Demo - Independent Publisher Connector - OpenAI connector on using AI for content creation and interactions – [Robin Rosengrün](https://twitter.com/power_r2) (EnBW) \| @power_r2 – [19:34](https://youtu.be/Yt4QcHjNr6A?t=1174)
* Demo - How to animate SVGs in Adaptive Cards – [Kristine Kolodziejski](https://twitter.com/kristinekk94) (Computacenter) \| @kristinekk94 – [34:08](https://youtu.be/Yt4QcHjNr6A?t=2048)


## Together Mode

![together-mode-220901.gif](images/together-mode-220901.gif)

Thank you for being part of the Community. We appreciate you and your feedback. Our goal is to make everyone’s lives a bit easier.

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Join us next Tuesday – September 6th at 8 am PT for the resumption of the weekly Microsoft 365 platform call.
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Writing for the Web \| Tuesday, September 6th, 9:30am PT \| 12:30pm ET \| 6:30pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Maturity Model Practitioners \| Tuesday, September 20th, 7am PST - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
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

* **Independent Publisher Connector - OpenAI connector on using AI for content creation and interactions**
    * Documentation - [OpenAI (Independent Publisher) (Preview)](https://docs.microsoft.com/connectors/openaiip/)
    * Repo – [OpenAI](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/OpenAI)
    * Connectors - [Welcome to the Independent Publisher Connector Directory!](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/MailJet)
* **How to animate SVGs in Adaptive Cards**
    * Example – [a Pen by Kristine Kolodziejski](https://codepen.io/powerpuffkk/pen/oNdvmJj)
    * Images – [svgshare](https://svgur.com/) (share SVG vector files)
    * Twitter - [Kristine Kolodziejski](https://twitter.com/kristinekk94) \| @kristinekk94
    * YouTube [Kristine Kolodziejski](https://www.youtube.com/channel/UCGmsp6wr31Bj77QSMzMCElg) (channel)
    * Blog - [Kristine Kolodziejski](https://www.kristinekolodziejski.com/)

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)

## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.10.0 GA|Prepping 1.11.0 (after summer break)
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.7.0 GA|Prepping for 1.8.0 (after summer break)
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

* Microsoft 365 platform call \| Tuesday, September 6, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Viva Connections & SharePoint Framework call \| Thursday, September 8, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Adaptive Cards monthly call \| Thursday, September 8, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Office add-in monthly call \| Wednesday, September 14, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Microsoft 365 General Dev call \| Thursday, September 15, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, September 15, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Power Platform monthly call \| Wednesday, September 21, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 1st of September 2022*

{{< attachments >}}

