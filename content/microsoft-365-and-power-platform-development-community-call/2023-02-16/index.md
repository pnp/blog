---
title: "Microsoft 365 & Power Platform Development Community call - 16th of February, 2023"
date: 2023-02-16T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-16th-feb.png
tags: []
type: "regular"
summary: "TTwo demos: Building Microsoft Teams tabs with Adaptive Cards and Creating an Internal CV (Curriculum Vitae) with List Formatting. Delivered Microsoft Teams Toolkit – v4.2.2, 10 Connectors, 1 Teams, 3 Script, and 2 Power Apps samples."
videos:
- https://www.youtube.com/watch?v=6qtx04uZsgs
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Announcements
    * LinkedIn group for discussions – aka.ms/community/Li
    * Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, February 21st, 8:00 am PT.
        * Latest news from Microsoft engineering on Microsoft 365 topics
        * Demo - **Dan Wahlin** – Integrate Azure Communication Services Calling into a React App
        * Demo - **Garry Trinder** – Teams Toolkit Learn Path - Build a bot using Teams Toolkit for Visual Studio Code
    * Microsoft Graph and .NET – March Hack Together - aka.ms/hack-together - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR0ktYAUCTtVIvJkJdFsfkalUMlM0SVBXRjIyTEFJQVFYOUMzTDE2SEY1WS4u)
    * Teams Toolkit - Pre-release of major release for VS code extension on February 17. Option to participate in a paid [Teams Toolkit vNext Research](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR8OQoXNnVBNAhorPb5Q2zppUQ1EwODFEUjYxM1JIRzJPODlMSjNNSlJDVS4u) study on new features – aka.ms/AAjnc9a
    * Global [POWER PLATFORM BOOTCAMP \#2023](http://WWW.POWERPLATFORMBOOTCAMP.COM) – Feb 24 - 25
    * Power Platform Samples Contributor \| Thursday, February 23rd, 9:00am PT \| 12:00pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
* Project releases
    * [Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx) – v4.2.2 (GA) VS Code Extension
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) submissions
    * [NREL](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/NREL) - [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * [Hugging Face](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Hugging%20Face) - [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * [Lexica](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Lexica) - [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * [DiceBear](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/DiceBear) - [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * [IBM Watson Text to Speech](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/IBM%20Watson%20Text%20to%20Speech) - [Lucas Titus](https://twitter.com/offline) \| @offline
    * [IBM Watson Assistant](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/IBM%20Watson%20Assistant) - [Lucas Titus](https://twitter.com/offline) \| @offline
    * [WhatsApp](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/WhatsApp) - [Zakariya Fakir](https://github.com/zak0807)
    * [Krozu PM](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Krozu%20PM) - [Osazee Odigie](https://twitter.com/osazee_odigie) \| @osazee_odigie
    * [MeaningCloud](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/MeaningCloud) - [Clement Oliver](https://twitter.com/Clement0livier) \| @Clement0livier
    * [Coupa](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Coupa) - [NovaGL](https://github.com/NovaGL)
    * Updated - [OpenAI](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/OpenAI) – now supports DALL E2 - [PowerRobin](https://github.com/PowerRobin)
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
    * Good Flow story? Tell us. [FlowOfTheWeek](https://aka.ms/FlowOfTheWeekForm) – aka.ms/FlowOfTheWeekForm
* [Script samples](https://pnp.github.io/script-samples/)
    * New – PnP PowerShell – [Bulk import data from multiple files to multiple lists](https://pnp.github.io/script-samples/spo-bulk-import-data/README.html?tabs=pnpps) - [Reshmee Auckloo](http://twitter.com/ReshmeeAuckloo) \| @ReshmeeAuckloo
    * New – PnP PowerShell – [Pinpoint the items/docs that hasn’t been indexed yet after an update](https://pnp.github.io/script-samples/spo-get-items-not-indexed-since-last-update/README.html?tabs=pnpps) - [Kasper Bo Larsen](http://twitter.com/kasperbolarsen) \| @kasperbolarsen
    * New – General PowerShell – [Bulk Email Send from CSV using Microsoft Graph API](https://pnp.github.io/script-samples/graph-send-email-from-csv-onbehalf-of-user/README.html?tabs=graphps) - [Siddharth Vaghasia](http://twitter.com/siddh_me) \| @siddh_me
    * [Good first issue asks](https://github.com/pnp/script-samples)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/) – Featured Teams App Samples with Full Tutorials
    * [Tab Office Offer Creation](https://adoption.microsoft.com/en-us/sample-solution-gallery/sample/pnp-sp-dev-teams-sample-tab-office-offer-creation/) - [Markus Möller](https://twitter.com/Moeller2_0) (Avanade) \| @Moeller2_0
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* [Power Platform Samples](https://pnp.github.io/powerplatform-samples/) & [Power Apps Samples](https://github.com/pnp/powerapps-samples)
    * Power Apps – [App Login](https://github.com/pnp/powerapps-samples/tree/main/samples/app-login) - [Seth Addo](https://github.com/seths10) \| seths10
    * Power Apps – [Search Movies](https://github.com/pnp/powerapps-samples/tree/main/samples/SearchMovies) - [Aaryan Arora](https://github.com/aaryan2134) \| aaryan2134
    * Power Apps – [Student Application Process](https://github.com/pnp/powerapps-samples/commit/4273e53196e955369c341f3671c83c44aab7ff50) - [Samia Sohail Azim](https://github.com/sam-404) \| sam-404
* [Conversations](https://aka.ms/pnpweekly)
    * Microsoft 365 PnP Weekly – Episode 197 (February 13th) with Belgium-based Senior Software Engineer on the ODSP team at Microsoft - [Bert Jansen](https://twitter.com/O365Bert) (Microsoft) \| @O365Bert \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-197/) \| [podcast](https://www.podbean.com/eas/pb-jpx9m-138e49f)
    * Microsoft 365 Developer Podcast – Partner showcase: ShareGate with Louis Beaudoin-Allaire (February 13th) \| [podcast](https://m365devpodcast.com/e/partner-showcase-sharegate-with-louis-beaudoin-alliare/)
    * Microsoft 365 Developer Podcast – Graph Developer Proxy with Waldek Mastykarz and Sebastien Levert (February 5th) \| [podcast](https://m365devpodcast.com/e/graph-developer-proxy-with-waldek-mastykarz-and-sebastien-levert/)


### Demos

* **Building Microsoft Teams tabs with Adaptive Cards** – and using Microsoft Search API to search resources. Build tabs using ready-made UI building blocks for native UI on Desktop/Web/Mobile. Use Bot for back-end and Adaptive Cards for front-end. Reviews prerequisites like bot development/registration and SSO configuration if login is required. Also covers technology limitations. Step through configurations for app manifest, SSO, App Registration, task modules, use of adaptive card Designer, and more. [aka.ms/Feb16-Demo1](https://aka.ms/Feb16-Demo1)
* **Creating an Internal CV (Curriculum Vitae) with List Formatting** – using Microsoft Lists to track info about people and their work history. Change your thinking from a standard card to a single large CV card footprint using JSON view formatting. Microsoft Lists card elements: In place field editing, expandable editing boxes, custom hovercards and clickable attachments (automation using Power Automate). Field editing box embedded in a card thanks to inlineEditField JSON property. [aka.ms/Feb16-Demo2](https://aka.ms/Feb16-Demo2)

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube 6qtx04uZsgs >}}

## Agenda items

[00:00](https://youtu.be/6qtx04uZsgs?t=0) – Intro - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[06:18](https://youtu.be/6qtx04uZsgs?t=378) – PnP .NET library updates - [Bert Jansen](http://twitter.com/O365bert) (Microsoft) @O365bert

[08:30](https://youtu.be/6qtx04uZsgs?t=510) – PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Valo Intranet) \| @gautamdsheth

[10:40](https://youtu.be/6qtx04uZsgs?t=640) – yo Teams updates - [Rick Van Rousselt](http://twitter.com/rickvanrousselt) (Advantive) \| @rickvanrousselt

[12:04](https://youtu.be/6qtx04uZsgs?t=724) – Microsoft Teams Toolkit updates - [John Miller](https://twitter.com/jmillerdev) (Microsoft) \| @jmillerdev

[13:36](https://youtu.be/6qtx04uZsgs?t=816) – Microsoft Graph Toolkit updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[14:04](https://youtu.be/6qtx04uZsgs?t=844) – Independent Publisher Connectors - [Jocelyn Panchal](https://twitter.com/JocelynP_PM) (Microsoft) \| @JocelynP_PM

[15:53](https://youtu.be/6qtx04uZsgs?t=953) – Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock

[17:49](https://youtu.be/6qtx04uZsgs?t=1069) – Microsoft Teams Samples - [Bob German](https://twitter.com/Bob1German) (Microsoft) @Bob1German

[19:02](https://youtu.be/6qtx04uZsgs?t=1142) – Microsoft Power Platform Samples - [April Dunnam](http://twitter.com/aprildunnam) (Microsoft) \| @aprildunnam

[20:10](https://youtu.be/6qtx04uZsgs?t=1210) – Together mode picture

[21:18](https://youtu.be/6qtx04uZsgs?t=1278) – Demo - Building Microsoft Teams tabs with Adaptive Cards – [Ramin Ahmadi](https://twitter.com/raminahmadi1986) (Content+Cloud)​ \| @raminahmadi1986

[38:09](https://youtu.be/6qtx04uZsgs?t=2289) – Demo - Creating an Internal CV (Curriculum Vitae) with List Formatting – [Federico Sapia](https://twitter.com/X365Fede)​ (ANPAL Servizi) \| @X365Fede

[53:45](https://youtu.be/6qtx04uZsgs?t=3225) – Closing

## Together Mode

![together-230216.png](images/together-230216.png)

A virtually packed virtual auditorium! Thank you everybody once again for joining on the call. Awesome to see you.

## Actions

* Microsoft Graph and .NET – March Hack Together - aka.ms/hack-together - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR0ktYAUCTtVIvJkJdFsfkalUMlM0SVBXRjIyTEFJQVFYOUMzTDE2SEY1WS4u)
* Request a Demo spot on the call – <https://aka.ms/community/request/demo>
* Join the next monthly Power Platform Integrations / Connectors LABs Participant call. [Complete this form](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR0BHMrjhL0hDmckROosW6AFUOUVHNTlRRlAxQUI5S0hJNFdIWkZBRzlaTy4u).
* Chime into a Community Calls Conversation – chat about demos anytime. Links and QR Codes associated to every demo – see in call deck and in demo summaries.
* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Maturity Model Practitioners \| Tuesday, February 21st, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * Power Platform Samples Contributor \| Thursday, February 23rd, 9:00am PT \| 12:00pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Do you have a cool flow? Tell us about it so we can write about it. \#FlowOfTheWeek aka.ms/FlowOfTheWeekForm
* What key scenarios are missing from the PnP Core SDK? Let us know and/or view the latest changes at [PnP Core SDK Changelog](https://github.com/pnp/pnpcore/blob/dev/src/sdk/CHANGELOG.md).
* PowerShell – The team is thinking of dropping support for PS 5, any strong objections? Suggestions in general? Please visit [PnP.PowerShell Changelog](https://github.com/pnp/powershell/blob/dev/CHANGELOG.md)
* Ideas for Microsoft Lists? aka.ms/Feedback/Lists
* Suggestions for yo teams? [Discussions](https://github.com/pnp/generator-teams/discussions)
* Create a connector – [Top Power Platform Independent Publisher Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* Wish list for [Microsoft Teams](https://github.com/pnp/teams-dev-samples/issues/new/choose)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Download the recurrent invite for this call – <http://aka.ms/spdev-sig-call>

## Demo references

* **Building Microsoft Teams tabs with Adaptive Cards**
    * Samples – [teams-dev-samples](https://github.com/pnp/teams-dev-samples/tree/main/samples)
    * Documentation - [Build tabs with Adaptive Cards](https://learn.microsoft.com/microsoftteams/platform/tabs/how-to/build-adaptive-card-tabs)
    * Documentation – [Configure SSO for your bot](https://learn.microsoft.com/microsoftteams/platform/sbs-bots-with-sso?tutorial-step=3)
    * Documentation – [Overview of the Microsoft Search API in Microsoft Graph](https://learn.microsoft.com/graph/search-concept-overview)
    * Tool – [Adaptive Cards Designer](https://www.adaptivecards.io/designer/)
* **Creating an Internal CV (Curriculum Vitae) with List Formatting**
    * Sample - [Internal CV](https://github.com/pnp/List-Formatting/tree/master/view-samples/internal-cv)
    * chrome web store - [SP Formatter](https://chrome.google.com/webstore/detail/sp-formatter/fmeihfaddhdkoogipahfcjlicglflkhg?hl=en)
    * Visual Studio Marketplace – [SP Formatter](https://marketplace.visualstudio.com/items?itemName=s-kainet.sp-formatter#:~:text=SP%20Formatter%20VSCode%20extension%20creates,to%20browser%20with%20live%20preview.)

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)

## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.11.0 GA| 
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.8.0 GA|
[Microsoft 365 Assessment tool](https://docs.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool                                     
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.12.0 GA|v2.x is available in nightly builds !!!
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v4.1.0 GA, v4.1.1-preview.2|
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.8.0 GA, v1.8.1-preview
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.2.0 GA, v1.4.0-preview
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1 GA
[Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx)|v4.2.2 GA (VS Code), v17.4 (VS), v17.5-preview-2 (VS)|New builds daily                          
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

* Microsoft 365 platform call \| Tuesday, February 21, 8:00 am PT - <https://aka.ms/m365-dev-call> (weekly)
* Viva Connections & SharePoint Framework call \| Thursday, February 23, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft 365 General Dev call \| Thursday, March 2, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Office add-in monthly call \| Wednesday, March 8, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Power Platform monthly call \| Wednesday, March 15, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, March 16, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 16th of February 2023*

{{< attachments >}}
