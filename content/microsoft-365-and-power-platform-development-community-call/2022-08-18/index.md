---
title: "Microsoft 365 & Power Platform Development Community call - 18th of August, 2022"
date: 2022-08-18T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-18th-aug.png
tags: []
type: "regular"
summary: "Demos: Independent Publisher Connectors - RegEx Matching Demo, List Formatting Magic – Data and Time formatting options, and Create a list template from your pre-configured list with list formatting definitions. Delivered 2 Independent Publisher Connectors, 10 script, 2 Teams and 4 Power Platform samples."
videos:
- https://www.youtube.com/watch?v=N1ZsqY6JdFo
draft: false
---


## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) submissions
    * Updated – [Square Business](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Square%20Business) - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * Updated – [Square Payments](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Square%20Payments) - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* [Script samples](https://pnp.github.io/script-samples/)
    * New PowerShell – [Export checked-out files in all sites associated with a hub site to CSV](https://pnp.github.io/script-samples/spo-export-checked-out-files-in-all-sites-associated-with-a-hub-site-to-csv/README.html?tabs=pnpps) by Arash Aghajani
    * New PowerShell – [Restore large number of items from SharePoint Recycle bin in bulk](https://pnp.github.io/script-samples/bulk-restore-from-recyclebin/README.html?tabs=pnpps) by Paul Matthews
    * New PowerShell – [Request Reindex of SharePoint User Profile Properties](https://pnp.github.io/script-samples/spo-request-pnp-reindex-user-profile/README.html?tabs=pnpps) by [Todd Klindt](https://twitter.com/ToddKlindt) \| @ToddKlindt
    * New PowerShell – [Create a SharePoint site using the configuration of another site](https://pnp.github.io/script-samples/spo-extract-and-invoke-site-template/README.html?tabs=pnpps) by Lewis Baybutt
    * New PowerShell – [Bulk Publish Syntex Models To Libraries](https://pnp.github.io/script-samples/spo-bulk-publish-syntex-model/README.html?tabs=pnpps) by [Leon Armston](http://twitter.com/LeonArmston) \| @LeonArmston
    * New PowerShell – [Update web part properties on modern pages](https://pnp.github.io/script-samples/spo-update-modern-webpart-properties/README.html?tabs=pnpps) by [Ramin Ahmadi](https://twitter.com/raminahmadi1986) \| @raminahmadi1986
    * New CLI – [Get Azure AD app permission info](https://pnp.github.io/script-samples/aad-get-app-permission/README.html?tabs=cli-m365-ps) by [Michaël Maillot](https://twitter.com/michael_maillot) \| @michael_maillot
    * Updated PowerShell – [Add a document library web part to a page](https://pnp.github.io/script-samples/spo-add-document-library-webpart-to-page/README.html?tabs=pnpps) by [Todd Klindt](https://twitter.com/ToddKlindt) \| @ToddKlindt
    * Updated PowerShell – [Request Reindex of SharePoint User Profile Properties](https://pnp.github.io/script-samples/spo-request-pnp-reindex-user-profile/README.html?tabs=pnpps) by [Todd Klindt](https://twitter.com/ToddKlindt) \| @ToddKlindt
    * Updated PowerShell – [Copy Planner Plan](https://pnp.github.io/script-samples/planner-copy-planner-plan/README.html?tabs=cli-m365-ps) by [Reshmee Auckloo](http://twitter.com/ReshmeeAuckloo) \| @ReshmeeAuckloo
    * [Good first issue asks](https://github.com/pnp/script-samples)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/)
    * Teams Toolkit sample - [One Productivity Hub](https://aka.ms/teamsfx-one-productivity-hus) - [Ayca Bas](https://twitter.com/aycabs) \| @aycabs
    * Bot sample - [Teams Meeting Details](https://aka.ms/tab-meeting-details) - [Markus Möller](https://twitter.com/Moeller2_0) @Moeller2_0
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* [Power Platform Samples](https://pnp.github.io/powerplatform-samples/)
    * Progress-Bar Components - [Luise Freese](https://twitter.com/LuiseFreese) \| @LuiseFreese
    * Twitter Connection - [Lama Alluwaym](https://github.com/Lama-alluwaymi)i
    * Get terms from Term Store - [Ramin Ahmadi](https://twitter.com/raminahmadi1986) \| @raminahmadi1986
    * SharePoint Site Creation Bot - [Michel Mendes](https://twitter.com/michelcarlo) \| @michelcarlo
* The MGT samples repository is now live! \| aka.ms/mgt/samples

### Demos

* **Independent Publisher Connectors - RegEx Matching Demo** – need to validate end-user data input? Familiar with IsMatch, Match and MatchAll functions in Power Apps? Now this same capability to test for a match or extract portions of a text string based on a pattern is available within Power Automate using this RegEx Matching connector! Returns true/false results. Multiple pre-defined expressions or developer can provide their own custom regular expression.
* **List Formatting Magic – Data and Time formatting options** – eliminate times aligned to dates for clean date-to-date comparisons. Here’s four functions for Zeroing out dates – Date () (convert text to date based on locale), getDate () (get day of month), getMonth () (get month index), and getYear () (get 4-digit year). In list, display number of days since list item was modified. Show date formatting in list and gallery views. Apply conditional formatting for clarity.
* **Create a list template from your pre-configured list with list formatting definitions** – favorite formatted list that you want to replicate? Create a custom list template using 3 PowerShell commands. Adds all formatting – list and gallery views to template. Task prerequsites – SharePoint Online PowerShell and Global or SharePoint Admin role. Template creation. Fine-tune your list in the UI, then extract to Site Script (Get-SPOSiteScript), register Site Script (Add-SPOSiteScript), Upload a thumbnail, and register list design (Add-SPOListDesign).

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII)
(Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube N1ZsqY6JdFo >}}

## Agenda items

* PnP .NET library updates – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) @vesajuvonen – [5:50](https://youtu.be/N1ZsqY6JdFo?t=350)
* PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Valo Intranet) \| @gautamdsheth – [7:11](https://youtu.be/N1ZsqY6JdFo?t=431)
* yo Teams updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [9:01](https://youtu.be/N1ZsqY6JdFo?t=541)
* Microsoft Graph Toolkit updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [9:23](https://youtu.be/N1ZsqY6JdFo?t=563)
* Independent Publisher Connectors - [Natalie Pienkowska](http://twitter.com/NataliePienkow1) (Microsoft) \| @NataliePienkow1 – [10:09](https://youtu.be/N1ZsqY6JdFo?t=609)
* Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock – [12:04](https://youtu.be/N1ZsqY6JdFo?t=724)
* Microsoft Teams Samples - [Bob German](https://twitter.com/Bob1German) (Microsoft) @Bob1German – [14:14](https://youtu.be/N1ZsqY6JdFo?t=854)
* Microsoft Power Platform Samples - [April Dunnam](http://twitter.com/aprildunnam) (Microsoft) \| @aprildunnam – [16:09](https://youtu.be/N1ZsqY6JdFo?t=969)
* Demo - Independent Publisher Connectors - RegEx Matching Demo – [Mitanshu Garg](https://twitter.com/mitanshu) (Schlumberger) \| @mitanshu – [18:37](https://youtu.be/N1ZsqY6JdFo?t=1117)
* Demo - List Formatting Magic – Data and Time formatting options – [Chris Kent](https://twitter.com/theChrisKent) (DMI) \| @theChrisKent – [24:52](https://youtu.be/N1ZsqY6JdFo?t=1492)
* Demo - Create a list template from your pre-configured list with list formatting definitions – [Chris Kent](https://twitter.com/theChrisKent) (DMI) \| @theChrisKent – [47:00](https://youtu.be/N1ZsqY6JdFo?t=2820)


## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Writing for the Web \| Tuesday, September 6th, 9:30am PT \| 12:30pm ET \| 6:30pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Maturity Model Practitioners \| Tuesday, September 20th, 7am PST - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* What key scenarios are missing from the PnP Core SDK? Let us know and/or view the latest changes at [PnP Core SDK Changelog](https://github.com/pnp/pnpcore/blob/dev/src/sdk/CHANGELOG.md).
* Thinking of dropping support for PS 5, any strong objections ??? PowerShell suggestions in general? Please visit [PnP.PowerShell Changelog](https://github.com/pnp/powershell/blob/dev/CHANGELOG.md)
* Ideas for Microsoft Lists? aka.ms/Feedback/Lists
* Create a connector – [Top Power Platform Independent Publisher Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Request a Demo spot on the call – <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call – <http://aka.ms/spdev-sig-call>

## Demo references

* **Independent Publisher Connectors - RegEx Matching Demo**
    * Documentation – [RegEx Connector](https://learn.microsoft.com/connectors/regexmatchingip/)
    * Connectors - [Welcome to the Independent Publisher Connector Directory!](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/)
* **List Formatting Magic – Data and Time formatting options**
    * Documentation - [Use column formatting to customize SharePoint](https://learn.microsoft.com/sharepoint/dev/declarative-customization/column-formatting) \| aka.ms/spdev-column-formatting
    * Icons - [Flicon.io](https://flicon.io/)
    * Repo - Farrier [Community-tooling](https://github.com/pnp/community-tooling)
    * Samples - [SharePoint List Formatting Samples](https://github.com/pnp/List-Formatting)
* **Create a list template from your pre-configured list with list formatting definitions**
    * Documentation - [Use column formatting to customize SharePoint](https://learn.microsoft.com/sharepoint/dev/declarative-customization/column-formatting) \| aka.ms/spdev-column-formatting
    * Icons - [Flicon.io](https://flicon.io/)
    * Repo - Farrier [Community-tooling](https://github.com/pnp/community-tooling)
    * Samples - [SharePoint List Formatting Samples](https://github.com/pnp/List-Formatting)

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)


## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.10.0 GA|Prepping 1.11.0 (after summer break)
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.7.0 GA|Prepping for 1.8.0 (after summer break)
[Microsoft 365 Assessment tool](https://learn.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool
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

* Viva Connections & SharePoint Framework call \| Thursday, August 25, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft 365 General Dev call \| Thursday, September 1, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Microsoft 365 platform call \| Tuesday, September 6, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Adaptive Cards monthly call \| Thursday, September 8, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Office add-in monthly call \| Wednesday, September 14, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Microsoft Identity Platform call \| Thursday, September 15, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Power Platform monthly call \| Wednesday, September 21, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 18th of August 2022*

{{< attachments >}}{{< /attachments >}}
