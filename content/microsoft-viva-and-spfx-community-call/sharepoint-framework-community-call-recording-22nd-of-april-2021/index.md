---
title: "SharePoint Framework Community Call Recording -- 22nd of April, 2021"
date: 2021-04-23T02:30:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
tags: []
type: "regular"
---


SharePoint Framework Special Interest Group (SIG) bi-weekly community
call recording from April 22nd is now available from the Microsoft 365
Community YouTube channel at <https://aka.ms/m365pnp-videos>. You can use
SharePoint Framework for building solutions for **Microsoft Teams** and
for **SharePoint** Online.

## Call summary


Preview the new [Microsoft 365 Extensibility look book
gallery](https://aka.ms/m365/extensibility) co-developed by Microsoft
Teams and SharePoint engineering.  Download showcase apps, samples, and
documentation.   Register now for April trainings on
[Sharing-is-caring](https://pnp.github.io/sharing-is-caring/).  Give us
feedback, the [Microsoft 365 developer community
survey](https://aka.ms/m365pnp/survey) is now open.  Announcing public
preview of SharePoint Framework 1.12.1.
There were six **PnP SPFx web part samples** delivered in last 2 weeks. 
Great work!    
**Latest project updates include: **
  --------------------------------------- --------------------- -----------------------------------------
  **PnP Project**                         **Current version**   **Release/Status**
  SharePoint Framework (SPFx)             v1.12.1 (beta)        GA by end-of-April
  PnPjs Client-Side Libraries             v2.4.0                April 9th
  CLI for Microsoft 365                   v3.9 (beta)           Upgrading SPFx projects to v1.12.1-rc.2
  Reusable SPFx React Controls            v2.6.0                v3.0.0 when SPFx v1.12.1 GA
  Reusable SPFx React Property Controls   v2.5.0                v3.0.0 when SPFx v1.12.1 GA
  PnP SPFx Generator                      v1.16.0                
  PnP Modern Search                       v3.19 and v4.1.0      April and March 20th
  --------------------------------------- --------------------- -----------------------------------------
The host of this call is [Patrick
Rodgers](https://twitter.com/mediocrebowler) (Microsoft)
@mediocrebowler.  Q&A takes place in chat throughout the call.

## Actions


-   Complete the Microsoft 365 Developer Community Survey --
    <https://aka.ms/m365pnp/survey>
-   Reserve date - SharePoint Monthly community call - 13th of April 8
    AM PDT | <https://aka.ms/sp-call>
-   Register for Sharing is Caring Events:
    -   First Time Contributor Session -- [April
        27th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)  
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session
        -- [April](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    -   PnP -- SPFx Developer Workstation Setup -- [April
        29th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- May TBD
    -   AMA (Ask Me Anything) -- Power Platform Samples -- [May
        5th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMUIxSldXNDdTOFJWTENSTTM0QlBLWUM3NS4u)
    -   AMA (Ask Me Anything) -- Tech Community -- [May
        11th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQlpKUUlUUUtFR1VTSUxUVzI3NUs5SzhNWC4u)
    -   First Time Presenter -- May TBD
    -   More than Code with VSCode -- [April
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
    -   Maturity Model Practitioners -- May TBD
    -   PnP Office Hours -- 1:1 session -
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
-   Download the recurrent invite for this call
    -- <https://aka.ms/spdev-spfx-call>

## Demos

1.  **Running the CLI for Microsoft 365 in Azure Container Instances
    orchestrated by Logic Apps** -- or Flow in Power Automate.  Step
    through how the Azure Container Instance is created with the
    specified managed identity.  Docker enables you to bundle a
    pre-configured version of CLI for Microsoft 365 together with all
    its required dependencies and also is used to orchestrate
    containers.   Purpose of configuration is to run scripts or reports
    against your tenant.

2.  **Advanced Page Properties web part solution** -- when the normal
    page properties web part is not enough, this new Advanced Page
    Properties web part delivers more.  New properties supporting theme
    variants, capsule format for list options, support for image fields,
    for links, for currency, and for dates.  Tour the code for tracking
    available properties for drop downs, tracking property selections
    and parameters for refreshing and rendering the data. 

3.  **SharePoint Framework 1.12.1 new features** -- support for Node
    v12, Gulp 4, Microsoft Teams SDK v1.8 and for creating Microsoft
    Teams meeting apps.  Demos -- 1) Increased access to page structure
    and context to avoid DOM dependency (web part detects DOM structure
    and selects output size to fit allotted space) and 2) SPFx support
    for Complex Microsoft Teams solutions (manifest included in Package
    to synchronize with Teams App catalog).



**SPFx extension samples:  (<https://aka.ms/spfx-extensions>)**


-   [News
    Ticker](https://github.com/pnp/sp-dev-fx-extensions/tree/master/samples/react-send-to-teams)
    [-](https://github.com/pnp/sp-dev-fx-extensions/tree/master/samples/react-send-to-teams)
    [Ari Gunawan](https://twitter.com/arigunawan)
    [| @arigunawan](https://github.com/pnp/sp-dev-fx-extensions/tree/master/samples/react-send-to-teams)

**SPFx web part samples:  (<https://aka.ms/spfx-webparts>)**


-   [Data Table](https://github.com/pnp/sp-dev-fx-webparts/pull/1818) -
    [Chandani
    Prajapati](https://twitter.com/Chandani_SPD) | @Chandani_SPD
-   [Staff
    Directory](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-staffdirectory) -
    Tristian O'Brien
-   [OneDrive
    Finder](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-onedrive-finder) -
    [André
    Lage](https://twitter.com/aaclage) | @aaclage
-   [Graph MGT
    Client](https://github.com/pnp/sp-dev-fx-webparts/blob/master/samples/react-graph-mgt-client) -
    [Sébastien
    Levert](https://twitter.com/sebastienlevert) | [sebastienlevert](https://github.com/sebastienlevert)
-   [Teams Membership
    Updater](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-teams-membership-updater) -
    [Nick Brown](https://twitter.com/techienickb) | @techienickb
Thank you for your great work.  Samples are often showcased in Demos. 
  
## Agenda items

-   Latest updates on SharePoint Framework - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen -- [6:25](https://youtu.be/08UBXLU-g04?t=385)
-   PnPjs Client-Side Libraries - [Julie
    Turner](https://twitter.com/jfj1997) (Sympraxis Consulting) |
    @jfj1997 -- [8:07](https://youtu.be/08UBXLU-g04?t=487)
-   CLI for Microsoft 365 - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [10:20](https://youtu.be/08UBXLU-g04?t=620)
-   PnP SPFx Controls - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [11:34](https://youtu.be/08UBXLU-g04?t=694)
-   PnP Modern Search - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [12:49](https://youtu.be/08UBXLU-g04?t=769)
-   PnP SPFx Samples - [Hugo
    Bernier](https://twitter.com/bernierh) (Tahoe Ninjas) |
    @bernierh -- [13:57](https://youtu.be/08UBXLU-g04?t=837)

## Demos

-   Running the CLI for Microsoft 365 in Azure Container Instances
    orchestrated by Logic Apps -- [Albert-Jan
    Schot](https://twitter.com/appieschot) (Portiva) | @appieschot |
    [deck](https://1drv.ms/p/s!AlposW7ozA_90kWX8lhXVWx2QXGF?e=VogeNR) [--][ [18:04](https://youtu.be/08UBXLU-g04?t=1084)]

-   Advanced Page Properties web part solution -- [Mike
    Homol](https://twitter.com/homol) (ThreeWill) | @homol |
    [deck](https://1drv.ms/p/s!AlposW7ozA_90kQb2NjM2sQAiEOu?e=q7eLpV) [--][ [32:00](https://youtu.be/08UBXLU-g04?t=1920)]

-   SharePoint Framework 1.12.1 new features -- [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen

    [
    --][ [45:33](https://youtu.be/08UBXLU-g04?t=2733)]


## Resources

Additional resources around the covered topics and links from the
slides.

-   [The presentation used for this community
    call](https://1drv.ms/p/s!AlposW7ozA_90kMrJvE87jh_s6n1?e=bsowBg)

-   Walkthrough - [Running the CLI for Microsoft 365 in an Azure
    Container
    Instance](https://www.cloudappie.nl/running-m365-cli-container-instances/) 

-   Tool - [CLI for Microsoft 365](https://aka.ms/cli-m365)

-   Docker Hub -
    [m365pnp/cli-microsoft365](https://hub.docker.com/r/m365pnp/cli-microsoft365) 

-   Blog - [Run CLI for Microsoft 365 in
    Docker](https://developer.microsoft.com/microsoft-365/blogs/run-cli-microsoft-365-in-docker/) 

-   Article - [Improving the Page Properties web
    part](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/improving-the-page-properties-web-part/ba-p/2256651) 

-   Repo - [Advanced Page
    Properties](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-advanced-page-properties) 

    Framework - v1.12.1 public preview \\ npm install --g
    @microsoft/generator-sharepoint@next

-   Gallery - [Microsoft 365 Extensibility look book
    gallery](https://aka.ms/m365/extensibility) |
    [aka.ms/m365/extensibility](https://aka.ms/m365/extensibility)  

-   PnP Weekly -- Episode 123 with guest Power Platform Cloud Advocate
    - [April Dunnam](https://twitter.com/aprildunnam) (Microsoft)
    | @aprildunnam  |
    [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-123/ba-p/2278796)
    |
    [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-123-19th-of-april-2021/)

-   Viva Connections <https://aka.ms/VivaConnections>

## General resources

-   [CLI for Microsoft 365
    v3](https://developer.microsoft.com/office/blogs/cli-microsoft-365-3/)
-   [CodeTour](https://aka.ms/codetour)
-   [Sharing is Caring](https://aka.ms/sharing-is-caring) |
    aka.ms/sharing-is-caring
-   [Tools -](https://aka.ms/pnp-search) [PnP Modern Search
    v4](https://microsoft-search.github.io/pnp-modern-search/)[ 
    |](https://aka.ms/pnp-search) <https://aka.ms/pnp-search>
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

-   **M365 General Dev call --** April 29th at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Microsoft Graph call -** May 4th at 8:00 am PDT |
    <https://aka.ms/microsoftgraphcall>
-   **SharePoint Framework call** -- May 6th at 7:00 am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **SharePoint monthly call --** May 11th at 8:00am PDT |
    <https://aka.ms/sp-call>
-   **Office add-in monthly call --** May 12th at 8:00 am PDT |
    [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscommunitycall)
-   **Adaptive Cards monthly call --** May 13th at 9:00 am PDT |
    <https://aka.ms/adaptivecardscommunitycall>
-   **Microsoft Teams monthly call --** May 18th at 8:00 am PDT |
    <https://aka.ms/microsoftteamscommunitycall>
-   **Power Apps monthly call --** May 19th at 8:00 am PDT |
    <https://aka.ms/PowerAppsMonthlyCall>
-   **Microsoft Identity Platform --** [May
    20]th at 9:00 am PDT
    | <https://aka.ms/IDDevCommunityCalendar>
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

