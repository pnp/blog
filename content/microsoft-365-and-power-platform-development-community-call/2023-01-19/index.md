---
title: "Microsoft 365 & Power Platform Development Community call - 19th of January, 2023"
date: 2023-01-19T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-19th-january.png
tags: []
type: "regular"
summary: "Demos: Extend Azure AD to add pronouns to a people card component in Power Apps using Microsoft Graph and Create a conversational bot in Microsoft Teams using OpenAI. Released YoTeams & Teams Toolkit previews and 17 samples."
videos:
- https://www.youtube.com/watch?v=SVfxqBpQF4o
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Announcements
    * Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, January 24th, 8:00 am PT.
        * Latest news from Microsoft engineering on Microsoft 365 topics
        * **Luca Bandinelli, John Nguyen** and **Alex Terentiev** – SPFx and next steps with Microsoft engineering
        * **Vesa Juvonen** and **Andrew Connell (Voitanos)** – Introduction to Viva Connection learn module - tutorial 3
    * Sharing-Is-Caring training dates in February - aka.ms/sharing-is-caring
    * Community Recognition Program badges for 2023 - aka.ms/community/recognition
    * Community Calls Conversations – continue the conversation - chat about demos anytime
* Project releases
    * [Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams) – v4.1.1-preview.2
    * [Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core) – v1.8.1-preview
    * [Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy) – v1.4.0-preview
    * [Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx) – v17.5-preview-2 (VS)
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) submissions
    * [Readwise](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Readwise) - [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * [Swagger Converter](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Swagger%20Converter) - [Andras Fordos](https://github.com/fordosa90)
    * [LanguageTool](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/LanguageTool) - [Andras Fordos](https://github.com/fordosa90)
    * [TSheets Quickbooks Time](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/TSheets%20Quickbooks%20Time) - Artesian Software)
    * Postman - [Tomasz Poszytek](https://twitter.com/TomaszPoszytek) \| @TomaszPoszytek
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
    * Good Flow story? Tell us. [FlowOfTheWeek](https://aka.ms/FlowOfTheWeekForm) – aka.ms/FlowOfTheWeekForm
* [Script samples](https://pnp.github.io/script-samples/)
    * New – Azure CLI + Microsoft Graph - [Uploads a large file to SharePoint using MS Graph REST API and PowerShell](https://pnp.github.io/script-samples/graph-upload-file-to-sharepoint/README.html?tabs=azure-cli) - [Paul Matthews](https://twitter.com/cann0nf0dder) \| @cann0nf0dder
    * New – Microsoft Graph PowerShell SDK - [Create Dynamic Install and Uninstall Azure AD Groups using Graph](https://pnp.github.io/script-samples/aad-graph-create-dynamic-groups-project-visio/README.html?tabs=graphps) - [Andrew Taylor](https://twitter.com/Andrewtaylor_2) \| @Andrewtaylor_2
    * New – PnP PowerShell - [Creates and apply site designs](https://pnp.github.io/script-samples/spo-add-sitedesign-permissions/README.html?tabs=pnpps) - [Reshmee Auckloo](http://twitter.com/ReshmeeAuckloo) \| @ReshmeeAuckloo
    * New – PnP PowerShell - [Enable page scheduling on a modern site pages library](https://pnp.github.io/script-samples/spo-enable-page-scheduling/README.html?tabs=pnpps) - [Nanddeep Nachan](http://twitter.com/NanddeepNachan) \| @NanddeepNachan
    * New – PnP PowerShell - [Retrieve Message Centre announcements and post to teams](https://pnp.github.io/script-samples/spo-get-message-centre-announcements-and-post-to-teams-channel/README.html?tabs=pnpps) - [Valeras Narbutas](http://twitter.com/ValerasNarbutas) (Macaw) \| @ValerasNarbutas
    * New – PnP PowerShell - [Create Document Set in SharePoint Library](https://pnp.github.io/script-samples/spo-create-documentset/README.html?tabs=pnpps) - [Jimmy Hang](https://www.linkedin.com/in/jimmyhang/)
    * New – PnP PowerShell - [Enable Site Collection App Catalogs on a specific sites using CSV](https://pnp.github.io/script-samples/spo-enable-site-collection-app-catalog/README.html?tabs=spoms-ps) - [Nanddeep Nachan](http://twitter.com/NanddeepNachan) \| @NanddeepNachan
    * New – PnP PowerShell - [Extract the employees shown on modern pages (Author byline) in a selection of Site Collections to CSV](https://pnp.github.io/script-samples/spo-export-people-web-part-users/README.html?tabs=pnpps) - [Kasper Bo Larsen](http://twitter.com/kasperbolarsen) \| @kasperbolarsen
    * New – Azure AD Module - [Create AD app, add permissions and connect to SharePoint](https://pnp.github.io/script-samples/aad-add-app-permissions-and-connect-to-sharepoint/README.html?tabs=azuread) - [Valeras Narbutas](http://twitter.com/ValerasNarbutas) (Macaw) \| @ValerasNarbutas
    * Updated – CLI for Microsoft 365 - [Create AD app, add permissions, and connect to SharePoint](https://pnp.github.io/script-samples/aad-add-app-permissions-and-connect-to-sharepoint/README.html?tabs=azuread) - [Adam Wójcik](http://twitter.com/Adam25858782) \| @Adam25858782
    * Updated – PnP PowerShell - [Deploy sppkgs and install apps](https://pnp.github.io/script-samples/spo-deploy-sppkgs-and-install-apps/README.html?tabs=pnpps) - [Matteo Serpi](https://github.com/srpmtt)
    * [Good first issue asks](https://github.com/pnp/script-samples)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/) – Featured Teams App Samples with Full Tutorials
    * [HR Consulting App](https://aka.ms/hr-talent-app) – C\#
    * [HR Consulting App node](https://aka.ms/hr-talent-app-node) – TypeScript
    * [One Productivity Hub](https://aka.ms/one-productivity-hub)
    * [Emergency Response site](https://aka.ms/emergency-response)
    * [Northwind Orders App](https://aka.ms/app-camp)
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* [Power Platform Samples](https://pnp.github.io/powerplatform-samples/)
    * [PDF Reader Creator Kit](https://angelogulisano.com/creator-kit-introduction/) - [Angelo Gulisano](https://twitter.com/angelog1908) \| @angelog1908
* Conversations
    * Microsoft 365 PnP Weekly – Episode 193 (January 16th) with UK-based M365 Consultant, Content AI Specialist and Microsoft MVP (M365 Apps & Services) - [Leon Armston](https://twitter.com/LeonArmston) (Intelogy) \| @LeonArmston \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-193/) \| [podcast](https://www.podbean.com/eas/pb-z33y6-1365f69)
    * Microsoft 365 PnP Weekly – Episode 192 (January 9th) with Netherlands based CTO Low-Code Solutions and Microsoft MVP - [Albert-Jan Schot](https://twitter.com/appieschot) (BLIS.digital) \| @appieschot \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-192/) \| [podcast](https://pnpweekly.podbean.com/)

### Demos

* **Extend Azure AD to add pronouns to a people card component in Power Apps using Microsoft Graph** – register application in AAD to create extension. In Graph Explorer - associate new property with user object, patch user with new property and get user to check if property is in place. Create custom connector for Power Platform (bring Graph API into Power Platform) and call custom connector in a Power Apps canvas app (people card you create) to display and patch pronouns. Conversation [aka.ms/Jan19-Demo1](https://aka.ms/Jan19-Demo1)
* **Create a conversational bot in Microsoft Teams using OpenAI** – development - user sends message from Teams client to the Azure Bot ID defined in Teams app manifest, Azure Bot sends message to Bot code that is running in an Azure Function (doesn’t have to be an Azure Function), Bot sends the text from message sent from Teams to OpenAI API and answer/response is sent back to Teams (in Adaptive Cards). Conversation [aka.ms/Jan19-Demo2](https://aka.ms/Jan19-Demo2)

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube SVfxqBpQF4o >}}

## Agenda items

[00:00](https://youtu.be/SVfxqBpQF4o?t=0) – Intro - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[06:20](https://youtu.be/SVfxqBpQF4o?t=380) – PnP .NET library updates - [Bert Jansen](http://twitter.com/O365bert) (Microsoft) @O365bert

[08:14](https://youtu.be/SVfxqBpQF4o?t=494)<https://youtu.be/Qiw1jrys_lw?t=557> – PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Valo Intranet) \| @gautamdsheth

[10:05](https://youtu.be/SVfxqBpQF4o?t=605) – yo Teams updates - [Stephan Bisser](https://twitter.com/stephanbisser) (Solvion) \| @stephanbisser

[11:19](https://youtu.be/SVfxqBpQF4o?t=679) – Microsoft Teams Toolkit updates - [John Miller](https://twitter.com/jmillerdev) (Microsoft) \| @jmillerdev

[13:48](https://youtu.be/SVfxqBpQF4o?t=828) – Microsoft Graph Toolkit updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[14:20](https://youtu.be/SVfxqBpQF4o?t=860) – Independent Publisher Connectors - [Jocelyn Panchal](https://twitter.com/JocelynP_PM) (Microsoft) \| @JocelynP_PM

[15:37](https://youtu.be/SVfxqBpQF4o?t=937) – Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock

[18:34](https://youtu.be/SVfxqBpQF4o?t=1114) – Microsoft Teams Samples - [Bob German](https://twitter.com/Bob1German) (Microsoft) @Bob1German

[20:56](https://youtu.be/SVfxqBpQF4o?t=1256) – Microsoft Power Platform Samples - [April Dunnam](http://twitter.com/aprildunnam) (Microsoft) \| @aprildunnam

[21:34](https://youtu.be/SVfxqBpQF4o?t=1294) – Together mode picture

[22:23](https://youtu.be/SVfxqBpQF4o?t=1343) – Demo - Extend Azure AD to add pronouns to a people card component in Power Apps using Microsoft Graph – [Luise Freese](https://twitter.com/LuiseFreese) \| @LuiseFreese

[36:37](https://youtu.be/SVfxqBpQF4o?t=2197) – Demo - Create a conversational bot in Microsoft Teams using OpenAI – [Lee Ford](https://twitter.com/lee_ford) (Symity) \| @lee_ford

[51:56](https://youtu.be/SVfxqBpQF4o?t=3116) – Closing

## Together Mode

![together-230119.png](images/together-230119.png)

Thanks everyone for joining the call and sinking into those new posh seats during today’s Together Mode! Please keep the feedback coming. See you again soon.

## Actions

* Chime into a Community Calls Conversation – chat about demos anytime. Links and QR Codes associated to every demo – see in call deck and in demo summaries.
* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Do you have a cool flow? Tell us about it so we can write about it. \#FlowOfTheWeek aka.ms/FlowOfTheWeekForm
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Writing for the Web \| Monday, January 23rd, 10am PT \| 1pm ET \| 7:00pm CET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMFNPNFMyUk9CNFROUjJWTFFGSzdJV0czVC4u)
    * PnP SPFx Samples w/NVM \| Wednesday, January 25th, 9am PT \| 12pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNEE2SUdTOU1UOEtCTFU3MlM1SERDMlNVNi4u)
    * Maturity Model Practitioners \| Tuesday, February 21st, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * Power Platform Samples Contributor \| Thursday, February 23rd, 9:00am PT \| 12:00pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
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

* **Extend Azure AD to add pronouns to a people card component in Power Apps using Microsoft Graph**
    * Playground - [Microsoft Graph Toolkit: UI Components and Authentication Providers for Microsoft Graph](https://mgt.dev/) \| mgt.dev/
    * Tool – [Microsoft Graph Explorer](https://developer.microsoft.com/graph/graph-explorer) \| aka.ms/ge
    * Article - [How to add Azure AD directory extensions](https://www.m365princess.com/blogs/azure-ad-directory-extensions/)
* **Create a conversational bot in Microsoft Teams using OpenAI**
    * Sample - [Teams OpenAI Conversation Bot](https://github.com/pnp/teams-dev-samples/tree/main/samples/bot-openai) \| aka.ms/bot-openai
    * Org – [Open AI](https://openai.com/about/)
    * Documentation – [GPT-3 model](https://beta.openai.com/docs/models/gpt-3)

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)

## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.11.0 GA|
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.8.0 GA|
[Microsoft 365 Assessment tool](https://learn.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.12.0 GA|Prepping v1.12.0 coming soon.  Nightly builds
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v4.1.0 GA, v4.1.1-preview.2|
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.8.0 GA, v1.8.1-preview
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.2.0 GA, v1.4.0-preview
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1 GA
[Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx)|v4.2.1 GA (VS Code), v17.4 (VS), v17.5-preview-2 (VS)|New builds daily
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

* Microsoft 365 platform call \| Tuesday, January 24, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Viva Connections & SharePoint Framework call \| Thursday, January 26, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft 365 platform call \| Tuesday, January 31, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Microsoft 365 General Dev call \| Thursday, February 2, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Office add-in monthly call \| Wednesday, February 8, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Power Platform monthly call \| Wednesday, February 15, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, February 16, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 19th of January 2023*

{{< attachments >}}{{< /attachments >}}
