---
title: "Viva Connections & SharePoint Framework Community Call – 4th of May, 2023"
date: 2023-05-04T04:00:22.873Z
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-4th-may.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Demos: Building Conversation search experience for Microsoft Teams with SPFx and Replicating the Quick Links web part for extensibility. Projects: CLI for Microsoft 365 – v6.7 (GA), Microsoft Graph Developer Proxy – v0.7 (GA), and 2 conversations."
videos:
- https://www.youtube.com/watch?v=wzGFtEj7NMQ
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Announcements
    * Agenda set for next [Microsoft 365 & Power Platform weekly call](https://aka.ms/m365-dev-call) - Tuesday, May 9th, 8:00 am PT.
        * Latest news from Microsoft engineering on Microsoft 365 topics
        * **Eric Scherlinger** & **Avadhesh Dubey** – Power Automate and Microsoft Teams
        * **Cathy Dew** – Latest on the SharePoint site templates - site creation and template updates
        * **Vesa Juvonen** - Latest on using SPFx for Microsoft Teams extensibility
* Shows and Events
    * Upcoming [Community Days](https://communitydays.org/) Events - aka.ms/communitydays
* Project releases
    * [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) – v6.7 (GA)
    * [Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download) – v0.7 (GA)
* Conversations
    * Microsoft 365 PnP Weekly – Episode 208 (May 1st) with Paris, France-based Principal Product Manager - [David Rousset](https://twitter.com/davrous) (Microsoft) \| @davrous \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-208/) \| [podcast](https://www.podbean.com/eas/pb-w7dk6-13f8aaa)
    * Power Platform Connections - Power Platform Connections Ep 11 - Chris Huntingford (April 27th) \| [video](https://www.youtube.com/watch?v=0uo-lZckCJQ&t=5s)

### Demos

* **Building Conversation search experience for Microsoft Teams with SPFx** – web part (react-teams-conversationview) shows a Teams channel’s conversation simply, making it easier for users to search and filter for latest conversations and replies. SPFx web part optimized for a channel conversation on a Teams tab. Latest conversations on top, filters to sort by person, topic, dates and attachments. Display in chat format or tabular view. 10-step CodeTour guides viewers through solution. Gets messages using Graph API.
* **Replicating the Quick Links web part for extensibility** – the modern, intuitive to edit Quick Lines web part. What are Quick links? Sorting and storing items, calculating sort weight (to position cards), and tricks for working with property pane - like drag n’ drop and Quick Links URL options. 6 Quick Links layouts including the Tiles option from year’s past. Appreciate implementation challenges overcome – like ordering tiles. Get the sample to see the code.

The host of this call is [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder. Q&A takes place as always in chat throughout the call.

{{< youtube wzGFtEj7NMQ >}}

## Agenda items

[00:00](https://youtu.be/wzGFtEj7NMQ?t=0) – Intro – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[10:14](https://youtu.be/wzGFtEj7NMQ?t=614) – PnPjs Client-Side Libraries – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[11:10](https://youtu.be/wzGFtEj7NMQ?t=670) – CLI for Microsoft 365 – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[13:18](https://youtu.be/wzGFtEj7NMQ?t=798) – Microsoft Graph Developer Proxy – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[15:40](https://youtu.be/wzGFtEj7NMQ?t=940) – PnP SPFx Controls – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[17:01](https://youtu.be/wzGFtEj7NMQ?t=1021) – PnP Modern Search – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[17:48](https://youtu.be/wzGFtEj7NMQ?t=1068) – PnP Samples - [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[18:26](https://youtu.be/wzGFtEj7NMQ?t=1106) – Together mode picture – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[19:30](https://youtu.be/wzGFtEj7NMQ?t=1170) – Demo – Building Conversation search experience for Microsoft Teams with SPFx – [Siddharth Vaghasia](https://twitter.com/siddh_me) (BinaryRoots) \| @siddh_me and [Kunj Sangani](https://twitter.com/sanganikunj) \| @sanganikunj

[38:34](https://youtu.be/wzGFtEj7NMQ?t=2314) – Demo – Replicating the Quick Links web part for extensibility – [Dan Toft](https://twitter.com/tanddant) (Evobis ApS) \| @tanddant

[49:58](https://youtu.be/wzGFtEj7NMQ?t=2998) – Closing

## Together Mode

![together-230504.png](images/together-230504.png)

Great as always to see many of you on the call today.  Thank you for joining call and for being part of your vibrant community.

## Actions

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

* **Building Conversation search experience for Microsoft Teams with SPFx**
    * Sample - [Teams Tab Conversation View](https://adoption.microsoft.com/sample-solution-gallery/sample/pnp-sp-dev-spfx-web-parts-react-teams-conversationview/)
    * Documentation - [Build Microsoft Teams tab using SharePoint Framework – Tutorial](https://learn.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/using-web-part-as-ms-teams-tab)
    * Documentation - [Build your first app with SPFx](https://learn.microsoft.com/microsoftteams/platform/sbs-gs-spfx)
* **Replicating the Quick Links web part for extensibility**
    * Sample – [Quick Links](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-quick-links)
    * Blog – [Dan Toft](https://blog.dan-toft.dk/)
    * Documentation - [Office URI Schemes](https://learn.microsoft.com/office/client-developer/office-uri-schemes)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.17.1 (GA)
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.14 (GA)|v3.15 to release on May 12
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v6.7 (GA)
[Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download)|v0.7 (Preview)|v0.8 to be released May 31
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

* Microsoft 365 platform call \| Tuesday, May 9, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Office add-in monthly call \| Wednesday, May 10, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Microsoft 365 & Power Platform Dev call \| Thursday, May 11, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Power Platform monthly call \| Wednesday, May 17, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, May 18, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
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

*Microsoft 365 PnP team, Microsoft - 4th of May 2023*
