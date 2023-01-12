---
title: "Microsoft 365 Developer Community Call recording -- 14th of October, 2021"
date: 2021-10-15T12:41:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: []
images:
- images/recording-14th-pnp-generic.png
tags: []
type: "regular"
---




## Call summary

Updated [Viva Connections public developer
preview](https://aka.ms/viva/connections/developer/preview)!  Have a
look at Microsoft 365 tenant -- [script samples
gallery](https://aka.ms/script-samples) (101 scenarios and 135 scripts,
using CLI for Microsoft 365, PnP PowerShell, SPO Management Shell
tooling and more...). Register Today for Hacktoberfest 2021 \...Begins
October 1.   Sign up and attend a session in October -- November hosted
by [Sharing is Caring](https://pnp.github.io/sharing-is-caring/).  Sign
up for the [PnP Recognition
Program](https://aka.ms/m365pnp-recognition).  Dial into the [Microsoft
365 platform call](https://aka.ms/m365-dev-call) on October 19th @ 8 AM
PT.   Project releases this week include **PnP Core SDK** v1.4.0 GA,
**PnP PowerShell** v1.8.0GA, **Yo teams - generator-teams** - v3.3.1
GA.     
**Open-source project status:  (Bold indicates new this call)**

  ----------------------------------------- ----------------------------------------------------------------------- ----------------------------------------------------------
  **Project**                               **Current Version**                                                     **Release/Status**
  PnP .NET Libraries - PnP Framework        v1.6.0 GA, PnP Provisioning Engine Schema v202103                       Version 1.7.0 -- Early Autumn 2021, v1.8.0 Winter 2021
  PnP .NET Libraries - PnP Core SDK         **v1.4.0 GA**, PnP Transformation Framework: Public Preview released!   Prepping for v1.5.0
  PnP PowerShell                            **v1.8.0 GA**                                                           In progress: V2 POC, Prepping for v1.8, nightly releases
  Yo teams - generator-teams                **v3.3.1 GA (Support for Teams JS SDK 1.11)**                            
  Yo teams - yoteams-build-core             v1.3.0 GA                                                                
  Yo teams -- yoteams-deploy                v1.0.1 GA                                                                
  Yo teams - msteams-react-base-component   v3.1.0                                                                   
  Microsoft Graph Toolkit (MGT)             v2.3.0 GA                                                               Working on v3.0.0
  ----------------------------------------- ----------------------------------------------------------------------- ----------------------------------------------------------
**\* Note:  While version releases are periodic, nightly releases are
nightly!  Subscribe to nightly releases for the latest capabilities. 
    **

As well, there were 17 script samples, 2 Teams samples and 3 Power
Platform Samples this week.  The host of this call was [David Warner
II](https://twitter.com/DavidWarnerII) (Catapult Systems) |
@DavidWarnerII.   Q&A takes place in chat throughout the call.

## Actions




-   Register today for Hacktoberfest 2021
    -- [https://hacktoberfest.digitalocean.com](https://hacktoberfest.digitalocean.com/)
-   Visit Teams, Graph Toolkit, and other project Repos/sample
    repositories for issues that can be submitted in the Repo and
    recognized by Hactoberfest.
-   Register for Microsoft Ignite (Digital event) - November 2-4,
    2021- [https://ignite.microsoft.com](https://ignite.microsoft.com/)
-   Opt in to PnP Recognition Program
    | <https://aka.ms/m365pnp-recognition>
-   **Register for Sharing is Caring Events:**
    -   First Time Contributor Session -- [November
        3rd](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session -- [November
        17th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)  
    -   Power Platform Samples -- First Time Contributor - [October
        27th](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMTFJWFFGVUxBNUFZQjZWRUdaOE5BMFkwNS4u)
    -   PnP -- SPFx Developer Workstation Setup -- [November
        16th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [November
        30th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)  
    -   Ask Me Anything (AMA) -- PnP PowerShell -- [October
        26th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMElCOUdaTkUwQVI2UVBITExPSTU3WjJRTS4u)
    -   First Time Presenter -- TBS
    -   More than Code with VSCode -- [November
        9th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)  
    -   Maturity Model Practitioners -- [October
        19th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u) 
        (every 3rd Tuesday of month, 7:00am PT)
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

-   **[bot meeting lifecycle feedback - Microsoft Teams
    App](https://github.com/pnp/teams-dev-samples/tree/main/samples/bot-meeting-lifecycle-feedback)** -
    [Markus Möller](https://twitter.com/Moeller2_0) (Avanade) |
    @Moeller2_0
-   **[TeamsLeaderboard](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-blazor-leaderboard)** -
    [Thomy Gölles](https://twitter.com/thomyg) (Solvion) | @thomyg
**Microsoft Power Platform
Samples:  **([https://aka.ms/powerplatform-samples)](https://aka.ms/powerplatform-samples)

-   **\*Request Review and Approval -** [Lindsay
    Shelton](https://twitter.com/LShelton_Tech) | @LShelton_Tech
-   **\*Hide SharePoint Page Title -** [Michel
    Mendes](https://twitter.com/michelcarlo) | @michelcarlo
-   **\*Collect Feedback Workflow -** [April
    Dunnam](https://twitter.com/aprildunnam) | @aprildunnam

[\*These latest samples should show within 24 hours of date of this
call]{style="font-size: 10.5pt; font-family: 'Segoe UI',sans-serif;"}
**Script
Samples: ** ([https://aka.ms/script-samples)](https://aka.ms/script-samples)

-   11 New Samples + 6 Updated Samples🤩  -- WOW!  Contributed by
    -   [Valeras Narbutas](https://twitter.com/ValerasNarbutas) |
        @ValerasNarbutas
    -   [Chandani Prajapati](https://twitter.com/Chandani_SPD) |
        @Chandani_SPD
    -   [Adam Wójcik](https://twitter.com/Adam25858782) | @Adam25858782
    -   [Reshmee Auckloo](https://twitter.com/reshmeeauckloo) |
        @reshmeeauckloo
    -   [Dipen Shah](https://twitter.com/Dips_365) | @Dips_365

-- Thank you
   

## Demos

Demos delivered in this session

-   **Introduction to the new PnP Transformation Framework --** next
    step in the evolution of the PnP Modernization Framework is the PnP
    Transformation Framework (Public Preview) -- for migrating content
    from any CMS (data source provider) to SharePoint online modern with
    the assistance of in-memory abstraction (virtual layout of page) and
    web part mapping providers.  Not for migrating content, but for
    transforming content presentation to modern.   Targeting RC end
    November, GA end 2021. 

-   **Teams Meeting App -- Record and playback attendee names --** for
    pronunciation purposes, capture and subsequently hear upon demand, a
    meeting participant's name.  Start by creating a meeting and install
    Teams app into the meeting.  See experience in UI from scheduler and
    participant perspectives.  Understand usage prerequisites,
    pre-meeting and in-meeting experiences, and step through core code -
    Teams manifest, handling device types, meeting status, custom audio
    control.

-   **Feedback bot using the new Adaptive Card capabilities --** this
    bot functional in Microsoft Teams and Outlook (Universal actions),
    showcases 3 Adaptive Card features - **Sequential workflow**
    (concurrently awaits/tracks action from initiator and each
    participant), **Up-to-date cards** (real-time refresh across all
    users' cards) and **Contextual views** (Reader's view changes based
    on role).  Sample created with node JS/Type script and Yeoman
    Generator for Bot v4.  Step through well commented code.      

Thank you for your work. Samples are often showcased in Demos.   
Request a Demo spot on the call <https://aka.ms/m365pnp/request/demo>

## Topics

Topics covered in this call

-   PnP .NET library updates - [Bert
    Jansen](https://twitter.com/O365bert) (Microsoft) | @O365bert --
    [5:36](https://youtu.be/f4NrenOuADg?t=336)

-   PnP PowerShell - [Erwin van
    Hunen](https://twitter.com/erwinvanhunen) (Valo Intranet) |
    @erwinvanhunen -- [7:08](https://youtu.be/f4NrenOuADg?t=428)

-   yo Teams updates - [David Warner
    II](https://twitter.com/DavidWarnerII) (Catapult Systems)
    @DavidWarnerII -- [8:55](https://youtu.be/f4NrenOuADg?t=535)

-   Microsoft Graph Toolkit updates - [Beth
    Pan](https://twitter.com/beth_panx) (Microsoft)
    [beth-panx](https://github.com/beth-panx) -- [9:29](https://youtu.be/f4NrenOuADg?t=569)

-   Microsoft Script Samples -  [Paul
    Bullock](https://twitter.com/pkbullock) (CaPa Creative Ltd) |
    @pkbullock -- [2:03](https://youtu.be/f4NrenOuADg?t=123)

-   Microsoft Teams Samples -[ Bob
    German](https://twitter.com/Bob1German) (Microsoft)
    @Bob1German -- [10:58](https://youtu.be/f4NrenOuADg?t=658)

-   Microsoft Power Platform Samples - [April
    Dunnam](https://twitter.com/aprildunnam) (Microsoft) |
    @aprildunnam -- [12:20](https://youtu.be/f4NrenOuADg?t=740)

-   **D1:**  Introduction to the new PnP Transformation Framework --
    [Bert Jansen](https://twitter.com/O365Bert) | @O365Bert & [Paolo
    Pialorsi](https://twitter.com/PaoloPia) | @PaoloPia --
    [14:29](https://youtu.be/f4NrenOuADg?t=869)

-   **D2:**  Teams Meeting App -- Record and playback attendee names --
    [Markus Möller](https://twitter.com/Moeller2_0) | @ Moeller2_0 --
    [29:04](https://youtu.be/f4NrenOuADg?t=1744)

-   **D3:**  Feedback bot using the new Adaptive Card capabilities --
    [Rabia Williams](https://twitter.com/williamsrabia) |
    @williamsrabia -- [42:50](https://youtu.be/f4NrenOuADg?t=2570)



## Resources

Additional resources around the covered topics and links from the
slides.

-   D1:  Article - [Introducing the New Microsoft 365 PnP Transformation
    Framework](https://practical365.com/introducing-the-new-microsoft-365-pnp-transformation-framework/) 

-   D1:  Tools - [PnP Core SDK](https://github.com/pnp/pnpcore) 

-   D2:  Article - [Meeting apps in Microsoft Teams (1) --
    Pre-meeting](https://mmsharepoint.wordpress.com/2021/09/07/meeting-apps-in-microsoft-teams-1-pre-meeting/) 

-   D2:  Sample - [tab meeting record name - Microsoft Teams
    App](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-meeting-record-name) 

-   D2:  Documentation - [Apps for Teams
    meetings](https://docs.microsoft.com/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings) 

-   D3:  Article - [Universal Actions for Adaptive Cards in a NodeJs
    project](https://rabiawilliams.com/teams/uam-bot/)

-   D3:  Sample - [Card Bot - Bot showcasing the Adaptive Card Universal
    Action Model in
    Node/TypeScript](https://github.com/pnp/teams-dev-samples/tree/main/samples/bot-uam-cardbot) 

-   D3:  Documentation - [Universal Actions for Adaptive
    Cards](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/cards/universal-actions-for-adaptive-cards/overview?WT.mc_id=m365-42737-rwilliams&tabs=mobile) 

-   D3:  Documentation - [Bots and
    SDKs](https://docs.microsoft.com/microsoftteams/platform/bots/bot-features#bots-with-the-microsoft-bot-framework?WT.mc_id=m365-42737-rwilliams&tabs=mobile) 

-   D3:  Samples -
    [BotBuilder-Samples](https://github.com/Microsoft/BotBuilder-Samples/tree/main/samples/javascript_nodejs) 

-   D3:  Demo - [TCS' Incident Management Teams app integrates Universal
    Actions for Adaptive
    Cards](https://www.youtube.com/watch?v=FaBGvnAzAS4) 

-   **PnP Weekly -- Episode 138** (October 11th) with Germany-based
    Office Apps and Services MVP, consultant, developer [Luise
    Freese](https://twitter.com/LuiseFreese) | @LuiseFreese and
    Belgium-based SharePoint/Power Platform developer at Qubix, [Carmen
    Ysewijn](https://twitter.com/CarmenYsewijn) | @CarmenYsewijn
    | [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-138-carmen-ysewijn-qubix-and/ba-p/2834568) | [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-138-%E2%80%93-11th-of-october-2021/)


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


-   **Microsoft 365 platform call** -- October 19th at 8:00 am PDT
    | <https://aka.ms/m365-dev-call>
-   **Power Apps monthly call**-- October 20th at 8:00 am PDT
    | <https://aka.ms/PowerAppsMonthlyCall>
-   **SharePoint Framework call** -- October 21st at 7:00 am PDT
    | <https://aka.ms/spdev-spfx-call>
-   **Microsoft Identity Platform call** -- October 21st at 9:00 am
    PDT | <https://aka.ms/IDDevCommunityCalendar>
-   **M365 General Dev call** -- October 28th at 7:00 am PDT
    | <https://aka.ms/m365-dev-sig>
-   **Office add-in monthly call** -- November 10th at 8:00 am PDT
    | <https://aka.ms/officeaddinscall>
-   **Adaptive Cards monthly call** **-- **November 11th at 9:00 am
    PDT | <https://aka.ms/adaptivecardscommunitycall>
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

------------------------------------------------------------------------
*"Sharing is caring"*

*Microsoft 365 PnP team, Microsoft - 15th of October 2021*
