---
title: "Microsoft 365 & Power Platform Development Community call - 9th of June, 2022"
date: 2022-06-09T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-9th-june.png
tags: []
type: "regular"
summary: "Demos - Independent Publishing Connectors Sessionize Demo, List Formatting - Payment Registration, and Understanding Sites.Selected permissions in SharePoint Online. Yo teams version preview releases, 5 Independent Publisher Connectors, 9 scripts and 1Teams sample. Power Platform Samples Contributor training announced."
videos:
- https://www.youtube.com/watch?v=DPye7S6lVf0
draft: false
---


## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, June 14, 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * **Rabeb Othmani** - Introduction to Microsoft Graph Postman collection
    * **Maisa Rissi** - Microsoft Graph .Net SDK v5
    * **Greg Taylor** - Latest on deprecating basic auth for Exchange
* Project releases
    * [Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams) - v4.0.0-preview.3
    * [Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core) - v1.7.0-preview.3
    * Note: Between major releases there are many fixes and improvements on all projects each week and for these we thank the many contributors who work tirelessly behind the scenes to bring first rate capabilities to the members of this community. Anytime you wish to see latest updates or contribute to a project, please pull down a repo to get started. Thanks!
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors)
    * New - MS Graph Groups and Users - [Jay Jani](https://www.linkedin.com/in/jayjani03/)
    * New - RegEx Matching - Mitanshu Garg
    * New - Meme - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * New - Unofficial Netflix Search - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * Updated - [GoQR](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/GoQR) (originally built by Rui Santos) - [Woong Choi](https://www.linkedin.com/in/woongchoi/)
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* [Script samples](https://adoption.microsoft.com/sample-solution-gallery)
    * New CLI Scenario – [Copy planner plan](https://adoption.microsoft.com/sample-solution-gallery/planner-copy-planner-plan) - [Milan Holemans](https://www.linkedin.com/in/milan-holemans/)
    * Updated CLI Scenario – [Fetch User Profile Properties from Site Collection and export to CSV](https://adoption.microsoft.com/sample-solution-gallery/fetch-user-profile-properties) - [Mathijs Verbeeck](https://www.linkedin.com/in/mathijsverbeeck/)
    * Updated CLI Scenario – [SharePoint Online Hub Site Association](https://adoption.microsoft.com/sample-solution-gallery/spo-hub-sites-association) - [Jasey Waegebaert](https://twitter.com/JWaegebaert) \| @JWaegebaert
    * Updated CLI Scenario – [Get SharePoint List or Library Permissions and export to CSV](https://adoption.microsoft.com/sample-solution-gallery/spo-get-list-library-permission-export-to-csv) - [Nanddeep Nachan](https://twitter.com/NanddeepNachan) \| @NanddeepNachan
    * Updated CLI Scenario – [Reset files permissions unique to inheritance](https://adoption.microsoft.com/sample-solution-gallery/reset-files-permission-unique-to-inherited) - [Nanddeep Nachan](https://twitter.com/NanddeepNachan) \| @NanddeepNachan
    * Updated CLI Scenario – [Script allow copy column format in SharePoint and appl to different column](https://adoption.microsoft.com/sample-solution-gallery/spo-apply-column-format) - [Jasey Waegebaert](https://twitter.com/JWaegebaert) \| @JWaegebaert
    * Updated CLI Scenario – [Bulk Library generation](https://adoption.microsoft.com/sample-solution-gallery/spo-create-bulk-libraries) - [Milan Holemans](https://www.linkedin.com/in/milan-holemans/)
    * Updated CLI Scenario – [Run a search query and export to CSV](https://adoption.microsoft.com/sample-solution-gallery/spo-search-export-to-csv) - [Smita Nachan](https://www.linkedin.com/in/smitanachan/)
    * Updated PowerShell Scenario – [Planner migration to SharePoint List](https://adoption.microsoft.com/sample-solution-gallery/planner-migration-spo-list) - [Reshmee Auckloo](https://twitter.com/ReshmeeAuckloo) \| @ReshmeeAuckloo
    * [Good first issue asks](https://github.com/pnp/script-samples)
* [Teams samples](https://adoption.microsoft.com/sample-solution-gallery?sortby=creationDateTime-true&keyword=&product=Teams&action=ajax_plugin_call_sample_solution_gallery)
    * New - [Movie Vote - Tab meeting w/stageview](https://adoption.microsoft.com/sample-solution-gallery/pnp-sp-dev-teams-sample-tab-meeting-stageview-basic) - [Markus Moeller](https://twitter.com/Moeller2_0) \| @Moeller2_0
* Microsoft 365 PnP Weekly – Episode 169 (June 6th) with Belgium based Microsoft 365 Solution Architect and MVP at Qubix - [Yannick Reekmans](https://twitter.com/YannickReekmans) \| @YannickReekmans \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-169/) \| [podcast](https://www.podbean.com/media/share/pb-uvjxj-1244047)

### Demos

* **Independent Publishing Connectors Sessionize Demo** - use Sessionize connector with Power Automate to populate an e-mail listing speakers and sessions from Sessionize, on agenda for conference you’re organizing. Step through creating a Power App, gallery, selecting data source (Sessionize connector), and choosing methods to complete UI. Then create a cloud flow in Power Automate that creates an HTML table (containing speakers and sessions) and sends table in e-mail to conference attendees.
* **List Formatting - Payment Registration** - extending Microsoft Lists Expense tracker template’s capabilities by adding file picker, locations (embedded Bing maps), payment timeline view and mobile view list formatting. Solution leverages a SharePoint page - filter web parts, Power Automate - declarative JSON for flow (expense approval), and Adaptive Cards for approval in a Teams channel. Create/populate a new expense item and call a flow action for large expense approval.
* **Understanding Sites.Selected permissions in SharePoint Online** - the new Sites.Selected permission in AAD negates the need for ACS. Sites.Selected is an application permission for Microsoft Graph and/or SPO and allows Admins to grant Read or Write permission to the selected/targeted sites. Manage sites using Graph or CSOM/REST. PnP PowerShell can be used to Grant, Get, Revoke and Set AAD app permissions in Azure. Perfect for running an application in the background.

The host of this call was [David Warner II](https://twitter.com/DavidWarnerII)
(Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the
call.

{{< youtube DPye7S6lVf0 >}}

## Agenda items

* PnP .NET library updates - [Bert Jansen](https://twitter.com/O365bert) (Microsoft) @O365bert – [6:12](https://youtu.be/DPye7S6lVf0?t=372)
* PnP PowerShell updates - [Gautam Sheth](https://twitter.com/gautamdsheth) (Valo Intranet) \| @gautamdsheth – [8:14](https://youtu.be/DPye7S6lVf0?t=494)
* yo Teams updates - [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [9:39](https://youtu.be/DPye7S6lVf0?t=579)
* Microsoft Graph Toolkit updates - [Sébastien Levert](https://twitter.com/sebastienlevert) (Microsoft) \| @sebastienlevert – [10:00](https://youtu.be/DPye7S6lVf0?t=600)
* Independent Publisher Connectors - [Natalie Pienkowska](https://twitter.com/NataliePienkow1) (Microsoft) \| @NataliePienkow1 – [11:00](https://youtu.be/DPye7S6lVf0?t=660)
* Microsoft Script Samples - [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [13:22](https://youtu.be/DPye7S6lVf0?t=802)
* Microsoft Teams Samples - [Bob German](https://twitter.com/Bob1German) (Microsoft) \| @Bob1German – [13:57](https://youtu.be/DPye7S6lVf0?t=837)
* Microsoft Power Platform Samples - [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [15:33](https://youtu.be/DPye7S6lVf0?t=933)
* Demo - Independent Publishing Connectors Sessionize Demo - [Nanddeep Nachan](https://twitter.com/NanddeepNachan) \| @NanddeepNachan & [Smita Nachan](https://twitter.com/SmitaNachan) \| @SmitaNachan – [17:00](https://youtu.be/DPye7S6lVf0?t=1020)
* Demo - List Formatting - Payment Registration - [André Lage](https://twitter.com/aaclage) (Datalynx AG) \| @aaclage – [29:05](https://youtu.be/DPye7S6lVf0?t=1745)
* Demo - Understanding Sites.Selected permissions in SharePoint Online - [Paolo Pialorsi](https://twitter.com/PaoloPia) (PiaSys.com) \| @PaoloPia – [43:56](https://youtu.be/DPye7S6lVf0?t=2636)

## Actions

* Create a connector – [Top Power Platform Independent Publisher Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* Attend the next [Power Platform LABs call](https://aka.ms/PowerPlatformIntegrationLABs), June 29, 8am PT \|11am ET
* Opt into PnP Recognition Program \| <https://aka.ms/m365pnp-recognition>
* Register for [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Writing for the Web \| Thursday, June 23, 12pm PT \| 3pm ET \| 9pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Writing for the Web \| Monday, June 27, 10am PT \| 1pm ET \| 7pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Power Platform Samples Contributor \| Wednesday, June 29, 10:00 am PT - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN09VTVU2QzRLNE0yVERQMklHSDBMUTJGWC4u)
    * Maturity Model Practitioners \| [Register](https://aka.ms/mm4m365)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* What do you need from PnP Core SDK? Let us know and/or view the latest changes at [PnP Core SDK Changelog](https://github.com/pnp/pnpcore/blob/dev/src/sdk/CHANGELOG.md).
* PowerShell suggestions? Please visit [PnP.PowerShell Changelog](https://github.com/pnp/powershell/blob/dev/CHANGELOG.md)
* Ideas for Microsoft Lists? aka.ms/Feedback/Lists
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Sign up to [Share your story](https://aka.ms/share-your-story) in the [Learn from the community](https://aka.ms/LearnFromTheCommunity/ThisWeek) series.
* Request a Demo spot on the call – <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call – <https://aka.ms/spdev-sig-call>

## Demo references

* **Independent Publishing Connectors Sessionize Demo**
    * Documentatiuon - [Sessionize (Independent Publisher) (Preview)](https://learn.microsoft.com/connectors/sessionizeip/)
    * Repo – [Sessionize](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Sessionize)
    * Blog – [Nadddeep Nachan](https://nanddeepnachanblogs.com/)
    * Documentation – [Sessionize API / Embed Documentation for Developers](https://sessionize.com/api-documentation)
* **List Formatting - Payment Registration**
    * Sample - [Payment format](https://github.com/pnp/List-Formatting/tree/master/view-samples/payments-format)
    * Sample - [Bing Maps format](https://github.com/pnp/List-Formatting/tree/master/column-samples/generic-bingmaps-format)
    * Sample - [File Picker format](https://github.com/pnp/List-Formatting/tree/master/column-samples/generic-filepicker-format)
    * Samples - [SharePoint List Formatting Samples](https://github.com/pnp/List-Formatting)
* **Understanding Sites.Selected permissions in SharePoint Online**
    * Video - [Sites.Selected Application permission for Graph and SharePoint APIs](https://youtu.be/mz4ye-AsUnY)
    * Documentation - [Sites permissions - Application permissions](https://learn.microsoft.com/graph/permissions-reference#application-permissions-56)
    * Article - [Controlling app access on a specific SharePoint site collections is now available in Microsoft Graph](https://devblogs.microsoft.com/microsoft365dev/controlling-app-access-on-specific-sharepoint-site-collections/)

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)


## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.9.0 GA|Prepping for v1.10.0 (end of June)
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.6.0 GA|Prepping for v1.7.0 (end of June)
[Microsoft 365 Assessment tool](https://learn.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.10.0 GA|Bug fixes and improvements continue to 1.11 release (end of June)
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v3.5.0 GA,v4.0.0-preview.3|Version 4.0 is imminent – pending an issue with the new Teams JS SDK
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.6.0 GA, v1.7.0-preview.3
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

* Microsoft 365 platform call \| Tuesday, June 14, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Power Platform monthly call \| Wednesday, June 15, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, June 16, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, June 16, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* M365 General Dev call \| Thursday, June 23, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Office add-in monthly call \| Wednesday, July 13, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Adaptive Cards monthly call \| Thursday, June 14, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 9th of June 2022*

{{< attachments >}}{{< /attachments >}}
