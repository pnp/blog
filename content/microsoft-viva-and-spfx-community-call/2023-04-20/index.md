---
title: "Viva Connections & SharePoint Framework Community Call – 20th of April, 2023"
date: 2023-04-20T04:00:22.873Z
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-20th-april.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Demos: The Canary in the coalmine - how to keep an eye on SharePoint Search updates, Building Service Health solution for Microsoft 365 with SPFx, and Introduction to hTWOo v2.0 - a better Fluent UI framework. 6 project releases and 2 conversations."
videos:
- https://www.youtube.com/watch?v=AJ-zFICSyXY
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Announcements
    * Announcing new SharePoint Framework 1.17 Version
    * Agenda set for next [Microsoft 365 & Power Platform weekly call](https://aka.ms/m365-dev-call) - Tuesday, April 25th, 8:00 am PT.
        * Latest news from Microsoft engineering on Microsoft 365 topics
        * **Stuart McCarthy & Marcus Castro** – Why build Power Solutions in Teams?
        * **Garry Trinder** – Bring your existing projects to Teams Toolkit for Visual Studio Code
        * **Ahmad Mozaffar** – Microsoft Graph Hackathon winner - Magic Note app to plan the day efficiently with AI & MS Graph
    * Microsoft Teams App Camp – Extend your Azure solution in Microsoft Teams – April 27, 8:00 am PT. aka.ms/TeamsAppCamp
* Shows and Events
    * Microsoft 365 Conference – May 2 – 4. 2023, Las Vegas – m365Con.com - [Register](https://m365conf.com/)
    * Upcoming [Community Days](https://communitydays.org/) Events - aka.ms/communitydays
* Project releases
    * [SharePoint Framework (SPFx)](https://aka.ms/spfx) – v1.17.1 (GA)
    * [PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/) – v3.14 (GA)
    * [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) – v6.6 (Beta)
    * [Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react) – v3.14.0 (GA)
    * [Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls) – v3.13.0 (GA)
    * [Viva Connections Toolkit for VS Code](https://github.com/pnp/vscode-viva) – v0.4.4 (GA)
* Conversations
    * Microsoft 365 PnP Weekly – Episode 206 (April 17th) with by UK-based Consultant, ECS organizer, and Microsoft MVP - [Spencer Harbar](https://twitter.com/harbars) \| @harbars \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-206/) \| [podcast](https://www.podbean.com/eas/pb-8xezu-13e666e)
    * Power Platform Connections - Power Platform Connections Episode Nine - Vesa Juvonen (April 14th) \| [video](https://www.youtube.com/watch?v=Qg4ZetD9iwM&t=655s)

### Demos

* **The Canary in the coalmine or how to keep an eye on the SharePoint Search updates** – a simple brute force solution that addresses unadvertised search outages that affect customer’s search result accuracy – site performance. The early warning system monitors search refresh - site indexing activities using an Azure function to compare SharePoint list and index values every 5 minutes. If values don’t match after 30 minutes, email is sent to the admin account.
* **Building Service Health solution for Microsoft 365 with SharePoint Framework** – a SPFx web part that uses the Graph API to display the health status for all Microsoft 365 services as seen only by Admins in Admin Center, presently. The web part delivers a similar appearance and drill down functionality as in Admin center. Web part broken into multiple sub-components with separate styling for code manageability/reuse. Many of the components are stateless.
* **Introduction to hTWOo v2.0 - a better Fluent UI framework** – created 2 years ago. There are 2 flavors of hTWOo 2.0 (hTWOo-core (html/CSS/js), and hTWOo-react (components)). Changes from 1.0 – no breaking changes, completely rewrote the library internal to CSS in SASS-dart, completely revamped website, and more. See how to get hTWOo into your SPFx project. Step through pulling a button and an accordion item into your project. Q&A - modern browser support, using hTWOo outside SPFx.

The host of this call is [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder. Q&A takes place as always in chat throughout the call.

{{< youtube AJ-zFICSyXY >}}

## Agenda items

[00:00](https://youtu.be/AJ-zFICSyXY?t=0) – Intro – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[07:41](https://youtu.be/AJ-zFICSyXY?t=461) – SharePoint Framework – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[08:56](https://youtu.be/AJ-zFICSyXY?t=536) – PnPjs Client-Side Libraries – [Julie Turner](http://twitter.com/jfj1997) (Sympraxis Consulting) \| @jfj1997

[10:40](https://youtu.be/AJ-zFICSyXY?t=640) – CLI for Microsoft 365 – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[12:33](https://youtu.be/AJ-zFICSyXY?t=753) – Microsoft Graph Developer Proxy – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[13:36](https://youtu.be/AJ-zFICSyXY?t=816) – PnP SPFx Controls – [Alex Terentiev](https://twitter.com/alexaterentiev) (Microsoft) \| @alexaterentiev

[14:16](https://youtu.be/AJ-zFICSyXY?t=856) – Viva Connections Toolkit for Visual Studio Code – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[14:55](https://youtu.be/AJ-zFICSyXY?t=895) – PnP Modern Search – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[15:32](https://youtu.be/AJ-zFICSyXY?t=932) – PnP Samples - [Hugo Bernier](http://twitter.com/bernierh) (Microsoft) \| @bernierh

[16:06](https://youtu.be/AJ-zFICSyXY?t=966) – Together mode picture – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[17:19](https://youtu.be/AJ-zFICSyXY?t=1039) – Demo – The Canary in the coalmine or how to keep an eye on the SharePoint Search updates - [Kasper Bo Larsen](https://twitter.com/kasperbolarsen) (Fellowmind) \| @kasperbolarsen

[23:43](https://youtu.be/AJ-zFICSyXY?t=1423) – Demo – Building Service Health solution for Microsoft 365 with SharePoint Framework - [Harminder Singh](https://ineleccom-my.sharepoint.com/personal/andrb_inelec_com/Documents/Desktop/SharePoint%20Videos/April%2020%20-%20SPFx%20Client-side%20call/Harminder%20Singh) (Nagarro) \| @Harminder_Sethi

[33:23](https://youtu.be/AJ-zFICSyXY?t=2003) – Demo – Introduction to hTWOo v2.0 - a better Fluent UI framework - [Stefan Bauer](https://ineleccom-my.sharepoint.com/personal/andrb_inelec_com/Documents/Desktop/SharePoint%20Videos/April%2020%20-%20SPFx%20Client-side%20call/Stefan%20Bauer) (N8D) \| @StfBauer

[52:34](https://youtu.be/AJ-zFICSyXY?t=3154) – Closing


## Together Mode

![together-230420.png](images/together-230420.png)

Thanks everybody for joining today. Awesome to have you in the call and hopefully we will see each other soon at an in-person event location near you.

## Actions

* Plan to attend Microsoft Teams App Camp – Extend your Azure solution in Microsoft Teams – April 27, 8:00 am PT. aka.ms/TeamsAppCamp
* Request a Demo spot on the call \| <https://aka.ms/community/request/demo>
* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| aka.ms/m365pnp-recognition
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Maturity Model Practitioners \| Tuesday, May 16th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Download the recurrent invite for this call \| <https://aka.ms/spdev-spfx-call>

## Demo references

* **The Canary in the coalmine or how to keep an eye on the SharePoint Search updates**
    * Repo - [The canary in the coalmine](https://github.com/kasperbolarsen/thecanaryinthecoalmine/)
* **Building Service Health solution for Microsoft 365 with SharePoint Framework**
    * Sample - [Service Health for Microsoft 365](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-m365-services-health)
* **Introduction to hTWOo v2.0 - a better Fluent UI framework**
    * npm – [htwoo packages](https://www.npmjs.com/search?q=htwoo)
    * Guidelines - [Web Content Accessibility Guidelines (WCAG)](https://ineleccom-my.sharepoint.com/personal/andrb_inelec_com/Documents/Desktop/SharePoint%20Videos/April%2020%20-%20SPFx%20Client-side%20call/Web%20Content%20Accessibility%20Guidelines%20(WCAG))
    * Documentation – [hTWOo](https://lab.n8d.studio/htwoo/)
    * Blog – [n8d](https://n8d.at)
    * Items - [Quick Links Compact and List Items](https://lab.n8d.studio/htwoo/htwoo-core/?p=organism-pnp-search-grid)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.17.1 (GA)
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.14 (GA)
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v6.6 (GA)
[Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download)|v0.6 (Preview)| v0.7 to be released April 26, 2023
[Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)|v3.14.0 (GA), v2.9.0|
[Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls)|v3.13.0 (GA), v2.7.0|
[Viva Connections Toolkit for VS Code](https://github.com/pnp/vscode-viva) | v0.4.4 (GA)|
[PnP SPFx Generator](https://github.com/pnp/generator-spfx)|v1.16.0|v1.17.0 on the way
[PnP Modern Search](https://microsoft-search.github.io/pnp-modern-search/)|v4.8.0 (GA), v3.23.0 (GA)|

## Links in this call

* Microsoft 365 & Power Platform community videos - aka.ms/community/videos
* LinkedIn group for discussions and updates - aka.ms/community/Li
* Open-source assets –
    * github.com/pnp
    * github.com/officedev
    * github.com/sharepoint
    * github.com/microsoftgraph
* Unified Sample gallery - aka.ms/community/samples
* Product sample galleries
    * aka.ms/teams-samples
    * aka.ms/spfx-webparts
    * aka.ms/spfx-extensions
    * aka.ms/powerplatform-samples
    * aka.ms/list-formatting
* One place for Open-source initiatives and samples - aka.ms/community/home
* Microsoft 365 & Power Platform community calls - aka.ms/community/calls
* Community call agendas - aka.ms/community/meetup
* Request to Present - aka.ms/community/request/demo
* Invite (ics) for the Microsoft 365 & Power Platform call - aka.ms/community/ms-speakers-call-invite
* Learn how to get started in the open-source PnP community! – aka.ms/sharing-is-caring
* Community Recognition Program – aka.ms/community/recognition
* Project Specific
    * SharePoint Framework
        * Release notes - learn.microsoft.com/sharepoint/dev/spfx/roadmap
        * Repo - github.com/SharePoint/sp-dev-docs
    * PnPjs Client-side Libraries
        * Repo/Docs – pnp.github.io/pnpjs
        * nightly builds – npm install @pnp/sp@v3nightly –save
    * CLI for Microsoft 365
        * Repo – github.com/cli-microsoft365
        * CLI community on Discord aka.ms/cli-m365/discord
        * Twitter @climicrosoft365
        * Documentation - aka.ms/cli-m365/
    * Microsoft Graph Developer Proxy – aka.ms/graph/proxy/download
    * Reusable SPFx Controls
        * Release notes - pnp.github.io/sp-dev-fx-property-controls/about/release-notes/
        * Documentation - sharepoint.github.io/sp-dev-fx-property-controls
        * Twitter - @M365PnPControls
    * React Property Controls –
        * Release notes - pnp.github.io/sp-dev-fx-property-controls/about/release-notes/
        * Documentation - sharepoint.github.io/sp-dev-fx-controls-react
        * Twitter - @M365PnPControls
    * Viva Connections Toolkit for Visual Studio Code
        * Repo - aka.ms/viva/vscode
    * PnP Modern Search
        * Documentation - aka.ms/pnp-search
        * Repo - github.com/microsoft-search/pnp-modern-search/releases
* All community calls – aka.ms/community/calls
* Feedback on this call - aka.ms/community/calls/feedback
* Follow us on Twitter for updates - @m365pnp, and @Microsoft365Dev

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

* Microsoft 365 & Power Platform community call \| Tuesday, April 25, 8:00 am PT - <https://aka.ms/m365-dev-call> (weekly)
* Microsoft 365 & Power Platform Dev call \| Thursday, April 27, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Viva Connections & SharePoint Framework call \| Thursday, May 4, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Office add-in monthly call \| Wednesday, May 10, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Power Platform monthly call \| Wednesday, May 17, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, May 18, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

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

*Microsoft 365 PnP team, Microsoft - 20th of April 2023*
