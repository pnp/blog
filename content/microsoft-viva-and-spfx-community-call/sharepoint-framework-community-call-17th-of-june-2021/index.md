---
title: "SharePoint Framework Community Call -- 17th of June, 2021"
date: 2021-06-18T12:58:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
tags: []
type: "regular"
---


SharePoint Framework Special Interest Group (SIG) bi-weekly community
call recording from June 17th is now available from the Microsoft 365
Community YouTube channel at <https://aka.ms/m365pnp-videos>. You can use
SharePoint Framework for building solutions for **Microsoft Teams** and
for **SharePoint** Online.

## Call summary


Summer break and community call schedule updates reviewed.  Register now
for June trainings on
[Sharing-is-caring](https://pnp.github.io/sharing-is-caring/).  You are
invited to join the [Viva Connections private
preview](https://aka.ms/viva/connections/preview/register)!    Update on
SharePoint Framework v1.13.0 features -- extensibility options with Viva
Connections, Teams improvements, tooling updates, Store modernization
and more.   Released **PnPjs for Client-side Libraries** v2.6.0, **CLI
for Microsoft 365** v3.11.0 Beta, and **PnP Modern Search** v4.2.3 &
v3.20.0.   [Microsoft Teams Toolkit for Visual Studio & Visual Studio
Code](https://aka.ms/teams-toolkit) now available for preview.    
There were four **PnP SPFx samples** (2 extensions and 2 web parts)
delivered in last 2 weeks.  Great work!   
**Latest project updates include: ** (**Bold** indicates update from
previous report 2 weeks ago) 

  **PnP Project**                         **Current version**                          **Release/Status**
  SharePoint Framework (SPFx)             v1.12.1                                      v1.13.0 Preview in summer
  PnPjs Client-Side Libraries             **v2.6.0**                                   v3.0.0 developments underway
  CLI for Microsoft 365                   **v3.11.0 Beta**                             v3.10.0 preview released
  Reusable SPFx React Controls            v2.7.0 (SPFx v1.11), v3.1.0 (SPFx v1.12.1)    
  Reusable SPFx React Property Controls   v2.6.0 (SPFx v1.11), v3.1.0 (SPFx v1.12.1)    
  PnP SPFx Generator                      v1.16.0                                      Angular 11 support
  PnP Modern Search                       **v4.2.3 & v3.20.0**                          

The host of this call is [Vesa Juvonen](https://twitter.com/vesajuvonen)
(Microsoft) @vesajuvonen.  Q&A takes place in chat throughout the call.

## Actions





-   Join on the Viva Connections private preview! |
    [aka.ms/viva/connections/preview/register](https://aka.ms/viva/connections/preview/register)
-   Feedback wanted:  [Microsoft Teams Toolkit for Visual Studio &
    Visual Studio Code](https://aka.ms/teams-toolkit) now available for
    preview. 
    -   Tools - <https://aka.ms/teams-toolkit>
    -   Support -- StackOverflow - #TeamsToolkit
    -   Feedback -- <https://github.com/Officeev/TeamsFx/Issues>
-   Register for Sharing is Caring Events:
    -   First Time Contributor Session -- [June
        29th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session -- [June
        23rd](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
         
    -   PnP -- SPFx Developer Workstation Setup -- July  
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [June
        24th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   Ask Me Anything -- Teams Dev - July
    -   First Time Presenter -- [June
        30th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- July
    -   Maturity Model Practitioners -- July
    -   PnP Office Hours -- 1:1 session -
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    -   PnP Buddy System - [Request a
        Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
-   Download the recurrent invite for this call
    -- <https://aka.ms/spdev-spfx-call>

## Demos

-   **spfx-fast-serve: faster SharePoint Framework development** -- a
    spfx command line utility, that accelerates SPFx development by
    modifying your SPFx project to run a serve command immediately upon
    Save.   Reduces SPFx build pipeline rebuild/reload time from \>7 to
    \<1 second by applying updates only changes rather than rebuilding
    entire project.   Install CLI, spfx-fast-serve then apply fast-serve
    to your SPFx project.  Presenter shows/explains project file
    modifications.   Recently added hot model replacement (HMR)
    feature. 

-   **Building team time zone assistant Teams solution with SPFx v1.13,
    including Viva Connections Card** -- a Team Time Clock app shown as
    Teams app, Personal app and Viva Dashboard Card (SPFx web part +
    Adaptive Card extension).  On Card, see high level information
    (people and time) and deep link into Teams to schedule meeting
    experience.  Based on when people prefer to meet (green times),
    select time by aligning green fields in time slot.  Full code
    walkthrough, many features.    
**Topic:**

-   **Microsoft Teams Toolkit for Visual Studio & Visual Studio Code now
    available for preview**.   

    Did you know a feature in this latest version of the Teams Toolkit
    is the SPFx dev experience is truly integrated into this Toolkit? 
    Of course, the build decision is largely a UX hosting decision. 
    TypeScript devs, will prefer SPFx/M365 hosting while ISVs will
    gravitate to Azure for external hosting Please share feedback on
    your SPFx development experience in Teams Toolkit v2.0. 



**SPFx extension samples:  (<https://aka.ms/spfx-extensions>)**



-   [**Copy PnP search results web part
    settings**](https://github.com/pnp/sp-dev-fx-extensions/tree/main/samples/react-command-copy-pnp-search-webpart-settings) -
    [Anoop Tatti](https://twitter.com/anooptells) | @anooptells
-   [**Follow
    Documents**](https://github.com/pnp/sp-dev-fx-extensions/tree/main/samples/react-command-follow-document) -
    [André
    Lage](https://twitter.com/aaclage) | @aaclage
-    

**SPFx web part samples:  (<https://aka.ms/spfx-webparts>)**

-   **[Remote Event Receiver
    Manager](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-remote-event-receiver-manager)** -
    [Dan Toft](https://twitter.com/tanddant) | @tanddant
-   **[Carousel](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-carousel)** -
    [Giuliano De
    Luca](https://twitter.com/delucagiulian) | @delucagiulian

Thank you for your great work.  Samples are often showcased in Demos. 
  
## Agenda items

-   Latest updates on SharePoint Framework - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen -- [6:36](https://youtu.be/NyZP1oso8Mg?t=396)
-   PnPjs Client-Side Libraries - [Julie
    Turner](https://twitter.com/jfj1997) (Sympraxis Consulting) |
    @jfj1997 -- [8:47](https://youtu.be/NyZP1oso8Mg?t=527)
-   CLI for Microsoft 365 - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen -- [10:34](https://youtu.be/NyZP1oso8Mg?t=634)
-   PnP SPFx Controls - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen -- [11:54](https://youtu.be/NyZP1oso8Mg?t=714)
-   PnP Modern Search - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen -- [12:56](https://youtu.be/NyZP1oso8Mg?t=776)
-   PnP SPFx Samples - [Hugo
    Bernier](https://twitter.com/bernierh) (Tahoe Ninjas) |
    @bernierh -- [14:03](https://youtu.be/NyZP1oso8Mg?t=843)
-   Topic:  Microsoft Teams Toolkit v2.0 - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen -- [52:48](https://youtu.be/NyZP1oso8Mg?t=3168) 

## Demos

-   **Demo:**  spfx-fast-serve: faster SharePoint Framework development
    -- [Sergei Sergeev](https://twitter.com/sergeev_srg) (Mastaq) |
    @sergeev_srg - [17:42](https://youtu.be/NyZP1oso8Mg?t=1062)
-   **Demo:**  Building team time zone assistant Teams solution with
    SPFx v1.13, including Viva Connections Card -- [Julie
    Turner](https://twitter.com/jfj1997) (Sympraxis Consulting) |
    @jfj1997 & [Derek Cash-Peterson](https://twitter.com/spdcp) |
    @spdcp - [31:22](https://youtu.be/NyZP1oso8Mg?t=1882)


## Resources

Additional resources around the covered topics and links from the
slides.

-   Repo - [SPFx Fast Serve
    Tool](https://github.com/s-KaiNet/spfx-fast-serve) 

-   Article - [hTWOo v0.3.0 released -- Teams Splash Cards, Placeholder
    and demo](https://n8d.at/htwoo-v0-3-0-release) 

-   Tool - [ABOUT HTWOO UI](http://my.n8d.at/hTWOo) 

-   Tools - <https://aka.ms/teams-toolkit>

-   Register - [Register for Viva Connections developer platform updates
    and private Beta](https://aka.ms/viva/connections/preview/register) 

-   Viva Connections <https://aka.ms/VivaConnections>

-   PnP Weekly -- Episode 131 [Vesa
    Juvonen ](https://twitter.com/vesajuvonen)(Microsoft) |
    @vesajuvonen, [Waldek
    Mastykarz](https://twitter.com/waldekm) (Microsoft) | @waldekm were
    joined by Senior Program Manager - Zhenya Savchenko (Microsoft),
    from the Developer Division of Visual Studio group to talk about
    new [Microsoft Teams Toolkit v2 extension for Visual Studio
    Code](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension).
    |
    [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-131/ba-p/2445655)
    |
    [podcast](https://pnpweekly.podbean.com/e/Microsoft-365-pnp-weekly-episode-131-14th-of-June-2021/)

## General resources

-   Gallery - [Microsoft 365 Extensibility look book
    gallery](https://aka.ms/m365/extensibility)   
-   [Microsoft Build sessions
    guide](https://aka.ms/modernworkbuildsessions) (Modern Work Digital
    Brochure) - aka.ms/modernworkbuildsessions
-   SharePoint Framework - v1.12.1 npm install
    --g [@microsoft](https://techcommunity.microsoft.comhttps://techcommunity.microsoft.com/t5/user/viewprofilepage/user-id/41501)/generator-sharepoint@next
-   [CLI for Microsoft 365
    v3](https://developer.microsoft.com/office/blogs/cli-microsoft-365-3/)
-   [CodeTour](https://aka.ms/codetour)
-   [Sharing is Caring](https://aka.ms/sharing-is-caring) |
    aka.ms/sharing-is-caring
-   [Tools - ](https://aka.ms/pnp-search)[PnP Modern Search
    v4](https://microsoft-search.github.io/pnp-modern-search/)[ 
    | ](https://aka.ms/pnp-search)<https://aka.ms/pnp-search>
-   [M365 PnP site](https://aka.ms/m365pnp) | aka.ms/m365pnp
-   [SharePoint Starter Kit
    v2](https://github.com/pnp/sp-starter-kit/tree/v2)
-   Blog: "[A Lap Around Microsoft Graph Toolkit" blog
    series](https://aka.ms/mgtLap)
-   [New Microsoft 365 Patterns and Practices (PnP) team model with new
    community
    leads](https://developer.microsoft.com/microsoft-365/blogs/new-microsoft-365-patterns-and-practices-pnp-team-model-with-new-community-leads/)
-   [Microsoft 365 Community
    Content](https://aka.ms/m365-community-docs) (non-Dev docs)
-   [PnP SPFx web part samples](https://aka.ms/spfx-webparts)
-   [PnP SPFx extension samples](https://aka.ms/spfx-extensions)
-   [GitHub PnPjs](https://github.com/pnp/pnpjs/)
-   Tutorials - [Getting started with SharePoint Framework v1.10
    Tutorials](https://www.youtube.com/playlist?list=PLR9nK3mnD-OXvSWvS2zglCzz4iplhVrKq) (12
    videos)
-   Tutorials - [Getting started with SharePoint Framework v1.10
    Extensions](https://www.youtube.com/playlist?list=PLR9nK3mnD-OXtWO5AIIr7nCR3sWutACpV) (6
    videos)
-   Docs - [Tutorials and training material for SharePoint
    Development](https://docs.microsoft.com/sharepoint/dev/training/training/?wt.mc_id=YT_CCrecording)
-   [SPFX Training Package](https://aka.ms/spfx-training)
-   [SPFx Web Parts](https://aka.ms/spfx-webparts)
-   [SPFx Extensions](https://aka.ms/spfx-extensions)
-   [SPFx Library Components](https://aka.ms/spfx-library-components)
-   Documentation - [PnPjs v2
    documentation](https://pnp.github.io/pnpjs/)
-   Link - [Microsoft 365 developer
    training](https://aka.ms/M365DevTraining)
-   Link - [Office 365 Developer Program](https://aka.ms/O365DevProgram)
-   [Latest documentation on SharePoint
    Framework](https://aka.ms/spdev-docs)
-   Found an issue with SharePoint Dev? - please let us know
    at <https://aka.ms/spdev-issues>
-   [Reusable web part property
    controls](https://sharepoint.github.io/sp-dev-fx-property-controls/)
-   [Reusable react controls for SharePoint Framework
    solutions](https://sharepoint.github.io/sp-dev-fx-controls-react/)
-   [Reusable controls
    webcast](https://devblogs.microsoft.com/microsoft365dev/webcast-reusable-controls-for-your-sharepoint-framework-solutions/)
-   [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365)
-   [PnP SPFx Yeoman Generator](https://github.com/pnp/generator-spfx) -
    Extends the out-of-the-box experience with open-source community
    capabilities
-   [SharePoint Dev UserVoice](https://aka.ms/spdev-uservoice) - for new
    feature requests

## Other topics mentioned

-   [SharePoint dev
    documentation](https://docs.microsoft.com/sharepoint/dev/)
-   [SharePoint dev issue
    list](https://github.com/SharePoint/sp-dev-docs/issues)


## Upcoming Calls | Recurrent Invites

-   **M365 General Dev call** -- June 24th at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **SharePoint Framework call** -- July 1**st**at 7:00 am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **Office add-in monthly call --** July 14th at 8:00 am PDT |
    [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscommunitycall)
-   **Adaptive Cards monthly call --** July 8th at 9:00 am PDT |
    <https://aka.ms/adaptivecardscommunitycall>
-   **Microsoft Identity Platform --** July 15th at 9:00 am PDT |
    <https://aka.ms/IDDevCommunityCalendar>
-   **Power Apps monthly call --** July[
    21]st[ at 8:00 am PDT |
    ]<https://aka.ms/PowerAppsMonthlyCall>
PnP SharePoint Framework Special Interest Group bi-weekly calls are
targeted at anyone who is interested in the JavaScript-based development
towards Microsoft Teams, SharePoint Online, and also on-premises. SIG
calls are used for the following objectives.

-   SharePoint Framework engineering update from Microsoft
-   Talk about PnP JavaScript Core libraries
-   CLI for Microsoft 365 Updates
-   SPFx reusable controls
-   PnP SPFx Yeoman generator
-   Share code samples and best practices
-   Possible engineering asks for the field - input, feedback, and
    suggestions
-   Cover any open questions on the client-side development
-   Demonstrate SharePoint Framework in practice in Microsoft Teams or
    SharePoint context
-   You can download a recurrent invite
    from <https://aka.ms/spdev-spfx-call>. Welcome and join the
    discussion!

*"Sharing is caring"*

------------------------------------------------------------------------

*Microsoft 365 PnP team, Microsoft - 18th of June 2021*
