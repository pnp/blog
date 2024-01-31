---
title: "Viva Connections & SharePoint Framework Community Call – 9th of March, 2023"
date: 2023-03-09T04:00:22.873Z
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-9th-march.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Two demos: Build a SPFx solution to create AI generated images with DALL-E API and Build AI integration for Microsoft 365 using Chat GPT and SPFx solution. Releases: 6 Project releases, 8 SPFx and 2 ACE samples, plus 2 conversations."
videos:
- https://www.youtube.com/watch?v=GKZ0WSUXoxI
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Announcements
    * Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, March 14, 2023, 8:00 am PT.
        * Latest news from Microsoft engineering on the Microsoft 365 topics
        * Community together mode group photo
        * Demo – **Waldek Mastykarz** - Microsoft Graph Hackathon – Recap on the second week
        * Demo – **Gary Pretty -** Boost your conversations with GPT and PVA
        * Demo – **Dan Wahlin** - Deploying the Azure Communications Services Application to Azure
    * [Sharing-Is-Caring training](https://pnp.github.io/sharing-is-caring/) event next week - Power Platform Samples Contributor \| Wednesday, March 15th, 10:00am PT \| 1:00pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
    * [Community Recognition Program](https://pnp.github.io/recognitionprogram/) badges for 2023 - aka.ms/community/recognition
* Project releases
    * [SharePoint Framework (SPFx)](https://aka.ms/spfx) – v1.17 (Preview)
    * [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) – v6.3 (GA)
    * [Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download) – v0.5 (Preview)
    * [Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react) – v3.13.0 (GA)
    * [Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls) – v3.12.0 (GA)
    * [Viva Connections Toolkit for VS Code](https://github.com/pnp/vscode-viva) – v0.4.1 (Preview)
* [SPFx samples](https://aka.ms/spfx-webparts)
    * Updated - [All Microsoft 365 Groups and Teams with SPFx](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-groups-teams) - [Alison Collins](https://github.com/ReactIntern) \| ReactIntern
    * New - [Search Conversation Teams Tab](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-teams-conversationview) - [Siddharth Vaghasia](https://twitter.com/siddh_me) \| @siddh_me
    * Updated - [Chat GPT App](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-chatgpt-app) - [João Mendes](https://twitter.com/joaojmendes) \| @joaojmendes
    * New - [Quick Links](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-quick-links) - [Dan Toft](https://twitter.com/tanddant) \| @tanddant
    * Updated - [Applications Secrets Expiration](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-graph-app-secret-expiration) - [Aimery Thomas](https://twitter.com/aimery_Thomas) \| @aimery_Thomas
    * Updated - [Advanced Page Properties](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-advanced-page-properties) - [Valeras Narbuta](https://twitter.com/ValerasNarbuta)s \| @ValerasNarbutas
    * Updated - [Twitter](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-twitter) - [Reshmee Auckloo](https://twitter.com/ReshmeeAuckloo) \| @ReshmeeAuckloo
    * New - [Multilingual SharePoint Page Summarization with Open AI API and Microsoft Graph Pages API](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-openai-summarise-page-content) - [Anoop Tatti](https://twitter.com/anooptells) \| @anooptells
* [ACE samples](https://aka.ms/spfx-aces)
    * New - [Daily Insights with ChatGPT](https://github.com/pnp/sp-dev-fx-aces/pull/125) - [Siddharth Vaghasia](https://twitter.com/siddh_me) \| @siddh_me
    * Updated - [Join New Teams Upgrade – SPFx 1.16.1](https://github.com/pnp/sp-dev-fx-aces/pull/126)- [Aimery Thomas](https://twitter.com/aimery_Thomas) \| @aimery_thomas
* Conversations
    * Microsoft 365 PnP Weekly – Episode 200 (March 6th) with hossts [Sébastien Levert](https://twitter.com/sebastienlevert) (Microsoft) \| @sebastienlevert, [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen and [Waldek Mastykarz](https://twitter.com/waldekm) (Microsoft) \| @waldekm \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-200/) \| [podcast](https://www.podbean.com/eas/pb-cuzet-13ad58a)
    * Microsoft 365 PnP Weekly – Episode 199 (February 27th) with reflections from [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen and [Waldek Mastykarz](https://twitter.com/waldekm) (Microsoft) \| @waldekm \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-199/) \| [podcast](https://pnpweekly.podbean.com)

### Demos

* **Build a SPFx solution to create AI generated images with DALL-E API** – review DALL-E capabilities and billing model. Access [Open AI API of DALL-E 2](https://openai.com/dall-e-2/), create an account, generate an API key. Next create an image first by calling image API from Postman, then via the SPFx web part. Save image to document library. Step through the web part code – uses SPFx to call API, PnPjs to save image to library, base64 encoding.
* **Build AI integration for Microsoft 365 using ChatGPT and SPFx solution** – to easily incorporate this search capability in your Microsoft 365 environment. Review prerequisites - get OpenAI API key, install the web part, add web part to a site and add your API key to Properties. Code deep dive – install OpenAI package, configure chatGPT and API response parameters. Review 4 Open AI language models, options for concealing your API key and token usage optimization.

The host of this call is [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) @bernierh. Q&A takes place as always in chat throughout the call.

{{< youtube GKZ0WSUXoxI >}}

## Agenda items

[00:00](https://youtu.be/GKZ0WSUXoxI?t=0) – Intro – [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) @bernierh

[04:48](https://youtu.be/GKZ0WSUXoxI?t=288) – SharePoint Framework – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[06:19](https://youtu.be/GKZ0WSUXoxI?t=379) – PnPjs Client-Side Libraries – [Patrick Rodgers](https://twitter.com/mediocrebowler) (Microsoft) \| @mediocrebowler

[07:11](https://youtu.be/GKZ0WSUXoxI?t=431) – CLI for Microsoft 365 – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[08:47](https://youtu.be/GKZ0WSUXoxI?t=527) – Microsoft Graph Developer Proxy – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[10:24](https://youtu.be/GKZ0WSUXoxI?t=624) – PnP SPFx Controls – [Alex Terentiev](https://twitter.com/alexaterentiev) (Microsoft) \| @alexaterentiev

[11:14](https://youtu.be/GKZ0WSUXoxI?t=674) – Viva Connections Toolkit for Visual Studio Code – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[12:09](https://youtu.be/GKZ0WSUXoxI?t=729) – PnP Modern Search – [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) @bernierh

[12:55](https://youtu.be/GKZ0WSUXoxI?t=775) – PnP Samples - [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) \| @bernierh

[14:53](https://youtu.be/GKZ0WSUXoxI?t=893) – PnP SPFx ACEs Samples - [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[15:46](https://youtu.be/GKZ0WSUXoxI?t=946) – Together mode picture – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[17:08](https://youtu.be/GKZ0WSUXoxI?t=1028) – Demo – Build a SPFx solution to create AI generated images with DALL-E API – [Luis Mañez](https://twitter.com/luismanez) (ClearPeople) \| @luismanez

[28:47](https://youtu.be/GKZ0WSUXoxI?t=1727) – Demo – Build AI integration for Microsoft 365 using ChatGPT and SPFx solution – [Nico De Cleyre](https://twitter.com/NicoDeCleyre) (Ordina) \| @NicoDeCleyre

[49:00](https://youtu.be/GKZ0WSUXoxI?t=2940) – Closing

## Together Mode

![together-230309.png](images/together-230309.png)

And the winners are captured above herein, right here. Congratulations! Thanks for joining and participating in the call today. Cheers.

## Actions

* Request a Demo spot on the call \| <https://aka.ms/community/request/demo>
* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| aka.ms/m365pnp-recognition
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Power Platform Samples Contributor \| Wednesday, March 15th, 10:00am PT \| 1:00pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
    * Maturity Model Practitioners \| Tuesday, March 21st, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Download the recurrent invite for this call \| <https://aka.ms/spdev-spfx-call>

## Demo references

* **Build a SPFx solution to create AI generated images with DALL-E API**
    * Sample - [Image generation using DALL-E API](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-dall-e-image-generation)
* **Build AI integration for Microsoft 365 using ChatGPT and SPFx solution**
    * Key – platform.openai.com/account/api-keys
    * Sample - [ChatGPT inside SPFx](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-chat-gpt)
    * Article - [Integrate ChatGPT into SPFx solutions](https://nicodecleyre.com/2023/02/08/integrate-chatgpt-into-spfx-solutions/)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.16.1 (GA), v1.17 (Preview)| v1.17 (GA) April 2023
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.12 (GA)| v3.13 to be released March 17, 2023
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v6.3 (GA)|
[Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download)|v0.5 (preview)| v0.6 to be released March 30, 2023
[Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)|v3.13.0 (GA), v2.9.0|
[Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls)|v3.12.0 (GA), v2.7.0|
[Viva Connections Toolkit for VS Code](https://github.com/pnp/vscode-viva) | v0.4.1 (Preview)|
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

* Microsoft 365 platform call \| Tuesday, March 14, 8:00 am PT - <https://aka.ms/m365-dev-call> (weekly)
* Power Platform monthly call \| Wednesday, March 15, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft 365 General Dev call \| Thursday, March 16, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, March 16, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, March 23, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Office add-in monthly call \| Wednesday, April 12, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)

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

*Microsoft 365 PnP team, Microsoft - 9th of March 2023*

{{< attachments >}}{{< /attachments >}}
