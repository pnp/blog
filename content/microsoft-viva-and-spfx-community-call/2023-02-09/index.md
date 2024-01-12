---
title: "Viva Connections & SharePoint Framework Community Call – 9th of February, 2023"
date: 2023-02-09T04:00:22.873Z
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-9th-feb.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Two demos: Getting started your SPFx form customizer journey with a boilerplate and Consuming Search API in Adaptive Card Extension. Releases: PnPjs v3.12, CLI v6.2, Graph Developer Proxy v0.4 and v0.5, plus 2 SPFx samples."
videos:
- https://www.youtube.com/watch?v=pI4ifJ7VyN8
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Announcements
    * Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, February 14, 2023, 8:00 am PT.
        * Latest news from Microsoft engineering on the Microsoft 365 topics
        * Community together mode group photo
        * Demo - **Dan Wahlin** - Create an Azure Communication Services Resource
        * Demo - **Sébastien Levert** - What's next for the Microsoft Graph Toolkit!
        * Demo - **Garry Trinder** - Teams Toolkit Learn Path - Get started building apps for Microsoft Teams using Teams Toolkit for Visual Studio Code
    * [Sharing-Is-Caring training](https://pnp.github.io/sharing-is-caring/) dates in February - aka.ms/sharing-is-caring
    * [Community Recognition Program](https://pnp.github.io/recognitionprogram/) badges for 2023 - aka.ms/community/recognition
    * New Microsoft Viva learning module – [Create Adaptive Card Extensions (ACE) for Microsoft Viva Connections](https://learn.microsoft.com/training/modules/sharepoint-spfx-adaptive-card-extension-card-types) focus on the ACE development - aka.ms/viva/ace/learn
* Project releases
    * [PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/) – v3.12 (GA) on February 10th
    * [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) – v6.2 (GA)
    * [Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download) – v0.4 (preview), v0.5.0 (beta.1)
* [SPFx samples](https://aka.ms/spfx-webparts)
    * New - [Chat GPT inside SPFx](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-chat-gpt) - [Nico De Cleyre](https://twitter.com/NicoDeCleyre) \| @NicoDeCleyre
    * Updated - Interactive Map - [Azure Application Insights Dashboard](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-interactive-map) - [Kinga Kazala](https://twitter.com/kinga_kazala) \| @kinga_kazala
* Conversations
    * Microsoft 365 Developer Podcast – Graph Developer Proxy with Waldek Mastykarz and Sebastien Levert (February 5th) \| [podcast](https://m365devpodcast.com/e/graph-developer-proxy-with-waldek-mastykarz-and-sebastien-levert/)
    * Microsoft 365 PnP Weekly – Episode 196 (February 6th) with Austria-based Microsoft AI & M365 Development MVP and Technical Project Lead at Solvion - [Stephan Bisser](https://twitter.com/stephanbisser) \| @stephanbisser \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-196/) \| [podcast](https://www.podbean.com/eas/pb-3nrjj-1383b9a)

### Demos

* **Getting started your SPFx form customizer journey with a boilerplate** – a modified out-of-box form customizer that will get you up and running in no time. The presenter essentially walks viewers through his form customizer article, UI and code while delivering tips for fine tuning and debugging along with a historical reference. One time saver is the ability to toggle between form customizer, list and Item on form. Works only if running SPFx v1.15 or greater.
* **Consuming Search API in Adaptive Card Extension** – a way to expose content search almost natively in mobile. In this ACE see implementing the Search API client and exposing the setQuery method, creating an adaptive card with input and search button, creating an adaptive card to present the results (template by [João Mendes](https://twitter.com/joaojmendes)), and adding navigation events. You can use SharePoint Search API or Graph Search API, use the quickViewNavigator.

The host of this call is [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) @bernierh. Q&A takes place as always in chat throughout the call.

{{< youtube pI4ifJ7VyN8 >}}

## Agenda items

[00:00](https://youtu.be/pI4ifJ7VyN8?t=0) – Intro – [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) @bernierh

[05:43](https://youtu.be/pI4ifJ7VyN8?t=343) – SharePoint Framework – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[07:27](https://youtu.be/pI4ifJ7VyN8?t=447) – PnPjs Client-Side Libraries – [Patrick Rodgers](http://twitter.com/mediocrebowler) (Microsoft) \| @mediocrebowler

[08:57](https://youtu.be/pI4ifJ7VyN8?t=537) – CLI for Microsoft 365 – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[11:05](https://youtu.be/pI4ifJ7VyN8?t=665) – Microsoft Graph Developer Proxy – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[12:38](https://youtu.be/pI4ifJ7VyN8?t=758) – PnP SPFx Controls – [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) @bernierh

[13:35](https://youtu.be/pI4ifJ7VyN8?t=815) – Viva Connections Toolkit for Visual Studio Code – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[14:06](https://youtu.be/pI4ifJ7VyN8?t=846) – PnP Modern Search – [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) @bernierh

[14:44](https://youtu.be/pI4ifJ7VyN8?t=884) – PnP Samples - [Hugo Bernier](http://twitter.com/bernierh) (Microsoft) \| @bernierh

[15:47](https://youtu.be/pI4ifJ7VyN8?t=947) – PnP SPFx ACEs Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[16:14](https://youtu.be/pI4ifJ7VyN8?t=974) – Together mode picture – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[17:17](https://youtu.be/pI4ifJ7VyN8?t=1037) – Demo – Getting started your SPFx form customizer journey with a boilerplate – [Michaël Maillot](https://twitter.com/michael_maillot) (onepoint) \| @michael_maillot

[35:50](https://youtu.be/pI4ifJ7VyN8?t=2150) – Demo – Consuming Search API in Adaptive Card Extension – [Marcin Wojciechowski](https://twitter.com/mgwojciech) (Valo) \| @mgwojciech

[48:30](https://youtu.be/pI4ifJ7VyN8?t=2910) – Closing

## Together Mode

![together-230209.png](images/together-230209.png)

Wait, wait, wait!  Here we go, now wave, wave, wave. Thank you for joining in the fun during today’s community call. Hope to see you again soon.

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| aka.ms/m365pnp-recognition
* Help shape the Microsoft Community Advisory Board priorities for the next six months by completing survey - Microsoft Community Insights - January 2023 \| aka.ms/CommunityInsightsJan23
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

* **Getting started your SPFx form customizer journey with a boilerplate**
    * Documentation - [Build your first Form Customizer extension](https://learn.microsoft.com/sharepoint/dev/spfx/extensions/get-started/building-form-customizer)
    * Article - [[SPFx] Form Customizer Boilerplate](https://michaelmaillot.github.io/tips/20221223-spfx-form-boilerplate/)
    * Repo - [spfx-form-boilerplate](https://github.com/michaelmaillot/spfx-form-boilerplate)
    * Controls - [Dynamic Form](https://pnp.github.io/sp-dev-fx-controls-react/controls/DynamicForm/)
    * Demo - [Episode \#223 - Advanced SPFx Form Customizers with DynamicForm](https://www.youtube.com/watch?v=fuVrosr-NgQ) \| [Paolo Pialorsi](https://twitter.com/paolopia) (PiaSys.com) @paolopia
* **Consuming Search API in Adaptive Card Extension**
    * Sample - [primary-text-card-search](https://github.com/pnp/sp-dev-fx-aces/tree/main/samples/PrimaryTextCard-Search)
    * npm Package - [MGWDEV M365 Helpers](https://www.npmjs.com/package/mgwdev-m365-helpers)
    * Code snippet - [sp-browser-utils](https://github.com/mgwojciech/sp-browser-utils/blob/main/utils.js)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.16.1 (GA)|v1.17 - Q1, 2023
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.12 (GA), v2.13 (GA)|v 3.12 to be released Feb 10th 2023
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v6.2 (GA), v5.9.0 GA|
[Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download)|v0.4 (preview), v0.5.0 (beta.1)|
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

* Microsoft 365 platform call \| Tuesday, February 14, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Power Platform monthly call \| Wednesday, February 15, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft 365 General Dev call \| Thursday, February 16, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, February 16, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, February 23, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Office add-in monthly call \| Wednesday, March 8, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)

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

*Microsoft 365 PnP team, Microsoft - 9th of February 2023*

{{< attachments >}}{{< /attachments >}}
