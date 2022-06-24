---
title: "SharePoint Framework Community Call -- 29th of July, 2021"
date: 2021-07-29T04:59:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/PnP-Calls-TogetherMode-LowResolution.gif
tags: []
type: "regular"
---


SharePoint Framework Special Interest Group (SIG) bi-weekly community
call recording from July 29th is now available from the Microsoft 365
Community YouTube channel at <https://aka.ms/m365pnp-videos>. You can use
SharePoint Framework for building solutions for **Microsoft Teams** and
for **SharePoint** Online.

## Call summary

Summer and Fall community call schedule updates reviewed.  Register
today for August events on
[Sharing-is-caring](https://pnp.github.io/sharing-is-caring/).   [PnP
Recognition Program](https://aka.ms/m365pnp-recognition) announced. 
 [Viva Connections public developer
preview!](https://aka.ms/viva/connections/developer/preview)
  **SharePoint Framework v1.13 beta** released earlier this week with
preview on the Viva Connections extensibility tooling.  
**Latest project updates include: ** (**Bold** indicates update from
previous report 2 weeks ago) 
|                                       |                                            |                             |
| ------------------------------------- | ------------------------------------------ | --------------------------- |
| PnP Project                           | Current version                            | Release/Status              |
| SharePoint Framework (SPFx)           | v1.12.1, v1.13 beta                        | v1.13.0 Beta end of July    |
| PnPjs Client-Side Libraries           | v2.7.0                                     | 2.8.0 scheduled for Aug 13, |
| v3.0.0 developments underway          |
| CLI for Microsoft 365                 | v3.12.0 Preview, v4.0.0 Preview            | v4.0.0 to release this fall |
| Reusable SPFx React Controls          | v2.8.0 (SPFx v1.11), v3.2.1 (SPFx v1.12.1) |                             |
| Reusable SPFx React Property Controls | v2.7.0 (SPFx v1.11), v3.2.0 (SPFx v1.12.1) |                             |
| PnP SPFx Generator                    | v1.16.0                                    | v1.17.0 on the way          |
| PnP Modern Search                     | v4.3.0 & v3.21.0                           |                             |

There was 1 **PnP SPFx extension** and 4 **PnP web part samples**
delivered in the last 2 weeks as well.  Nice work!    The host of this
call is [Patrick Rodgers](https://twitter.com/mediocrebowler) (Microsoft)
| @mediocrebowler.  Q&A takes place in chat throughout the call.
![PnP-Calls-TogetherMode-LowResolution.gif](images/PnP-Calls-TogetherMode-LowResolution.gif)
 

Yep!  Nice wave action.  Great seeing you this week.  Looking forward to
seeing you again in August.    Data for Hugo:  24 left-handed wavers, 4
right-handed wavers, 2 bi-handed wavers and 4 non-handed wavers.  But
wait, now there's 35 wavers!   Data corruption.  

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
        Version Manager -- [August
        25th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   Ask Me Anything -- Power Platform Development & Samples --
        [September
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNFJZNThMWFk0QlEzWFJNVE5aNVMzM1UwUi4u)
    -   First Time Presenter -- [August
        30th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- TBS
    -   Maturity Model Practitioners -- [August
        17th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
        and every 3rd Tuesday of month, 7:00am PT
    -   PnP Office Hours -- 1:1 session -
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    -   PnP Buddy System - [Request a
        Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
-   Download the recurrent invite for this call
    -- <https://aka.ms/spdev-spfx-call>

## Demos

-   **Hero Web Part and Tiles V2 Web Part** -- **Tiles v2** -- displays
    a group of responsive flex tiles that can be configured to navigate
    to different URLs.   **REACT Hero** -- provides a customizable Hero
    web part that displays 5 images in a stand-alone carousel view.
      Both web parts use a stored collection from
    PnP PropertyFieldCollectionData control and custom field rendering
    control, file/icon pickers and fluid flex layout.   Site theme
    selectable in Tiles v2.  Thorough code walkthrough.

-   **Exposing business data in Viva Connections or in SharePoint with
    custom diagram web parts**​ -- or in Microsoft Teams.  React
    diagraming web parts updated to v1.13.  Updates accommodate Dynamic
    Data Connections, full bleed, handling section color changes, Viva
    Connections, and to search content in web part.  Web parts leverage
    libraries/code from Mermaid, flowchart.js, and js-sequence-diagrams
    along with the Monaco Editor and PnP markdown property pane to both
    generate diagrams and to overlay text on them.



**SPFx extension samples:  (<https://aka.ms/spfx-extensions>)**

-   **[Machine
    Translations](https://github.com/pnp/sp-dev-fx-extensions/tree/main/samples/react-application-machine-translations)
    -** [Michał
    Romiszewski](https://twitter.com/romiszewski) | @romiszewski

</div>

**SPFx web part samples:  (<https://aka.ms/spfx-webparts>)**

-   **[Datatable](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-datatable)** -
    [Abderahman
    Moujahid](https://twitter.com/Abderahman88) | @Abderahman88
-   **[Hero Web
    Part](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-hero-webpart)** -
    [Omar El-Anis](https://twitter.com/omarelanis) | @omarelanis
-   **[Cross-Device
    Data](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-cross-device-data)** (link
    pending) - [Giuliano De
    Luca](https://twitter.com/delucagiulian) | @delucagiulian
-   **[Diagrams](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-diagram-webparts)** (link
    pending) - [Hugo Bernier](https://twitter.com/bernierh) | @bernierh

Thank you for your great work.  Samples are often showcased in Demos. 
  
## Agenda items

-   SharePoint Framework - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft)
    @mediocrebowler - [7:16](https://youtu.be/BMXZlYtyKp4?t=436)
-   PnPjs Client-Side Libraries - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft)
    @mediocrebowler -- [10:11](https://youtu.be/BMXZlYtyKp4?t=611)
-   CLI for Microsoft 365 - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft)
    @mediocrebowler -- [11:47](https://youtu.be/BMXZlYtyKp4?t=707)
-   PnP SPFx Controls - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft)
    @mediocrebowler -- [13:08](https://youtu.be/BMXZlYtyKp4?t=788)
-   PnP Modern Search - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft)
    @mediocrebowler -- [13:58](https://youtu.be/BMXZlYtyKp4?t=838)
-   PnP SPFx Samples - [Hugo
    Bernier](https://twitter.com/bernierh) (Tahoe Ninjas) |
    @bernierh -- [15:00](https://youtu.be/BMXZlYtyKp4?t=900)

## Demos

-   **Demo:**  Hero Web Part and Tiles V2 Web Part -- [Omar
    El-Anis](https://twitter.com/omarelanis) |
    @omarelanis [--][ [18:12](https://youtu.be/BMXZlYtyKp4?t=1092)]

-   **Demo:**[  Exposing business data in Viva Connections or in
    SharePoint with custom diagram web parts --
    ][Hugo
    Bernier](https://twitter.com/bernierh)[ (Microsoft) |
    @bernierh ][--][ [41:12](https://youtu.be/BMXZlYtyKp4?t=2472)]


## Resources

Additional resources around the covered topics and links from the
slides.

-   Omar's blog -- [SP Bytes](http://www.spdeveloper.co.uk/) 

-   Sample - [Hero web
    part](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-hero-webpart) 

-   Sample - [Tiles
    V2](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-tiles-v2) 

-   Controls -- [PropertyFieldCollectionData
    control](https://pnp.github.io/sp-dev-fx-property-controls/controls/PropertyFieldCollectionData) 

-   Hugo's Repo - [React Diagram Web
    Parts](http://github.com/hugoabernier/react-diagram-webparts) 

-   Gallery - [SharePoint Framework Client-Side Web Part
    Samples](https://aka.ms/spfx-webparts) 

-   Tool - [About Mermaid](https://mermaid-js.github.io/mermaid/#/) 

-   Library -
    [js-sequence-diagrams ](https://bramp.github.io/js-sequence-diagrams/)

-   Tool -- [flowchart.js](https://flowchart.js.org/) 

-   Editor -- [Monaco
    Editor](https://microsoft.github.io/monaco-editor/) 

-   PnP/SPFx-property-controls - [PropertyPaneMarkdownContent
    control](https://pnp.github.io/sp-dev-fx-property-controls/controls/PropertyPaneMarkdownContent) 

-   PnP/SPFx-controls-react - [Placeholder
    control](https://pnp.github.io/sp-dev-fx-controls-react/controls/Placeholder) 

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


## Upcoming Calls | Recurrent Invites

-   **M365 General Dev call** -- August 5th at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Office add-in monthly call** -- August 11th at 8:00 am PDT |
    <https://aka.ms/officeaddinscall>
-   **SharePoint Framework call** -- August 12th at 7:00 am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **Adaptive Cards monthly call** -- August 12th at 9:00 am PDT |
    <https://aka.ms/adaptivecardscommunitycall>
-   **Power Apps monthly call** -- August 18th at 8:00 am PDT |
    <https://aka.ms/PowerAppsMonthlyCall>
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

*Microsoft 365 PnP team, Microsoft - 29th of July 2021*
