---
title: "Viva Connections & SharePoint Framework Community Call – 6th of April, 2023"
date: 2023-04-06T04:00:22.873Z
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/800-450-recording-6th-april.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Demos: A SharePoint document generator as Microsoft 365 app with SPFx, Productivity Studio: SPFx accelerators used in Microsoft to speed up SPFx development cycle. Releases: SPFx, CLI for Microsoft 365, Microsoft Graph Developer Proxy, 7 samples, 4 conversations"
videos:
- https://www.youtube.com/watch?v=bdVBHcrYjno
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Announcements
    * Announcing new SharePoint Framework 1.17 Version
    * Agenda set for next [Microsoft 365 & Power Platform weekly call](https://aka.ms/m365-dev-call) - Tuesday, April 11th, 8:00 am PT.
        * Latest news from Microsoft engineering on Microsoft 365 topics
        * **Ayca Bas & Garry Trinder** – Announcing Teams toolkit cloud skill challenge
        * **John Miller** – Introduction to Microsoft Teams Toolkit v5 - New features and capabilities
        * **Houssem Ayadi** – Hack together winner - Using Microsoft Graph and Azure Form Recognizer for optimize productivity
    * [Community Recognition Program](https://pnp.github.io/recognitionprogram/) badges for 2023 - aka.ms/community/recognition
* Shows and Events
    * Microsoft 365 Conference – May 2 – 4. 2023, Las Vegas – m365Con.com - [Register](https://m365conf.com/)
    * Upcoming [Community Days](https://communitydays.org/) Events - aka.ms/communitydays
* Project releases
    * [SharePoint Framework (SPFx)](https://aka.ms/spfx) – v1.17 (GA)
    * [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) – v6.5 (Beta)
    * [Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download) – v0.6 (Preview)
* [SPFx samples](https://aka.ms/spfx-webparts)
    * Updated – [Field Item Order](https://github.com/pnp/sp-dev-fx-extensions/tree/main/samples/jquery-field-itemorder) - [Valeras Narbutas](http://twitter.com/ValerasNarbutas) (Macaw) \| @ValerasNarbutas
    * New – [Weather Application Customizer](https://github.com/pnp/sp-dev-fx-extensions/tree/main/samples/react-application-weather-widget) - [Rishabh Shukla](https://github.com/rishabhshukla12) \| rishabhshukla12
    * Updated – [RSS Reader](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-rss-reader) - [Abderahman Moujahid](https://github.com/Abderahman88) \| Abderahman88
    * Updated – [Azure DevOps Tasks](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-azure-devops-tasks) - [Takashi Shinohara](https://twitter.com/karamem0) \| @karamem0
    * Updated – [Dynamic Accordion - FAQ Builder](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-accordion-dynamic-section) - [Valeras Narbutas](http://twitter.com/ValerasNarbutas) (Macaw) \| @ValerasNarbutas
    * New – [IFramePanel Control](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-spfx-control-iframepanel) - [Valeras Narbutas](http://twitter.com/ValerasNarbutas) (Macaw) \| @ValerasNarbutas
    * Updated – [Pages Hierarchy](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-pages-hierarchy) - [ruslan-s](https://github.com/ruslan-s)
* Conversations
    * Microsoft 365 PnP Weekly – Episode 204 (April 3rd) with by Sweden-based Microsoft MVP and CTO at Rencore - [Erwin van Hunen](https://twitter.com/erwinvanhunen) \| @erwinvanhunen \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-204/) \| [podcast](https://www.podbean.com/eas/pb-2jgsw-13d3aee)
    * Microsoft 365 Developer Podcast – Partner showcase: Syskit with Hrvoje Bagaric (April 3rd) \| [podcast](https://m365devpodcast.com/e/partner-showcase-syskit-with-hrvoje-bagaric/)
    * Power Platform Connections - Power Platform Connections Ep 7 - Dian Taylor (March 31st) \| [video](https://www.youtube.com/watch?v=5GEEhSSgMDo&t=65s)
    * Power Platform Connections - Power Platform Connections Ep 8 - Hugo Bernier (April 6th) \| [video](https://www.youtube.com/watch?v=HuKLj12NMk0)

### Demos

* **A SharePoint document generator as Microsoft 365 app with SPFx** – with this Microsoft 365 SPFx app, generate template-based Offer documents with custom meta data from within Teams, Outlook, Office, and SharePoint. The “Offer Creation” app shows up in the Add Apps menu within M365 products because it was installed as a personal app in Microsoft Teams. Templates created from M365 apps are stored in the same “Offerings” document library. Review key code elements and configuration.
* **Productivity Studio: SPFx accelerators used in Microsoft to speed up SPFx development cycle** – after getting grounded on what is the open-source SPFx Solution Accelerator and its features, step though Rhythm of the Business (RoB) Calendar app sample built with the accelerator to highlight the features, functions and code. The SPFx web part app helps users to manage a team’s events and can be added to SharePoint site or as a Teams tab.

The host of this call is [Paolo Pialorsi](https://twitter.com/paolopia) (PiaSys.com) @paolopia. Q&A takes place as always in chat throughout the call.

{{< youtube bdVBHcrYjno >}}

## Agenda items

[00:00](https://youtu.be/bdVBHcrYjno?t=0) – Intro – [Paolo Pialorsi](https://twitter.com/paolopia) (PiaSys.com) @paolopia

[06:33](https://youtu.be/bdVBHcrYjno?t=393) – SharePoint Framework – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[08:07](https://youtu.be/bdVBHcrYjno?t=487) – PnPjs Client-Side Libraries – [Julie Turner](http://twitter.com/jfj1997) (Sympraxis Consulting) \| @jfj1997

[10:40](https://youtu.be/bdVBHcrYjno?t=640) – CLI for Microsoft 365 – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[12:49](https://youtu.be/bdVBHcrYjno?t=769) – Microsoft Graph Developer Proxy – [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder

[13:32](https://youtu.be/bdVBHcrYjno?t=812) – PnP SPFx Controls – [Paolo Pialorsi](https://twitter.com/paolopia) (PiaSys.com) @paolopia

[14:55](https://youtu.be/bdVBHcrYjno?t=895) – Viva Connections Toolkit for Visual Studio Code – [Paolo Pialorsi](https://twitter.com/paolopia) (PiaSys.com) @paolopia

[15:51](https://youtu.be/bdVBHcrYjno?t=951) – PnP Modern Search – [Paolo Pialorsi](https://twitter.com/paolopia) (PiaSys.com) @paolopia

[17:04](https://youtu.be/bdVBHcrYjno?t=1024) – PnP Samples - [Hugo Bernier](http://twitter.com/bernierh) (Microsoft) \| @bernierh

[18:17](https://youtu.be/bdVBHcrYjno?t=1097) – PnP SPFx ACEs Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[18:33](https://youtu.be/bdVBHcrYjno?t=1113) – Together mode picture – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen

[19:41](https://youtu.be/bdVBHcrYjno?t=1181) – Demo – A SharePoint document generator as Microsoft 365 app with SPFx – [Markus Möller](https://twitter.com/Moeller2_0) (Avanade) \| @Moeller2_0

[35:46](https://youtu.be/bdVBHcrYjno?t=2146) – Demo – Productivity Studio: SPFx accelerators used in Microsoft to speed up SPFx development cycle – Daniel Turley (Avanade)

[49:49](https://youtu.be/bdVBHcrYjno?t=2989) – Closing

## Together Mode

![together-230406.png](images/together-230406.png)

Thank you everybody and/or their avatar representative, once again for joining the call and participating in Together Mode. Hope to see you in person at a conference near you this Spring.

## Actions

* Request a Demo spot on the call \| <https://aka.ms/community/request/demo>
* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| aka.ms/m365pnp-recognition
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Power Platform Samples Contributor \| Monday, April 10th, 11:00am PT \| 2:00pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
    * Maturity Model Practitioners \| Tuesday, April 18th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Download the recurrent invite for this call \| <https://aka.ms/spdev-spfx-call>

## Demo references

* **A SharePoint document generator as Microsoft 365 app with SPFx**
    * Article – [A SharePoint document generator as Microsoft 365 app II (SPFx)](https://mmsharepoint.wordpress.com/2022/12/28/a-sharepoint-document-generator-as-microsoft-365-app-ii-spfx/)
    * Article – [A user configured Teams personal app with SPFx web part](https://mmsharepoint.wordpress.com/2023/01/02/a-user-configured-teams-personal-app-with-spfx-web-part/)
    * Sample - [Offer Creation](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-office-offer-creation)
    * Documentation - [Extend Outlook and Office with the SharePoint Framework](https://learn.microsoft.com/sharepoint/dev/spfx/office/overview)
    * Demo - [Extend Microsoft Teams apps across Microsoft 365 (Outlook and Office)](https://youtu.be/32uOBsCDMlQ) - [Markus Möller](https://twitter.com/Moeller2_0) (Avanade) \| @Moeller2_0
* **Productivity Studio: SPFx accelerators used in Microsoft to speed up SPFx development cycle**
    * Sample - [Rhythm of Business Calendar](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-rhythm-of-business-calendar)
    * Sample Documentation - [SPFx Solution Accelerator Deep Dive](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-rhythm-of-business-calendar/documentation)
    * AppSource - [Rhythm of Business Calendar](https://appsource.microsoft.com/product/office/WA200004833)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.17 (GA)  
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.13 (GA)| v3.14 to be released April 17, 2023 
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v6.5 (GA)
[Microsoft Graph Developer Proxy](https://aka.ms/graph/proxy/download)|v0.6 (Preview)| v0.7 to be released April 26, 2023 
[Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)|v3.13.0 (GA), v2.9.0|
[Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls)|v3.12.0 (GA), v2.7.0|
[Viva Connections Toolkit for VS Code](https://github.com/pnp/vscode-viva) | v0.4.1 (GA)|
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

* Microsoft 365 platform call \| Tuesday, April 11, 8:00 am PT - <https://aka.ms/m365-dev-call> (weekly)
* Office add-in monthly call \| Wednesday, April 12, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Microsoft 365 & Power Platform Dev call \| Thursday, April 13, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Power Platform monthly call \| Wednesday, April 19, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, April 20, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, April 20, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

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

*Microsoft 365 PnP team, Microsoft - 6th of April 2023*
