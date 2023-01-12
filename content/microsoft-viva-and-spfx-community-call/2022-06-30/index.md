---
title: "Viva Connections & SharePoint Framework Community Call – 30th of June, 2022"
date: 2022-07-01T02:00:00-05:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-30th-june.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Demos: Building custom accordion Tabs experience with rich text experiences, Using Microsoft Graph Profile API in SPFx for awards web part experience, and Adaptive Cards Extensions strategy pattern for multi-action QuickView. Released Reusable SPFx React Controls v3.8.1 and 2 samples."
videos:
- https://www.youtube.com/watch?v=y-XxYJiEINM
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Project releases
    * [Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react) – v3.8.1(GA) – Fixed: LivePersona not showing card on hover
* Web part samples
    * [Page Navigator](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-page-navigator) - [Jasey Waegebaert](http://twitter.com/JWaegebaert) \| @JWaegebaert
    * [Staff Directory](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-staffdirectory) **-** [Milan Holemans](https://github.com/milanholemans) \| milanholemans
* Microsoft 365 Developer Podcast (June 28th) - PowerShell and Azure AD with Merill Fernando \| [podcast](https://www.m365devpodcast.com/e/powershell-and-azure-ad-with-merill-fernando/)
* Microsoft 365 PnP Weekly – Episode 172 (June 27th) with by Colorado, US based Architect, Developer and MVP at DMI - [Beau Cameron](https://twitter.com/Beau__Cameron) \| @Beau__Cameron \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-172/) \| [podcast](https://www.podbean.com/media/share/pb-itk6r-125e65b)
* Microsoft 365 PnP Weekly – Episode 171 (June 20th) with Germany based Teams/Power Apps Consultant, Partner Manager, MVP at Valo Solutions - [Edyta Gorzon](https://twitter.com/EdytaGorzon) \| @EdytaGorzon \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-171/) \| [podcast](https://www.podbean.com/media/share/pb-axtx9-1255b1a)

### Demos

* **Building custom accordion Tabs experience with rich text experiences** – this web part allows users to create and manage content laid out in tabbed or accordion format for both desktop and mobile. Switch between views using Property Field Collection Data and edit content with tinyMCE Rich Text Editor for SharePoint Online. Uses Custom Accordion components and Custom Tab components included in the code. Also uses primary colors and themes from host site.
* **Using Microsoft Graph Profile API in SPFx for awards web part experience** – shows user profile and awards courtesy of the recently released beta Microsoft Graph profile endpoint. Awards is an example of new information (skills, projects, languages…) you can attach to a user’s profile using Graph. Sample shows title, description, badge and link to more information about award. See using Postman to add an award. Uses the me endpoint to get list of awards.
* **Adaptive Cards Extensions strategy pattern for multi-action QuickView** – with complex ACE’s, handling many conditional quick view onActions (many if action.id statements), can seriously complicate code. Example scenario – exposing news items with next and previous actions, options to like and comment, and the ability to post news in a Teams channel. Move from many onActions to a single action with refactoring. See how acions are handled/combined by the ActionExecutor!


The host of this call is [Patrick Rodgers](http://twitter.com/mediocrebowler)
(Microsoft) \| @mediocrebowler. Q&A takes place as always in chat throughout the
call.

{{< youtube y-XxYJiEINM >}}

## Agenda items

* SharePoint Framework - [Vesa Juvonen](http://twitter.com/vesajuvonen) (Microsoft) \| vesajuvonen – [5:35](https://youtu.be/y-XxYJiEINM?t=335)
* PnPjs Client-Side Libraries - [Julie Turner](http://twitter.com/jfj1997) (Sympraxis Consulting) \| @jfj1997 – [7:24](https://youtu.be/y-XxYJiEINM?t=444)
* CLI for Microsoft 365 - [Patrick Rodgers](http://twitter.com/mediocrebowler) (Microsoft) \| @mediocrebowler – [9:27](https://youtu.be/y-XxYJiEINM?t=567)
* PnP SPFx Controls - [Patrick Rodgers](http://twitter.com/mediocrebowler) (Microsoft) \| @mediocrebowler – [11:18](https://youtu.be/y-XxYJiEINM?t=678)
* PnP Modern Search - [Patrick Rodgers](http://twitter.com/mediocrebowler) (Microsoft) \| @mediocrebowler – [11:55](https://youtu.be/y-XxYJiEINM?t=715)
* PnP Samples - [Hugo Bernier](http://twitter.com/bernierh) (Microsoft) \| @bernierh – [12:33](https://youtu.be/y-XxYJiEINM?t=753)
* PnP SPFx ACEs Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [13:58](https://youtu.be/y-XxYJiEINM?t=838)
* Demo - Building custom accordion Tabs experience with rich text experiences – [Arun Kumar Perumal](https://twitter.com/arun_perumal16) (Wipro) \| @arun_perumal16 – [15:36](https://youtu.be/y-XxYJiEINM?t=936)
* Demo - Using Microsoft Graph Profile API in SPFx for awards web part experience – [Luis Mañez](https://twitter.com/luismanez) (ClearPeople) \| @luismanez – [24:49](https://youtu.be/y-XxYJiEINM?t=1489)
* Demo - Adaptive Cards Extensions strategy pattern for multi-action QuickView – [Marcin Wojciechowski](https://twitter.com/mgwojciech) (Valo) \| @mgwojciech – [32:38](https://youtu.be/y-XxYJiEINM?t=1958)


## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Writing for the Web \| Monday, July 11th, 10am PT \| 1pm ET \| 7pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Power Platform Samples Contributor \| Wednesday, July 20th, 10am PST \| 1pm EST - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN09VTVU2QzRLNE0yVERQMklHSDBMUTJGWC4u)
    * Maturity Model Practitioners \| Tuesday, September 20th, 7am PST - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Sign up to [Share your story](https://aka.ms/share-your-story) in the [Learn from the community](https://aka.ms/LearnFromTheCommunity/ThisWeek) series.
* Request a Demo spot on the call \| <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call \| <https://aka.ms/spdev-spfx-call>

## Demo references

* **Building custom accordion Tabs experience with rich text experiences**
    * Sample - [Tab Accordion Web Part with Property Field Collection Data and tinyMCE for Rich Text Editing](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-accordion-with-richtext)
* **Using Microsoft Graph Profile API in SPFx for awards web part experience**
    * Documentation - [profile resource type](https://docs.microsoft.com/graph/api/resources/profile?view=graph-rest-beta)
    * Sample - [My Awards](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-graph-profile-awards)
* **Adaptive Cards Extensions strategy pattern for multi-action QuickView**
    * Sample - [ace-strategy-pattern](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/ace-strategy-pattern)
    * Wikipedia - [Strategy pattern](https://wikipedia.org/wiki/Strategy_pattern)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
SharePoint Framework (SPFx)|v1.14 GA, v1.15 RC|v1.16 preview late July/early August, v1.16 GA September
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v2.13 GA, v3.4.0 GA|v3.5 GA to be released July 8th, nightly builds
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v4.3.0 GA, v5.4.0 preview|
[Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)|v3.8.1, v2.9.0 (SPFx v1.11)|
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

* M365 General Dev call \| Thursday, July 7, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Office add-in monthly call \| Wednesday, July 13, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, July 14, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Adaptive Cards monthly call \| Thursday, July 14, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Power Platform monthly call \| Wednesday, July 20, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, July 21, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Microsoft 365 platform call \| Tuesday, September 6, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)

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

*Microsoft 365 PnP team, Microsoft - 1st of July 2022*

{{< attachments >}}
