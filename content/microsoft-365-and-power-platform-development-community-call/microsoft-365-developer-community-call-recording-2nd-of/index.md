---
title: "Microsoft 365 Developer Community Call recording -- 2nd of September, 2021"
date: 2021-09-03T03:45:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-2nd-september-call.png
tags: []
type: "regular"
---

## Call summary

Welcome back from summer holiday!  Have a look at Microsoft 365 tenant
-- [script samples gallery](https://aka.ms/script-samples) - s*cripts
for PowerShell and CLIs. * Sign up and attend one of a growing list of
events hosted by [Sharing is
Caring](https://pnp.github.io/sharing-is-caring/) this month.  Announced
the [PnP Recognition Program](https://aka.ms/m365pnp-recognition).  No
project releases this week, but as many are back from holidays, you can
surely expect releases soon.  
**Open-source project status:  (Bold indicates new this call)**
  ----------------------------------------- --------------------------------------------------- -----------------------------------------------
  **Project**                               **Current Version**                                 **Release/Status**
  PnP .NET Libraries - PnP Framework        v1.6.0 GA, PnP Provisioning Engine Schema v202103   Version 1.7.0 -- Late Summer 2021
  PnP .NET Libraries - PnP Core SDK         v1.3.0 GA                                           Version 1.4.0 -- Late Summer 2021
  PnP PowerShell                            v1.7.0 GA                                            
  Yo teams - generator-teams                v3.2.0 GA                                           v3.3.0 Preview soonish
  Yo teams - yoteams-build-core             v1.2.0 GA, v1.2.1 Preview                            
  Yo teams -- yoteams-deploy                v1.1.0 GA, v1.0.1 Preview                            
  Yo teams - msteams-react-base-component   v3.1.0                                               
  Microsoft Graph Toolkit (MGT)             v2.2.0 GA                                           Bug fixes and Updates, v2.3.0 later in August
  ----------------------------------------- --------------------------------------------------- -----------------------------------------------
There are 2 new Microsoft Teams samples this week.  Have you visited the
[Teams Samples wish list](https://aka.ms/teams-sample-wishlist)?  Need
an idea for a sample?  Consider collaborating with Microsoft Teams
Engineering to create a sample and earn a Credly badge.   The host of
this call was [David Warner II](https://twitter.com/DavidWarnerII)
(Catapult Systems) @DavidWarnerII.   Q&A takes place in chat throughout
the call.

## Actions

-   Create a Teams Sample - [Microsoft Teams Samples Wish
    list](https://github.com/pnp/teams-dev-samples/issues) -- 10
    opportunities to share your Teams Dev prowess with the community
    | [<https://aka.ms/teams-sample-wishlist>]{.underline}
-   Opt in to PnP Recognition Program
    | <https://aka.ms/m365pnp-recognition>
-   Register for Sharing is Caring Events:
    -   First Time Contributor Session -- [September
        21st](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session -- [October
        5th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u) 
    -   PnP -- SPFx Developer Workstation Setup -- TBS
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [September
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u) 
    -   Ask Me anything (AMA) -- Recognition Program -- [September
        7th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNzVJQTEyMkw4VVBIVjc3NE9PWDFDM1M3My4u)
    -   Ask Me anything (AMA) -- Script Samples -- [September
        14th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURjNZTDA4VEJGNUYyMVlCNkZUVzlYQ0FaQy4u)
    -   Ask Me Anything (AMA) -- Power Platform Development & Samples --
        [September
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNFJZNThMWFk0QlEzWFJNVE5aNVMzM1UwUi4u)
    -   Ask Me Anything (AMA) -- List Formatting -- [October
        5th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNTVHSFFMRDdDSjA0MklUSUtTQ0IxMFpPNS4u)
    -   First Time Presenter -- [October
        12th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- [September
        14th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u) 
    -   Maturity Model Practitioners -- [September
        21st](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
        and every 3rd Tuesday of month, 7:00am PT
    -   PnP Office Hours -- 1:1 session --
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    -   PnP Buddy System -- [Request a
        Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
-   Download the recurrent invite for this call
    -- <https://aka.ms/m365-dev-sig>
-   Call attention to your great work by using
    the [#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click) on
    Twitter.
**Microsoft Teams Development
Samples:  **(<https://aka.ms/TeamsSampleBrowser>)

-   **[Teams Tab with SSO and Microsoft Graph Toolkit
    usage](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-mgt-person)** -
    [Markus Möller](https://twitter.com/Moeller2_0) (Avanade) |
    @Moeller2_0
-   **[Teams Tab Single Sign-on (SSO)
    Sample](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-sso) **(updated)
    **-** Doğan Erişen (Microsoft)

**Microsoft Power Platform
Samples:  **([https://aka.ms/powerplatform-samples)](https://aka.ms/powerplatform-samples)

-   No new Power Platform samples this week

**Script
Samples: ** ([https://aka.ms/script-samples)](https://aka.ms/script-samples)

-   No new Script samples this week

## Demos

Demos delivered in this session

-   **SharePoint Approval Workflow Status Tracking with Column
    Formatting --** create dynamic multi-step expense approval workflow
    in SharePoint leveraging a Power Automate flow.   Very deliberate
    step-by-step explanation of list creation and of flow/process.
     Create 2 SharePoint lists -- Expense Types and Expense Reports
    (with column and view formatting + list form configuration), Add the
    approval process flow (a sample) to Power Automate, done!    Clear
    visual status in UI to track output and status of workflows.

-   **Build your first conversational chatbot for Teams without any
    development using --** in Bot Framework Composer, use the
    CoreWithLanguage bot template with triggers calling an Azure Bot. 
    Stephen defines various elements to have before building.  Add
    triggers to new bot -- GetREportsDialog, add OAuth login service
    connection, store turn.tokens, and install
    Microsoft.Bot.Components.Graph package for more action options,
    deploy app to Azure.  Create new Microsoft Teams app in App Studio,
    add the Azure Bot to a Channel.   

-   **Updates on the Independent Publisher Connectors for Power Platform
    --** connectors can be submitted by anyone in GitHub.com and they
    are subsequently certified by Microsoft.  Since July 19th, 8
    connectors have been submitted/certified, 11 in process.   Quick
    demo of fun dogs API -- the Placedog connector.  A Power Apps Canvas
    app displays 12 dog photos.  Connector functionality - get a dog
    photo, store it in SharePoint, and make URL available to the Power
    App.         

Thank you for your work. Samples are often showcased in Demos.

## Topics

Topics covered in this call

-   PnP .NET library updates - [Bert
    Jansen](https://twitter.com/O365bert) (Microsoft)
    @O365bert - [5:57](https://youtu.be/qsr-OspeYug?t=357)

-   PnP PowerShell - [Bert Jansen](https://twitter.com/O365bert)
    (Microsoft) @O365bert - [7:30](https://youtu.be/qsr-OspeYug?t=450)

-   yo Teams updates - [Paolo Pialorsi](https://twitter.com/paolopia)
    (PiaSys.com) @paolopia - [8:22](https://youtu.be/qsr-OspeYug?t=502)

-   Microsoft Graph Toolkit updates - [Beth
    Pan](https://twitter.com/beth_panx) (Microsoft)
    | [beth-panx](https://github.com/beth-panx) - [9:23](https://youtu.be/qsr-OspeYug?t=563)

-   Microsoft Teams Samples - [Bob
    German](https://twitter.com/Bob1German) (Microsoft) | @Bob1German -
    [11:24](https://youtu.be/qsr-OspeYug?t=684)

-   Microsoft Power Platform Samples - [April
    Dunnam](https://twitter.com/aprildunnam) (Microsoft) | @aprildunnam
     - [12:45](https://youtu.be/qsr-OspeYug?t=765)

-   **Demo:**  SharePoint Approval Workflow Status Tracking with Column
    Formatting - [Reza Dorrani](https://twitter.com/rezadorrani)
    (Catapult) |
    [rdorrani](https://github.com/rdorrani) -
    [15:16](https://youtu.be/qsr-OspeYug?t=916)

-   **Demo:**  Build your first conversational chatbot for Teams -
    [Stephan Bisser](https://twitter.com/stephanbisser) (Solvion) |
    @stephanbisser - [34:39](https://youtu.be/qsr-OspeYug?t=2079)

-   **Demo:**
-   Updates on Independent Publisher Connectors for Power
    Platform - [Natalie
    Pienkowska](https://twitter.com/NataliePienkow1)[ (Microsoft) |
    @NataliePienkow1 and ][Troy
    Taylor](https://twitter.com/troystaylor)[ (Hitachi Solutions) |
    [troystaylor](https://github.com/troystaylor) -
    [45:46](https://youtu.be/qsr-OspeYug?t=2746)]



## Resources

Additional resources around the covered topics and links from the
slides.

-   Repo --
    [rdorrani/SharePoint](https://github.com/rdorrani/SharePoint) 

-   Playlist - [SharePoint List
    Formatting](https://www.youtube.com/playlist?list=PLTyFh-qDKAiE7C_2lVNAPzgHXsBykG0Tf) 

-   [Documentation - ][Bot Framework
    Composer
    documentation](https://docs.microsoft.com/composer/)

-   [[Documentation - ][Add
    authentication to your Teams
    bot](https://docs.microsoft.com/microsoftteams/platform/bots/how-to/authentication/add-authentication?tabs=dotnet%2Cdotnet-sample)]

-   Documentation  - [Create your
    project](https://docs.microsoft.com/microsoftteams/platform/get-started/first-app-bot?tabs=vscode#create-your-project) 

-   [Connectors - ][Microsoft Power
    Platform
    Connectors](https://github.com/microsoft/PowerPlatformConnectors)

-   [Demo - ][Publish a connector to the
    Power Platform](https://youtu.be/ulTBvCHw8MU)[ -- [Natalie
    Pienkowska](https://twitter.com/NataliePienkow1) (Microsoft)  |
    @NataliePienkow1]

-   [[How I Make Power Platform Independent Publisher Custom
    Connectors](https://www.troystaylor.com/how-i-make-power-platform-independent-publisher-custom-connectors)
    - [Troy Taylor](https://twitter.com/troystaylor) (Hitachi Solutions)
    |
    [troystaylor](https://github.com/troystaylor)]

## General resources

-   Samples - [Power Platform
    Samples](https://aka.ms/powerplatform-samples) | [aka.ms/](https://aka.ms/powerplatform-samples)[powerplatform](https://aka.ms/powerplatform-samples)[-samples](https://aka.ms/powerplatform-samples)
-   Microsoft 365 tenant -- [Script Samples
    Gallery](https://aka.ms/script-samples) | aka.ms/script-samples
-   [Microsoft Teams Samples
    Gallery](https://pnp.github.io/teams-dev-samples/) |
    aka.ms/teams-samples
-   [Microsoft 365 Extensibility look book
    gallery](https://adoption.microsoft.com/extensibility-look-book?WT.mc_id=m365-24198-cxa) |
    aka.ms/m365/extensibility
-   Archives - Microsoft 365 PnP Weekly
    - [Videos](https://www.youtube.com/playlist?list=PLR9nK3mnD-OVYI-St_CBiFfuL4CZbBpkC), [Podcasts](https://pnpweekly.podbean.com/)  
-   PnP Teams Quickstart
    | [aka.ms/pnp-teams-quickstart](https://aka.ms/pnp-teams-quickstart)
-   Microsoft Teams Toolkit v2.2 | <https://aka.ms/teams-toolkit>
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

-   **Microsoft 365 platform call** -- September 7that 8:00 am PDT
    | <https://aka.ms/m365-dev-call>
-   **Office add-in monthly call** -- September 8th at 8:00 am PDT
    | <https://aka.ms/officeaddinscall>
-   **SharePoint Framework call** -- September 9th at 7:00 am PDT
    | <https://aka.ms/spdev-spfx-call>
-   **Adaptive Cards monthly call** -- September 9th at 9:00 am PDT
| <https://aka.ms/adaptivecardscommunitycall>

-   **Power Apps monthly call** -- September 15th at 8:00 am PDT
    | <https://aka.ms/PowerAppsMonthlyCall>
-   **Microsoft 365 platform call** -- September 16th at 7:00 am PDT
    | <https://aka.ms/m365-dev-sig>
-   **Microsoft Identity Platform call** -- September 16th at 9:00 am
    PDT | <https://aka.ms/IDDevCommunityCalendar>
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

*Microsoft 365 PnP team, Microsoft - 3rd of September 2021*

