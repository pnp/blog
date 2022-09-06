---
title: "SharePoint Framework Community Call Recording -- 25th of March, 2021"
date: 2021-03-26T02:08:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/together-pnp-25th-march-bi-weekly.gif
tags: []
type: "regular"
---


SharePoint Framework Special Interest Group (SIG) bi-weekly community
call recording from March 25th is now available from the Microsoft 365
Community YouTube channel at <https://aka.ms/m365pnp-videos>. You can use
SharePoint Framework for building solutions for **Microsoft Teams** and
for **SharePoint** Online.

## Call summary


Welcome Luise Freese | @LuiseFreese to the **Sharing is Caring** team
and Joel Rodrigues | @JoelFMRodrigues who is a new maintainer on the
**Reusable SPFx Controls** team.  ** **Register now for April trainings
on [Sharing-is-caring](https://pnp.github.io/sharing-is-caring/). 
** SharePoint Framework** v1.12 has been deprecated due to unexpected
regressions.   Discussion later in the call on **SharePoint Framework**
v1.12.1 capabilities to be released shortly.  Latest project updates
include:  **PnPjs Client-Side Libraries** v2.3.0 released and please
provide feedback on v3.0 Hub planning and discussion issues posted -
[issue #1636](https://github.com/pnp/pnpjs/issues/1636).  **CLI for
Microsoft 365** GA v3.7 delivered.   **Reusable SPFx React Controls** --
v2.6.0 and v3.0.0 (SPFx v1.12 support) and **Reusable SPFx React
Property Controls** -- v2.5.0 and v3.0.0 (SPFx v1.12 support) delivered.
  Released **PnP SPFx Generator** v1.16.0 (Angular 11 supported), **PnP
Modern Search** v3.18.1 released March 9th and v4.1.0 released March
20th.     There were six **PnP SPFx web part samples** delivered last
2 weeks.  Great work!    The host of this call is [Patrick
Rodgers](https://twitter.com/mediocrebowler) (Microsoft)
@mediocrebowler.  Q&A takes place in chat throughout the call.
![together-pnp-25th-march-bi-weekly.gif](images/together-pnp-25th-march-bi-weekly.gif)
 

## Actions





-   RSVP to attend - 2-hour livestream -- Building Apps for with
    Microsoft Graph -- 2 sessions -- 2:00pm AEST and 8:30am PDT |
    <https://aka.ms/learntogether-graph>
-   Join the discussion - PnPjs v3.0 Hub planning and discussion -
    [issue #1636](https://github.com/pnp/pnpjs/issues/1636).
-   Complete the Developer Success Survey -
    <https://aka.ms/developersuccess>
-   Join the M365 customer success platform panel -
    <https://aka.ms/SuccessPanel>
-   Register for Sharing is Caring Events:
    -   First Time Contributor Session -- [April 6th &
        27th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)  
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session
        -- [April](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    -   PnP -- SPFx Developer Workstation Setup -- [April
        29th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [April 8th &
        15th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   PnP -- AMA (Ask Me Anything) -- CLI for Microsoft 365 Edition --
        [April
        13](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN1ZUQ0tFMTFLVUZaTjZXRjdPRk5XOEdSMy4u)
    -   First Time Presenter - [April 7th &
        21st](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- [April 14th &
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
    -   Maturity Model Practitioners -- [April
        20th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    -   PnP Office Hours -- 1:1 session -
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
-   Download the recurrent invite for this call
    -- <https://aka.ms/spdev-spfx-call>

## Demos

1.  **Building extension to save documents as PDF in tenant document
    libraries - u**pdated list extension first created 2 years ago for
    converting one or more selected documents into pdfs using internal
    SharePoint REST APIs.  2 methods -- Export (create) and Save As
    (download).  Saves pdfs to current library.  Step through the
    conversion and render code - copy entire document and metadata to
    blob, writes data into pdf.   Tenant wide extension automatically
    created in App Catalog.

2.  **Sending messages to Microsoft Teams using Microsoft Graph from
    SharePoint Framework solution** - a simple web part for sending a
    message from a SharePoint page to a recipient's mailbox or into a
    Microsoft Teams chat using Microsoft Graph.  Conversation elements
    include send email, my profile information, target user's principal
    name, get chat ID (determines if existing chat or creates new). 
    Uses Graph APIs, PnP People Picker, React hooks and code snippets in
    Graph Explorer.

**Update:**

**Latest on SharePoint Framework --** SPFx v1.12.1 includes additional
functionality over v1.12 for creating complex Microsoft Teams solutions
including SPFx elements.  In addition to corrections to SPFx v1.12,
v1.12.1 includes Node v12/v14 and Gulp support, more access to page
structure, embed manifest configuration option, support for Teams
meeting apps and for Microsoft Teams SDK v1.8.  Post v1.12.1 --
integration in Microsoft Viva Connections, Teams Development, Store,
Communications and Quality improvements.     

**SPFx extension samples:  (<https://aka.ms/spfx-extensions>)**


-   No new or updated extensions last week

**SPFx web part samples:  (<https://aka.ms/spfx-webparts>)**

-   **[Teams Meeting Questionnaire
    App](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-teams-meeting-app-questionnaire)** -
    [Nanddeep
    Nachan](https://twitter.com/NanddeepNachan) | [nanddeepn](https://github.com/nanddeepn),
    [Ravi Kulkarni](https://twitter.com/RaviKul16a87) | @RaviKul16a87,
    [Smita
    Nachan](https://twitter.com/SmitaNachan) | @SmitaNachan
-   **[Questions and
    Answers](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-questions-and-answers)** -
    [Bo George](https://twitter.com/bo_george) | @bo_george
-   **[Calendar](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-calendar)** -
    [Peter Paul
    Kirschner ](https://twitter.com/petkir_at)| @petkir\_at
-   **[Image
    Editor](https://github.com/pnp/sp-dev-fx-webparts/blob/master/samples/react-image-editor)** -
    [Peter Paul
    Kirschner](https://twitter.com/petkir_at) | @petkir\_at
-   **[Jump to
    Folder](https://github.com/pnp/sp-dev-fx-extensions/tree/master/samples/react-jump-to-folder)** -
    [Joel
    Rodrigues ](https://twitter.com/joelfmrodrigues)| @joelfmrodrigues
-   **[Calendar](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-calendar)** -
    [Mohammad Amer ](https://twitter.com/Mohammad3mer)| @Mohammad3mer
As is the case this week, samples are often showcased in Demos.  Thank
you for your great work.

## Agenda items

-   Latest updates on SharePoint Framework - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen -- [7:30](https://youtu.be/K_aiG8RlBDU?t=450)
-   PnPjs Client-Side Libraries - [Julie
    Turner](https://twitter.com/jfj1997) (Sympraxis Consulting) |
    @jfj199 -- [8:55](https://youtu.be/K_aiG8RlBDU?t=535)
-   CLI for Microsoft 365 - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [11:03](https://youtu.be/K_aiG8RlBDU?t=663)
-   PnP SPFx Controls - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [12:03](https://youtu.be/K_aiG8RlBDU?t=723)
-   PnP SPFx Generator - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [13:15](https://youtu.be/K_aiG8RlBDU?t=795)
-   PnP Modern Search - [Mikael
    Svenson](https://twitter.com/mikaelsvenson) (Microsoft) |
    @MikaelSvenson
-   PnP SPFx Samples - [Hugo
    Bernier](https://twitter.com/bernierh) (Tahoe Ninjas) |
    @bernierh -- [15:24](https://youtu.be/K_aiG8RlBDU?t=924)

## Demos

-   **Building extension to save documents as PDF in tenant document
    libraries** -- [Mikael Svenson](https://twitter.com/mikaelsvenson)
    (Microsoft) |
    @MikaelSvenson
-   **Sending messages to Microsoft Teams using Microsoft Graph from
    SharePoint Framework solution** -- [David
    Ramalho](https://twitter.com/DavRamalho) (Storm Technology) |
    @davRamalho

**Update: **

-   **Latest on SharePoint Framework - **[Pat
    Miller](https://twitter.com/PatMill_MSFT) (Microsoft)
    | @PatMill_MSFT & [Luca
    Bandinelli](https://twitter.com/BandinelliLuca) (Microsoft) |
    @BandinelliLuca**-** [42:48](https://youtu.be/K_aiG8RlBDU?t=2568)


## Resources

Additional resources around the covered topics and links from the
slides.

-   [The presentation used for this community
    call](https://1drv.ms/p/s!AlposW7ozA_90jkH1Fk0_gv6Jl_n?e=MY5TLx)

-   Gallery - [Microsoft 365 Extensibility look book
    gallery](https://aka.ms/m365/extensibility) 

-   Repo - [Save and convert as PDF by
    PnP](https://github.com/pnp/sp-dev-fx-extensions/tree/master/samples/react-command-convert-to-pdf) 

-   Documentation -  [SPRenderListDataOptions
    options](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest#sprenderlistdataoptions-options) 

-   Article - [Send a message to Microsoft Teams using Microsoft Graph
    in
    SPFx](https://sharepoint-tricks.com/send-a-message-to-microsoft-teams-using-microsoft-graph-in-spfx/) 

-   Documentation - [Message Teams
    User](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-teams-message-user) 

-   Graph Explorer --
    <https://developer.microsoft.com/graph/graph-explorer>

-   Documentation - [Add Viva Connections for Microsoft Teams
    desktop](https://docs.microsoft.com/sharepoint/viva-connections-desktop) 

-   PnP Weekly -- Episode 119 with guest MVP [Chris
    O'Brien](https://twitter.com/ChrisO_Brien) | @ChrisO_Brien |
    [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-119/ba-p/2228107)
    |
    [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-119-22nd-of-march-2021/)

-   Viva Connections <https://aka.ms/VivaConnections> 

## General resources

-   [CLI for Microsoft 365
    v3](https://developer.microsoft.com/office/blogs/cli-microsoft-365-3/)
-   [CodeTour](https://aka.ms/codetour)
-   [Sharing is Caring](https://aka.ms/sharing-is-caring) |
    aka.ms/sharing-is-caring
-   [PnP Modern Search](https://aka.ms/pnp-search) | aka.ms/pnp-search
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
**Other mentioned topics**

-   [SharePoint dev
    documentation](https://docs.microsoft.com/sharepoint/dev/)
-   [SharePoint dev issue
    list](https://github.com/SharePoint/sp-dev-docs/issues)


## Upcoming Calls | Recurrent Invites


-   **M365 General Dev call --** April 1st at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Microsoft Graph call -** April 6th at 8:00 am PDT |
    <https://aka.ms/microsoftgraphcall>
-   **SharePoint Framework call** -- April 8th at 7:00 am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **Adaptive Cards monthly call --** April 8th at 9:00 am PDT |
    <https://aka.ms/adaptivecardscommunitycall>
-   **SharePoint monthly call --** April 13th at 8:00am PDT |
    <https://aka.ms/sp-call>
-   **Office add-in monthly call --** April 14th at 8:00 am PDT |
    [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscommunitycall)
-   **M365 General Dev call --** April 15th at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Microsoft Identity Platform** -- April 15th at 9:00 am PDT |
    <https://aka.ms/IDDevCommunityCalendar> 
-   **Microsoft Teams monthly call --** April 20th at 8:00 am PDT |
    <https://aka.ms/microsoftteamscommunitycall>
-   **Power Apps monthly call --** April 21st at 8:00 am PDT |
    <https://aka.ms/PowerAppsMonthlyCall>
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
