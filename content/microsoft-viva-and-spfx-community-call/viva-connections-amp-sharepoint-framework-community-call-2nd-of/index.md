---
title: "Viva Connections & SharePoint Framework Community Call -- 2nd of December, 2021"
date: 2021-12-03T01:19:00-05:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-2nd-of-dec.png
tags: []
type: "regular"
---

Viva Connections & SharePoint Framework bi-weekly community call
recording from December 2nd is now available from the Microsoft 365
Community YouTube channel at <https://aka.ms/m365pnp/videos>. You can use
SharePoint Framework for building solutions for **Microsoft Teams** and
for **SharePoint** Online.



## Call summary



-   Tune in each Tuesday for the [Microsoft 365 platform community
    call](https://aka.ms/m365-dev-call).  Featured topics for the
    December 7th call - **Introduction to Microsoft 365 Instant
    Sandbox** - Michael Aldridge, **Introduction to Microsoft Graph
    Connectors SDK** - Rajdeep Chandra, and **Microsoft Graph Toolkit
    Controls** - Sébastien Levert  
-   Register for training events in December - January hosted by
    [Sharing is Caring](https://pnp.github.io/sharing-is-caring/).
-   Register for the [PnP Recognition
    Program](https://aka.ms/m365pnp-recognition).
-   SharePoint Framework 1.13.1 released - npm install -g
    @microsoft/generator-sharepoint
-   The Road Ahead after 1.13.1 -- 1.14 and future.
-   Modernized app catalog for SharePoint Framework solutions - Preview
-   PnP project releases in the last two weeks
    -   **SharePoint Framework (SPFx)** v1.13.1 GA
    -   **CLI for Microsoft 365** v4.2.0 GA.
**Latest project updates include: ** (**Bold** indicates update from
previous report 2 weeks ago) 

  --------------------------------------------------------------------------------------------- -------------------------------------------- ------------------------------------------------
  **PnP Project**                                                                               **Current version**                          **Release/Status**
  SharePoint Framework (SPFx)                                                                   **v1.13.1 GA**                               v1.14.0 January target
  [PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)                                   v2.11.0 GA, v3.0.0 Preview                   nightly builds of v3
  [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)                              **v4.2.0 GA**                                 
  [Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)               v2.9.0 (SPFx v1.11), v3.4.0                  *3.5.0 with SPFx v1.13 support is coming soon*
  [Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls)   v2.7.0 (SPFx v1.11), v3.2.0 (SPFx v1.12.1)   *3.3.0 with SPFx v1.13 support is coming soon*
  [PnP SPFx Generator](https://github.com/pnp/generator-spfx)                                   v1.16.0                                      v1.17.0 on the way
  [PnP Modern Search](https://microsoft-search.github.io/pnp-modern-search/)                    v4.4.1 Preview, v4.3.0 & v3.21.0             Release expected by calendar year end
  --------------------------------------------------------------------------------------------- -------------------------------------------- ------------------------------------------------
Additionally, there were 2 extensions, 2 web parts and 2 ACE
**samples** were delivered!  Triple 2's are just great! Your
contributions are greatly appreciated by many.  The host of this call is
[Patrick Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
@mediocrebowler.  Q&A takes place as always in chat throughout the
call.

## Actions

-   Opt in to PnP Recognition Program
    | <https://aka.ms/m365pnp-recognition>
-   **Register for Sharing is Caring Events:**
    -   Ask me anything (AMA) PnP Search -- [January
        11th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOFpKRjdQQVlWOEdaRlk2WkI3WUVQWFVNUC4u)
    -   First Time Contributor Session -- [December
        15th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session -- 2022 Sessions Coming Soon   
    -   Power Platform Samples -- First Time Contributor -- [December
        15th](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMTFJWFFGVUxBNUFZQjZWRUdaOE5BMFkwNS4u)
    -   PnP -- SPFx Developer Workstation Setup -- 2022 Sessions Coming
        Soon
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- 2022 Sessions Coming Soon 
    -   First Time Presenter -- 2022 Sessions Coming Soon
    -   More than Code with VSCode -- More Dates Coming Soon 
    -   Maturity Model Practitioners -- [January
        18th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
        (every 3rd Tuesday of month, 7:00am PT)
    -   Getting Started with Viva Connection ACEs -- TBS soon
    -   PnP Office Hours -- 1:1 session --
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    -   PnP Buddy System -- [Request a
        Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
-   Request a Demo spot on the
    call -- <https://aka.ms/m365pnp/request/demo>
-   Download the recurrent invite for this call
    -- <https://aka.ms/spdev-spfx-call>

## Demos

-   **Introduction to HtwoO React library -- Fluent UI experiences
    easily --** learn about the new open-source HtwoO React library
    created by Julie Turner containing atomic components built by
    Stephan Bauer.   Step through installing and initializing the
    library in an SPFx project.  Then build a Splash card page
    containing multiple sub-components. Copy sample code from library
    into components and add components to a page -- modular development.
    Alpha library available now, will go GA shortly.    

-   **Getting started with using PnP Search Web Parts v4 --** create a
    modern Search Center page in minutes using 4 key PnP web parts -
    Search Results, Search Filters, Search Box and Search Verticals. 
    Get v4 package on GitHub and add to App Catalog. Add web parts to a
    page. Configure data sources -- SharePoint or Microsoft Search,
    layouts, create search queries and connections between web parts,
    refine filtering. Package updated by year end.      

     




**SPFx extension samples: (<https://aka.ms/spfx-extensions>)**

-   **[Microsoft Clarity for Modern
    SharePoint](https://github.com/pnp/sp-dev-fx-extensions/tree/main/samples/js-application-microsoft-clarity)** -
    [João Ferreira](https://twitter.com/joao12ferreira)
    | @joao12ferreira
-   **[Follow
    Document](https://github.com/pnp/sp-dev-fx-extensions/tree/main/samples/react-command-follow-document)**-
    [André Lage](https://twitter.com/aaclage) | @aaclage


## SPFx web part samples

<https://aka.ms/spfx-webparts>


-   **[React Calendar](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-calendar)** - [Mohammed Amer](https://twitter.com/Mohammad3mer) | @Mohammad3mer
-   **[Follow Document](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-follow-document)** - [André Lage](https://twitter.com/aaclage) | @aaclage

## PnP SPFx ACEs

[**https://aka.ms/spfx-aces**](https://aka.ms/spfx-aces)

-   **My Notifications* -**[João
    Mendes](https://twitter.com/joaojmendes) | @joaojmendes
-   **Follow Document*** - [André
    Lage](https://twitter.com/aaclage) | @aaclage

- to be posted soon.
Thank you for your great work.  Samples are often showcased in Demos. 


## Agenda items

-   SharePoint Framework - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen -- [6:56](https://youtu.be/NIjXZiEHx_8?t=416)
-   PnPjs Client-Side Libraries - [Julie
    Turner](https://twitter.com/jfj1997) (Sympraxis Consulting) |
    @jfj1997 -- [9:29](https://youtu.be/NIjXZiEHx_8?t=569)
-   CLI for Microsoft 365 - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [11:46](https://youtu.be/NIjXZiEHx_8?t=706)
-   PnP SPFx Controls - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [12:34](https://youtu.be/NIjXZiEHx_8?t=754)
-   PnP Modern Search - [Franck Cornu](https://twitter.com/FranckCornu)
    (aequos) | @FranckCornu --
    [13:18](https://youtu.be/NIjXZiEHx_8?t=798)
-   PnP SPFx Samples - [Hugo
    Bernier](https://twitter.com/bernierh) (Tahoe Ninjas) |
    @bernierh -- [13:56](https://youtu.be/NIjXZiEHx_8?t=836)
-   PnP SPFx ACEs Samples - [David Warner
    II](https://twitter.com/DavidWarnerII) (Catapult Systems) |
    @DavidWarnerII -- [16:01](https://youtu.be/NIjXZiEHx_8?t=961)

## Demos

-   **D1:**  Introduction to HtwoO React library -- Fluent UI experiences easily -- [Julie Turner](https://twitter.com/jfj1997) (Sympraxis Consulting) | @jfj1997 -- [18:31](https://youtu.be/NIjXZiEHx_8?t=1111)

-   **D2:** [Getting started with using PnP Search Web Parts v4 -- ][Franck Cornu][https://twitter.com/FranckCornu]( | @FranckCornu & )[Mikael Svenson](https://twitter.com/mikaelsvenson)[ (Microsoft) | @mikaelsvenson -- [38:10](https://youtu.be/NIjXZiEHx_8?t=2290)]


## Resources

Additional resources around the covered topics and links from the slides.

-   **D1:**  Tools - [Getting Started with
    HTWOO-REACT](https://lab.n8d.studio/htwoo/htwoo-react/) 

-   **D1:**  Icons - [hTWOo UI Icons](https://github.com/n8design/htwoo/tree/main/packages/htwoo-icons) 

-   **D1:**  Article - [ABOUT HTWOO UI](https://lab.n8d.studio/htwoo/) 

-   **D1:**  Splash card -- [Welcome to your hTWOo Splash
    card](https://lab.n8d.studio/htwoo/htwoo-core/?p=pages-teams-splash-screen) 

-   **D2:** Repo - [PnP Modern Search Solution][https://github.com/microsoft-search/pnp-modern-search](https://github.com/microsoft-search/pnp-modern-search)

-   **D2:** GitHub - [PnP Modern Search v4][https://microsoft-search.github.io/pnp-modern-search/](https://microsoft-search.github.io/pnp-modern-search/)

-   **PnP Weekly -- Episode 145** (November 30th) with Bristol,
    England, United Kingdom-based Senior Program Manager on the
    Microsoft Graph Dev-X team [Rabeb
    Othmani](https://twitter.com/Rabeb_Othmani) |
    @Rabeb_Othmani | [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-145-rabeb-othmani-microsoft/ba-p/3008950) | [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-144-%e2%80%93-22nd-of-november-2021/)

-   **PnP Weekly -- Episode 144** (November 22nd) with Atlanta,
    US-based Senior Program Manager on the Viva Connections Platform
    team - [Catherine
    Chuaga](https://www.linkedin.com/in/wanjiru-chuaga/) | [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-144-catherine-chuaga-microsoft/ba-p/2994387) | [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-144-%e2%80%93-22nd-of-november-2021/)

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
**Upcoming calls | Recurrent invites:  **

-   **Microsoft 365 platform call** -- December 7that 8:00 am PST
    | <https://aka.ms/m365-dev-call>
-   **Office add-in monthly call** -- December 8th at 8:00 am PST
    | <https://aka.ms/officeaddinscall>
-   **M365 General Dev call** -- December 9th at 7:00 am PST
    | <https://aka.ms/m365-dev-sig>
-   **Adaptive Cards monthly call** --December 9that 9:00 am PST
| <https://aka.ms/adaptivecardscommunitycall>

-   **Power Apps monthly call**-- December 15th at 8:00 am PST
    | <https://aka.ms/PowerAppsMonthlyCall>
-   **SharePoint Framework call** -- December 16th at 7:00 am PST
    | <https://aka.ms/spdev-spfx-call>
-   **Microsoft Identity Platform call** -- December 16th at 9:00 am
    PST | <https://aka.ms/IDDevCommunityCalendar>

Viva Connections & SharePoint Framework bi-weekly calls are targeted at
anyone who is interested in the JavaScript-based development towards
Microsoft Connections, Microsoft Teams, SharePoint Online, and also
on-premises. Calls are used for the following objectives.

-   SharePoint Framework engineering update from Microsoft
-   Talk about PnP JavaScript Core libraries
-   CLI for Microsoft 365 Updates
-   SPFx reusable controls
-   PnP SPFx Yeoman generator
-   Share code samples and best practices
-   Possible engineering asks for the field - input, feedback, and
    suggestions
-   Cover any open questions on the client-side development
-   Demonstrate SharePoint Framework in practice in Microsoft Viva,
    Microsoft Teams or SharePoint context
-   You can download a recurrent invite
    from <https://aka.ms/spdev-spfx-call>. Welcome and join the
    discussion!

*"Sharing is caring"*

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*Microsoft 365 PnP team, Microsoft - 3rd of December 2021*
