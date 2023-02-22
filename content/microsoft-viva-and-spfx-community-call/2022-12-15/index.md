---
title: "Viva Connections & SharePoint Framework Community Call – 15th of December, 2022"
date: 2022-12-15T02:00:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-15th-december.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Demos: Using custom SDK built with Microsoft Graph Kiota generator within SharePoint Framework solution and Building an ACE for showing real time trade prices of stocks. Released PnPjs Client-Side Libraries, CLI for Microsoft 365, 1 ACE sample, 1 training announced."
videos:
- https://www.youtube.com/watch?v=k1HhzNbmngE
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, December 20th 8:00 am PT.
    * During the holiday season, we will transform the calls to be coffee & tea with the community meetings – Q&A and discussions and without specific demos and agenda. Please join as you are able.
* Announcements
    * The Road Ahead – SPFx roadmap
    * Registration open
        * Power Platform Samples Contributor \| Tuesday, January 10th, 10:30am PST \| [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
        * First Time Contributor \| Thursday, January 12th, 10am PT \| 1pm ET \| 7pm CET – [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNjAwRVNETlA1MkxIR1MyTEs5STZFVVRJMC4u)
        * Writing for the Web \| Monday, January 23rd, 10am PT \| 1pm ET \| 7:00pm CET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMFNPNFMyUk9CNFROUjJWTFFGSzdJV0czVC4u)
        * PnP SPFx Samples w/ NVM \| Wednesday, January 25th, 9am PT \| 12pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNEE2SUdTOU1UOEtCTFU3MlM1SERDMlNVNi4u)
* Project releases
    * [PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/) – v3.10 (GA)
    * [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) – v6.1 (beta)
* ACE samples
    * [Simple Search in Adaptive Card](https://github.com/pnp/sp-dev-fx-aces/pull/112) – [Marcin Wojciechowski](https://twitter.com/mgwojciech) \| @mgwojciech
* Conversations
    * Microsoft 365 PnP Weekly – Episode 191 (December 12th) with Microsoft Redmond based Visual Studio Development Program Manager - [Julia Kasper](https://twitter.com/Jujujuliakasper) \| @Jujujuliakasper \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-191/) \| [podcast](https://www.podbean.com/media/share/pb-vp8k5-1338aee)
    * Microsoft 365 PnP Weekly – Episode 190 (December 5th) with Germany based developer, architect, business owner, Microsoft MVP, and regional conference event coordinator Adis Jugo \| @adisjugo \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-190/) \| [podcast](https://www.podbean.com/media/share/pb-bfn9g-1330430)

### Demos

* **Using custom SDK built with Microsoft Graph Kiota generator within SharePoint Framework solution** – using a Kiota generated client in an SPFx Teams webpart. Review what is Kiota, the OpenAPI Initiative (OAI), a Teamified SPFx web part, and architecture overviews on working with Graph and on Azure and Kiota client authentication in SPFx. Dive into the code to see how the SPFx TypeScript web part calls the API using Kiota and how Kioto can list off all dependencies for your project.
* **Building an ACE for showing real time trade prices of stocks** – an Adaptive card extension that displays prices of US stocks, forex and crypto in real time with the help of finnhub APIs. Simple change in property pane to see pricing in local currency. Code walkthrough. Uses [finnhub](https://finnhub.io/) APIs and WebSocket for fetching real-time data and Viva dashboard to target audience inside an organization. Samples available now and feedback greatly appreciated.

The host of this call is [Paolo Pialorsi](https://twitter.com/paolopia) (PiaSys.com) @paolopia. Q&A takes place as always in chat throughout the call.

{{< youtube k1HhzNbmngE >}}

## Agenda items

* [05:56](https://youtu.be/k1HhzNbmngE?t=356) – SharePoint Framework – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen
* [07:53](https://youtu.be/k1HhzNbmngE?t=473) – PnPjs Client-Side Libraries - [Julie Turner](http://twitter.com/jfj1997) (Sympraxis Consulting) \| @jfj1997
* [09:44](https://youtu.be/k1HhzNbmngE?t=584) – CLI for Microsoft 365 - [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder
* [12:01](https://youtu.be/k1HhzNbmngE?t=721) – PnP SPFx Controls - [Alex Terentiev](https://twitter.com/alexaterentiev) (Microsoft) \| @alexaterentiev
* [12:48](https://youtu.be/k1HhzNbmngE?t=768) – PnP Modern Search - [Paolo Pialorsi](https://twitter.com/paolopia) (PiaSys.com) @paolopia
* [13:56](https://youtu.be/k1HhzNbmngE?t=836) – PnP Samples - [Hugo Bernier](http://twitter.com/bernierh) (Microsoft) \| @bernierh
* [14:30](https://youtu.be/k1HhzNbmngE?t=870) – PnP SPFx ACEs Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII
* [15:33](https://youtu.be/k1HhzNbmngE?t=933) – Together mode picture
* [16:10](https://youtu.be/k1HhzNbmngE?t=970) – Demo – Using custom SDK built with Microsoft Graph Kiota generator within SharePoint Framework solution – [Luis Mañez](https://twitter.com/luismanez) (ClearPeople) \| @luismanez
* [29:36](https://youtu.be/k1HhzNbmngE?t=1776) – Demo – Building an ACE for showing real time trade prices of stocks – [Kunj Sangani](https://twitter.com/sanganikunj) (Cognizant) \| @sanganikunj

## Together Mode

![together-221215.png](images/together-221215.png)

Thank you everybody for joining. Really, really cool to have you in the call.  If you missed the call, no worries, view it on demand and plan on joining us on a future call.

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| aka.ms/m365pnp-recognition
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Register for upcoming [Sharing Is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Maturity Model Practitioners \| Tuesday, December 20th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * Power Platform Samples Contributor \| Tuesday, January 10th, 10:30am PST \| [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
    * First Time Contributor \| Thursday, January 12th, 10am PT \| 1pm ET \| 7pm CET – [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNjAwRVNETlA1MkxIR1MyTEs5STZFVVRJMC4u)
    * Writing for the Web \| Monday, January 23rd, 10am PT \| 1pm ET \| 7:00pm CET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMFNPNFMyUk9CNFROUjJWTFFGSzdJV0czVC4u)
    * PnP SPFx Samples w/ NVM \| Wednesday, January 25th, 9am PT \| 12pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNEE2SUdTOU1UOEtCTFU3MlM1SERDMlNVNi4u)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
* PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Request a Demo spot on the call \| <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call \| <https://aka.ms/spdev-spfx-call>

## Demo references

* **Using custom SDK built with Microsoft Graph Kiota generator within SharePoint Framework solution**
    * Sample - [Using Kiota to generate a client to your AzureAd API and use it from a SPFx webpart](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-kiota-custom-api-client)
    * Documentation - [Welcome to Kiota](https://microsoft.github.io/kiota/)
    * Repo - [Project Kiota](https://github.com/microsoft/kiota)
    * Library – [Project Kiota TypeScript](https://github.com/microsoft/kiota-typescript)
    * Article – [Using Microsoft Kiota tool to generate Atlas API SDKs](https://www.clearpeople.com/blog/microsoft-kiota-tool-to-generate-atlas-api-sdks)
    * Article - [Using a Kiota client for your API in a SharePoint framework solution](https://www.clearpeople.com/blog/howto-kiota-client-api-sharepoint-framework-solution)
* **Building an ACE for showing real time trade prices of stocks**
    * Resource - [Finnhub Stock API](https://finnhub.io/)
    * Sample - [primary-text-card-stock-bitcoin-feed](https://github.com/pnp/sp-dev-fx-aces/tree/main/samples/PrimaryTextCard-StockBitcoinFeed)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.16.1 (GA)|v1.17 - Q1, 2023
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.10 GA, v2.13 GA|
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v6.1 (beta), v5.9.0 GA|
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

* Microsoft 365 platform call - **(Coffee & chat with Community)** \| Tuesday, December 20, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Power Platform monthly call \| Wednesday, December 21, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft 365 General Dev call - \| Thursday, December 22, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Microsoft 365 platform call - **(Coffee & chat with Community)** \| Tuesday, December 27, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Viva Connections & SharePoint Framework call \| Thursday, December 29, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Office add-in monthly call \| Wednesday, January 11, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Microsoft Identity Platform call \| Thursday, January 19, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

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

*Microsoft 365 PnP team, Microsoft - 15th of December 2022*

{{< attachments >}}
