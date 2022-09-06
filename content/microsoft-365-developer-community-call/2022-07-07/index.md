---
title: "Microsoft 365 & Power Platform Development Community call - 7th of July, 2022"
date: 2022-07-07T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 Developer Community Call"]
images:
- images/recording-7th-july.png
tags: []
type: "regular"
summary: "Demos - Building Publishing Connectors for MailJet product, Microsoft Graph “Sites.Selected” permissions within SharePoint Online, and Introduction to available open-source list formatting samples from updated list formatting sample portal. Releases from .Net Libraries and PowerShell + 16 scripts/samples."
videos:
- https://www.youtube.com/watch?v=hH5Bk4OGuxQ
draft: false
---


## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Project releases
  * PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework) – v1.10.0 GA
  * PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev) - v1.7.0 GA
  * [PnP PowerShell](https://github.com/pnp/PnP-PowerShell) - v1.11.0 GA
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors)
  * New - [Easyship](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Easyship) - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
  * New - [DadJokesIO](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/DadJokesIO) - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
  * New - [CarbonFootprint](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/CarbonFootprint) - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
  * New - [Givebutter](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Givebutter) - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
  * New - [DHL Shipment Tracking](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/DHL%20Shipment%20Tracking) - [Woong Choi](https://www.linkedin.com/in/woongchoi/)
  * Updated - [RegEx Matching](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/RegEx%20Matching) - [Mitanshu Garg](https://twitter.com/mitanshu)
  * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* [Script samples](https://pnp.github.io/script-samples/)
  * New PowerShell - Add bulk users to SharePoint site groups from CSV - [Chandani Prajapati](http://twitter.com/Chandani_SPD) \| @Chandani_SPD
  * New Power App PowerShell -Get Flows Connected to SharePoint - [Russell Gove](http://twitter.com/russgove) (Tronox) \| @russgove
  * Updated CLI - Planner migration to SharePoint list - [Jasey Waegebaert](https://twitter.com/JWaegebaert) \| @JWaegebaert
  * Updated CLI - SharePoint Modern Page Publishing Report - [Nanddeep Nachan](http://twitter.com/NanddeepNachan) \| @NanddeepNachan
  * Updated CLI - Multiple Samples update – m365 connection check - [Jasey Waegebaert](https://twitter.com/JWaegebaert) \| @JWaegebaert
  * Updated CLI - Copy Planner plan - [Milan Holemans](https://github.com/milanholemans) \| milanholemans
  * Updated CLI - Copy library view to another library(ies) - [Reshmee Auckloo](http://twitter.com/ReshmeeAuckloo) \| @ReshmeeAuckloo
  * Updated PowerShell - Add multiple folders in libraries using a CSV file - [Jiten Palmer](https://twitter.com/Jitenpa44241205) \| @Jitenpa44241205
  * [Good first issue asks](https://github.com/pnp/script-samples)
* [Power Platform Samples](https://pnp.github.io/powerplatform-samples/)
  * [Accessibility color checker](https://github.com/LuiseFreese/powerapps-samples/tree/main/samples/accessibility-color-contrast-checker) - [Luise Freese](https://twitter.com/LuiseFreese) \| @LuiseFreese
  * Power Automate – Set SharePoint item level permissions - [Ramin Ahmadi](https://twitter.com/raminahmadi1986) \| @raminahmadi1986
* The MGT samples repository is now live! aka.ms/mgt/samples
* Microsoft 365 PnP Weekly – Episode 173 (July 4th) with by UK based Cloud Developer Advocate at Microsoft - [Garry Trinder](https://twitter.com/garrytrinder) \| @garrytrinder \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-173/) \| [podcast](https://www.podbean.com/media/share/pb-h8afv-1267cf7)

### Demos

* **Building Publishing Connectors for MailJet product** – the custom connector is a complete collection of all publicly available endpoints and methods for the Mailjet API. Mailjet is an easy-to-use all-in-one campaign e-mail tracking and reporting platform. Learn about Mailjet’s APIs and accessing them, the custom connector actions, and see a quick demo of the canvas app (Built in 10 minutes) for adding a mail recipient, sending a mail, and campaign reporting dashboard.
* **Microsoft Graph “Sites.Selected” permissions within SharePoint Online** – how to access SharePoint resources using a headless account without granting full permissions site access. Learn about Access Control Service (ACES) and its retirement, using PowerShell and the new Sites.Selected MS Graph permission for granular site level access, and how to automate and govern the granular access of sites with the *Sites Selected Request Tracker (SSRT)* tool. Step-by-step tool usage explained/shown herein.
* **Introduction to available open-source list formatting samples from updated list formatting sample portal** – exciting updates regarding the List Formatting Repo that address sample inconsistencies, currency and discovery. All samples and documentation have been updated. The Repo has been reorganized including new groupings by Operator, Placeholder Token, Action, Category, Feature, Author, and by Class. Instruction for submissions created. Go behind scenes to learn about the Farrier tool and automations now used to keep the repo up-to-date.


The host of this call was [David Warner II](http://twitter.com/DavidWarnerII)
(Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the
call.

{{< youtube hH5Bk4OGuxQ >}}

## Agenda items

* PnP .NET library updates - [Paolo Pialorsi](http://twitter.com/paolopia) (PiaSys.com) \| @paolopia – [5:35](https://youtu.be/hH5Bk4OGuxQ?t=335)
* PnP PowerShell updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [6:58](https://youtu.be/hH5Bk4OGuxQ?t=418)
* yo Teams updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [7:32](https://youtu.be/hH5Bk4OGuxQ?t=452)
* Microsoft Graph Toolkit updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [7:52](https://youtu.be/hH5Bk4OGuxQ?t=472)
* Independent Publisher Connectors - [Natalie Pienkowska](http://twitter.com/NataliePienkow1) (Microsoft) \| @NataliePienkow1 – [8:17](https://youtu.be/hH5Bk4OGuxQ?t=497)
* Microsoft Script Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [9:52](https://youtu.be/hH5Bk4OGuxQ?t=592)
* Microsoft Teams Samples - [Bob German](https://twitter.com/Bob1German) (Microsoft) @Bob1German – [10:30](https://youtu.be/hH5Bk4OGuxQ?t=630)
* Microsoft Power Platform Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [11:20](https://youtu.be/hH5Bk4OGuxQ?t=680)
* Demo - Building Publishing Connectors for MailJet product – [Clément Olivier](https://twitter.com/Clement0livier) \| @Clement0livier – [13:25](https://youtu.be/hH5Bk4OGuxQ?t=805)
* Demo - Microsoft Graph “Sites.Selected” permissions within SharePoint Online – [Pankaj Surti](https://twitter.com/pankajsurti) (Microsoft) \| @pankajsurti – [22:50](https://youtu.be/hH5Bk4OGuxQ?t=1370)
* Demo - Introduction to available open-source list formatting samples from updated list formatting sample portal – [Chris Kent](https://twitter.com/theChrisKent) (DMI) \| @theChrisKent – [41:41](https://youtu.be/hH5Bk4OGuxQ?t=2501)

## Together Mode

![together-mode-220707.gif](images/together-mode-220707.gif)

Welcome to July.  You are looking marvelous today!  Thanks for taking the time to join this call. 

## Actions

* Opt into PnP Recognition Program \| <https://aka.ms/m365pnp-recognition>
* Register for [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
  * Writing for the Web \| Monday, July 11th, 10am PT \| 1pm ET \| 7pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
  * Writing for the Web \| Tuesday, August 2nd, 9:30am PT \| 12:30pm ET \| 6:30pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
  * Writing for the Web \| Tuesday, September 6th, 9:30am PT \| 12:30pm ET \| 6:30pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
  * Power Platform Samples Contributor \| Wednesday, July 20th, 10am PST \| 1pm EST - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN09VTVU2QzRLNE0yVERQMklHSDBMUTJGWC4u)
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
* Sign up to [Share your story](https://aka.ms/share-your-story) in the [Learn from the community](https://aka.ms/LearnFromTheCommunity/ThisWeek) series.
* Request a Demo spot on the call – <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call – <http://aka.ms/spdev-sig-call>

## Demo references

* **Building Publishing Connectors for MailJet product**
  * Connector - [MailJet (Independent Publisher) (Preview)](https://docs.microsoft.com/connectors/mailjetip/)
  * Repo – [MailJet](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/MailJet)
  * Connectors - [Welcome to the Independent Publisher Connector Directory!](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors)
* **Microsoft Graph “Sites.Selected” permissions within SharePoint Online**
  * Article - [How does the MS Graph “Sites.Selected” permission work for granular permissions for SPO sites?](https://pankajsurti.com/2021/12/15/how-do-sites-selected-work-for-granular-permissions-for-spo-sites/)
  * Article – [How to automate and govern the “Sites.Selected” permissions using a custom tool?](https://pankajsurti.com/2022/01/16/how-to-automate-and-govern-the-sites-selected-permissions-using-a-custom-tool/)
  * Article - [Controlling app access on a specific SharePoint site collections is now available in Microsoft Graph](https://devblogs.microsoft.com/microsoft365dev/controlling-app-access-on-specific-sharepoint-site-collections/)
* **Introduction to available open-source list formatting samples from updated list formatting sample portal**
  * Repo - [Community-tooling](https://github.com/pnp/Community-Tooling)
  * Samples - [SharePoint List Formatting Samples](https://github.com/pnp/List-Formatting)
  * Documentation – [Use column formatting to customize SharePoint](https://docs.microsoft.com/sharepoint/dev/declarative-customization/column-formatting?WT.mc_id=m365-15744-cxa) \| aka.ms/spdev-column-formatting

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

* Office add-in monthly call \| Wednesday, July 13, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, July 14, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Adaptive Cards monthly call \| Thursday, July 14, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Power Platform monthly call \| Wednesday, July 20, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* M365 General Dev call \| Thursday, July 21, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, July 21, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Microsoft 365 platform call \| Tuesday, September 6, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 7th of July 2022*

{{< attachments >}}

