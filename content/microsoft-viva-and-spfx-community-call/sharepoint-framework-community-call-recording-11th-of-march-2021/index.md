---
title: "SharePoint Framework Community Call Recording -- 11th of March, 2021"
date: 2021-03-12T01:38:00-05:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/PictureTime-OutsideInTheGreenAmphitheater.png
tags: []
type: "regular"
---

SharePoint Framework Special Interest Group (SIG) bi-weekly community
call recording from March 11th is now available from the Microsoft 365
Community YouTube channel at <https://aka.ms/m365pnp-videos>. You can use
SharePoint Framework for building solutions for **Microsoft Teams** and
for **SharePoint** Online.

## Call summary


New [Microsoft 365 Extensibility look book
gallery](https://aka.ms/m365/extensibility) preview released.  Work
continues on Microsoft Viva Connections -- an extensibility model to be
previewed in weeks.  Register now for March trainings on
[Sharing-is-caring](https://pnp.github.io/sharing-is-caring/).   Latest
project updates include:  SPFx v1.12 release -- ETA -- in days.  **PnPjs
Client-Side Libraries** v2.3.0 release scheduled for March 12th, v3.0
Hub planning and discussion issues posted - [issue
1636](https://github.com/pnp/pnpjs/issues/1636).   **CLI for Microsoft
365** Beta v3.7 delivered.   **Reusable SPFx React Controls** -- v2.5.0
and **Reusable SPFx React Property Controls** -- v2.4.0 delivered. 
**PnP Modern Search** v3.18.0 released March 9th, v4.1 in progress.
  There were five **PnP SPFx web part samples** delivered last week.  So
useful!    The host of this call is [Patrick
Rodgers](https://twitter.com/mediocrebowler) (Microsoft)
@mediocrebowler.  Q&A takes place in chat throughout the call.
![PictureTime-OutsideInTheGreenAmphitheater.png](images/PictureTime-OutsideInTheGreenAmphitheater.png)

## Actions





-   Register for [Sharing is Caring
    Events](https://aka.ms/sharing-is-caring)
    -   First Time Contributor Session -- [March
        22nd](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u) 
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session
        -- [March](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    -   PnP -- SPFx Developer Workstation Setup -- April TBD
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- April TBD
    -   PnP -- AMA (Ask Me Anything) -- SPFx Samples Edition -- April 13
    -   First Time Presenter - [March
        24th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u&wdLOR=c0033DF17-137F-493D-9E65-F324D601FD08)
    -   More than Code with VSCode -- [March
        23rd](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
    -   Maturity Model Practitioners -- [March
        16th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    -   PnP Office Hours -- 1:1 session -
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
-    Download the recurrent invite for this call
    -- <https://aka.ms/spdev-spfx-call>


## Demos

1.  **DataTable web part for rendering data from lists with advance
    features** -- this web part provides an easy way to render an
    interactive SharePoint custom list in DataTable view with many
    configuration options in the property pane.  Provides all the
    important table formatting features like: Search & exclude from
    search, filter, pagination, column selection, column ordering,
    alternative row formatting, etc.  Export the selected table data to
    CSV or PDF.  Uses PnPjs, React property controls.

2.  **Building List Search web part for showing data flexibly from lists
    or libraries** -- this React list search web part allows the user to
    show data that's pulled from different lists or libraries on
    multiple sites into a searchable summary list.  Presenter steps
    through extensive, appropriate configuration options. 
    Functionally - Select source data - sites, lists and fields, and Set
    up destination (summary) list columns, formatting, filtering, and
    on-select dynamic data functionality.  Full documentation with
    sample.

3.  **Using a web part to control which Sites have been granted
    permissions in Azure AD application** -- the Sites Selected Admin
    SPFx web part enables Site Collection Admins to check which in scope
    apps have been added to a SharePoint site, to list Azure AD
    registered apps using Microsoft Graph API scope, and to add
    SharePoint sites to the Azure AD listed Apps.  Uses functional
    components to granularly control apps accessing their SharePoint
    sites using Microsoft Graph APIs.   

**SPFx extension samples:  (<https://aka.ms/spfx-extensions>)**


-   No new or updated extensions last week

**SPFx web part samples:  (<https://aka.ms/spfx-webparts>)**

-   [Data
    Table](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-datatable) -
    [Chandani Prajapati](https://twitter.com/Chandani_SPD) |
    @Chandani_SPD 

-   [Feedback](https://github.com/pnp/sp-dev-fx-webparts/blob/master/samples/react-feedback/README.md) -
    Abderahman Moujahid

-   Search Directory - Abderahman Moujahid

-   [Sites Selected
    Admin](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-sites-selected-admin) -
    [Fredrik Thorild](https://twitter.com/taxonomythorild) |
    @taxonomythorild

-   [Security
    Grid](https://github.com/pnp/sp-dev-fx-webparts/blob/master/samples/react-securitygrid) -
    [Russell Gove](https://twitter.com/russgove)
    | @russgove

As is the case this week, samples are often showcased in Demos.  Thank
you for your great work.

## Agenda items

-   Latest updates on SharePoint Framework - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen -- [5:30](https://youtu.be/o_xcui0RZGM?t=330)
-   PnPjs Client-Side Libraries - [Julie
    Turner](https://twitter.com/jfj1997) (Sympraxis Consulting) |
    @jfj199 -- [8:16](https://youtu.be/o_xcui0RZGM?t=496)
-   CLI for Microsoft 365 - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [10:33](https://youtu.be/o_xcui0RZGM?t=633)
-   PnP SPFx Controls - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [11:31](https://youtu.be/o_xcui0RZGM?t=691)
-   PnP SPFx Generator - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [12:25](https://youtu.be/o_xcui0RZGM?t=745)
-   PnP Modern Search - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [13:07](https://youtu.be/o_xcui0RZGM?t=787)
-   PnP SPFx Samples - [Hugo Bernier](https://twitter.com/bernierh)
    (Tahoe Ninjas) | @bernierh --
    [13:42](https://youtu.be/o_xcui0RZGM?t=822)

**Demos :**

-   **DataTable web part for rendering data from lists with advance
    features** -- [Chandani Prajapati](https://twitter.com/Chandani_SPD)
    | @Chandani_SPD & [David
    Warner](https://twitter.com/DavidWarnerII) | @DavidWarnerII --
    [16:45](https://youtu.be/o_xcui0RZGM?t=1005)
-   **Building List Search web part for showing data flexibly from lists
    or libraries** -- [Alberto Gutierrez
    Perez](https://twitter.com/albertogperez) (Minsait) |
    @albertogperez -- [28:00](https://youtu.be/o_xcui0RZGM?t=1680)
-   **Using a web part to control which Sites have been granted
    permissions in Azure AD application** --  [Fredrik
    Thorild](https://twitter.com/taxonomythorild) (Sogeti) |
    @taxonomythorild -- [35:50](https://youtu.be/o_xcui0RZGM?t=2150)



## Resources

Additional resources around the covered topics and links from the
slides.

-   [The presentation used for this community
    call](https://1drv.ms/p/s!AlposW7ozA_90jWOOb1Syq3a3Lqv?e=V8NbH3)

-   Gallery - [Microsoft 365 Extensibility look book
    gallery](https://aka.ms/m365/extensibility) 

-   Repo - [SharePoint Framework DataTable web part
    sample](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-datatable) 

-   Samples - [SharePoint Framework Client-Side Web Part
    Samples](https://aka.ms/spfx-webparts) 

-   Repository - [Reusable React controls for your SharePoint Framework
    solutions](https://aka.ms/pnp-react-controls) 

-   Repo - [List
    Search](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-list-search) 

-   Blog - [Controlling app access on a specific SharePoint site
    collections is now available in Microsoft
    Graph](https://developer.microsoft.com/graph/blogs/controlling-app-access-on-specific-sharepoint-site-collections/) 

-   Repo - [Sites Selected Admin client-side web
    part](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-sites-selected-admin) 

-   Documentation - [Permission resource
    type](https://learn.microsoft.com/graph/api/resources/permission?view=graph-rest-1.0) 

-   Video -- [Requesting API Permissions in
    Azure](https://www.youtube.com/watch?v=wcJRQDsXMQ8&list=PLWZJrkeLOrbYJEr_LoIJ7-1Goy09XJzha) 

-   PnP Weekly -- Episode 117 **with** guest Bert Jansen (Microsoft) |
    @o365bert |
    [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-117/ba-p/2193707)
    |
    [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-117-8th-of-march-2021/)

-   Microsoft 365 Developer Podcast -- March 8, 2021, with guest Stephan
    Bisser (Solvion) | @stephanbisser |
    [podcast](https://www.m365devpodcast.com/e/conversational-ai-with-stephan-bisser/)
     

-   Viva Connections <https://aka.ms/VivaConnections> 

## General resources

-   [CLI for Microsoft 365
    v3](https://developer.microsoft.com/office/blogs/cli-microsoft-365-3/)
-   [CodeTour](https://aka.ms/codetour)
-   [Sharing is Caring](https://aka.ms/sharing-is-caring) |
    aka.ms/sharing-is-caring
-   [PnP Modern Search](https://aka.ms/pnp-search) | aka.ms/pnp-search
-   [M365 PnP site](https://aka.ms/m365pnp) | aka.ms/m365pnp
-   [SharePoint Starter Kit
    v2](https://github.com/pnp/sp-starter-kit/tree/v2)
-   Blog: "[A Lap Around Microsoft Graph Toolkit" blog
    series](https://aka.ms/mgtLap)
-   [New Microsoft 365 Patterns and Practices (PnP) team model with new
    community
    leads](https://developer.microsoft.com/microsoft-365/blogs/new-microsoft-365-patterns-and-practices-pnp-team-model-with-new-community-leads/)
-   [Microsoft 365 Community Content](https://aka.ms/m365-community-docs)
    (non-Dev docs)
-   [PnP SPFx web part samples](https://aka.ms/spfx-webparts)
-   [PnP SPFx extension samples](https://aka.ms/spfx-extensions)
-   [GitHub PnPjs](https://github.com/pnp/pnpjs/)
-   Tutorials - [Getting started with SharePoint Framework v1.10
    Tutorials](https://www.youtube.com/playlist?list=PLR9nK3mnD-OXvSWvS2zglCzz4iplhVrKq)
    (12 videos)
-   Tutorials - [Getting started with SharePoint Framework v1.10
    Extensions](https://www.youtube.com/playlist?list=PLR9nK3mnD-OXtWO5AIIr7nCR3sWutACpV)
    (6 videos)
-   Docs - [Tutorials and training material for SharePoint
    Development](https://learn.microsoft.com/sharepoint/dev/training/training/?wt.mc_id=YT_CCrecording)
-   [SPFX Training Package](https://aka.ms/spfx-training)
-   [SPFx Web Parts](https://aka.ms/spfx-webparts)
-   [SPFx Extensions](https://aka.ms/spfx-extensions)
-   [SPFx Library Components](https://aka.ms/spfx-library-components)
-   Documentation - [PnPjs v2
    documentation](https://pnp.github.io/pnpjs/)
-   Link - [Microsoft 365 developer
    training](https://aka.ms/M365DevTraining)
-   Link - [Office 365 Developer Program](https://aka.ms/O365DevProgram)
-   [Latest documentation on SharePoint
    Framework](https://aka.ms/spdev-docs)
-   Found an issue with SharePoint Dev? - please let us know at
    <https://aka.ms/spdev-issues>
-   [Reusable web part property
    controls](https://sharepoint.github.io/sp-dev-fx-property-controls/)
-   [Reusable react controls for SharePoint Framework
    solutions](https://sharepoint.github.io/sp-dev-fx-controls-react/)
-   [Reusable controls
    webcast](https://devblogs.microsoft.com/microsoft365dev/webcast-reusable-controls-for-your-sharepoint-framework-solutions/)
-   [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365)
-   [PnP SPFx Yeoman Generator](https://github.com/pnp/generator-spfx) -
    Extends the out-of-the-box experience with open-source community
    capabilities
-   [SharePoint Dev UserVoice](https://aka.ms/spdev-uservoice) - for new
    feature requests

**Other mentioned topics**

-   [SharePoint dev
    documentation](https://learn.microsoft.com/sharepoint/dev/)
-   [SharePoint dev issue
    list](https://github.com/SharePoint/sp-dev-docs/issues)



## Upcoming Calls | Recurrent Invites


-   **Microsoft Teams monthly call --** March 16th at 8:00am PDT |
    <https://aka.ms/microsoftteamscommunitycall>
-   **Power Apps monthly call -** March 17th at 8:00am PDT |
    <https://aka.ms/PowerAppsMonthlyCall>
-   **M365 General Dev call --** March 18th at 07:00am PDT |
    <https://aka.ms/m365-dev-sig>
-   **SharePoint Framework call** -- March 25th at 07:00am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **Microsoft Graph call - April** 6th at 8:00am PDT **|**
    <https://aka.ms/microsoftgraphcall>
-   **SharePoint monthly call --** April 9th at 08:00am PDT |
    <https://aka.ms/sp-call>
-   **Office add-in monthly call --** April 10th at 8 AM PDT |
    [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscommunitycall)
-   **Adaptive Cards monthly call --** April 11th at 9:00 am PDT |
    <https://aka.ms/adaptivecardscommunitycall>

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
-   You can download a recurrent invite from
    <https://aka.ms/spdev-spfx-call>. Welcome and join the discussion!

*"Sharing is caring"*

------------------------------------------------------------------------

*Microsoft 365 Patterns and Practices team - 12th of March, 2021*
