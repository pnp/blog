---
title: "Viva Connections & SharePoint Framework Community Call – 25th of August, 2022"
date: 2022-08-25T02:00:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-25th-august.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Demos on Using the Microsoft Graph education endpoints in SPFx to create a my assignments web part and Getting started on building custom list form experiences with SharePoint Framework. Project releases for CLI for Microsoft 365 and Reusable Controls. 1 ACE sample delivered."
videos:
- https://www.youtube.com/watch?v=nHM2rXHs7nY
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Project releases
    * [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) – v5.7.0 (Beta)
    * [Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react) – v3.10.0 (GA)
    * [Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls) – v3.9.0 (GA)
* ACE samples
    * Shared Graph client (with batching) - [Marcin Wojciechowski](https://twitter.com/mgwojciech) \| @mgwojciech
* Microsoft 365 PnP Weekly – Episode 175 (August 22nd) with by Redmond-based Principal Software Engineer for Microsoft Graph - [Gavin Barron](https://twitter.com/gavinbarron) (Microsoft) \| @gavinbarron \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-175/) \| [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-%e2%80%93-episode-175-%e2%80%93-gavin-barron-microsoft/)
* Microsoft 365 PnP Weekly – Episode 174 (August 15th) with by Oslo Norway based Power Platform Architect Lead and MVP at Avanade - [Ahmad Najjar](https://twitter.com/ahmadn82) \| @ahmadn82 \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-174/) \| [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-%e2%80%93-episode-174-%e2%80%93-ahmad-najjar-avanade/)

### Demos

* **Using the Microsoft Graph education endpoints in SPFx to create a my assignments web part** – while using Assignments capability in Microsoft Teams for Education, you may want to render an aggregated list of assignments in SharePoint. That’s now possible using the My Assignments web part carefully explained here. Learn about the education related APIs in Microsoft Graph. EDU specific end points shown: /education/me, /ms/joinedTeams, /education/me/classes, /education/me/assignments. Review API permissions, caching service, refresh technique and capability limitations. Requires Education tenant.
* **Getting started on building custom list form experiences with SharePoint Framework** – a new feature (extension) introduced in SPFx v1.15 for customizing the form experience of a list. Focus on 3 behaviors – create, view and edit items in a list. Render one or more behaviors on a form. Starting with required tools, create a SPFx extension project, review provisioned components/code, 2 MUST use methods, overriding behaviors, creation and rendering options and finally deploying a form to production.

The host of this call is [Vesa Juvonen](http://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen. Q&A takes place as always in chat throughout the call.

{{< youtube nHM2rXHs7nY >}}

## Agenda items

* SharePoint Framework – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen – [8:31](https://youtu.be/nHM2rXHs7nY?t=511)
* PnPjs Client-Side Libraries - [Julie Turner](http://twitter.com/jfj1997) (Sympraxis Consulting) \| @jfj1997 – [10:49](https://youtu.be/nHM2rXHs7nY?t=649)
* CLI for Microsoft 365 - [Garry Trinder](https://twitter.com/garrytrinder) (CPS Solutions) \| @garrytrinder – [12:28](https://youtu.be/nHM2rXHs7nY?t=748)
* PnP SPFx Controls - [Alex Terentiev](https://twitter.com/alexaterentiev) (Microsoft) \| @alexaterentiev – [15:05](https://youtu.be/nHM2rXHs7nY?t=905)
* PnP Modern Search - [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen – [16:52](https://youtu.be/nHM2rXHs7nY?t=1012)
* Latest Search Episodes [216 -219](https://www.youtube.com/watch?v=Sl0dcgd70Q4) from Paolo Pialorsi (PiaSys) \| @paolopia
* PnP SPFx ACEs Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [17:36](https://youtu.be/nHM2rXHs7nY?t=1056)
* Demo – Using the Microsoft Graph education endpoints in SPFx to create a my assignments web part – [Tony Philips](https://twitter.com/TonyMSTeams) (Cloud Design Box) \| @TonyMSTeams – [19:41](https://youtu.be/nHM2rXHs7nY?t=1181)
* Demo – Getting started on building custom list form experiences with SharePoint Framework – [Waldek Mastykarz](https://twitter.com/waldekm) (Microsoft) \| @waldekm – [37:36](https://youtu.be/nHM2rXHs7nY?t=2256)


## Together Mode

![together-mode-220825.gif](images/together-mode-220825.gif)

Thank you everybody for joining. Great to see many familiar faces. It’s awesome to have you on the call today.

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| aka.ms/m365pnp-recognition
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Writing for the Web \| Tuesday, September 6th, 9:30am PT \| 12:30pm ET \| 6:30pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Maturity Model Practitioners \| Tuesday, September 20th, 7am PST - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Request a Demo spot on the call \| <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call \| <https://aka.ms/spdev-spfx-call>

## Demo references

* **Using the Microsoft Graph education endpoints in SPFx to create a my assignments web part**
    * Repo - [My Assignments Web Part by Cloud Design Box](https://github.com/CloudDesignBox/CDBAssignments)
    * Documentation - [Education API overview](https://docs.microsoft.com/graph/education-concept-overview)
    * Documentation - [Overview of School Data Sync](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)
    * Documentation - [Assignments in Teams for Education](https://docs.microsoft.com/microsoftteams/expand-teams-across-your-org/assignments-in-teams)
* **Getting started on building custom list form experiences with SharePoint Framework**
    * Documentation - [Build your first Form Customizer extension (preview)](https://docs.microsoft.com/sharepoint/dev/spfx/extensions/get-started/building-form-customizer)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.15.2 GA|v1.16 preview in September, v1.16 GA end of 2022, v1.17 Preview December/January
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.6.0 GA, v2.13 GA|
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v4.3.0 GA, v5.6.0 GA, v5.7 beta|
[Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)|v3.10.0, v2.9.0 (SPFx v1.11)|Supports SPFx v1.15.2
[Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls)|v3.9.0, v2.7.0 (SPFx v1.11)|Supports SPFx v1.15.2
[PnP SPFx Generator](https://github.com/pnp/generator-spfx)|v1.16.0|v1.17.0 on the way
[PnP Modern Search](https://microsoft-search.github.io/pnp-modern-search/)|v4.7.0 preview, v3.23.0|


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

* Microsoft 365 General Dev call \| Thursday, September 1, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Microsoft 365 platform call \| Tuesday, September 6, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Viva Connections & SharePoint Framework call \| Thursday, September 8, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Adaptive Cards monthly call \| Thursday, September 8, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Office add-in monthly call \| Wednesday, September 14, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Microsoft Identity Platform call \| Thursday, September 15, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Power Platform monthly call \| Wednesday, September 21, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)

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

*Microsoft 365 PnP team, Microsoft - 25th of August 2022*

{{< attachments >}}
