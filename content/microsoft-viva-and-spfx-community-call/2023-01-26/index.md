---
title: "Viva Connections & SharePoint Framework Community Call – 26th of January, 2023"
date: 2023-01-26T04:00:22.873Z
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-january-26th.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Demos: Building SPFx Visio file presenter for Teams and SharePoint, Extend the PnP React SPFx ListView control with a contextual menu, and Building CAML query web part for easy data presentation. CLI for Microsoft 365 + 4 samples."
videos:
- https://www.youtube.com/watch?v=49yC8DmN5lY
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Announcements
    * Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, January 31, 2023, 8:00 am PT.
        * Latest news from Microsoft engineering on the Microsoft 365 topics
        * Community together mode group photo
        * **Nancy Handa** & **Anshuman Gaur** – Introduction to Microsoft Viva Home
        * **Tomas Chladek** – Introduction to Azure Communication Services
    * [Sharing-Is-Caring training](https://pnp.github.io/sharing-is-caring/) dates in January - aka.ms/sharing-is-caring
    * [Community Recognition Program](https://pnp.github.io/recognitionprogram/) badges for 2023 - aka.ms/community/recognition
    * New Learning Module – [Create Adaptive Card Extensions (ACE) for Microsoft Viva Connections](https://learn.microsoft.com/training/modules/sharepoint-spfx-adaptive-card-extension-card-types) and for Microsoft Viva Home - aka.ms/viva/ace/learn
* Project releases
    * [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) – v6.2 (beta)
    * [Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download) – v0.4 release due Jan 31 2023
* [SPFx samples](https://aka.ms/spfx-webparts)
    * Updated - [Fluent UI 9](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-fluentui-9) – [Nick Brown](https://twitter.com/techienickb) \| @techienickb
    * New - Interactive Map – [Sergej Schwabauer](https://twitter.com/spfxappdev) \| @spfxappdev
    * Updated - [Page Navigator](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-page-navigator) – [Nils Andresen](https://twitter.com/nils_andresen) \| @nils_andresen
* [ACE samples](https://aka.ms/spfx-aces)
    * New - Presence Status with Presence Graph API - [Yves Habersaat](https://twitter.com/yhabersaat) \| @yhabersaat

### Demos

* **Building SPFx Visio file presenter for Teams and SharePoint** – this SharePoint web part replaces the classic Visio diagram AND Diagram Frame web parts (for embedding Visio drawings in your page) with equivalent and better functionality. The modern File Viewer web part does not offer the interactivity options previously available the classic web part. The open-source web part accesses the Visio Online API. Available from AppSource and tips on publishing in AppSource.
* **Extend the PnP React SPFx ListView control with a contextual menu** – to perform actions on selected list items. Add a context menu to the list item like it’s available in the default modern experience of lists and like the “edit control block” in the classic experience. Does not physically insert a column inside the SharePoint list view. Uses the ECB (Edit Control Block) control custom render option. Review core code and solution alternatives.
* **Building CAML query web part for easy data presentation** – when you need to quickly test a query, as an alternative to PowerShell, this simple web part allows the user to input a [CAML Query](https://learn.microsoft.com/sharepoint/dev/schema/collaborative-application-markup-language-caml-schemas), select a list and run the query. Uses PnPjs behind scenes to map out item. Several custom CAML queries ship with sample – for example: to query things based on SharePoint Groups. Post Demo bonus – PnP CAML overview.

The host of this call is [Paolo Pialorsi](https://twitter.com/paolopia) (PiaSys.com) @paolopia. Q&A takes place as always in chat throughout the call.

{{< youtube 49yC8DmN5lY >}}

## Agenda items

[00:00](https://youtu.be/49yC8DmN5lY?t=0) – Intro - [Paolo Pialorsi](https://twitter.com/paolopia) (PiaSys.com) \| @paolopia

[04:38](https://youtu.be/49yC8DmN5lY?t=278) – SharePoint Framework – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[06:25](https://youtu.be/49yC8DmN5lY?t=385) – PnPjs Client-Side Libraries – [Julie Turner](https://twitter.com/jfj1997) (Sympraxis) \| @jfj1997

[07:46](https://youtu.be/49yC8DmN5lY?t=466) – CLI for Microsoft 365 – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[09:15](https://youtu.be/49yC8DmN5lY?t=555) – Microsoft Graph Developer Proxy – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[10:09](https://youtu.be/49yC8DmN5lY?t=609) – PnP SPFx Controls – [Alex Terentiev](https://twitter.com/alexaterentiev) (Microsoft) \| @alexaterentiev

[11:14](https://youtu.be/49yC8DmN5lY?t=674) – Viva Connections Toolkit for Visual Studio Code – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[11:50](https://youtu.be/49yC8DmN5lY?t=710) – PnP Modern Search – [Paolo Pialorsi](https://twitter.com/paolopia) (PiaSys.com) \| @paolopia

[12:22](https://youtu.be/49yC8DmN5lY?t=742) – PnP Samples - [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) \| @bernierh

[13:55](https://youtu.be/49yC8DmN5lY?t=835) – PnP SPFx ACEs Samples - [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[14:21](https://youtu.be/49yC8DmN5lY?t=861) – Together mode picture – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[15:19](https://youtu.be/49yC8DmN5lY?t=919) – Demo – Building SPFx Visio file presenter for Teams and SharePoint – [Nikolay Belykh](https://github.com/nbelyh) (unmanagedvisio)

[28:12](https://youtu.be/49yC8DmN5lY?t=1692) – Demo – Extend the PnP React SPFx ListView control with a contextual menu – [Markus Möller](https://twitter.com/Moeller2_0) (Avanade) \| @Moeller2_0

[35:22](https://youtu.be/49yC8DmN5lY?t=2122) – Demo – Building CAML query web part for easy data presentation – [Dan Toft](https://twitter.com/tanddant) (Evobis ApS) \| @tanddant

[45:51](https://youtu.be/49yC8DmN5lY?t=2751) – Closing


## Together Mode

![together-230126.png](images/together-230126.png)

Awesome to see a full auditorium with a lot of familiar faces today.

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| aka.ms/m365pnp-recognition
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Maturity Model Practitioners \| Tuesday, February 21st, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * Power Platform Samples Contributor \| Thursday, February 23rd, 9:00am PT \| 12:00pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Request a Demo spot on the call \| <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call \| <https://aka.ms/spdev-spfx-call>

## Demo references

* **Building SPFx Visio file presenter for Teams and SharePoint**
    * Documentation - [Visio JavaScript API overview](https://learn.microsoft.com/office/dev/add-ins/reference/overview/visio-javascript-reference-overview)
    * Controls - [Reusable React controls for your SharePoint Framework solutions](https://pnp.github.io/sp-dev-fx-controls-react/)
    * Pipeline - [nbelyh.VisioOnlineSpfxWebPart](https://dev.azure.com/unmanagedvisio/UV-GitHub-Public/_build?definitionId=18&_a=summary)
    * VS Marketplace - [SPFx Localization](https://marketplace.visualstudio.com/items?itemName=eliostruyf.vscode-spfx-localization)
    * Documentation - [Publish SharePoint Framework applications to the marketplace](https://learn.microsoft.com/sharepoint/dev/spfx/publish-to-marketplace-overview)
    * Repo - [Diagram Frame sharepoint Visio web part](https://github.com/nbelyh/VisioOnlineSpfxWebPart)
    * AppSource - [Diagram Frame WebPart](https://appsource.microsoft.com/product/office/wa200002491)
    * Article - [Diagram Frame sharepoint Visio web part](https://unmanagedvisio.com/products/diagram-frame-sharepoint-visio-web-part/)
* **Extend the PnP React SPFx ListView control with a contextual menu**
    * Article - [Extend PnP SharePoint Framework React ListView Control with a context menu](https://mmsharepoint.wordpress.com/2018/03/11/extend-pnp-sharepoint-framework-react-listview-control-with-a-context-menu/)
    * Sample - [Employee ListView Contextual Menu](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-listview-context-ecb)
    * Documentation - [ListView: Add a contextual menu](https://pnp.github.io/sp-dev-fx-controls-react/controls/ListView.ContextualMenu/)
* **Building CAML query web part for easy data presentation**
    * Sample - [CAML to Table](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-caml2table)
    * Documentation - [Collaborative Application Markup Language (CAML) schemas](https://learn.microsoft.com/sharepoint/dev/schema/collaborative-application-markup-language-caml-schemas)
    * Controls - [Reusable React controls for your SharePoint Framework solutions](https://pnp.github.io/sp-dev-fx-controls-react/)
    * Repo – [CAMLjs](https://github.com/andrei-markeev/camljs)
    * chrome web store - [CamlJS Console](https://chrome.google.com/webstore/detail/camljs-console/ohjcpmdjfihchfhkmimcbklhjdphoeac)
    * library - [Camlex.NET.dll](https://www.nuget.org/packages/Camlex.NET.dll/)
    * PnP Repo [- CAML-Designer](https://github.com/pnp/CAML-Designer)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.16.1 (GA)|v1.17 - Q1, 2023
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.11 (GA), v2.13 (GA)|v 3.12 to be released Feb 10th 2023
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v6.1 (GA), v5.9.0 GA, v6.2 (beta)|
[Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download)|v0.3 (beta)|v0.4 release due Jan 31 2023
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
*   Docs - [Tutorials and training material for SharePoint Development](https://learn.microsoft.com/sharepoint/dev/training/training/?wt.mc_id=YT_CCrecording)
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

*   [SharePoint dev documentation](https://learn.microsoft.com/sharepoint/dev/)
*   [SharePoint dev issue list](https://github.com/SharePoint/sp-dev-docs/issues)

## Upcoming calls | Recurrent invites

* Microsoft 365 platform call \| Tuesday, January 31, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Microsoft 365 General Dev call \| Thursday, February 2, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Office add-in monthly call \| Wednesday, February 8, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, February 9, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Power Platform monthly call \| Wednesday, February 15, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, February 16, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

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

*Microsoft 365 PnP team, Microsoft - 26th of January 2023*

{{< attachments >}}{{< /attachments >}}
