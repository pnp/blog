---
title: "SharePoint Framework Community Call -- 15th of July, 2021"
date: 2021-07-15T08:22:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/210715-together-mode.gif
tags: []
type: "regular"
---

SharePoint Framework Special Interest Group (SIG) bi-weekly community
call recording from July 15th is now available from the Microsoft 365
Community YouTube channel at <https://aka.ms/m365pnp-videos>. You can use
SharePoint Framework for building solutions for **Microsoft Teams** and
for **SharePoint** Online.

## Call summary


Summer and Fall community call schedule updates reviewed.  Register
today for July/August events on
[Sharing-is-caring](https://pnp.github.io/sharing-is-caring/).   [PnP
Recognition Program](https://aka.ms/m365pnp-recognition) announced. 
 Coming soon - Viva Connections public developer preview!   Update on
SharePoint Framework v1.13.0 beta to be released at end of July with
Viva Connections preview extensibility and more.    Delivered - project
releases include **PnPjs Client-side Libraries** v2.7.0, **CLI for
Microsoft 365** v3.12.0 Preview, and **PnP Modern Search** v4.3.0 &
v3.21.0.   
**Latest project updates include: ** (**Bold** indicates update from
previous report 2 weeks ago) 

  **PnP Project**                         **Current version**                          **Release/Status**
  SharePoint Framework (SPFx)             v1.12.1                                      **v1.13.0 Beta end of July**
  PnPjs Client-Side Libraries             **v2.7.0**                                   v2.7.0 scheduled for July 9, v3.0.0 developments underway
  CLI for Microsoft 365                   **v3.12.0 Preview,** v4.0.0 Preview          v4.0.0 to release this fall
  Reusable SPFx React Controls            v2.8.0 (SPFx v1.11), v3.2.1 (SPFx v1.12.1)    
  Reusable SPFx React Property Controls   v2.7.0 (SPFx v1.11), v3.2.0 (SPFx v1.12.1)    
  PnP SPFx Generator                      v1.16.0                                      v1.17.0 on the way
  PnP Modern Search                       **v4.3.0 & v3.21.0**                          

There were 2 **PnP SPFx extensions** and **7 web part samples**
delivered in the last 2 weeks as well.  Way to go contributors!    The
host of this call is [David Warner II](https://twitter.com/DavidWarnerII)
(Catapult Systems) @DavidWarnerII.  Q&A takes place in chat throughout
the call.

## Actions





-   Register for Sharing is Caring Events:
    -   First Time Contributor Session -- [August
        31st](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session -- [August
        23rd](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    -   PnP -- SPFx Developer Workstation Setup -- [August
        24th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
          
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [July 27th, August
        25th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   Ask Me Anything -- Power Platform Development & Samples --
        [September
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNFJZNThMWFk0QlEzWFJNVE5aNVMzM1UwUi4u)
    -   First Time Presenter -- [August
        30th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- [July
        20th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
    -   Maturity Model Practitioners -- [July
        20th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
        and every 3rd Tuesday of month, 7:00am PT
    -   PnP Office Hours -- 1:1 session -
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    -   PnP Buddy System - [Request a
        Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
-   Download the recurrent invite for this call
    -- <https://aka.ms/spdev-spfx-call>

## Demos

-   **Building a COVID attestation solution for Microsoft Teams and Viva
    Connections with SPFx** -- a personal app that collects information
    from users and provides a custom dashboard for working with the
    results.  Dashboard has a Viva Connection COVID-19 attestation card
    built with Adaptive Card Extensions (ACE) and SPFx v1.13.   From
    Card View, users answer attestation questions in Quick View.   A
    cool capability - questions on Quick View card can be updated by
    Admin without having to modify Quick View template! 

-   **Building SharePoint Framework solutions with Microsoft Teams
    Toolkit v2** -- an alternative to using the SPFx Yeoman Generator
    for building Teams apps.   The Toolkit -- a VS Code extension
    targeted to web stack developers, supports the rapid creation of
    apps using SPFx.  Step through Teams Toolkit installation, project
    creation, manifest file validation, etc.   As the toolkit is in
    preview, the co-creators - Teams, SharePoint and Visual Studio
    engineering groups are very interested in your feedback.    



**SPFx extension samples:  (<https://aka.ms/spfx-extensions>)**

-   **[List
    Notifications](https://github.com/pnp/sp-dev-fx-extensions/tree/main/samples/react-application-my-lists-notifications)
    -** [João
    Mendes](https://twitter.com/joaojmendes) | [joaojmendes](https://github.com/joaojmendes)
-   **[Google
    Analytics](https://github.com/pnp/sp-dev-fx-extensions/tree/main/samples/js-application-analytics)
    -** [João
    Ferreira](https://twitter.com/joao12ferreira) | @joao12ferreira


**SPFx web part samples:  (<https://aka.ms/spfx-webparts>)**

-   **[Calendar](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-calendar)** -
    [Mohammad Amer](https://twitter.com/Mohammad3mer) | @Mohammad3mer
-   **[Tiles
    V2](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-tiles-v2)** -
    [Omar El-Anis](https://twitter.com/omarelanis) | @omarelanis
-   **[Team Membership
    Updater](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-teams-membership-updater)** -
    [Nick Brown](https://twitter.com/techienickb) | @techienickb
-   **[Facebook Page Social
    Plugin](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-facebook-plugin)** -
    [Ari Gunawan](https://twitter.com/AriGunawan3023) | @AriGunawan3023
-   **[Hero Web
    Part](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-hero-webpart)** -
    [Omar El-Anis](https://twitter.com/omarelanis) | @omarelanis
-   **[Page
    Contributors](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-pagecontributors)** -
    [Ari Gunawan](https://twitter.com/AriGunawan3023) | @AriGunawan3023
-   **[Private Library/Folder
    Manager](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-private-libraries)** -
    [Russell
    Gove](https://twitter.com/russgove) | @russgove

Thank you for your great work.  Samples are often showcased in Demos. 
  
## Agenda items

-   SharePoint Framework - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft)
    | @vesajuvonen - [7:33](https://youtu.be/RwgpMcqLgrs?t=455)
-   PnPjs Client-Side Libraries - [Julie
    Turner](https://twitter.com/jfj1997) (Sympraxis Consulting) |
    @jfj1997 -- [10:53](https://youtu.be/RwgpMcqLgrs?t=653)
-   CLI for Microsoft 365 - [David Warner
    II](https://twitter.com/DavidWarnerII) (Catapult Systems)  |
    @DavidWarnerII  -- [12:52](https://youtu.be/RwgpMcqLgrs?t=772)
-   PnP SPFx Controls - [David Warner
    II](https://twitter.com/DavidWarnerII) (Catapult Systems)  |
    @DavidWarnerII -- [13:35](https://youtu.be/RwgpMcqLgrs?t=815)
-   PnP Modern Search - [David Warner
    II](https://twitter.com/DavidWarnerII) (Catapult Systems)  |
    @DavidWarnerII -- [14:33](https://youtu.be/RwgpMcqLgrs?t=873)
-   PnP SPFx Samples - [Hugo
    Bernier](https://twitter.com/bernierh) (Tahoe Ninjas) |
    @bernierh -- [15:07](https://youtu.be/RwgpMcqLgrs?t=907)

## Demos

-   **Demo:**  Building a COVID attestation solution for Microsoft Teams
    and Viva Connections with SPFx -- [Julie
    Turner](https://twitter.com/jfj1997) (Sympraxis Consulting) |
    @jfj1997 & [Derek Cash-Peterson](https://twitter.com/spdcp)
    (Sympraxis Consulting) |
    @Spdcp]

-   **Demo:**[  Building SharePoint Framework solutions with Microsoft
    Teams Toolkit v2 -- ][Vesa
    Juvonen](https://twitter.com/vesajuvonen)[ (Microsoft) |
    @vesajuvonen]

    [
    --][ [45:02](https://youtu.be/RwgpMcqLgrs?t=2702)]


## Resources

Additional resources around the covered topics and links from the
slides.

-   Sample -
    [covid-spfx](https://github.com/pnp/spfx-teams/tree/main/samples/COVID) 

-   Tools - [Teams Toolkit (v2.2
    Preview)](https://aka.ms/teams-toolkit) 

-   Tools - [Microsoft Teams Framework
    (TeamsFx)](https://github.com/officedev/teamsfx) 

-   July 14th Blog post - [Viva Connections welcomes new partners and
    opens developer
    preview](https://techcommunity.microsoft.com/t5/microsoft-viva-blog/viva-connections-welcomes-new-partners-and-opens-developer/ba-p/2540643)

-   Viva Connections <https://aka.ms/VivaConnections>

-   Archives - Microsoft 365 PnP Weekly -
    [Videos](https://www.youtube.com/playlist?list=PLR9nK3mnD-OVYI-St_CBiFfuL4CZbBpkC),
    [Podcasts](https://pnpweekly.podbean.com/)  

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

-   **Power Apps monthly call** -- July 21st at 8:00 am PDT |
    <https://aka.ms/PowerAppsMonthlyCall>
-   **M365 General Dev call** -- July 22nd at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **SharePoint Framework call** -- July 29th at 7:00 am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **Office add-in monthly call** -- August 11th at 8:00 am PDT |
    <https://aka.ms/officeaddinscall>
-   **Adaptive Cards monthly call** -- August 12th at 9:00 am PDT |
    <https://aka.ms/adaptivecardscommunitycall>
-   **Microsoft Identity Platform** -- August 19th at 9:00 am PDT |
    <https://aka.ms/IDDevCommunityCalendar>
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

*Microsoft 365 PnP team, Microsoft - 15th of July 2021*
