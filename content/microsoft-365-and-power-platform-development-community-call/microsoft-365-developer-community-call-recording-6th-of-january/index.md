---
title: "Microsoft 365 Developer Community Call recording -- 6th of January, 2021"
date: 2022-01-07T01:01:00-05:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-6th-jan.png
tags: []
type: "regular"
---




## Call summary




Welcome to the New Year.  It's a great time to visit the Microsoft 365
tenant -- [script samples gallery](https://aka.ms/script-samples) (129
scenarios and 173 scripts) including recently added Teams PowerShell
support!  Sign up and attend an AMA and other events this month hosted
by [Sharing is Caring](https://pnp.github.io/sharing-is-caring/).  At
the same time, sign up for the [PnP Recognition
Program](https://aka.ms/m365pnp-recognition). Released **PnP Core SDK**
v1.5.0 and **PnP PowerShell** v1.9.0, and much work is being done on
other projects.  Check out the TeamsFx authentication provider preview
in **MGT**!  To see current releases and latest updates/nightly builds,
access the Repos via the links in table below.  There were 7 new/updated
script samples delivered this week.  

## Open-source project status

(**Bold** indicates new this call)

  ----------------------------------------------------------------------------------------------------------------- --------------------------------------------------------- -----------------------------------------------------------------------------------------------------------
  **Project**                                                                                                       **Current Version**                                       **Release/Status**
  PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)                                         v1.8.0 GA with .NET 6.0 support added                     **Prepping v1.9**
  PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)                                      v1.5.0 GA with .NET 6.0 support added                     **Prepping v1.6**
  [PnP PowerShell](https://github.com/pnp/PnP-PowerShell)                                                           v1.9.0 GA                                                 In progress: V2 POC, Prepping for v1.8, nightly releases
  [Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)         v3.5.0 GA                                                 v4.0.0-next
  [Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)   v1.5.0 GA, Next: v1.6.0-next.1                             
  [Yo teams -- yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)          v1.1.0 GA                                                  
  [Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)            v3.1.1                                                     
  [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)                        v2.3.1 GA, **TeamsFx authentication provider preview!**   Preparing v2.3.1 release, working on v3.0.0 - Aligning all Toolkit components to Fluent UI Web Components
  ----------------------------------------------------------------------------------------------------------------- --------------------------------------------------------- -----------------------------------------------------------------------------------------------------------
{{< notice note>}}
While version releases are periodic, nightly releases are nightly!  Subscribe to nightly releases for the latest capabilities.
{{< /notice >}}



The host of this call was [David Warner
II](https://twitter.com/DavidWarnerII) (Catapult Systems) |
@DavidWarnerII.   Q&A takes place in chat throughout the call.

## Actions





-   Opt into PnP Recognition Program
    | <https://aka.ms/m365pnp-recognition>
-   Join us at the next** Microsoft 365 platform call 11th of January
    @ 8 AM PT**
    -   Latest news from Microsoft engineering on Microsoft 365 topics
    -   Demos: 
        -   **Rajdeep Chandra** -- Introduction to Microsoft Graph
            connectors SDK
        -   **Wajeed Shaikh** -- Building a Microsoft Teams bot for
            scheduling tasks and to get reminders
        -   **Sébastien Levert** -- Introduction to Microsoft Graph
            Toolkit control
-   **Register for Sharing is Caring Events: **
    -   Ask me anything (AMA) PnP Search -- [Tuesday, January 11th, 9am
        PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOFpKRjdQQVlWOEdaRlk2WkI3WUVQWFVNUC4u)
    -   First Time Contributor Session -- [Tuesday, January 25th, 2pm
        PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
    -   Community Docs Session -- 2022 Sessions Coming Soon  
    -   Power Platform Samples -- First Time Contributor -- [Tuesday,
        January 18th, 1pm
        PST](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMTFJWFFGVUxBNUFZQjZWRUdaOE5BMFkwNS4u)
    -   PnP -- SPFx Developer Workstation Setup -- [Tuesday, February
        8th, 2pm
        PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [Wednesday, January 26th, 7am
        PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   First Time Presenter -- [Wednesday, February 9th, 9am
        PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- [Tuesday, February 15th, 2pm
        PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
    -   Maturity Model Practitioners -- [Tuesday, January 18th, 7am
        PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u) (every
        3rd Tuesday of month, 7:00am PT)
    -   Getting Started with Viva Connection ACEs (2-part session) --
        February 2022
    -   PnP Office Hours -- 1:1 session
        -- [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    -   PnP Buddy System -- [Request a
        Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
-   Download the recurrent invite for this call
    -- <https://aka.ms/m365-dev-sig>
-   Call attention to your great work by using
    the [#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click) on
    Twitter.
**Microsoft Teams Development
Samples: **(<https://aka.ms/TeamsSampleBrowser>)

-   no samples this week
**Microsoft Power Platform
Samples: **([https://aka.ms/powerplatform-samples)](https://aka.ms/powerplatform-samples)

-   no samples this week
**Script
Samples: **([https://aka.ms/script-samples)](https://aka.ms/script-samples)

6 new scenarios and 1 script update contributed by

-   [Rodrigo Pinto](https://twitter.com/ScoutmanPt) (Storm Technology) |
    @ScoutmanPt
-   [Reshmee Auckloo](https://twitter.com/ReshmeeAuckloo) |
    @reshmeeauckloo
-   [Kasper Larsen](https://twitter.com/kasperbolarsen) |
    @kasperbolarsen
-   Jiten Parmar

Blog: [Getting started with PnP Script
Samples](https://aka.ms/script-samples/getting-started)
-- aka.ms/script-samples/getting-started
-- Many thanks!

## Demos

Demos delivered in this session

**Building enterprise solutions with Power Platform - Things to do and
not to do** -- based on learnings from creating Teams ProvisionGenie
that uses Power Apps Canvas app as UI, Dataverse as relational database
and Azure Logic Apps to handle provisioning, Power Platform and
supporting technologies are great, but plan differently when creating
enterprise ready solutions.  Optimize developer experience, performance
and security by using right tool for job.  Don'ts and recommended do's
for process flows, identity management, and database presented. 

**SharePoint site provisioning with Microsoft Teams Notifications using
Bot Framework** -- see how the PnP Framework (containing PnP
Provisioning engine) is used to provision a new site based on the PnP
template.  Azure provisioning web job is triggered by a queue message
from a custom site template (previously known as site design).
 Microsoft Teams bot pushes proactive notifications about current
provisioning state to the configured channel via Adaptive Card updates. 
Notifications are electively disabled/enabled from card. 

**Updates on Independent Publisher Connectors & Coinbase Connector
Demo** --

49 connectors in production, 34 in pipeline today!  The Coinbase
platform allows anyone to get crypto exchange rates, currencies, and
current crypto market rates at a point in time.  This connector was
built by a non-developer in a Power Apps sandbox.  Required creating
first pull request and working through publishing process.  Canvas app
calls a flow that uses connector to get currency information.   
Thank you for your work. Samples are often showcased in Demos.   
Request a Demo spot on the call <https://aka.ms/m365pnp/request/demo>

## Topics

Topics covered in this call

-   PnP .NET library updates - [Bert
    Jansen](https://twitter.com/O365bert) (Microsoft) | @O365bert --
    [6:50](https://youtu.be/25L63KGPru0?t=410)

-   PnP PowerShell updates - [Bert Jansen](https://twitter.com/O365bert)
    (Microsoft) |
    @O365bert -- [8:54](https://youtu.be/25L63KGPru0?t=534)

-   yo Teams updates - [David Warner
    II](https://twitter.com/DavidWarnerII) (Catapult Systems) |
    @DavidWarnerII -- [9:45](https://youtu.be/25L63KGPru0?t=585)

-   Microsoft Graph Toolkit updates - [David Warner
    II](https://twitter.com/DavidWarnerII) (Catapult Systems) |
    @DavidWarnerII -- [10:19](https://youtu.be/25L63KGPru0?t=619)

-   Microsoft Script Samples - [Paul
    Bullock](https://twitter.com/pkbullock) (CaPa Creative Ltd) |
    @pkbullock -- [2:40](https://youtu.be/25L63KGPru0?t=160)

-   Microsoft Teams Samples - [Bob
    German](https://twitter.com/Bob1German) (Microsoft) |
    @Bob1German -- [10:58](https://youtu.be/25L63KGPru0?t=658)

-   Microsoft Power Platform Samples - [April
    Dunnam](https://twitter.com/aprildunnam) (Microsoft) | @aprildunnam
    -- [12:19](https://youtu.be/25L63KGPru0?t=739)

-   **Demo 1**:  Building enterprise solutions with Power Platform -
    Things to do and not to do -- [Luise
    Freese](https://twitter.com/LuiseFreese)[ |
    @LuiseFreese ]--
    [14:24](https://youtu.be/25L63KGPru0?t=864)

-   **Demo 2**:  SharePoint site provisioning with Microsoft Teams
    Notifications using Bot Framework -- [Sergei
    Sergeev](https://twitter.com/sergeev_srg) (Mastaq) |
    @sergeev_srg -- [27:22](https://youtu.be/25L63KGPru0?t=1642)

-   **Demo 3**:  Updates on Independent Publisher Connectors & Coinbase
    Connector Demo -- [Natalie
    Pienkowska](https://twitter.com/NataliePienkow1) (Microsoft) |
    @NataliePienkow1 & [Roy Paar](https://twitter.com/RoyPaar)
    (Microsoft) | @RoyPaar
    ** ** ** **

    -- [40:50](https://youtu.be/25L63KGPru0?t=2450)


## Resources

Additional resources around the covered topics and links from the
slides.

-   **D1**:  Site --
    [ProvisionGenie](https://provisiongenie.com/)

-   **D1**:  Blog -- [Luise
    Freese](https://www.m365princess.com/)

-   [[**D2**:  ]]Article
    -- [Building PnP Provisioning notifier
    Bot](https://spblog.net/post/2022/01/04/building-pnp-provisioning-notifier-bot)

-   [**D2**:  ]Repo - [Sample code which
    demonstrates how to use MS Teams bot to send PnP Provisioning
    progress
    notificatio\...](https://github.com/spblog/pnp-provision-teams-bot-notifier) 

-   [**D2**:  ]Repo - [PnP
    Framework](https://github.com/pnp/pnpframework) 

-   [**D3**:  ]Repo -
    [PowerPlatformConnector --
    Coinbase](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Coinbase) 

-   [**D3**:  ]paconn 0.0.19 - [Microsoft
    Power Platform Connectors CLI](https://pypi.org/project/paconn/) 

-   [**D3**:  ]API -- [Coinbase
    Introduction](https://developers.coinbase.com/api/v2#introduction) 

-   [**D3**:  ]Sandbox -- [Your
    Environment](https://make.preview.powerapps.com/) | (resolves to
    your organizations Power Apps environment)

-   [**D3**:  ]Connectors - [Welcome to
    the Independent Publisher Connector
    Directory!](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors)

## General resources

-   Script Samples - [Getting started with PnP Script
    Samples](https://aka.ms/script-samples/getting-started)[
    aka.ms/script-samples/getting-started]
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


  
- **Microsoft 365 platform call** -- January 11th at 8:00 am PST
    | <https://aka.ms/m365-dev-call>
-   **Office add-in monthly call** -- January 12th at 8:00 am PST
    | <https://aka.ms/officeaddinscall>
-   **SharePoint Framework call** -- January 13th at 7:00 am PST
    | <https://aka.ms/spdev-spfx-call>
-   **Adaptive Cards monthly call** --January 13th at 9:00 am PST
| <https://aka.ms/adaptivecardscommunitycall>

-   **Power Apps monthly call**-- January 19th at 8:00 am PST
    | <https://aka.ms/PowerAppsMonthlyCall>
-   **M365 General Dev call** -- January 20th at 7:00 am PST
    | <https://aka.ms/m365-dev-sig>
-   **Microsoft Identity Platform call** -- January 20th at 9:00 am
    PST | <https://aka.ms/IDDevCommunityCalendar>
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

*Microsoft 365 PnP team, Microsoft - 7th of January 2022*
