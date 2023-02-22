---
title: "Viva Connections & SharePoint Framework Community Call – 17th of November, 2022"
date: 2022-11-17T02:00:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-17th-nov.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Three demos: Add form customizers to list web part, Using Fluent UI 9 in SPFx solutions, and Visualizing dynamically SharePoint data within SPFx solutions using ERD model. Project releases for SPFx, PnPjs, CLI, React controls, Property controls and 24 samples!"
videos:
- https://www.youtube.com/watch?v=7bvNLC1fn-U
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, November 22nd 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * Monthly community contributors
    * Demos
        * **Vesa Juvonen** – Creating SPFx powered multi-tab solution using Microsoft Teams Toolkit
        * **Bill Baer** – Microsoft Search Usage Reports
        * **Ayca Bas** – Build your first Notification bot in C\# for Microsoft Teams with Teams Toolkit for Visual Studio
* Announcement
    * Article - [Announcing general availability of SharePoint Framework 1.16](https://devblogs.microsoft.com/microsoft365dev/announcing-general-availability-of-sharepoint-framework-1-16-enabling-spfx-across-microsoft-365-platform/)
* Project releases
    * [SharePoint Framework (SPFx)](https://aka.ms/spfx) – v 1.16 (GA) \| aka.ms/SPFx/116
    * [PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/) – v 3.9 (GA)
    * [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/about/release-notes/#v580) – v6.0 (beta)
    * [Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react) – v 3.12.0 (GA)
    * [Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls) – v 3.11.0 (GA)
* Web part samples
    * PnPjs React Hooks – [Beau Cameron](https://twitter.com/beau__cameron) \| @beau__cameron
    * [Add form customizer to list](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-add-formcustomizer-to-list) – [Siddharth Vaghasia](https://twitter.com/siddh_me) \| @siddh_me
    * Rhythm of Business Calendar – Dan Turley
    * Feedback Sidebar Web Part – Alessia De Martino, Andrea Bellini, Matteo Serpi & Michele Catena
    * Find time and Planner experiences – [Christophe Humbert](https://twitter.com/Path2SharePoint) \| @Path2SharePoint
    * Consume Azure Function app – [Joao Livio](https://twitter.com/jlivio) \| @jlivio
    * Display Sharepoint data as ERD – [Niklas Wilhelm](https://twitter.com/NiklasWilhelm4) \| @NiklasWilhelm4
    * Zod Usage in SPFx solutions – [Ari Gunawan](https://twitter.com/arigunawan3023) \| @arigunawan3023
    * CSV Importer – [Michał Romiszewski](https://twitter.com/romiszewski) \| @romiszewski
    * Graph auto batching – [Marcin Wojciechowski](https://twitter.com/mgwojciech) \| @mgwojciech
    * Image generation using DALL-E API – [Luis Mañez](https://twitter.com/luismanez) \| @luismanez
    * Using KIOTA SDK with SPFx solutions – [Luis Mañez](https://twitter.com/luismanez) \| @luismanez
    * Associated Sites Links – [Ari Gunawan](https://twitter.com/arigunawan3023) \| @arigunawan3023
    * Flight Tracker – [João Mendes](https://twitter.com/joaojmendes) \| @joaojmendes
    * On behalf Azure AD flow with SPFx – [Paolo Pialorsi](https://twitter.com/paolopia) \| @paolopia
* Extension samples
    * Custom Message Banner for Modern SharePoint Sites – [Brad Schlintz](https://twitter.com/bschlintz) \| @bschlintz, [Paul Matthews](https://twitter.com/cann0nf0dder) \| @cann0nf0dder
    * Share List, Folder or File to Teams – [Russell Gove](https://twitter.com/russgove) \| @russgove
    * Field Votes – [Ari Gunawan](https://twitter.com/arigunawan3023) \| @arigunawan3023
    * My Followed Sites Application Customizer – Rahul Suryawanshi
* ACE samples
    * Share Graph Client between ACEs – [Marcin Wojciechowski](https://twitter.com/mgwojciech) \| @mgwojciech
    * Stock / Bitcoin feed – [Kunj Sangani](https://twitter.com/sanganikunj) \| @sanganikunj
    * Flight Tracker – [João Mendes](https://twitter.com/joaojmendes) \| @joaojmendes
    * Dynamic SVG image charts – [Patrick Rodgers](https://twitter.com/mediocrebowler) \| @mediocrebowler
    * Multi-tenant ISV reference solution – [Paolo Pialorsi](https://twitter.com/paolopia) \| @paolopia
* Conversations
    * Microsoft 365 PnP Weekly – Episode 187 (November 14th) with Velencia, Spain based SharePoint and Cloud Solution Architect and Microsoft MVP [Luis Máñez](https://twitter.com/luismanez) (ClearPeople) \| @luismanez \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-187/) \| [podcast](https://www.podbean.com/media/share/pb-zufjw-1314b06)
    * Microsoft 365 PnP Weekly – Episode 186 (November 7th) with US/India based Microsoft Principal Product Manager - [DC Padur](https://twitter.com/dcpadur) \| @dcpadur \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-186/) \| [podcast](https://www.podbean.com/media/share/pb-xyxgw-130a0da)

### Demos

* **Add form customizers to list web part** – learn about a utility web part for managing the SPFx form customizer for your SharePoint List and libraries. Webpart allows user to associate a form customizer to a list/library. The web part has a simple interface to associate/remove, can be used across site collections, ability to Select Site, List, Content Type, and ability to choose form type (view/edit/new). CodeTour for walk through.
* **Using Fluent UI 9 in SPFx solutions** – see the new [Fluent UI version 9](https://github.com/microsoft/fluentui/tree/master/packages/react-components) controls and theme provider in a SharePoint Communication site and Teams site. The UI framework has native theming for Teams, SharePoint and Windows. What is Fluent and Fluent UI 9, how are Fluent UI components configured. Fluent UI 7 currently ships with SPFx. UI 9 – Windows 11 styled react based, merges 8 and Northstar (Teams) into 1 library.
* **Visualizing dynamically SharePoint data within SPFx solutions using ERD model** – this SPFx web part was built to help Admins visualize data in a SharePoint site using an Entity Relationship Diagram (ERD). PnPjs pulls all data from SharePoint and GoJS generates the ERD visualization. Install the web part as an app page web part. Loads all sites, lists, fields, relationships, then dumps data into GoJS, add alerts for threshold limits. Uses SPFx, PnPjs and GoJS.

The host of this call is [Marc D Anderson](https://twitter.com/sympmarc) (Sympraxis Consulting) - @sympmarc. Q&A takes place as always in chat throughout the call.

{{< youtube 7bvNLC1fn-U >}}

## Agenda items

* SharePoint Framework – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen – [6:31](https://youtu.be/7bvNLC1fn-U?t=391)
* PnPjs Client-Side Libraries - [Julie Turner](http://twitter.com/jfj1997) (Sympraxis Consulting) \| @jfj1997 – [8:38](https://youtu.be/7bvNLC1fn-U?t=518)
* CLI for Microsoft 365 - [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder – [9:51](https://youtu.be/7bvNLC1fn-U?t=591)
* PnP SPFx Controls - [Alex Terentiev](https://twitter.com/alexaterentiev) (Microsoft) \| @alexaterentiev – [11:51](https://youtu.be/7bvNLC1fn-U?t=711)
* PnP Modern Search - [Marc D Anderson](https://twitter.com/sympmarc) (Sympraxis Consulting LLC) \| @sympmarc – [12:29](https://youtu.be/7bvNLC1fn-U?t=749)
* PnP Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [13:03](https://youtu.be/7bvNLC1fn-U?t=783)
* Demo – Add form customizers to list web part – [Siddharth Vaghasia](https://twitter.com/siddh_me) (Tata Consulting) \| @siddh_me – [15:33](https://youtu.be/7bvNLC1fn-U?t=933)
* Demo – Using Fluent UI 9 in SPFx solutions – [Nick Brown](https://twitter.com/techienickb) (Jisc) \| @techienickb – [26:46](https://youtu.be/7bvNLC1fn-U?t=1606)
* Demo – Visualizing dynamically SharePoint data within SPFx solutions using ERD model – [Niklas Wilhelm](https://twitter.com/NiklasWilhelm4) (NetForce 365) \| @NiklasWilhelm4 – [41:00](https://youtu.be/7bvNLC1fn-U?t=2460)

## Together Mode

![together-221117.png](images/together-221117.png)

Thank you everybody for joining today’s call. It’s really awesome to see you here. Your continuing support makes this community great for everyone.

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| aka.ms/m365pnp-recognition
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Power Platform Samples Contributor \| Monday, November 28th, 11:30am PST - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
    * Maturity Model Practitioners \| Tuesday, December 20th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Request a Demo spot on the call \| <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call \| <https://aka.ms/spdev-spfx-call>

## Demo references

* **Add form customizers to list web part**
    * Sample - [Add Form Customizer to List](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-add-formcustomizer-to-list)
    * Package - [package for formcustomizer utility webpart](https://github.com/siddharth-vaghasia/public-docs/blob/master/react-add-formcustomizer-to-list.sppkg)
* **Using Fluent UI 9 in SPFx solutions**
    * Sample - [react-fluentui-9](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-fluentui-9)
    * Components - [Fluent UI React Components v9.7.0](https://react.fluentui.dev/?path=/docs/concepts-introduction--page)
* **Visualizing dynamically SharePoint data within SPFx solutions using ERD model**
    * npm - [gojs-react](https://www.npmjs.com/package/gojs-react)
    * Tools – [GoJS - Build Diagrams for the Web in JavaScript and TypeScript](https://gojs.net/latest/index.html)
    * Sample - [SP Site ER Diagram](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-pnpjs-spsite-er-diagram)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.16 (GA)|v1.17 - Q1, 2023
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.9 GA, v2.13 GA|
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|V6.0 (beta), v5.9.0 GA|
[Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)|v3.12.0 (GA), v2.9.0|
[Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls)|v3.11.0 (GA), v2.7.0|
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

* Microsoft 365 platform call \| Tuesday, November 22, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Microsoft 365 General Dev call \| Thursday, November 24, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Viva Connections & SharePoint Framework call \| Thursday, December 1, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Office add-in monthly call \| Wednesday, December 14, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Microsoft Identity Platform call \| Thursday, December 15, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Power Platform monthly call \| Wednesday, December 21, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)

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

*Microsoft 365 PnP team, Microsoft - 17th of November 2022*

{{< attachments >}}
