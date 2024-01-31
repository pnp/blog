---
title: "Viva Connections & SharePoint Framework Community Call – 29th of June, 2023"
date: 2023-06-29T04:00:22.873Z
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-230629.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Demos: Multilingual SharePoint Page Summarization with Open AI API and Microsoft Graph Pages API, SPFx framework at Microsoft - Accelerator Live Update Feature, and Viva Connections + Stage View in Teams. Updates: PnPjs, CLI, Modern Search, 6 samples."
videos:
- https://www.youtube.com/watch?v=QkzH_rbCONs
draft: true
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### Demos

* **Multilingual SharePoint Page Summarization with Open AI API and Microsoft Graph Pages API** – add this Summarize web part (to webpage) that requests summary (of text on page) in 4 languages from OpenAI, results are displayed on page. Code walkthrough - get page text using microsoft.graph.textWebPart. call Azure PS function, construct a prompt… Overview on OpenAI and Azure OpenAI, setting up the API, integrating with SPFx, and use cases. See webpart and Azure functions code, in sample.
* **SPFx framework at Microsoft - Accelerator Live Update Feature** – see how event created by one user is seen by other users, no page refresh needed. Content (field) updates by others are announced in your version of form by visual indicator dots courtesy of Live Update React Component. You have option to choose best update of many for field. Uses package called sp-list-subscription. Covers Live Updates implementation (entities and States) and React UI.
* **Viva Connections + Stage View in Teams** – reduce Viva Dashboard clutter, cleanly open/respond to multiple forms using Stage View accessed from this single custom ACE card or access multiple Power Apps from this custom ACE. Convenience, authentication, process benefits become clear in demo. How does it work - review supporting list structure, ACE card configuration and deep-link generation.

The host of this call is [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) @bernierh. Q&A takes place as always in chat throughout the call.

{{< youtube QkzH_rbCONs >}}

## Agenda items

[00:00](https://youtu.be/QkzH_rbCONs?t=0) – Intro – [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) \| @bernierh

[05:43](https://youtu.be/QkzH_rbCONs?t=343) – PnPjs Client-Side Libraries – [Beau Cameron](https://twitter.com/beau_cameron) (Aerie Consulting) \| @beau_cameron

[07:08](https://youtu.be/QkzH_rbCONs?t=428) – CLI for Microsoft 365 – [Adam Wójcik](https://twitter.com/Adam25858782) (Hitachi Energy) \| @Adam25858782

[08:47](https://youtu.be/QkzH_rbCONs?t=527) – PnP SPFx Controls – [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) \| @bernierh

[09:38](https://youtu.be/QkzH_rbCONs?t=578) – Viva Connections Toolkit for Visual Studio Code – [Adam Wójcik](https://twitter.com/Adam25858782) (Hitachi Energy) \| @Adam25858782

[11:30](https://youtu.be/QkzH_rbCONs?t=690) – PnP Modern Search – [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) \| @bernierh

[11:59](https://youtu.be/QkzH_rbCONs?t=719) – PnP Samples - [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) \| @bernierh

[14:12](https://youtu.be/QkzH_rbCONs?t=852) – PnP SPFx ACEs Samples - [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[14:44](https://youtu.be/QkzH_rbCONs?t=884) – Together mode picture

[15:40](https://youtu.be/QkzH_rbCONs?t=940) – Demo – Multilingual SharePoint Page Summarization with Open AI API and Microsoft Graph Pages API – [Anoop Tatti](https://twitter.com/anooptells) (Content and Code) \| @anooptells

[29:04](https://youtu.be/QkzH_rbCONs?t=1744) – Demo – SPFx framework at Microsoft - Accelerator Live Update Feature – Daniel Turley (Avanade)

[38:47](https://youtu.be/QkzH_rbCONs?t=2327) – Demo – Viva Connections + Stage View in Teams – Marcus Castro (Microsoft)

[47:55](https://youtu.be/QkzH_rbCONs?t=2875) – Closing

## Together Mode

![together-230615.png](images/together-230615.png)

Here’s the proof that you were here today! Thanks for being part of this awesome community.

## Upcoming activities and actions

* [Rate this call](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR02h_1H9_XFFp4etSzu5JxFUOEc5UkxDN0dGMUgyOTBDVklBREJPRVI1Qi4u)’s content and let us know how we can improve \| aka.ms/community/calls/feedback Thanks!
* [Join](https://aka.ms/community/discord) Our Official Discord Server! \| aka.ms/community/discord
* Request a Demo spot on the call \| <https://aka.ms/community/request/demo>
* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| aka.ms/m365pnp-recognition
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Maturity Model Practitioners \| *monthly* – 3rd Tuesday, 7am PST - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Download the [recurrent invite for this call](https://aka.ms/spdev-spfx-call) \| aka.ms/spdev-spfx-call

## Demo references

* **Multilingual SharePoint Page Summarization with Open AI API and Microsoft Graph Pages API**
    * Policies – OpenAI - [API data usage policies](https://openai.com/policies/api-data-usage-policies)
    * Documentation - [Data, privacy, and security for Azure OpenAI Service](https://learn.microsoft.com/legal/cognitive-services/openai/data-privacy)
    * Sample - [Multilingual SharePoint Page Summarization with Open AI API and Microsoft Graph Pages API](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-openai-summarise-page-content)
* **SPFx framework at Microsoft - Accelerator Live Update Feature**
    * Sample - [Rhythm of Business Calendar](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-rhythm-of-business-calendar)
    * Sample - [SPFx Solution Accelerator Deep Dive](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-rhythm-of-business-calendar/documentation)
    * AppSource - [Rhythm of Business Calendar](https://appsource.microsoft.com/product/office/WA200004833)
    * Documentation – [Get notified of changes to documents stored in a SharePoint Document Library](https://learn.microsoft.com/sharepoint/dev/spfx/subscribe-to-list-notifications)
* **Viva Connections + Stage View in Teams**
    * Documentation - [Link to a Form](https://learn.microsoft.com/viva/connections/use-the-link-card#link-to-a-form)
    * Documentation - [Link to PowerApps](https://learn.microsoft.com/viva/connections/use-the-link-card#link-to-powerapps)
    * Sample - [Basic Card - Multiple Forms](https://github.com/pnp/sp-dev-fx-aces/tree/main/samples/BasicCard-Multiple-Forms-Apps)
    * Documentation - [Overview of Viva Connections](https://learn.microsoft.com/viva/connections/viva-connections-overview)
    * Documentation - [Create deep links](https://learn.microsoft.com/microsoftteams/platform/concepts/build-and-test/deep-links)
    * Samples – [SPFx ACE Samples](https://github.com/pnp/sp-dev-fx-aces/tree/main/samples)
    * Documentation – [Designing Viva Connections Quick Views](https://learn.microsoft.com/sharepoint/dev/spfx/viva/design/designing-quick-view)
    * Documentation – [Viva Connections Adaptive Card Extension Quick View samples](https://learn.microsoft.com/sharepoint/dev/spfx/viva/design/quick-view-samples)
    * Repo – [TeamsDeeplinkHelper](https://github.com/ericsche/TeamsDeeplinkHelper) (Deep-link Generator App)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.17.3 (GA)|v1.18 around September
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.16 (GA)|v4.0 Planning – Issue #2678
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v6.9 (beta)
[Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download)|v0.8 (Preview)
[Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)|v3.14.0 (GA), v2.9.0|
[Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls)|v3.13.0 (GA), v2.7.0|
[Viva Connections Toolkit for VS Code](https://github.com/pnp/vscode-viva) |v1.0 (GA)|v2.0 Roadmap shared
[PnP SPFx Generator](https://github.com/pnp/generator-spfx)|v1.16.0|v1.17.0 on the way
[PnP Modern Search](https://microsoft-search.github.io/pnp-modern-search/)|v4.9.0 (GA), v3.23.0 (GA)

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

* Microsoft 365 platform call \| *weekly* - Tuesday, 8:00 am PT – <https://aka.ms/m365-dev-call> (**Note:** This call will be on holiday.  Last call on 27th of June and back on 22nd of August)
* Microsoft 365 & Power Platform Dev call \| *bi-weekly* - Thursday, 7:00 am PT - <https://aka.ms/m365-dev-sig>
* Viva Connections & SharePoint Framework call \| *bi-weekly* - Thursday, 7:00 am PT - <https://aka.ms/spdev-spfx-call>
* Office add-in call \| *monthly* - 2nd Wednesday, 8:00 am PT - <https://aka.ms/officeaddinscall>
* Power Platform call \| *monthly* - 3rd Wednesday, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall>

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

*Microsoft 365 PnP team, Microsoft - 15th of June 2023*
