---
title: "Viva Connections & SharePoint Framework Community Call – 1st of June, 2023"
date: 2023-06-01T04:00:22.873Z
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-230601.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Demos: Building a custom Instagram Feed experience with SPFx, Using reusable IFramePanel control in your SPFx solutions, and Viva Connections ACE to display Daily Insights based on ChatGPT OpenAI API. Released: SPFx, CLI, Graph Dev Proxy, Viva Connections Toolkit."
videos:
- https://www.youtube.com/watch?v=yjhh0opXPn0
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### Demos

* **Building a custom Instagram Feed experience with SPFx** – sample web part that showcases an Instagram feed. Tips on upgrading original web part from SPFx v1.11 to v 1.16. Web part requires a user token. See SPFx code for generating token and rendering Instagram feed. Various methods discussed to bring in Instagram feed. Created an Independent Publisher Connecter (flow template) for a scheduled feed into SharePoint list. Uses the Instagram Basic Display API (graph.Instagram.com).
* **Using reusable IFramePanel control in your SPFx solutions** – this sample shows how to implement the richly capable React SPFx IFramePanel control in a SharePoint Framework web part. Observe very little coding required. Various out-of-box capabilities of the control shown in web part. Also conveyed in this sample was how the presenter happened to create the sample. He identified a “Good First Issue” in the SPFx issues list. Learned about capability, delivered solution + demo!
* **Viva Connections ACE to display Daily Insights based on ChatGPT OpenAI API** – an explorational Dev experience using OpenAI, Prompt Engineering, ChatGPT, calling external APIs. ACE with a PrimaryText card view and a quick view using ChatGPT OpenAI API. Card provides user with informational/motivational quotes, tips etc. Configurable options include API key, select prompt/category, max token, card title and description. Uses session storage to limit the number of requests per user. Deliberate UI and Code walk through (Code Tour).

The host of this call is [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) @bernierh. Q&A takes place as always in chat throughout the call.

{{< youtube yjhh0opXPn0 >}}

## Agenda items

[00:00](https://youtu.be/yjhh0opXPn0?t=0) – Intro – [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) \| @bernierh

[06:03](https://youtu.be/yjhh0opXPn0?t=363) – SharePoint Framework – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[08:24](https://youtu.be/yjhh0opXPn0?t=504) – PnPjs Client-Side Libraries – [Julie Turner](https://twitter.com/jfj1997) (Sympraxis Consulting) @jfj1997

[10:35](https://youtu.be/yjhh0opXPn0?t=635) – CLI for Microsoft 365 – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[12:21](https://youtu.be/yjhh0opXPn0?t=741) – Microsoft Graph Developer Proxy – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[13:40](https://youtu.be/yjhh0opXPn0?t=820) – PnP SPFx Controls – [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) \| @bernierh

[14:23](https://youtu.be/yjhh0opXPn0?t=863) – Viva Connections Toolkit for Visual Studio Code – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[15:22](https://youtu.be/yjhh0opXPn0?t=922) – PnP Modern Search – [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) \| @bernierh

[15:44](https://youtu.be/yjhh0opXPn0?t=944) – PnP Samples - [Hugo Bernier](http://twitter.com/bernierh) (Microsoft) \| @bernierh

[16:07](https://youtu.be/yjhh0opXPn0?t=967) – Together mode picture

[17:19](https://youtu.be/yjhh0opXPn0?t=1039) – Demo – Building a custom Instagram Feed experience with SPFx – [Reshmee Auckloo](https://twitter.com/ReshmeeAuckloo)​ (Pension Protection Fund) \| @ ReshmeeAuckloo

[29:52](https://youtu.be/yjhh0opXPn0?t=1792) – Demo – Using reusable IFramePanel control in your SPFx solutions – [Valeras Narbutas](https://twitter.com/ValerasNarbutas)​ (Macaw) \| @ValerasNarbutas

[36:34](https://youtu.be/yjhh0opXPn0?t=2194) – Demo – Viva Connections ACE to display Daily Insights based on ChatGPT OpenAI API – [Siddharth Vaghasia](https://twitter.com/siddh_me)​ \| @siddh_me

[49:08](https://youtu.be/yjhh0opXPn0?t=2948) – Closing

## Together Mode

![together-230601.png](images/together-230601.png)

The winners of the seat auction are pictured here.  You had to be there to appreciate the preceding statement. Nice work! Great to see everybody today.  Please join us on our next call.

## Upcoming activities and actions

* Agenda set for next [Microsoft 365 & Power Platform weekly call](https://aka.ms/m365-dev-call) - Tuesday, June 6th, 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * **Marc Windl –** Introduction to Microsoft Syntex Repository Services
    * **Luca Bandinelli** – Introduction to Bot Framework powered Viva Connections cards
    * **Paolo Pialorsi** - Extend SPFx apps across Microsoft 365 - Contoso Retail
* Event - [HackTogether: The Microsoft Teams Global Hack](https://github.com/microsoft/hack-together-teams) (June 1 – 15, 2023) \| aka.ms/hack-together-teams
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

* **Building a custom Instagram Feed experience with SPFx**
    * Sample - [Instagram Feed](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-instagram)
    * Article - [Instagram Feed in SPFx Web Part](https://medium.com/arfitect/instagram-feed-in-spfx-web-part-61f76fe1ded4) – Buse Kara
    * Article - [INDEPENDENT PUBLISHER CONNECTOR STEP BY STEP](https://poszytek.eu/en/microsoft-en/office-365-en/powerautomate-en/independent-publisher-connector-step-by-step/) - [Tomasz Poszytek](https://twitter.com/TomaszPoszytek)
    * IP Connector Repo - [Instagram Basic Display](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/InstagramBasicDisplay)
    * API - [Instagram Basic Display API](https://developers.facebook.com/docs/instagram-basic-display-api/)
* **Using reusable IFramePanel control in your SPFx solutions**
    * Sample – [IFramePanel Control in SPFx Web Part](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-spfx-control-iframepanel)
    * Sample - [IFramePanel sample](https://adoption.microsoft.com/en-us/sample-solution-gallery/sample/react-spfx-control-iframepanel/)
    * Issue with web part or sample - [SPFx Issues list](https://github.com/pnp/sp-dev-fx-webparts/issues)
* **Viva Connections ACE to display Daily Insights based on ChatGPT OpenAI API**
    * Documentation – [OpenAI Rate limits overview](https://platform.openai.com/docs/guides/rate-limits/overview)
    * Sample - [Daily Insights with ChatGPT](https://github.com/pnp/sp-dev-fx-aces/tree/main/samples/PrimaryTextCard-ChatGPTDailyInsights)
    * Documentation - [CodeTour](https://code.visualstudio.com/learn/educators/codetour)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.17.3 (GA)|v1.18 around September
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.15 (GA)|v3.16 to be released June 9th, v4.0 Planning – Issue #2678
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v6.8 (GA)
[Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download)|v0.8 (Preview)
[Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)|v3.14.0 (GA), v2.9.0|
[Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls)|v3.13.0 (GA), v2.7.0|
[Viva Connections Toolkit for VS Code](https://github.com/pnp/vscode-viva) | v1.0 (GA)
[PnP SPFx Generator](https://github.com/pnp/generator-spfx)|v1.16.0|v1.17.0 on the way
[PnP Modern Search](https://microsoft-search.github.io/pnp-modern-search/)|v4.8.0 (GA), v3.23.0 (GA)|v4.9 soon to be out – beta release this week!

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

* Microsoft 365 platform call \| *weekly* - Tuesday, 8:00 am PT – <https://aka.ms/m365-dev-call> (**Note:** This call will be on holiday from Tuesday July 4th through Tuesday August 15th)
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

*Microsoft 365 PnP team, Microsoft - 1st of June 2023*
