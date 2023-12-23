---
title: "Viva Connections & SharePoint Framework Community Call – 23rd of March, 2023"
date: 2023-03-23T04:00:22.873Z
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-23rd-march.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Demos: Building advance interactive world map for business information with SPFx, Creating Viva Connections extension with user presence status using Microsoft Graph Presence API and SPFx, and Exposing business data in Microsoft 365 using Azure Data API builder and SPFx."
videos:
- https://www.youtube.com/watch?v=v-P2Hcwcarc
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Announcements
    * Agenda set for next [Microsoft 365 & Power Platform weekly call](https://aka.ms/m365-dev-call) - Tuesday, March 28th, 8:00 am PT.
        * Latest news from Microsoft engineering on Microsoft 365 topics
        * **Luca Bandinelli, John Nguyen, Alex Terentiev** – SPFx v1.17 release - what's new and what's there
        * **Rabeb Othmani** – Kiota SDK generator is now available - What you need to know!
        * **Garry Trinder** - Deploy a Microsoft Teams app to Azure using Teams Toolkit for Visual Studio Code
    * [Community Recognition Program](https://pnp.github.io/recognitionprogram/) badges for 2023 - aka.ms/community/recognition
* Shows and Events
    * Build once, deploy efficiently, connect across Microsoft 365 – Virtual event. March 29, 2023, 9:00AM PST. [Register](https://aka.ms/BuildwithTeams)
    * Microsoft 365 Conference – May 2 – 4. 2023, Las Vegas – m365Con.com - [Register](https://m365conf.com/)
    * Upcoming [Community Days](https://communitydays.org/) Events - aka.ms/communitydays
* Project releases
    * [SharePoint Framework (SPFx)](https://aka.ms/spfx) – v1.17 (Preview)
    * [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) – v6.3 (GA)
    * [Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download) – v0.5 (Preview)
    * [Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react) – v3.13.0 (GA)
    * [Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls) – v3.12.0 (GA)
    * [Viva Connections Toolkit for VS Code](https://github.com/pnp/vscode-viva) – v0.4.1 (Preview)
* [SPFx samples](https://aka.ms/spfx-webparts)
    * Updated – [Birthdays](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-birthdays) - [Valeras Narbuta](https://twitter.com/ValerasNarbuta)s \| @ValerasNarbutas
    * Updated – [Page Navigator](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-page-navigator) - [Abderahman Moujahid](https://github.com/Abderahman88) \| Abderahman88
    * New – [DevOps Tasks](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-azure-devops-tasks) - [Takashi Shinohara](https://twitter.com/karamem0) \| @karamem0
* [ACE samples](https://aka.ms/spfx-aces)
    * New – Most Likes Pages - [Aimery Thomas](https://twitter.com/aimery_Thomas) \| @aimery_thomas
* Conversations
    * Microsoft 365 PnP Weekly – Episode 202 (March 20th) with US-based Microsoft MVP and Vice President of Engineering at tyGraph - [Corey Roth](https://twitter.com/coreyroth) \| @coreyroth \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-202/) \| [podcast](https://www.podbean.com/eas/pb-gr6za-13c0bd8)
    * Power Platform Connections - Power Platform Connections Ep 5 - Stephen Siciliano (March 17th) \| [video](https://www.youtube.com/watch?v=sT0w0kX_Qj8)

### Demos

* **Building advance interactive world map for business information with SPFx** – this Interactive Map web part delivers the ability to add custom markers, map layers and has a host of configuration options. “Bing Maps” has few configuration options comparatively speaking. Review creator’s idea and highlights, technology/packages used, demo, and resources. See property pane customization options (add marker, category, update legend) and general settings (define layers, plug-ins, categories). All markers are stored in web part.
* **Creating Viva Connections extension with user presence status using Microsoft Graph Presence API and SPFx** – an introduction to the Graph Presence API, API methods, presence sessions, presence sessions with SPFx, a setPresence method example, and suggestion to use Graph Explorer to experiment with API. This ACE demonstrates how to use the Presence Graph API endpoints (beta) to set and retrieve a presence status message for a user. Set/update a user’s presence – their availability and a message to viewers.
* **Exposing business data in Microsoft 365 using Azure Data API builder and SPFx** – integrate a ToDo list into an existing application without writing any code with an open-source tool Microsoft just released called Data API Builder for Azure Database. For a new/existing database, specify a table, and let tool create a REST API or GraphQL endpoint that’s then consumed by your application – an ACE in this case! Step through ACE code for managing security and tasks.

The host of this call is [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) @bernierh. Q&A takes place as always in chat throughout the call.

{{< youtube v-P2Hcwcarc >}}

## Agenda items

[00:00](https://youtu.be/v-P2Hcwcarc?t=0) – Intro – [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) @bernierh

[06:50](https://youtu.be/v-P2Hcwcarc?t=410) – SharePoint Framework – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[08:19](https://youtu.be/v-P2Hcwcarc?t=499) – PnPjs Client-Side Libraries – [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) @bernierh

[09:00](https://youtu.be/v-P2Hcwcarc?t=540) – CLI for Microsoft 365 – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[10:34](https://youtu.be/v-P2Hcwcarc?t=634) – Microsoft Graph Developer Proxy – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[12:02](https://youtu.be/v-P2Hcwcarc?t=722) – PnP SPFx Controls – [Alex Terentiev](https://twitter.com/alexaterentiev) (Microsoft) \| @alexaterentiev

[13:33](https://youtu.be/v-P2Hcwcarc?t=813) – Viva Connections Toolkit for Visual Studio Code – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[14:07](https://youtu.be/v-P2Hcwcarc?t=847) – PnP Modern Search – [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) @bernierh

[14:35](https://youtu.be/v-P2Hcwcarc?t=875) – PnP Samples - [Hugo Bernier](http://twitter.com/bernierh) (Microsoft) \| @bernierh

[15:04](https://youtu.be/v-P2Hcwcarc?t=904) – PnP SPFx ACEs Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[15:39](https://youtu.be/v-P2Hcwcarc?t=939) – Together mode picture – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[16:38](https://youtu.be/v-P2Hcwcarc?t=998) – Demo – Building advance interactive world map for business information with SPFx – [Sergej Schwabauer](https://twitter.com/spfxappdev) (Aurum GmbH) \| @spfxappdev

[29:17](https://youtu.be/v-P2Hcwcarc?t=1757) – Demo – Creating Viva Connections extension with user presence status using Microsoft Graph Presence API and SPFx – [Yves Habersaat](https://twitter.com/yhabersaat) (Sword Group) \| @yhabersaat

[39:44](https://youtu.be/v-P2Hcwcarc?t=2384) – Demo – Exposing business data in Microsoft 365 using Azure Data API builder and SPFx – [Davide Mauri](https://twitter.com/mauridb) (Microsoft) \| @mauridb & [Paolo Pialorsi](https://twitter.com/PaoloPia) (PiaSys) \| @PaoloPia

[56:24](https://youtu.be/v-P2Hcwcarc?t=3384) – Closing

## Together Mode

![together-230323.png](images/together-230323.png)

The people in this Community are nothing less than awesome! Thanks everyone for joining today’s call.

## Actions

* [Register](https://aka.ms/BuildwithTeams) for Build once, deploy efficiently, connect across Microsoft 365 – Virtual event. March 29, 2023, 9:00AM PST.
* Request a Demo spot on the call \| <https://aka.ms/community/request/demo>
* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| aka.ms/m365pnp-recognition
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Power Platform Samples Contributor \| Monday, April 10th, 11:00am PT \| 2:00pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
    * Maturity Model Practitioners \| Tuesday, April 18th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Download the recurrent invite for this call \| <https://aka.ms/spdev-spfx-call>

## Demo references

* **Building advance interactive world map for business information with SPFx**
    * Sample - [SharePoint Interactive Map Webpart](https://github.com/SPFxAppDev/sp-map-webpart)
    * Article - [My interactive maps app for Microsoft Teams/SharePoint](https://spfx-app.dev/my-interactive-maps-app-for-microsoft-teamssharepoint)
* **Creating Viva Connections extension with user presence status using Microsoft Graph Presence API and SPFx**
    * Sample - [BasicCard-StatusMessage](https://github.com/pnp/sp-dev-fx-aces/tree/main/samples/BasicCard-StatusMessage)
    * Tool – [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer) \| aka.ms/ge
* **Exposing business data in Microsoft 365 using Azure Data API builder and SPFx**
    * Tool - [Data API builder for Azure Databases](https://mcr.microsoft.com/product/azure-databases/data-api-builder/about)
    * Repo - [data-api-builder](https://github.com/Azure/data-api-builder) \| aka.ms/dab
    * Demo - [Data API builder and Microsoft 365](https://github.com/yorek/dab-microsoft365-demo)
    * Builder - [ace-dab-spfx](https://github.com/pnp/sp-dev-fx-aces/tree/main/scenarios/ace-data-api-builder/spfx)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.16.1 (GA), v1.17 (Beta 3)| v1.17 (GA) April 2023
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.13 (GA)| v3.13 to be released March 17, 2023
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v6.3 (GA), v6.4 (Beta)|
[Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download)|v0.5 (Preview)| v0.6 to be released March 30, 2023
[Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)|v3.13.0 (GA), v2.9.0|
[Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls)|v3.12.0 (GA), v2.7.0|
[Viva Connections Toolkit for VS Code](https://github.com/pnp/vscode-viva) | v0.4.1 (GA)|
[PnP SPFx Generator](https://github.com/pnp/generator-spfx)|v1.16.0|v1.17.0 on the way
[PnP Modern Search](https://microsoft-search.github.io/pnp-modern-search/)|v4.8.0 (GA), v3.23.0 (GA)|


## General Resources

*   Viva Connections [https://aka.ms/VivaConnections](https://aka.ms/VivaConnections)
*   Archives - Microsoft 365 PnP Weekly - [Videos](https://www.youtube.com/playlist?list=PLR9nK3mnD-OVYI-St_CBiFfuL4CZbBpkC), [Podcasts](https://pnpweekly.podbean.com/)  
*   Tools - [Teams Toolkit (v2.2 Preview)](https://aka.ms/teams-toolkit) 
*   Tools - [Microsoft Teams Framework (TeamsFx)](https://github.com/officedev/teamsfx) 
*   Gallery - [Microsoft 365 Extensibility look book gallery](https://aka.ms/m365/extensibility)   
*   [Microsoft Build sessions guide](https://aka.ms/modernworkbuildsessions) (Modern Work Digital Brochure) - aka.ms/modernworkbuildsessions
*   SharePoint Framework - v1.12.1 npm install –g @microsoft/generator-sharepoint@next
*   [CLI for Microsoft 365 v3](https://developer.microsoft.com/office/blogs/cli-microsoft-365-3/)
*   [CodeTour](https://aka.ms/codetour)
*   [Sharing is Caring](https://aka.ms/sharing-is-caring) | aka.ms/sharing-is-caring
*   [Tools -](https://aka.ms/pnp-search) [PnP Modern Search v4](https://microsoft-search.github.io/pnp-modern-search/)  [|](https://aka.ms/pnp-search) [https://aka.ms/pnp-search](https://aka.ms/pnp-search)
*   [M365 PnP site](https://aka.ms/m365pnp) | aka.ms/m365pnp
*   [SharePoint Starter Kit v2](https://github.com/pnp/sp-starter-kit/tree/v2)
*   Blog: "[A Lap Around Microsoft Graph Toolkit" blog series](https://aka.ms/mgtLap)
*   [New Microsoft 365 Patterns and Practices (PnP) team model with new community leads](https://developer.microsoft.com/microsoft-365/blogs/new-microsoft-365-patterns-and-practices-pnp-team-model-with-new-community-leads/)
*   [Microsoft 365 Community Content](https://aka.ms/m365-community-docs) (non-Dev docs)
*   [PnP SPFx web part samples](https://aka.ms/spfx-webparts)
*   [PnP SPFx extension samples](https://aka.ms/spfx-extensions)
*   [GitHub PnPjs](https://github.com/pnp/pnpjs/)
*   Tutorials - [Getting started with SharePoint Framework v1.10 Tutorials](https://www.youtube.com/playlist?list=PLR9nK3mnD-OXvSWvS2zglCzz4iplhVrKq) (12 videos)
*   Tutorials - [Getting started with SharePoint Framework v1.10 Extensions](https://www.youtube.com/playlist?list=PLR9nK3mnD-OXtWO5AIIr7nCR3sWutACpV) (6 videos)
*   Docs - [Tutorials and training material for SharePoint Development](https://docs.microsoft.com/sharepoint/dev/training/training/?wt.mc_id=YT_CCrecording)
*   [SPFX Training Package](https://aka.ms/spfx-training)
*   [SPFx Web Parts](https://aka.ms/spfx-webparts)
*   [SPFx Extensions](https://aka.ms/spfx-extensions)
*   [SPFx Library Components](https://aka.ms/spfx-library-components)
*   Documentation - [PnPjs v2 documentation](https://pnp.github.io/pnpjs/)
*   Link - [Microsoft 365 developer training](https://aka.ms/M365DevTraining)
*   Link - [Office 365 Developer Program](https://aka.ms/O365DevProgram)
*   [Latest documentation on SharePoint Framework](https://aka.ms/spdev-docs)
*   Found an issue with SharePoint Dev? - please let us know at [https://aka.ms/spdev-issues](https://aka.ms/spdev-issues)
*   [Reusable web part property controls](https://sharepoint.github.io/sp-dev-fx-property-controls/)
*   [Reusable react controls for SharePoint Framework solutions](https://sharepoint.github.io/sp-dev-fx-controls-react/)
*   [Reusable controls webcast](https://devblogs.microsoft.com/microsoft365dev/webcast-reusable-controls-for-your-sharepoint-framework-solutions/)
*   [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365)
*   [PnP SPFx Yeoman Generator](https://github.com/pnp/generator-spfx) \- Extends the out-of-the-box experience with open-source community capabilities
*   [SharePoint Dev UserVoice](https://aka.ms/spdev-uservoice) \- for new feature requests

## Other mentioned topics

*   [SharePoint dev documentation](https://docs.microsoft.com/sharepoint/dev/)
*   [SharePoint dev issue list](https://github.com/SharePoint/sp-dev-docs/issues)

## Upcoming calls | Recurrent invites

* Microsoft 365 platform call \| Tuesday, March 28, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Microsoft 365 & Power Platform Dev call \| Thursday, March 30, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Viva Connections & SharePoint Framework call \| Thursday, April 6, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Office add-in monthly call \| Wednesday, April 12, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Power Platform monthly call \| Wednesday, April 19, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, April 20, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

## About

Viva Connections & SharePoint Framework bi-weekly calls are targeted at anyone who is interested in the JavaScript-based development towards Microsoft Connections, Microsoft Teams, SharePoint Online, and also on-premises. Calls are used for the following objectives.

*   SharePoint Framework engineering update from Microsoft
*   Talk about PnP JavaScript Core libraries
*   CLI for Microsoft 365 Updates
*   SPFx reusable controls
*   PnP SPFx Yeoman generator
*   Share code samples and best practices
*   Possible engineering asks for the field - input, feedback, and suggestions
*   Cover any open questions on the client-side development
*   Demonstrate SharePoint Framework in practice in Microsoft Viva, Microsoft Teams or SharePoint context
*   You can download a recurrent invite from [https://aka.ms/spdev-spfx-call](https://aka.ms/spdev-spfx-call). Welcome and join the discussion!


*“Sharing is caring”*

* * *

*Microsoft 365 PnP team, Microsoft - 23rd of March 2023*

{{< attachments >}}{{< /attachments >}}
