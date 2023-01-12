---
title: "Viva Connections & SharePoint Framework Community Call – 12th of January, 2023"
date: 2023-01-12T04:00:22.873Z
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-12th-of-january.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Demos: Getting started with hTWOo React controls for Microsoft 365 and Adaptive Cards design samples for Viva Connections. Released PnPjs Client-Side Libraries, CLI for Microsoft 365, Microsoft Graph Developer Proxy, Viva Connections Toolkit for VS Code, 3 SPFx and 1 ACE samples."
videos:
- https://www.youtube.com/watch?v=UCtKZCODlXg
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Announcements
    * Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, January 17, 2023, 8:00 am PT.
        * Latest news from Microsoft engineering on the Microsoft 365 topics
        * Community together mode group photo
        * **David Rousset** - Metaverse experience implemented as a Teams meeting app using the Teams LiveShare SDK
        * **Vesa Juvonen** & **Andrew Connell** – Introduction to Viva Connection learn module - tutorial 2
    * [Sharing-Is-Caring training](https://pnp.github.io/sharing-is-caring/) dates in January - aka.ms/sharing-is-caring
    * [Community Recognition Program](https://pnp.github.io/recognitionprogram/) badges for 2023 - aka.ms/community/recognition
    * New Learning Module – [Create Adaptive Card Extensions (ACE) for Microsoft Viva Connections](https://learn.microsoft.com/training/modules/sharepoint-spfx-adaptive-card-extension-card-types) and for Microsoft Viva Home - aka.ms/viva/ace/learn
* Project releases
    * [PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/) - v3.11 (GA)
    * [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) – v6.1 (GA)
    * [Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download) – v0.3 (beta)
    * [Viva Connections Toolkit for VS Code](https://github.com/pnp/vscode-viva) – v0.3.2 (beta)
* [SPFx samples](https://aka.ms/spfx-webparts)
    * New - [Holiday Calendar](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-holidays-calendar) - Harminder Singh \| HarminderSethi
    * Updated - [Tab Accordion with Rich Text](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-accordion-with-richtext) - Constey \| Constey
    * New - Offer Creation - [Markus Moeller](https://twitter.com/moeller2_0) \| @moeller2_0
* [ACE samples](https://aka.ms/spfx-aces)
    * [People Search](https://github.com/pnp/sp-dev-fx-aces/pull/118) – [Kunj Sangani](https://twitter.com/sanganikunj) \| @sanganikunj

### Demos

* **Getting started with hTWOo React controls for Microsoft 365** – what is the hTWOo UI library (hTWOo – Core, – React, – Icons). Install and create SPFx solution using hTWOo assets. See setting up theme support, initializing icons, creating a class/function component, and importing hTOWo assets into an SPFx project. Extensibility is built in at the core. Uses Atomic Design to organize components. Components minimize bundle sizing. Teams theming for use in SPFx Teams solutions.
* **Adaptive Cards design samples for Viva Connections** – brief overview of Viva Connections Dashboard and Cards along with the Adaptive Card samples repo. Add an Adaptive Card template to a Dashboard page. Populate template with JSON from Adaptive Card Designer. Learn about Card JSON (the design) and Data JSON file (static data). Not shown is building out more robust “custom” cards – full SPFx ACE extensions that connect various end points, LOB systems, etc.

The host of this call is [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder. Q&A takes place as always in chat throughout the call.

{{< youtube UCtKZCODlXg >}}

## Agenda items

* [08:12](https://youtu.be/UCtKZCODlXg?t=492) – SharePoint Framework – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen
* [09:48](https://youtu.be/UCtKZCODlXg?t=588) – PnPjs Client-Side Libraries – [Julie Turner](https://twitter.com/jfj1997) (Sympraxis) \| @jfj1997
* [11:05](https://youtu.be/UCtKZCODlXg?t=665) – CLI for Microsoft 365 – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder
* [12:27](https://youtu.be/UCtKZCODlXg?t=747) – Microsoft Graph Developer Proxy – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder
* [14:18](https://youtu.be/UCtKZCODlXg?t=858) – PnP SPFx Controls – [Alex Terentiev](https://twitter.com/alexaterentiev) (Microsoft) \| @alexaterentiev
* [15:05](https://youtu.be/UCtKZCODlXg?t=905) – Viva Connections Toolkit for Visual Studio Code – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen
* [15:28](https://youtu.be/UCtKZCODlXg?t=928) – PnP Modern Search – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder
* [15:51](https://youtu.be/UCtKZCODlXg?t=951) – PnP Samples - [Hugo Bernier](http://twitter.com/bernierh) (Microsoft) \| @bernierh
* [16:55](https://youtu.be/UCtKZCODlXg?t=1015) – PnP SPFx ACEs Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII
* [17:13](https://youtu.be/UCtKZCODlXg?t=1033) – Together mode picture – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen
* [18:19](https://youtu.be/UCtKZCODlXg?t=1099) – Demo – Getting started with hTWOo React controls for Microsoft 365 – [Julie Turner](https://twitter.com/jfj1997) (Sympraxis) \| @jfj1997
* [37:47](https://youtu.be/UCtKZCODlXg?t=2267) – Demo – Adaptive Cards design samples for Viva Connections – [Alex Clark](https://twitter.com/sharepointalex) (Microsoft) \| @sharepointalex

## Together Mode

![together-230112.png](images/together-230112.png)

The world feels so small when you’re sitting next to your friends! Thanks for being here and for making this a better world.

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| aka.ms/m365pnp-recognition
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Maturity Model Practitioners \| Tuesday, January 17th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * Writing for the Web \| Monday, January 23rd, 10am PT \| 1pm ET \| 7:00pm CET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMFNPNFMyUk9CNFROUjJWTFFGSzdJV0czVC4u)
    * PnP SPFx Samples w/NVM \| Wednesday, January 25th, 9am PT \| 12pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNEE2SUdTOU1UOEtCTFU3MlM1SERDMlNVNi4u)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Request a Demo spot on the call \| <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call \| <https://aka.ms/spdev-spfx-call>

## Demo references

* **Getting started with hTWOo React controls for Microsoft 365**
    * Site - [hTWOo Design Studio](https://lab.n8d.studio/htwoo/)
    * Repo - [HTWOO UI framework](https://github.com/n8design/htwoo)
* **Adaptive Cards design samples for Viva Connections**
    * Templates - [Adaptive Card templates - design examples](https://github.com/pnp/AdaptiveCards-Templates)
    * Documentation - [Build your first SharePoint Adaptive Card Extension](https://learn.microsoft.com/sharepoint/dev/spfx/viva/get-started/build-first-sharepoint-adaptive-card-extension)
    * Learn - [Create Adaptive Card Extensions (ACE) for Microsoft Viva Connections](https://learn.microsoft.com/training/modules/sharepoint-spfx-adaptive-card-extension-card-types)
    * Documentation - [Adaptive Cards Template Language](https://learn.microsoft.com/adaptive-cards/templating/language)
    * Tool – [Adaptive Cards Designer](https://www.adaptivecards.io/designer/)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.16.1 (GA)|v1.17 - Q1, 2023
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.11 (GA), v2.13 (GA)|
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v6.1 (GA), v5.9.0 GA|
[Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download)|v0.3 (beta)| 
[Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)|v3.12.0 (GA), v2.9.0|
[Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls)|v3.11.0 (GA), v2.7.0|
[Viva Connections Toolkit for VS Code](https://github.com/pnp/vscode-viva) | v0.3.2 (preview)|
[PnP SPFx Generator](https://github.com/pnp/generator-spfx)|v1.16.0|v1.17.0 on the way
[PnP Modern Search](https://microsoft-search.github.io/pnp-modern-search/)|v4.7.0 (GA), v4.8.0 (beta), v3.23.0 (GA)|


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

* Microsoft 365 platform call \| Tuesday, January 17, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Power Platform monthly call \| Wednesday, January 18, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft 365 General Dev call \| Thursday, January 19, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, January 19, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, January 26, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Office add-in monthly call \| Wednesday, February 8, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)

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

*Microsoft 365 PnP team, Microsoft - 12th of January 2023*

{{< attachments >}}
