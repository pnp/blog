---
title: "Microsoft 365 Developer Community Call recording -- 27th of May, 2021"
date: 2021-05-28T12:20:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/sig-27th-may-recording.png
tags: []
type: "regular"
---
 


## Call summary



Latest news from Microsoft 365 engineering and updates on open-source
projects: PnP .NET libraries, PnP PowerShell, modernization tooling, on
yo Teams, on Microsoft Graph Toolkit, and on Microsoft Teams Samples.
Join on the [Viva Connections private
preview](https://aka.ms/viva/connections/preview/register)!  The
[Microsoft Teams Toolkit v2](https://aka.ms/teams-toolkit) is now
available!  Looking to get started with Microsoft Teams development?
Don't miss out our [Teams samples
gallery](https://aka.ms/teams-samples)!  Check out the [Microsoft 365
Extensibility look book gallery](https://aka.ms/m365/extensibility), and
register now for June trainings on
[Sharing-is-caring](https://pnp.github.io/sharing-is-caring/).   Recent
PnP project releases include - **yo Teams** ***generator-teams*** (apps
generator) v3.1.0 GA, v3.2.0 Preview, ***yo teams-build-core*** (gulp
tasks) v1.2.0 Preview, and **Microsoft Graph Toolkit** v2.2.0 GA along
with insights into MGT vNext.
 

**Open-source project status:**
  ----------------------------------------- ------------------------------------------------------------- ------------------------------------------------
  **Project**                               **Current Version**                                           **Release/Status**
  PnP .NET Libraries - PnP Framework        v1.4.0                                                        **Prepping for v1.5.0 release week of May 31**
  PnP .NET Libraries - PnP Core SDK         v1.1.0                                                        **Prepping for v1.2.0 release week of May 31**
  PnP PowerShell                            v1.5.0 (just added Cmdlets for Viva Connections and Syntex)   Prepping for v1.6.0 (June)
  Yo teams - generator-teams                **Released v3.1.0 GA, v3.2.0 Preview**                        Preview with Viva Connections support
  Yo teams - yoteams-build-core             v1.1.0, **v1.2.0 Preview**                                     
  Yo teams - msteams-react-base-component   v3.1.0                                                         
  Microsoft Graph Toolkit (MGT)             **v2.2.0 GA**                                                  
  ----------------------------------------- ------------------------------------------------------------- ------------------------------------------------
Additionally, 2 new Teams samples were delivered in the last 2 weeks. 
The host of this call was [David Warner
II](https://twitter.com/DavidWarnerII) (Catapult Systems) |
@DavidWarnerII.   Q&A takes place in chat throughout the call.

 


-   Join on the Viva Connections private preview! |
    [aka.ms/viva/connections/preview/register](https://aka.ms/viva/connections/preview/register)
-   **Feedback wanted:  Regarding PnP PowerShell** -- "What if we did
    not return classic CSOM objects from the cmdlets?"  Comments to: 
    @erwinvanhunen.    
-   **Register for Sharing is Caring Events**:

    -   First Time Contributor Session -- [June
        29th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session
        -- [May](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    -   PnP -- SPFx Developer Workstation Setup -- [June
        17th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
         
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [June
        24th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   AMA (Ask Me Anything) -- Microsoft Graph & MGT -- [June
        8th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xCOEtTWFJSREg2UFY2NkpPUk5GNk9YVS4u)
    -   AMA (Ask Me Anything) -- Microsoft Teams Dev - June
    -   First Time Presenter -- [June
        30th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- [May
        27th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u),
        [June
        16th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
    -   Maturity Model Practitioners -- [June
        15th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
-   PnP Office Hours -- 1:1 session -
    [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
-   PnP Buddy System - [Request a
    Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
-   Download the recurrent invite for this call
    -- <https://aka.ms/m365-dev-sig>
-   Call attention to your great work by using
    the [#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click) on
    Twitter.
**Microsoft Teams Development
Samples:  **(<https://aka.ms/TeamsSampleBrowser>)

-   **[Action
    Preview](https://github.com/pnp/teams-dev-samples/tree/main/samples/msgext-action-preview)
    -** [Markus Moeller](https://twitter.com/Moeller2_0) |@Moeller2_0

-   [**Teams Context Viewer
    tab**](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-context-viewer)
    **-** [Sébastien Levert](https://twitter.com/sebastienlevert) |
    [sebastienlevert](https://github.com/sebastienlevert)

## Demos

Demos delivered in this session

-   **Getting started with HTWOO UI -- Fluent Design in HTML and CSS**
    -- an open-source community driven Fluent UI driven framework that's
    just HTML, CSS and a bit of JS.   Simple to use in the Microsoft 365
    ecosystem, same branding as Fluent UI.   Complete component
    library - tables, typography, avatars, icons, dialogs and more.
     Steps through HTWOO install -- a npm package and 2 theme aware SPFx
    web parts.   Complete documentation and samples.

-   **Gain your users attention with the Microsoft Teams Activity Feed
    API** -- send activity notifications from both apps that live
    outside Teams and others (like static tabs) inside Teams, to Teams
    tabs, bots, chat.   Uses the activity feed notification APIs in
    Microsoft Graph.  Presenter review types of metadata on messages,
    requirements for sending defined activity type notifications, app
    registration, consent, manifest, notifications settings in Teams,
    etc.  Then steps through the code for simple and advanced
    notifications. 

-   **Deep linking from List Formatting to Power Automate solution** --
    Integrate lists, list formatting and Power Apps.  Achieve similar
    look and feel using same SVG icons in lists and Power App.  Call for
    list data from a Power App.  Launch a Power App and send mail from
    within a list.  Color SVG icons using fill properties in Inkscape
    SVG Editor.  Showed using code from 2 samples in this demo.      

     

Thank you for your work. Samples are often showcased in Demos.

## Topics

Topics covered in this call

-   PnP .NET library updates - [Bert
    Jansen](https://twitter.com/O365bert) (Microsoft) @O365bert
    - [5:50](https://youtu.be/y0diQu23g88?t=350)

-   PnP PowerShell updates -[ Erwin van
    Hunen](https://twitter.com/erwinvanhunen) (Valo Intranet)
    @erwinvanhunen - [8:21](https://youtu.be/y0diQu23g88?t=501)

-   yo Teams updates - [David Warner
    II](https://twitter.com/DavidWarnerII) (Catapult Systems)
    @DavidWarnerII - [10:00](https://youtu.be/y0diQu23g88?t=600)

-   Microsoft Graph Toolkit updates - [Nikola
    Metulev](https://twitter.com/metulev) (Microsoft) |
    @metulev - [10:31](https://youtu.be/y0diQu23g88?t=631)

-   Microsoft Teams Samples - [David Warner
    II](https://twitter.com/DavidWarnerII) (Catapult Systems)
    @DavidWarnerII - [13:38](https://youtu.be/y0diQu23g88?t=818)

-   **Demo:**  Getting started with HTWOO UI -- Fluent Design in HTML
    and CSS -- [Stefan Bauer](https://twitter.com/StfBauer) (N8D) |
    @StfBauer - [15:31](https://youtu.be/y0diQu23g88?t=931)

-   **Demo:**  Gain your users attention with the Microsoft Teams
    Activity Feed API -- [Thomas Gölles](https://twitter.com/thomyg)
    (Solvion) | @thomyg - [29:54](https://youtu.be/y0diQu23g88?t=1794)

-   **Demo:**  Deep linking from List Formatting to Power Automate
    solution -- [Chris Kent](https://twitter.com/theChrisKent) (DMI) |
    @theChrisKent
    -[ [44:55](https://youtu.be/y0diQu23g88?t=2695)][ ]

## Resources

Additional resources around the covered topics and links from the
slides.

-   Blog Post - [HTWOO UI launched -- Fluent Design in HTML and
    CSS](https://n8d.at/htwoo-ui-launched-fluent-design-in-html-and-css) 

-   Documentation: [ABOUT HTWOO UI](https://lab.n8d.studio/htwoo/) 

-   Repo: [HTWOO UI framework](https://github.com/n8design/htwoo) 

-   Samples: [htwoo-samples](https://github.com/n8design/htwoo-samples) 

-   [Documentation - ][Send activity feed
    notifications to users in Microsoft
    Teams](https://docs.microsoft.com/graph/teams-send-activityfeednotifications)

-   [Video - ][Microsoft Teams -- Use the
    teamwork Microsoft Graph
    endpoint](https://www.youtube.com/watch?v=G33bN7cl2QU&t=3536s)

-   [Documentation - ][Create deep
    links](https://docs.microsoft.com/microsoftteams/platform/concepts/build-and-test/deep-links)

-   [Graphics - ][Fluent UI Icon
    Search](https://www.flicon.io/)

-   [Sample - ][Person Mail To
    Link](https://github.com/pnp/List-Formatting/tree/master/column-samples/person-mailto)

-   [Sample - ][Launch Power App
    Button](https://github.com/pnp/List-Formatting/tree/master/column-samples/generic-launch-powerapp)

-   [[Blog post - ][Custom Icon Buttons
    in Power Apps with Hover
    Color](https://thechriskent.com/2021/05/27/custom-icon-buttons-in-power-apps-with-hover-color/)]

-   Editor - [Inkscape](https://inkscape.org/) - <https://inkscape.org>

-   PnP Weekly -- Episode 128 with guest [Katie
    Swanson](https://twitter.com/kswansondesign) (Microsoft) |
    @kswansondesign |
    [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-128/ba-p/2381362)
    |
    [podcast](https://pnpweekly.podbean.com/e/Microsoft-365-pnp-weekly-episode-128-24th-of-may-2021/)

-   Microsoft Teams Toolkit v2.2 | <https://aka.ms/teams-toolkit>

-   [Microsoft 365 Extensibility look book
    gallery](https://adoption.microsoft.com/extensibility-look-book?WT.mc_id=m365-24198-cxa) |
    aka.ms/m365/extensibility

-   [Microsoft Teams Samples
    Gallery](https://pnp.github.io/teams-dev-samples/) |
    aka.ms/teams-samples

## General resources

-   [Microsoft 365 PnP Community
    hub](https://techcommunity.microsoft.com/t5/microsoft-365-pnp/ct-p/Microsoft365PnP) |
    aka.ms/m365pnp/community 
-   Microsoft Graph Toolkit in Microsoft Learn
    | <https://aka.ms/learn-mgt>
-   Viva Connections <https://aka.ms/VivaConnections>
-   [SharePoint look
    book](https://lookbook.microsoft.com/?WT.mc_id=m365-24198-cxa)
-   [Yo Teams video training package](https://aka.ms/yoteams-training)
-   [.NET Standard 2.0 version of SharePoint Online CSOM
    API](https://developer.microsoft.com/microsoft-365/blogs/net-standard-version-of-sharepoint-online-csom-apis?WT.mc_id=m365-24198-cxa)
-   [Microsoft 365 community (PnP)
    videos](https://aka.ms/m365pnp-videos) | aka.ms/m365pnp-videos
-   [Microsoft Teams Toolkit for Visual Studio
    Code](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension)
-   [yo Teams](https://aka.ms/yoteams) | aka.ms/yoteams
-   Video - [Getting started using yo
    Teams](https://youtu.be/w0OrFkzNC10) | [Wictor
    Wilén](https://twitter.com/wictor) (Avanade)| @wictor
-   [Build a crisis management site to connect people and
    information](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/build-a-crisis-management-site-to-connect-people-and-information/ba-p/1216791?WT.mc_id=m365-24198-cxa)
-   [Developer
    documentation](https://aka.ms/spdev-docs) | <https://aka.ms/spdev-docs>
-   [PnP Power Shell](https://aka.ms/sppnp-powershell)
-   [SharePoint Modernization Partner
    Guidance](https://aka.ms/sppnp-modernization-partnerguidance) -
    Feedback welcome
-   Solution - [Building a modern search experiences with SharePoint
    Framework web parts](https://aka.ms/pnp-modern-search)
-   [Page transformation
    guidance](https://aka.ms/sppnp-pagetransformation)
-   [Page transformation
    videos](https://aka.ms/sppnp-pagetransformationvideos)
-   [Modernization scanner](https://aka.ms/sppnp-modernizationscanner)
-   [Microsoft 365 developer program
    site](https://developer.microsoft.com/office/dev-program?WT.mc_id=m365-24198-cxa) -
    Need to become a Tenant Admin to test look book capabilities? Get a
    Microsoft 365 E5 developer subscription (free tenant for 90 days)
-   [SharePoint Provisioning
    Service ](https://lookbook.microsoft.com/)- Easily provision
    look book designs to any tenant in the world
-   [SharePoint Provisioning templates on
    GitHub](https://github.com/SharePoint/sp-dev-provisioning-templates)
-   [PnP Provisioning Tenant Templates
    documentation](https://docs.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-tenant-templates?WT.mc_id=m365-24198-cxa)
-   [SharePoint Page Transformation webcast
    series](https://developer.microsoft.com/sharepoint/blogs/sharepoint-page-transformation-webcast-series?WT.mc_id=m365-24198-cxa)
-   [PnP Power Shell](https://aka.ms/sppnp-powershell)
-   [SharePoint Modernization
    Tools](https://github.com/SharePoint/sp-dev-modernization/tree/dev/Tools)

## Upcoming Calls | Recurrent Invites


-   **Microsoft Graph call --** June 1st at 8:00 am PDT |
    <https://aka.ms/microsoftgraphcall>
-   **SharePoint Framework call** -- June 3rdat 7:00 am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **SharePoint monthly call --** June 8th at 8:00am PDT |
    <https://aka.ms/sp-call>
-   **Office add-in monthly call --** June 9th at 8:00 am PDT |
    [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscommunitycall)
-   **Adaptive Cards monthly call --** June 10th at 9:00 am PDT |
    <https://aka.ms/adaptivecardscommunitycall>
-   **M365 General Dev call --** June 10th at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Microsoft Teams monthly call --** June 15th at 8:00 am PDT |
    <https://aka.ms/microsoftteamscommunitycall>
-   **Power Apps monthly call --** June 16th at 8:00 am PDT |
    <https://aka.ms/PowerAppsMonthlyCall>
-   **Microsoft Identity Platform --** June 17th at 9:00 am PDT |
    <https://aka.ms/IDDevCommunityCalendar> 
General Microsoft 365 Dev Special Interest Group bi-weekly calls are
targeted at anyone who's interested in the general Microsoft 365
development topics. This includes Microsoft Teams, Bots, Microsoft
Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core,
Site Designs, Power Automate, PowerApps, Column Formatting, list
formatting, etc. topics. More details on the Microsoft 365 community
from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome
community demos, if you are interested in doing a live demo in these
calls!
You can download recurrent invite from <https://aka.ms/m365-dev-sig>.
Welcome and join in the discussion. If you have any questions, comments,
or feedback, feel free to provide your input as comments to this post as
well. More details on the Microsoft 365 community and options to get
involved are available
from [https://aka.ms/m365pnp](https://aka.ms/sppnp).
*"Sharing is caring"*

------------------------------------------------------------------------

*Microsoft 365 PnP team, Microsoft - 28th of May 2021*
