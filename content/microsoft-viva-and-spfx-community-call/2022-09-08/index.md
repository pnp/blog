---
title: "Viva Connections & SharePoint Framework Community Call – 8th of September, 2022"
date: 2022-09-08T02:00:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-8th-september.png
tags: ["Adaptive Card Extensions", "Office Add-ins", "Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Demos on Building polished form experiences with SPFx form customizer and Building SPFx solution with Azure Communication Services integration. Project releases for SharePoint Framework, CLI for Microsoft 365, PnPjs and Modern Search. 6 web part samples delivered."
videos:
- https://www.youtube.com/watch?v=r2iTAgNRREA
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online. 

### New this week

* Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, September 6th, 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * Monthly community contributors
    * **Rabeb Othmani** - Microsoft Graph Postman - Scripts and advanced functionality
    * **Ayca Bas** - Build productivity tabs with Microsoft Teams Toolkit for Visual Studio
    * **Bob German** - Introduction to app camp
* Project releases
    * [SharePoint Framework (SPFx)](https://aka.ms/spfx) – v1.16 (public developer preview)
    * [PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/) – v3.7.0 (GA)
    * [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) – v5.7.0 (GA)
    * [PnP Modern Search](https://microsoft-search.github.io/pnp-modern-search/) – v4.7.0 (GA)
* SPFx Samples
    * New - [List Form](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-list-form) - Rosa Alice \| alicelupsan
    * Updated - [Copy Views](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-copy-views) - [Martin Lingstuyl](https://twitter.com/martinlingstuyl) \| @martinlingstuyl
    * New - [Script Editor](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-script-editor) – [salascz](https://github.com/salascz)
    * New - [PnPjs Sample](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-pnp-js-sample) – [Julie Turner](https://twitter.com/jfj1997) \| @jfj1997
    * Updated - Group Membership Manager - [Nick Brown](https://twitter.com/techienickb) \| @techienickb
    * Updated - Add Form Customizer to List - [Siddharth Vaghasia](https://twitter.com/siddh_me) \| @siddh_me
* Microsoft 365 PnP Weekly – Episode 177 (September 5th) with UK-based [Kevin McDonnell](https://twitter.com/kevmcdonk), Head of Practice Modern Workplace at CPS, Microsoft MVP (Office Apps & Services) \| @kevmcdonk \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-177/) \| [podcast](https://pnpweekly.podbean.com/)
* Microsoft 365 PnP Weekly – Episode 176 (August 29th) with Netherlands-based [Daniel Laskewitz](https://twitter.com/laskewitz), Microsoft Senior Cloud Developer Advocate – Power Platform \| @laskewitz \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-176/) \| [podcast](https://www.podbean.com/media/share/pb-dc4ui-12aef1a)
* **Huge thanks for Patrick Rodgers on his last call hosting today (for now)**.
    * This was his last time hosting the call as recurrent host based on his personal request. **Patrick started this call back in February 2016** as weekly call as first spin-off from the monthly Office 365 Patterns and Practices community call - see the historical blog post announcement from [https://devblogs.microsoft.com/microsoft365dev/introducing-office-dev-pnp-office-hours-and-interest-groups/.](https://devblogs.microsoft.com/microsoft365dev/introducing-office-dev-pnp-office-hours-and-interest-groups/)
    * This was few months before Microsoft announced \#SPFx as the new extensibility model for SharePoint Online, so we could not yet talk about the details, but started to push the community towards the right direction. As we started to have gradually bit more structure in our community initiative, call then transformed to be a bi-weekly call on Thursdays later 2016.
    * It's hard to calculate the exact number of the calls Patrick has hosted, but it's somewhere around 100-120 overall calls with conservative estimate. Each call has have on average around 150 attendees, which will sum up overall \>15.000 live attendees in the calls hosted by Patrick.
    * Thank you Patrick on the hosting of these calls. **You have provided help and smiles for thousands of people all around the world and sparked countless of ideas for products or pushed people forward on their career.** You've had undoubtedly massive impact on the success of Microsoft 365 platform all up, but more importantly you've had direct impact on countless people's careers and day to day life. It's been a pleasure to work with you on these calls. 🧡
    * Patrick is not going to disappear from the community topics, but rather wanted to provide other people the opportunity to host the call. So starting from next Viva & SPFx call, we'll have a larger team of MVPs and Microsoft employees who have volunteered to host the call.

### Demos

* **Building polished form experiences with SPFx form customizer** – working back from the final UI to the code behind the scenes, see how to create a custom form component. Steps include create a list or library structure using content types, create a Form Customizer extension project using SPFx, configure and debug, deploy solution to App Catalog, and finally associate the custom component to the content type. This capability is available only using SPFx v1.15.
* **Building SPFx solution with Azure Communication Services integration** – see how pre-built ACS composite chat component is used in a SPFx web part sample called RoomChat built by João Mendes. After an overview of ACS, create a Communications Service. Visit the ACS UI Library (sandbox) – and pick up a chat component. Step through core code elements of the web part. Use property panes or SharePoint Online tenant properties for storing information used by your web part.

The host of this call is [Patrick Rodgers](http://twitter.com/mediocrebowler) (Microsoft) \| @mediocrebowler.  Q&A takes place as always in chat throughout the call.

{{< youtube r2iTAgNRREA >}}

## Agenda items

* SharePoint Framework – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen – [6:47](https://youtu.be/r2iTAgNRREA?t=407)
* PnPjs Client-Side Libraries - [Julie Turner](http://twitter.com/jfj1997) (Sympraxis Consulting) \| @jfj1997 – [8:54](https://youtu.be/r2iTAgNRREA?t=534)
* CLI for Microsoft 365 - [Garry Trinder](https://twitter.com/garrytrinder) (CPS Solutions) \| @garrytrinder – [10:40](https://youtu.be/r2iTAgNRREA?t=640)
* PnP SPFx Controls - [Patrick Rodgers](http://twitter.com/mediocrebowler) (Microsoft) \| @mediocrebowler – [13:07](https://youtu.be/r2iTAgNRREA?t=787)
* PnP Modern Search - [Patrick Rodgers](http://twitter.com/mediocrebowler) (Microsoft) \| @mediocrebowler – [13:53](https://youtu.be/r2iTAgNRREA?t=833)
* PnP Samples - [Hugo Bernier](http://twitter.com/bernierh) (Microsoft) \| @bernierh – [14:25](https://youtu.be/r2iTAgNRREA?t=865)
* PnP SPFx ACEs Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [16:01](https://youtu.be/r2iTAgNRREA?t=961)
* Demo – Building polished form experiences with SPFx form customizer – [Ejaz Hussain](https://twitter.com/EjazHussain_) (Content & Cloud) \| @ EjazHussain\_ – [17:36](https://youtu.be/r2iTAgNRREA?t=1056)
* Demo – Building SPFx solution with Azure Communication Services integration – [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) \| @bernierh – [30:25](https://youtu.be/r2iTAgNRREA?t=1825)

## Together Mode

![together-mode-220908.gif](images/together-mode-220908.gif)

It’s a full house today for picture time!  Thank you everybody for joining the call today or viewing it at as time permits. 

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Join us **in-person** in the Power Platform Samples Contributor session at the [Microsoft Power Platform Conference](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/power-platform-conference-learn-about-collab-apps-and-more/ba-p/3574306) in Orlando, FL, September 20-22, 2022
    * Maturity Model Practitioners \| Tuesday, September 20th, 7am PST - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Request a Demo spot on the call \| <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call \| <https://aka.ms/spdev-spfx-call>

## Demo references

* **Building polished form experiences with SPFx form customizer**
    * Documentation - [Getting Started with SPFx Form Customizer](https://www.office365clinic.com/2022/07/11/getting-started-with-spfx-form-customizer/)
    * Repo - [cc-formcustomizer-playground](https://github.com/ejazhussain/spfx-projects/tree/main/react-formcustomizer-customers)
    * Documentation - [Build your first Form Customizer extension (preview)](https://docs.microsoft.com/sharepoint/dev/spfx/extensions/get-started/building-form-customizer)
* **Building SPFx solution with Azure Communication Services integration**
    * Documentation - [What is Azure Communication Services?](https://docs.microsoft.com/azure/communication-services/overview)
    * Tools – [ACS UI Library](https://azure.github.io/communication-ui-library/?path=/story/overview--page) \| aka.ms/acsstroybook
    * Sample - [Room Chat](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-roomchat)
    * Documentation - [SharePoint Online tenant properties](https://docs.microsoft.com/sharepoint/dev/spfx/tenant-properties?tabs=sprest)
    * ACS Quick Start - [Get started with the calling hero sample](https://docs.microsoft.com/azure/communication-services/samples/calling-hero-sample)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.15.2 GA, v1.16 (Preview)|v1.16 (GA) end of 2022, v1.17 Preview December/January
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.7.0 GA, v2.13 GA| 
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v4.3.0 GA, v5.7.0 GA, v5.7 beta|v6.0.0 ETA November 2022
[Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)|v3.10.0, v2.9.0 (SPFx v1.11)|Supports SPFx v1.15.2
[Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls)|v3.9.0, v2.7.0 (SPFx v1.11)|Supports SPFx v1.15.2
[PnP SPFx Generator](https://github.com/pnp/generator-spfx)|v1.16.0|v1.17.0 on the way
[PnP Modern Search](https://microsoft-search.github.io/pnp-modern-search/)|v4.7.0 (GA), v3.23.0 (GA)|


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

* Microsoft 365 platform call \| Tuesday, September 13, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Office add-in monthly call \| Wednesday, September 14, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Microsoft 365 General Dev call \| Thursday, September 15, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, September 15, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Microsoft 365 platform call \| Tuesday, September 20, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Power Platform monthly call \| Wednesday, September 21, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, September 22, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Adaptive Cards monthly call \| Thursday, October 13, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)

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

*Microsoft 365 PnP team, Microsoft - 8th of September 2022*

{{< attachments >}}
