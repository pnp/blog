---
title: "Viva Connections & SharePoint Framework Community Call – 3rd of November, 2022"
date: 2022-11-03T02:00:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-3rd-november.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Two demos: Getting started with PnPjs in SPFx solutions, AND Building ISV offering for Microsoft Viva with SPFx ACEs and multi-tenant APIs hosted in Azure. Project releases for SharePoint Framework (SPFx) and CLI for Microsoft 365."
videos:
- https://www.youtube.com/watch?v=j1cBiHY_06c
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, November 8th, 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * Monthly community contributors
        * **Bert Jansen** – Avoid throttling in SharePoint Online by using RateLimit headers in API calls
        * **Garry Trinder** - Build your first Workflow bot for Microsoft Teams with Teams Toolkit for Visual Studio Code
        * **Hugo Bernier** – Power Pages introduction series continues
* Announced
    * CLI for Microsoft 365
        * 100+ contributors now!
        * 5th Birthday Party, 17th Nov on [Discord](http://discord.com/invite/7rfW4kg6B5) @ 10:00 CET
    * SharePoint Framework v1.16 (RC). Previously released [Preview](https://devblogs.microsoft.com/microsoft365dev/updated-preview-of-the-sharepoint-framework-1-16/) article sums up the key updates in RC.
* Project releases
    * [SharePoint Framework (SPFx)](https://aka.ms/spfx) – v 1.16 (RC)
    * [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/about/release-notes/#v580) – v5.9.0 (GA). [Release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v590)
* Conversations
    * Microsoft 365 PnP Weekly – Episode 185 (October 31st) with Belgium based Microsoft 365 Development MVP and Consultant - Jasey Waegebaert (GMI group) \| @jwaegebaert. \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-185/) \| [podcast](https://pnpweekly.podbean.com/)
    * Microsoft 365 PnP Weekly – Episode 184 (October 24th) with UK based Microsoft MVP and Power Platform Technical Architect - [Kristine Kolodziejski](https://twitter.com/@kristinekk94) (Computacenter) \| @kristinekk94. \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-184/) \| [podcast](https://www.podbean.com/media/share/pb-brv6e-12f7bd6)

### Demos

* **Getting started with PnPjs in SPFx solutions** – explanation on files/code in a PnPjs v3.x sample. Items called out - changes between v2 and v3, dependencies, pnpjsConfig file (importing only selected bits of functionality libraries), chaining behaviors together, establishing global context for factory interfaces, caching, loadUser method (get information from Graph), rendering, creating a batched instance for grouped updates, discussion on approach to structure of production vs sample code.
* **Building ISV offering for Microsoft Viva with SPFx ACEs and multi-tenant APIs hosted in Azure** – capabilities in SPFx v1.15 make it easy (as in automate) for your customer to register, manage consent and deploy your SaaS app/ACE in their tenant. Step through configuration for managing a multi-tenant deployment including app registration in Azure AD, hosting multi-tenant aware back-end services on Azure, consent, permissions, etc. Understand architectural challenges and see an ACE on multiple tenants interact with the back-end multi-tenant API.

The host of this call is [Derek Cash-Peterson](https://twitter.com/spdcp) (Sympraxis Consulting) - @spdcp. Q&A takes place as always in chat throughout the call.

{{< youtube j1cBiHY_06c >}}

## Agenda items

* SharePoint Framework – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen – [5:11](https://youtu.be/j1cBiHY_06c?t=311)
* PnPjs Client-Side Libraries - [Julie Turner](http://twitter.com/jfj1997) (Sympraxis Consulting) \| @jfj1997 – [7:13](https://youtu.be/j1cBiHY_06c?t=433)
* CLI for Microsoft 365 - [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder – [8:54](https://youtu.be/j1cBiHY_06c?t=534)
* PnP SPFx Controls - [Alex Terentiev](https://twitter.com/alexaterentiev) (Microsoft) \| @alexaterentiev – [12:27](https://youtu.be/j1cBiHY_06c?t=747)
* PnP Modern Search - [Derek Cash-Peterson](https://twitter.com/spdcp) (Sympraxis Consulting) - @spdcp – [13:00](https://youtu.be/j1cBiHY_06c?t=780)
* PnP Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [13:26](https://youtu.be/j1cBiHY_06c?t=806)
* Demo – Getting started with PnPjs in SPFx solutions – [Julie Turner](https://twitter.com/jfj1997) (Sympraxis Consulting) \| @jfj1997 – [15:14](https://youtu.be/j1cBiHY_06c?t=914)
* Demo – Building ISV offering for Microsoft Viva with SPFx ACEs and multi-tenant APIs hosted in Azure – [Paolo Pialorsi](https://twitter.com/paolopia) (PiaSys) \| @paolopia – [33:42](https://youtu.be/j1cBiHY_06c?t=2022)

## Together Mode

![together-221103.png](images/together-221103.png)

Thank you everybody once again joining on the community call. Hope to see some of you in-person in Copenhagen and/or Las Vegas later this year. Great seeing you today.

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| aka.ms/m365pnp-recognition
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Maturity Model Practitioners \| Tuesday, November 15th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite).
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Request a Demo spot on the call \| <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call \| <https://aka.ms/spdev-spfx-call>

## Demo references

* **Getting started with PnPjs in SPFx solutions**
    * Library - [Getting Started PnPjs Library](https://pnp.github.io/pnpjs/getting-started/)
    * Sample - [SharePoint Framework sample using @pnp/js and ReactJS](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-pnp-js-sample)
    * Sample – [@pnp/js and ReactJS Functional Components](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-pnp-js-hooks)
* **Building ISV offering for Microsoft Viva with SPFx ACEs and multi-tenant APIs hosted in Azure**
    * Sample - [Contoso Orders ACE](https://adoption.microsoft.com/sample-solution-gallery/sample/pnp-spfx-reference-scenarios-ace-pnp-contoso-orders/)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.15.2 GA, v1.16 (RC)|v1.16 (GA) planned mid November 2022, v1.17 Preview December/January
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.8.0 GA, v2.13 GA|v3.9 GA to be released November 11
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v4.3.0 GA, v5.9.0 GA|v6.0.0 ETA November 2022
[Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)|v3.11.0, v2.9.0 (SPFx v1.11)|new version in 2 weeks
[Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls)|v3.10.0, v2.7.0 (SPFx v1.11)|new version in 2 weeks
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

* Microsoft 365 platform call \| Tuesday, November 8, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Office add-in monthly call \| Wednesday, November 9, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Microsoft 365 General Dev call \| Thursday, November 10, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Adaptive Cards monthly call \| Thursday, November 10, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Power Platform monthly call \| Wednesday, November 16, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, November 17, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, November 17, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

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

*Microsoft 365 PnP team, Microsoft - 3rd of November 2022*

{{< attachments >}}{{< /attachments >}}
