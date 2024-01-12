---
title: "Viva Connections & SharePoint Framework Community Call – 16th of June, 2022"
date: 2022-06-17T02:00:00-05:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-16th-june.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Demos:  Building a safer custom Content Editor Web Part with SPFx, Getting started on using GitHub Codespaces with your SharePoint Framework solutions, MyShifts – SharePoint Framework Viva Connections - Adaptive Card Extension. Project releases for PnPjs, CLI, Search + 4 samples."
videos:
- https://www.youtube.com/watch?v=cB63Da065dw
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Agenda set for Microsoft 365 platform call - Tuesday, June 21, 8:00 am PT \| aka.ms/m365-dev-call
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * Monthly community contributors
    * **Rabeb Othmani** - Microsoft Graph Postman
    * **Nik Charlebois** - Using the Microsoft Graph PowerShell SDK for common operations
    * **Alex Kwan** - Get started with UI Library for Azure Communication Services
* Project releases
    * [SharePoint Framework (SPFx)](https://aka.ms/spfx) - v1.15 (RC) – includes list and library form extensibility
    * [PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/) - v3.4.0 GA
    * [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) – v5.4.0 preview
    * [PnP Modern Search](https://microsoft-search.github.io/pnp-modern-search/) – v4.7.0 preview
* Web part samples
    * [Page Navigator](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-page-navigator) - [Jasey Waegebaert](http://twitter.com/JWaegebaert) \| @JWaegebaert
    * [React Script Editor](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-script-editor)  [Felix Bohnacker](https://github.com/felixbohnacker) \| felixbohnacker
* ACE samples
    * New - Card Composition – Multi Card View - [Marcin Wojciechowski](http://twitter.com/mgwojciech) \| @mgwojciech
    * Updated - My M365 Groups - *New Search & Grouping -* [Nanddeep Nachan](http://twitter.com/NanddeepNachan) \| @NanddeepNachan
* Microsoft 365 PnP Weekly – Episode 170 (June 13th) with Kraków, Poland based SharePoint developer at Valo Solutions - [Marcin Wojciechowski](https://twitter.com/mgwojciech) \| @mgwojciech \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-170/) \| [podcast](https://www.podbean.com/media/share/pb-w7j5e-124d4dc)
* Microsoft 365 PnP Weekly – Episode 169 (June 6th) with Belgium based Microsoft 365 Solution Architect and MVP at Qubix - [Yannick Reekmans](http://twitter.com/YannickReekmans) \| @YannickReekmans \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-169/) \| [podcast](https://www.podbean.com/media/share/pb-uvjxj-1244047)

### Demos

**Building a safer custom Content Editor Web Part​ with SPFx** – what happened to the CEWP/SEWP’s in the move from classic to modern? Thanks to SPFx and presenter, the content web part is back. Built with a Governance, not a technical approach to address security and governance issues. Meet the Cherry-Picked Content web part. Uses only snippets from approved libraries, and hardcoded in web part, from which user is allowed to Pick.
**Getting started on using GitHub Codespaces with your SharePoint Framework solutions**​ – opens with a great premier on GitHub Codespaces cloud-based development environment – what it is, what can you do with it, limits during beta, and cost. Step through creating and configuring a basic Codespaces container for a project. Then learn about the presenter’s template - SPFx GitHub Codespaces Container, and step through setting up a new container pre-configured for your SPFx project in minutes!
**MyShifts – SharePoint Framework Viva Connections - Adaptive Card Extension** – call Microsoft Graph API from an ACE, use Graph to store/read user's preferences on user's OneDrive. Uses card view (to display logged in user’s immediate upcoming Shift on a team) and quick view cards to display additional shifts, other teams and team selection confirmations. Delivers a Personalized Experience on the user’s Viva Connections dashboard. Complete CodeTour in this ACE sample.


The host of this call is [Patrick Rodgers](http://twitter.com/mediocrebowler)
(Microsoft) \| @mediocrebowler. Q&A takes place as always in chat throughout the
call.

{{< youtube cB63Da065dw >}}

## Agenda items

* SharePoint Framework - [Vesa Juvonen](http://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen – [7:09](https://youtu.be/cB63Da065dw?t=429)<https://youtu.be/3_QF94JWIlk?t=476>
* PnPjs Client-Side Libraries - [Julie Turner](http://twitter.com/jfj1997) (Sympraxis Consulting) \| @jfj1997 – [8:45](https://youtu.be/cB63Da065dw?t=525)
* CLI for Microsoft 365 - [Patrick Rodgers](http://twitter.com/mediocrebowler) (Microsoft) \| @mediocrebowler – [11:03](https://youtu.be/cB63Da065dw?t=663)
* PnP SPFx Controls - [Patrick Rodgers](http://twitter.com/mediocrebowler) (Microsoft) \| @mediocrebowler – [11:52](https://youtu.be/cB63Da065dw?t=712)
* PnP Modern Search - [Patrick Rodgers](http://twitter.com/mediocrebowler) (Microsoft) \| @mediocrebowler – [13:02](https://youtu.be/cB63Da065dw?t=782)
* PnP Samples - [Hugo Bernier](http://twitter.com/bernierh) (Microsoft) \| @bernierh – [13:37](https://youtu.be/cB63Da065dw?t=817)
* PnP SPFx ACEs Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII –[14:55](https://youtu.be/cB63Da065dw?t=895)
* Demo - Building a safer custom Content Editor Web Part​ with SPFx – [Christophe Humbert](https://twitter.com/Path2SharePoint) \| @Path2SharePoint – [16:39](https://youtu.be/cB63Da065dw?t=999)
* Demo - Getting started on using GitHub Codespaces with your SharePoint Framework solutions​ – [Emanuele Bartolesi](https://twitter.com/kasuken) (SoftwareONE) \| @kasuken – [33:44](https://youtu.be/cB63Da065dw?t=2024)
* Demo - MyShifts – SharePoint Framework Viva Connections - Adaptive Card Extension – [Siddharth Vaghasia](https://twitter.com/siddh_me) \| @siddh_me – [50:50](https://youtu.be/cB63Da065dw?t=3050)


## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Writing for the Web \| Thursday, June 23, 12pm PT \| 3pm ET \| 9pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Writing for the Web \| Monday, June 27, 10am PT \| 1pm ET \| 7pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Power Platform Samples Contributor \| Wednesday, June 29, 10:00 am PT - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN09VTVU2QzRLNE0yVERQMklHSDBMUTJGWC4u)
    * Maturity Model Practitioners \| [Register](https://aka.ms/mm4m365)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Sign up to [Share your story](https://aka.ms/share-your-story) in the [Learn from the community](https://aka.ms/LearnFromTheCommunity/ThisWeek) series.
* Request a Demo spot on the call \| <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call \| <https://aka.ms/spdev-spfx-call>

## Demo references

* **Building a safer custom Content Editor Web Part​ with SPFx**
    * Sample - [Cherry picked content](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-cherry-picked-content)
    * Article - [Aiming for a safer Content Editor Web Part](https://blog.pathtosharepoint.com/2022/04/19/aiming-for-a-safer-content-editor-web-part/)
    * Sample - [dangerous-content-web-part](https://github.com/PathToSharePoint/dangerous-content-web-part)
    * Issue - [Make React-Script-Editor more secure \#2228](https://github.com/pnp/sp-dev-fx-webparts/issues/2228)
    * Tool – [MGT](https://mgt.dev)
    * Sample - [Script editor web part for modern pages built in React](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-script-editor)
* **Getting started on using GitHub Codespaces with your SharePoint Framework solutions​**
    * Template - [SPFx GitHub Codespaces Container](https://github.com/kasuken/SPFxGitHubDevContainer)
    * Site – [GitHub Codespaces - Blazing fast cloud developer environments](https://github.com/features/codespaces)
    * Documentation - [GitHub Codespaces overview](https://docs.github.com/codespaces/overview)
    * Repo - [GitHub Codespaces (Default Linux Universal)](https://github.com/microsoft/vscode-dev-containers/tree/main/containers/codespaces-linux)
    * Documentation - [devcontainer.json reference](https://code.visualstudio.com/docs/remote/devcontainerjson-reference)
    * Repo - [VS Code Remote / GitHub Codespaces Container Definitions](https://github.com/microsoft/vscode-dev-containers)
    * Register - [Sign up for the Codespaces beta](https://github.com/features/codespaces/signup)
* **MyShifts – SharePoint Framework Viva Connections - Adaptive Card Extension**
    * Sample - [My Upcoming Shifts](https://github.com/pnp/sp-dev-fx-aces/tree/main/samples/PrimaryTextCard-MyShifts)
    * Article - [The easiest way to store user settings of your Microsoft 365 app](https://blog.mastykarz.nl/easiest-store-user-settings-microsoft-365-app/)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
SharePoint Framework (SPFx)|v1.14 GA, v1.15 RC|v1.15 GA in June 2022, v1.16 Beta in July
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v2.13 GA, v3.4.0 GA|Nightly builds.
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v4.3.0 GA, v5.4.0 preview|
[Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)|v3.8.0, v2.9.0 (SPFx v1.11)|
[Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls)|v3.7.0, v2.7.0 (SPFx v1.11)|
[PnP SPFx Generator](https://github.com/pnp/generator-spfx)|v1.16.0|v1.17.0 on the way
[PnP Modern Search](https://microsoft-search.github.io/pnp-modern-search/)|v4.7.0 preview, v3.23.0|June 2022 release (soon)


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

* Microsoft 365 platform call \| Tuesday, June 21, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* M365 General Dev call \| Thursday, June 23, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Viva Connections & SharePoint Framework call \| Thursday, June 30, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Office add-in monthly call \| Wednesday, July 13, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Adaptive Cards monthly call \| Thursday, July 14, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Power Platform monthly call \| Wednesday, July 20, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, July 21, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

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

*Microsoft 365 PnP team, Microsoft - 17th of June 2022*

{{< attachments >}}{{< /attachments >}}
