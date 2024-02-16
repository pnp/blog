---
title: "SharePoint Framework Community Call -- 20th of May, 2021"
date: 2021-05-21T02:44:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
tags: []
type: "regular"
---


SharePoint Framework Special Interest Group (SIG) bi-weekly community
call recording from May 20th is now available from the Microsoft 365
Community YouTube channel at <https://aka.ms/m365pnp-videos>. You can use
SharePoint Framework for building solutions for **Microsoft Teams** and
for **SharePoint** Online.

## Call summary


Preview the new [Microsoft 365 Extensibility look book
gallery](https://aka.ms/m365/extensibility) co-developed by Microsoft
Teams and SharePoint engineering.   Register now for May/June trainings
on [Sharing-is-caring](https://pnp.github.io/sharing-is-caring/).  View
the [Microsoft Build sessions
guide](https://aka.ms/modernworkbuildsessions) (Modern Work Digital
Brochure) -- Keynotes, breakouts, on-demand, roundtables and 1:1
consultations.  PnPjs Client-Side Libraries v2.5.0 GA and CLI for
Microsoft 365 v3.10.0 preview were released this month.   Also latest
updates on SPFx roadmap (v1.13.0 Preview in summer) and Viva Connections
extensibility shared.   
Four new/updated **PnP SPFx web part samples delivered** in last 2
weeks.  Great work!   
**Latest project updates include: ** (**Bold** indicates update from
previous report 2 weeks ago) 

  **PnP Project**                         **Current version**   **Release/Status**
  SharePoint Framework (SPFx)             v1.12.1               **v1.13.0 Preview in summer**
  PnPjs Client-Side Libraries             **v2.5.0**            **v3.0.0 developments underway**
  CLI for Microsoft 365                   v3.9.0                **v3.10.0 preview released**
  Reusable SPFx React Controls            v2.7.0, v3.1.0        v2.7.0 (SPFx v1.11), v3.1.0 (SPFx v1.12.1)
  Reusable SPFx React Property Controls   v2.6.0, v3.1.0        v2.6.0 (SPFx v1.11), v3.1.0 (SPFx v1.12.1)
  PnP SPFx Generator                      v1.16.0               Angular 11 support
  PnP Modern Search                       v3.19 and v4.1.0      April and March 20th

The host of this call is [Patrick
Rodgers](https://twitter.com/mediocrebowler) (Microsoft)
@mediocrebowler.  Q&A takes place in chat throughout the call.

## Actions





-   Register for Sharing is Caring Events:
    -   First Time Contributor Session -- [May
        24th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session
        -- [May](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    -   PnP -- SPFx Developer Workstation Setup -- June 
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [May
        20th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   AMA (Ask Me Anything) -- Microsoft Graph & MGT -- [June
        8th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xCOEtTWFJSREg2UFY2NkpPUk5GNk9YVS4u)
    -   AMA (Ask Me Anything) -- Microsoft Teams Dev - June
    -   First Time Presenter -- [May
        25th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- [May
        27th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
         
    -   Maturity Model Practitioners -- [May
        18th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    -   PnP Office Hours -- 1:1 session -
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
-   Download the recurrent invite for this call
    -- <https://aka.ms/spdev-spfx-call>

## Demos

1.  **Using Microsoft Graph Toolkit to easily access files in Sites and
    in OneDrive** -- a.k.a. OneDrive finder - find and explore
    OneDrives, folders and files using Microsoft Graph Toolkit.  Use
    Graph queries to get hostname, Sites on hostname, OneDrive item-id,
    and Sites Root item-id.  Use 2 beta controls from MGT for search --
    Mgt-File-List and MGT-File.  Refine search results by file
    extension, items on page, etc.  Display style -- light/dark mode. 
    Recommendations on managing file list cache and permissions.   

2.  **Building Microsoft Teams user bulk membership update tool with
    SPFx and Microsoft Graph** -- a.k.a. the Teams Membership Updater
    tool -- a web part for Teams' site owners that pulls member updates
    from a selected CSV file.  Upon load, the web part calls Graph to
    pull the list of Teams you are a member/owner.   Uses Graph batch
    functions to remove orphaned members and then to add new members. 
     Uses SPFx Reusable controls and react-papaparse.  

3.  **Building Microsoft Graph get client web part with latest Graph
    Client SDK** -- use Microsoft Graph Toolkit SharePoint provider to
    access and leverage new functionality of Graph JS SDK in SPFx.  Web
    part sample developed using React Framework that showcases how to
    use the latest microsoft-graph-client in SPFx.  The client enables
    throttling management (no 429s), Chaos management, uses latest
    types, getting RAW responses from API, Content-Type is already set
    for PUT, and a lot more!



**SPFx extension samples:**
*


**SPFx web part samples:**
<https://aka.ms/spfx-webparts>


-   [**List Items Menu (SP2019
    Version)**](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-list-items-menu-sp2019) -
    [João
    Mendes](https://twitter.com/joaojmendes) | [joaojmendes](https://github.com/joaojmendes)
-   **[News
    Banner](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-news-banner)** -
    [João
    Mendes](https://twitter.com/joaojmendes) | [joaojmendes](https://github.com/joaojmendes)
-   **[List
    Form](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-list-form)** -
    Ari Gunawan | AriGunawan
-   **[Calendar](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-calendar)** -
    [Eli H. Schei](https://twitter.com/acupof_dev) | @acupof_dev


-   **NEW Issue Templates!**

Thank you for your great work.  Samples are often showcased in Demos. 
  
## Agenda items

-   Latest updates on SharePoint Framework - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen -- [5:38](https://youtu.be/cAwKgUNR9jU?t=338)
-   PnPjs Client-Side Libraries - [Julie
    Turner](https://twitter.com/jfj1997) (Sympraxis Consulting) |
    @jfj1997 -- [9:27](https://youtu.be/cAwKgUNR9jU?t=567)
-   CLI for Microsoft 365 - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [11:29](https://youtu.be/cAwKgUNR9jU?t=689)
-   PnP SPFx Controls - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [12:28](https://youtu.be/cAwKgUNR9jU?t=748)
-   PnP Modern Search - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [13:24](https://youtu.be/cAwKgUNR9jU?t=804)
-   PnP SPFx Samples - [Hugo
    Bernier](https://twitter.com/bernierh) (Tahoe Ninjas) |
    @bernierh -- [14:30](https://youtu.be/cAwKgUNR9jU?t=870)

## Demos

-   **Demo:**  Using Microsoft Graph Toolkit to easily access files in
    Sites and in OneDrive -- [André Lage](https://twitter.com/aaclage)
    (Datalynx AG) | @aaclage [--
    [18:27](https://youtu.be/cAwKgUNR9jU?t=1107)]

    **Demo:**  Building Microsoft Teams user bulk membership update tool
    with SPFx and Microsoft Graph -- [Nick
    Brown](https://twitter.com/techienickb) (Cardiff University) |
    @techienickb [--
    [34:06](https://youtu.be/cAwKgUNR9jU?t=2046)]

    **Demo:**  Building Microsoft Graph get client web part with latest
    Graph Client SDK -- [Sébastien
    Levert](https://twitter.com/sebastienlevert) (Microsoft) |
    @sebastienlevert [
    --][ [47:30](https://youtu.be/cAwKgUNR9jU?t=2850)]



## Resources

Additional resources around the covered topics and links from the
slides.

-   [The presentation used for this community
    call](https://1drv.ms/p/s!AlposW7ozA_90ksbJaG1P1CIlwi2?e=iuz33z)

-   Article - [Navigate OneDrive data with Microsoft Graph and
    Mgt-File-List Beta
    version](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/navigate-onedrive-data-with-microsoft-graph-and-mgt-file-list/ba-p/2296730) 

-   Sample -- [OneDrive
    finder](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-onedrive-finder) 

-   Sample - [Teams Membership
    Updater](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-teams-membership-updater) 

-   Documentation - [Combine multiple requests in one HTTP call using
    JSON
    batching](https://learn.microsoft.com/graph/json-batching) 

-   Article - [Using the latest microsoft-graph-client in
    SPFx](https://www.sebastienlevert.com/2021/04/18/latest-microsoft-graph-client-spfx/) 

-   Library - [Microsoft Graph JavaScript Client
    Library](https://github.com/microsoftgraph/msgraph-sdk-javascript) 

-   Sample - [Graph MGT
    Client](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-graph-mgt-client) 

-   Gallery - [Microsoft 365 Extensibility look book
    gallery](https://aka.ms/m365/extensibility)   

-   PnP Weekly -- Episode 127 with MVP guest [Rick Van
    Rousselt](https://twitter.com/RickVanRousselt) (Advantive) |
    @RickVanRousselt |
    [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-127-rick-van-rousselt/ba-p/2361251)
    |
    [podcast](https://pnpweekly.podbean.com/e/Microsoft-365-pnp-weekly-episode-127-17th-of-may-2021/)

-   [Microsoft Build sessions
    guide](https://aka.ms/modernworkbuildsessions) (Modern Work Digital
    Brochure) - aka.ms/modernworkbuildsessions

## General resources

-   Viva Connections <https://aka.ms/VivaConnections> 
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
    Development](https://learn.microsoft.com/sharepoint/dev/training/training/?wt.mc_id=YT_CCrecording)
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
    documentation](https://learn.microsoft.com/sharepoint/dev/)
-   [SharePoint dev issue
    list](https://github.com/SharePoint/sp-dev-docs/issues)


## Upcoming Calls | Recurrent Invites

-   **M365 General Dev call --** May 27th at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Microsoft Graph call --** June 1st at 8:00 am PDT |
    <https://aka.ms/microsoftgraphcall>
-   **SharePoint Framework call** -- June 3rd at 7:00 am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **SharePoint monthly call --** June 8th at 8:00am PDT |
    <https://aka.ms/sp-call>
-   **Office add-in monthly call --** June 9th at 8:00 am PDT |
    [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscommunitycall)
-   **Adaptive Cards monthly call --** June 10th at 9:00 am PDT |
    <https://aka.ms/adaptivecardscommunitycall>
-   **Microsoft Teams monthly call --** June 15th at 8:00 am PDT |
    <https://aka.ms/microsoftteamscommunitycall>
-   **Power Apps monthly call --** June 16th at 8:00 am PDT |
    <https://aka.ms/PowerAppsMonthlyCall>
-   **Microsoft Identity Platform --** June 17th at 9:00 am PDT
    |<https://aka.ms/IDDevCommunityCalendar> 
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

*Microsoft 365 PnP team, Microsoft - 21st of May 2021*
