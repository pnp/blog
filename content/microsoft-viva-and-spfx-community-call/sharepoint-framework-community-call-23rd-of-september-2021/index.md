---
title: "SharePoint Framework Community Call -- 23rd of September, 2021"
date: 2021-09-24T12:57:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-23rd-sep.png
tags: []
type: "regular"
---
 

SharePoint Framework Special Interest Group (SIG) bi-weekly community
call recording from September 23rd is now available from the Microsoft
365 Community YouTube channel at <https://aka.ms/m365pnp/videos>. You can
use SharePoint Framework for building solutions for **Microsoft
Teams** and for **SharePoint** Online.

## Call summary


A reminder to tune in each Tuesday for the new [Microsoft 365 platform
community call](https://aka.ms/m365-dev-call).  Topics for the call on
September 28 are Building custom search layout experiences in SharePoint
with Microsoft Search and Introduction to Microsoft Viva Connections
extensibility.  Have a look at the updated list of training events
hosted by [Sharing is Caring](https://pnp.github.io/sharing-is-caring/).
  Register for the [PnP Recognition
Program](https://aka.ms/m365pnp-recognition).   SharePoint Framework
v1.13 GA coming soon (in Oct) -- The release focuses on the Microsoft
Viva Connections mobile experience!   Released **PnPjs Client-side
Libraries** v2.9.0 and updated **CLI for Microsoft 365** v4.0.0.
Preview.  
**Latest project updates include: ** (**Bold** indicates update from
previous report 2 weeks ago) 

  **PnP Project**                         **Current version**                             **Release/Status**
  SharePoint Framework (SPFx)             v1.12.1 GA, v1.13 Beta Viva.20                  **v1.13 GA in October**
  PnPjs Client-Side Libraries             **v2.9.0**                                      v3.0.0 developments underway
  CLI for Microsoft 365                   v3.13.0 Preview, **v4.0.0 Preview - updated**   v4.0.0 GA to release end September
  Reusable SPFx React Controls            v2.9.0 (SPFx v1.11), v3.3.0 (SPFx v1.12.1)       
  Reusable SPFx React Property Controls   v2.7.0 (SPFx v1.11), v3.2.0 (SPFx v1.12.1)       
  PnP SPFx Generator                      v1.16.0                                         v1.17.0 on the way
  PnP Modern Search                       v4.3.0 & v3.21.0                                **Release expected any day**

1 extension and 4 web part samples were delivered in the last 2 weeks! 
 Visit the new samples repository for Adaptive Card Extensions (ACE) -
aka.ms/spfx-aces.  Thank you all for your contributions!   The host of
this call is [David Warner II](https://twitter.com/DavidWarnerII)
(Catapult Systems) @DavidWarnerII.  Live Q&A at end and in chat
throughout this call.
![210923-together-mode.gif](images/210923-together-mode.gif)
Picture time is back!  Great to see all of you today.  Looking forward
to seeing some of you in Düsseldorf or Las Vegas later this year. 

## Actions





-   Register for Microsoft Ignite (Digital event) - November 2-4, 2021-
    <https://ignite.microsoft.com>
-   Opt in to PnP Recognition Program
    | <https://aka.ms/m365pnp-recognition>
-   Register for Sharing is Caring Events:
    -   First Time Contributor Session -- TBS (EMEA, APAC & US friendly
        times available)
    -   Community Docs Session -- [October
        5th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u) 
    -   **Power Platform Samples -- First Time Contributor** - [October
        27th](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMTFJWFFGVUxBNUFZQjZWRUdaOE5BMFkwNS4u)
    -   PnP -- SPFx Developer Workstation Setup -- TBS
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [September
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u) 
    -   Ask Me Anything (AMA) -- Power Platform Development & Samples --
        [September
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNFJZNThMWFk0QlEzWFJNVE5aNVMzM1UwUi4u)
    -   Ask Me Anything (AMA) -- List Formatting -- [October
        5th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNTVHSFFMRDdDSjA0MklUSUtTQ0IxMFpPNS4u)
    -   First Time Presenter -- [October
        12th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- TBS 
    -   Maturity Model Practitioners -- [October
        19th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
         (every 3rd Tuesday of month, 7:00am PT)
    -   PnP Office Hours -- 1:1 session --
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    -   PnP Buddy System -- [Request a
        Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
    -   Request a Demo spot on the call --
        <https://aka.ms/m365pnp/request/demo>
-   Download the recurrent invite for this call
    -- <https://aka.ms/spdev-spfx-call>

## Demos

-   **Apply a custom theme or a variation of the current SharePoint
    theme directly to the web part** -- see the 3 ways to change shading
    using the Fluent UI Theme variant inside a web part.  1) Use colors
    applied to the section where the web part is present, 2) Select
    color variations based on theme applied at Site level or 3) Apply
    variations set to the json of a custom theme, created through the
    Fluent UI Theme Designer tool.   

-   **Accessing personal files easily with My OneDrive Web Part --** a
    simple, powerful SPFx web part for an Intranet Landing or Viva
    connections page to display the current user's One Drive files. 
    Uses the One Drive Graph API and a custom component -
    OneDriveTable.  Shows User's One Drive files and folders, most file
    type icons, breadcrumbs, sorting by column, select columns to
    display, and option to copy URL to file in OneDrive.   Full code
    walkthrough.    

-   **Surface user specific calendar events with my Outlook events web
    part build** -- this SPFx React My Outlook Events web part uses
    event feeds and renders events using a look and feel consistent with
    the out-of-box SharePoint Group calendar/events web part.  This web
    part provides the logged in user's Outlook events with some
    advanced feature configuration -- layouts for rendering single and
    multi-day events, selectable date range, and navigation direct to
    Teams meeting. Full code walkthrough. 

**SPFx extension samples:  (<https://aka.ms/spfx-extensions>)**

-   **[Copy/Move Items within
    Lists](https://github.com/pnp/sp-dev-fx-extensions/tree/main/samples/react-command-copy-move-items)
    -** [Sudharsan
    Kesavanarayanan](https://twitter.com/sudharsank)[ | @sudharsank](https://github.com/pnp/sp-dev-fx-extensions/tree/main/samples/js-share-to-teams)


**SPFx web part samples:  (<https://aka.ms/spfx-webparts>)**

-   **[Applications Secrets
    Expiration](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-graph-app-secret-expiration)** -
    [Aimery Thomas](https://twitter.com/aimery_thomas) | @aimery_thomas
-   **[Teams Membership
    Updater](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-teams-membership-updater)** -
    [Nick Brown](https://twitter.com/techienickb) | @techienickb
-   **[Advanced Page
    Properties](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-advanced-page-properties)** -
    [Abderahman
    Moujahid](https://twitter.com/Abderahman88) | @Abderahman88
-   **[News](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-news)** -
    [Alison
    Collins](https://github.com/ReactIntern) | <https://github.com/ReactIntern>

Thank you for your great work.  Samples are often showcased in Demos. 
  
## Agenda items

-   SharePoint Framework - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen -- [5:57](https://youtu.be/5dUg6n6JQ7c?t=357)
-   PnPjs Client-Side Libraries - [Julie
    Turner](https://twitter.com/jfj1997) (Sympraxis Consulting) |
    @jfj1997 -- [8:21](https://youtu.be/5dUg6n6JQ7c?t=501)
-   CLI for Microsoft 365 - [David Warner
    II](https://twitter.com/DavidWarnerII) (Catapult Systems) |
    @DavidWarnerII -- [9:49](https://youtu.be/5dUg6n6JQ7c?t=589)
-   PnP SPFx Controls - [David Warner
    II](https://twitter.com/DavidWarnerII) (Catapult Systems) |
    @DavidWarnerII -- [10:29](https://youtu.be/5dUg6n6JQ7c?t=629)
-   PnP Modern Search - [David Warner
    II](https://twitter.com/DavidWarnerII) (Catapult Systems) |
    @DavidWarnerII -- [11:26](https://youtu.be/5dUg6n6JQ7c?t=686) 
-   PnP SPFx Samples - [Hugo
    Bernier](https://twitter.com/bernierh) (Tahoe Ninjas) |
    @bernierh -- [11:53](https://youtu.be/5dUg6n6JQ7c?t=713)

## Demos

-   **D1:  **Apply a custom theme or a variation of the current
    SharePoint theme directly to the web part -- [Fabio
    Franzini](https://twitter.com/franzinifabio) | @franzinifabio --
    [15:01](https://youtu.be/5dUg6n6JQ7c?t=901)

-   **D2:** Accessing personal files easily with My OneDrive Web Part
    -- [Siddharth
    Vaghasia](https://twitter.com/siddh_me) | @siddh_me --
    [26:23](https://youtu.be/5dUg6n6JQ7c?t=1583)

-   **D3:** Surface user specific calendar events with my Outlook
    events web part build -- [Chandani
    Prajapati](https://twitter.com/Chandani_SPD) | @Chandani_SPD --
    [35:38](https://youtu.be/5dUg6n6JQ7c?t=2138)


## Resources

Additional resources around the covered topics and links from the
slides.

-   D1:  Sample - [React Fluent UI Theme
    Variant](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-fluentui-theme-variant) 

-   D1:  PnP SPFx Controls - [Reusable property pane controls for the
    SharePoint Framework
    solutions](https://pnp.github.io/sp-dev-fx-property-controls/) 

-   D1:  Tools - [@fluentui/scheme-utilities --
    npm](https://www.npmjs.com/package/@fluentui/scheme-utilities) 

-   D2:  Sample - [My
    OneDrive](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-myonedrive)

-   D3:  Sample - [My
    Events](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-my-events) 

-   D3:  Repository - [Samples by
    Framework](https://aka.ms/spfx-webparts) 

-   D3:  PnP SPFx Controls - [Reusable React controls for your
    SharePoint Framework
    solutions](https://pnp.github.io/sp-dev-fx-controls-react/) 

-   D3:  Sample - [Calendar
    Feed](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-calendar-feed)

-   **[PnP Weekly -- Episode 135]** with
    [German-based MVP and founder
    of ][Nubelus](https://www.nubelus.com/)[Adis
    Jugo](https://twitter.com/adisjugo)[ | @adisjugo. |
    ][video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-135-adis-jugo-nubelus/ba-p/2770145)[
    |
    ][podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-135-%e2%80%93-22nd-of-september-2021/)

## General resources

-   Viva Connections <https://aka.ms/VivaConnections>

-   Archives - Microsoft 365 PnP Weekly
    - [Videos](https://www.youtube.com/playlist?list=PLR9nK3mnD-OVYI-St_CBiFfuL4CZbBpkC), [Podcasts](https://pnpweekly.podbean.com/)  

-   Tools - [Teams Toolkit (v2.2
    Preview)](https://aka.ms/teams-toolkit) 

-   Tools - [Microsoft Teams Framework
    (TeamsFx)](https://github.com/officedev/teamsfx) 

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
**Upcoming calls | Recurrent invites:  *(Subject to Updates in
September)***
-   **Microsoft 365 platform call** -- September 28th at 8:00 am
    PDT | <https://aka.ms/m365-dev-call>
-   **M365 General Dev call** -- September 30th at 7:00 am PDT
    | <https://aka.ms/m365-dev-sig>
-   **SharePoint Framework call** -- October 7th at 7:00 am PDT
    | <https://aka.ms/spdev-spfx-call>
-   **Office add-in monthly call** -- October 13th at 8:00 am PDT
    | <https://aka.ms/officeaddinscall>
-   **Adaptive Cards monthly call** --October 14th at 9:00 am PDT
| <https://aka.ms/adaptivecardscommunitycall>

-   **Power Apps monthly call**-- October 20th at 8:00 am PDT
    | <https://aka.ms/PowerAppsMonthlyCall>
-   **Microsoft Identity Platform call** -- October 21st at 9:00 am
    PDT | <https://aka.ms/IDDevCommunityCalendar>
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

*Microsoft 365 PnP team, Microsoft - 24th of September 2021*
