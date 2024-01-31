---
title: "SharePoint Framework Community Call Recording -- 6th of May, 2021"
date: 2021-05-07T12:41:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
tags: []
type: "regular"
---


SharePoint Framework Special Interest Group (SIG) bi-weekly community
call recording from May 6th is now available from the Microsoft 365
Community YouTube channel at <https://aka.ms/m365pnp-videos>. You can use
SharePoint Framework for building solutions for **Microsoft Teams** and
for **SharePoint** Online.

 

## Call summary


Preview the new [Microsoft 365 Extensibility look book
gallery](https://aka.ms/m365/extensibility) co-developed by Microsoft
Teams and SharePoint engineering.  Download showcase apps, samples, and
documentation.   Register now for May trainings on
[Sharing-is-caring](https://pnp.github.io/sharing-is-caring/)  New
releases in this call -- CLI for Microsoft 365 v3.9.0, Reusable SPFx
React Controls v3.1.0 and Property Controls v3.1.0 and SharePoint
Framework v1.12.1. Also, a look at what's ahead for SPFx - Microsoft
Viva Connections, Teams improvements, tooling updates, and Store
modernization. 
There were six **PnP SPFx samples** delivered in last 2 weeks, details
below.  Great work!    
**Latest project updates include: ** (**Bold** indicates update from
previous report 2 weeks ago) 

  **PnP Project**                         **Current version**   **Release/Status**
  SharePoint Framework (SPFx)             **v1.12.1 **          **GA** 
  PnPjs Client-Side Libraries             v2.4.0                **v2.5.0 scheduled for May 14th**
  CLI for Microsoft 365                   **v3.9.0**            **Upgrading SPFx projects to v1.12.1**
  Reusable SPFx React Controls            **v3.1.0**            **v2.7.0 (SPFx v1.11), v3.1.0 (SPFx v1.12.1)**
  Reusable SPFx React Property Controls   **v3.1.0**            **v2.6.0 (SPFx v1.11), v3.1.0 (SPFx v1.12.1)**
  PnP SPFx Generator                      v1.16.0               Angular 11 support
  PnP Modern Search                       v3.19 and v4.1.0      April and March 20th

The host of this call is [Patrick
Rodgers](https://twitter.com/mediocrebowler) (Microsoft)
@mediocrebowler.  Q&A takes place in chat throughout the call.

## Actions





-   Reserve date - SharePoint Monthly community call -- 11th of May 8
    AM PDT | <https://aka.ms/sp-call>
-   Register for Sharing is Caring Events:
    -   First Time Contributor Session -- [May
        24th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session
        -- [May](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    -   PnP -- SPFx Developer Workstation Setup -- [May
        13th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
         
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [May
        20th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   AMA (Ask Me Anything) -- Tech Community -- [May
        11th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQlpKUUlUUUtFR1VTSUxUVzI3NUs5SzhNWC4u)
    -   AMA (Ask Me Anything) -- Microsoft Graph & MGT - June
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

1.  **Adding support to add video with a text to modern pages with this
    video banner web part** -- from the Properties Pane, select a video,
    add banner title text and color it, adjust video brightness and
    banner height.  This elegantly coded modern web part was built with
    SPFx using standard PnP property pane controls in less than 3
    hours.   Add the web part to top of your pages.   The web part has
    only one functional component named: VideoBackground. 

2.  **Building company stories web part for story experience** -- this
    web part allows you to add images to a SharePoint List, and renders
    (cycles) them with related text on page similar to Instagram Stories
    as a way to engage social media adept employees. Text, images, and
    author details stored in a SharePoint list.   Uses an existing
    open-source React component called "*react-insta-stories*" and
    several Microsoft Graph Toolkit components.  Sample in PnP Samples
    repository.   

3.  **Building react groups and teams web part for aggregating detailed
    information for end users** -- this web part helps logged-in user
    quickly find their Microsoft Teams and Microsoft 365 Groups
    sites/content.  For selected site, options to go to site, mail,
    calendar, or Planner.  Match site color theme with one click. 
    Filter by public, private or all Groups/Teams.   The main React
    component is MicrosoftGroups.tsx.   A brilliant code walk-through by
    first time presenter Alison Collins. 



**SPFx extension samples:  (<https://aka.ms/spfx-extensions>)**



-   **[Print List Item Command View
    Set](https://github.com/pnp/sp-dev-fx-extensions/blob/main/samples/react-command-print)
    -** [Ari Gunawan](https://twitter.com/arigunawan3023)
    [| @arigunawan3023](https://github.com/pnp/sp-dev-fx-extensions/tree/master/samples/react-send-to-teams)

**SPFx web part samples:  (<https://aka.ms/spfx-webparts>)**


-   **[Teams Membership
    Updater](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-teams-membership-updater)
    -** [Nick Brown](https://twitter.com/techienickb) | @techienickb
-   **[OneDrive
    Finder](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-onedrive-finder)
    -** [André
    Lage](https://twitter.com/aaclage) | @aaclage
-   **[Organization
    Chart](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-organization-chart)
    -** [João
    Mendes](https://twitter.com/joaojmendes) | [joaojmendes](https://github.com/joaojmendes)
-   **[Remote Event Receiver
    Manager](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-remote-event-receiver-manager)
    -** [Dan Toft](https://twitter.com/tanddant) | @tanddant
-   **[All Microsoft 365 Groups and
    Teams](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-groups-teams)
    -** Alison Collins and [Sam
    Collins](https://twitter.com/Samc148) | @Samc148
Thank you for your great work.  Samples are often showcased in Demos. 
  
## Agenda items

-   Latest updates on SharePoint Framework - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen -- [5:24](https://youtu.be/yqz1HF72Guw?t=324)
-   PnPjs Client-Side Libraries - [Julie
    Turner](https://twitter.com/jfj1997) (Sympraxis Consulting) |
    @jfj1997 -- [7:49](https://youtu.be/yqz1HF72Guw?t=469)
-   CLI for Microsoft 365 - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [9:22](https://youtu.be/yqz1HF72Guw?t=562)
-   PnP SPFx Controls - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [10:27](https://youtu.be/yqz1HF72Guw?t=627)
-   PnP SPFx Generator - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [11:57](https://youtu.be/yqz1HF72Guw?t=717)
-   PnP SPFx Samples - [Hugo
    Bernier](https://twitter.com/bernierh) (Tahoe Ninjas) |
    @bernierh -- [12:18](https://youtu.be/yqz1HF72Guw?t=738)

## Demos

-   **Demo:**  Adding support to add video with a text to modern pages
    with this video banner web part -- [Mohamed
    Derhalli](https://twitter.com/MohamedDerhalli) (BDO Canada) |
    @MohamedDerhalli | Deck --
    [13:13](https://youtu.be/yqz1HF72Guw?t=793)

-   **Demo:**  Building company stories web part for story experience --
    [Luis Mañez](https://twitter.com/luismanez) (ClearPeople) |
    @luismanez | Deck -- [18:39](https://youtu.be/yqz1HF72Guw?t=1119)

-   **Demo:**  Building react groups and teams web part for aggregating
    detailed information for end users -- Alison Collins & [Sam
    Collins](https://twitter.com/samc148) (Coupled Technology) |
    @samc148 | Deck -- [29:39](https://youtu.be/yqz1HF72Guw?t=1779)


## Resources

Additional resources around the covered topics and links from the
slides.

-   [The presentation used for this community
    call](https://1drv.ms/p/s!AlposW7ozA_90kc5kQ_6Kxc592_s?e=hgy03Y)

-   Blog post - [Introducing React Video Banner Web
    Part](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/introducing-react-video-banner-web-part/ba-p/2329002) 

-   Repo - [Video
    Banner](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-video-banner) 

-   Blog post - [Community sample: Engage your users with SharePoint
    stories/reels](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/community-sample-engage-your-users-with-sharepoint-stories-reels/ba-p/2325128) 

-   Repo - [Company Stories
    Webpart](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-company-stories) 

-   Alison's Blog:  [Graphgod ](https://graphgod.dev/)

-   Repo - [All Microsoft 365 Groups and Teams with
    SPFx](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-groups-teams) 

-   Framework - v1.12.1 npm install
    --g [@microsoft](https://techcommunity.microsoft.comhttps://techcommunity.microsoft.com/t5/user/viewprofilepage/user-id/41501)/generator-sharepoint@next

-   Gallery - [Microsoft 365 Extensibility look book
    gallery](https://aka.ms/m365/extensibility)   

-   PnP Weekly -- Episode 125 with Business Applications MVP guest
    [Sandy Ussia](https://twitter.com/SandyU) (Lightning Tools ) |
    @SandyU |
    [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-125/ba-p/2318240)
    |
    [podcast](https://pnpweekly.podbean.com/e/Microsoft-365-pnp-weekly-episode-125-3rd-of-may-2021/)

-   Viva Connections <https://aka.ms/VivaConnections> 

## General resources

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

-   **SharePoint monthly call --** May 11th at 8:00am PDT |
    <https://aka.ms/sp-call>
-   **Microsoft Graph call --** June 1st at 8:00 am PDT |
    <https://aka.ms/microsoftgraphcall>
-   **Office add-in monthly call --** May 12th at 8:00 am PDT |
    [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscommunitycall)
-   **M365 General Dev call --** May 13th at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Adaptive Cards monthly call --** May 13th at 9:00 am PDT |
    <https://aka.ms/adaptivecardscommunitycall>
-   **Microsoft Teams monthly call --** May 18th at 8:00 am PDT |
    <https://aka.ms/microsoftteamscommunitycall>
-   **Power Apps monthly call --** May 19th at 8:00 am PDT |
    <https://aka.ms/PowerAppsMonthlyCall>
-   **SharePoint Framework call** -- May 20th at 7:00 am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **Microsoft Identity Platform --** May 20th at 9:00 am PDT |
    <https://aka.ms/IDDevCommunityCalendar> 
-   **Microsoft Graph call --** June 1st at 8:00 am PDT |
    <https://aka.ms/microsoftgraphcall>
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

*Microsoft 365 PnP team, Microsoft - 7th of May 2021*
