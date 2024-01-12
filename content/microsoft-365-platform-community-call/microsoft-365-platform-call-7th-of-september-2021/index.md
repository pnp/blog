---
title: "Microsoft 365 Platform Call -- 7th of September, 2021"
date: 2021-09-08T06:17:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 platform call"]
images:
- images/7th-sep-platform-call-recording.png
tags: []
type: "regular"
---

Microsoft 365 Platform Community Call - weekly community call recording
from September 7th, is now available from the Microsoft 365 Community
YouTube channel at <https://aka.ms/m365pnp-videos>. 

**Call Summary**

Welcome to the weekly call focused on capabilities of the Microsoft 365
platform.   New to Microsoft 365 Platform development?  You are
encouraged to register at [Microsoft 365 Developer
Program](https://aka.ms/m365/devprogram) for free E5 developer tenant
and other assets.   Visit the new [Microsoft 365 sample
gallery](https://aka.ms/m365/samples) with more than 500 samples from
Microsoft and community.  Sign up and attend one of a growing list of
events hosted by [Sharing is
Caring](https://pnp.github.io/sharing-is-caring/) in September.  Tune
into the weekly [Microsoft 365 Developer
Podcast](https://m365devpodcast.com) focused  exclusively on Microsoft
365 dev topics -- hosted by Jeremy Thake (Microsoft) and Paul Schaeflein
(Addin365).   View the [Microsoft 365 Developer
blog](https://aka.ms/m365dev/blog) for the latest news in last 7 days
from Microsoft on Microsoft 365 platform.  The host of this call was
[Brian T. Jackett](https://twitter.com/BrianTJackett) (Microsoft) |
@BrianTJackett.   Q&A takes
place in chat throughout the call.

**Microsoft 365 Platform News Flash**

-   Updates for Microsoft Teams bots in Multi-Geo environments
-   Changes to the Microsoft 365 usage reports API

-   Opt in to PnP Recognition Program
    | <https://aka.ms/m365pnp-recognition>
-   Register for Sharing is Caring Events:
    -   First Time Contributor Session -- [September
        21st](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u) (EMEA,
        APAC & US friendly times available)
    -   Community Docs Session -- [October
        5th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u) 
    -   PnP -- SPFx Developer Workstation Setup -- TBS
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [September
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   Ask me anything -- Script Samples -- [September
        14th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURjNZTDA4VEJGNUYyMVlCNkZUVzlYQ0FaQy4u)
    -   Ask Me Anything -- Power Platform Development & Samples
        -- [September
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNFJZNThMWFk0QlEzWFJNVE5aNVMzM1UwUi4u)
    -   First Time Presenter -- [October
        12th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- [September
        14th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u) 
    -   Maturity Model Practitioners -- [September
        21st](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u) and
        every 3rd Tuesday of month, 7:00am PT
    -   PnP Office Hours -- 1:1 session
        -- [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    -   PnP Buddy System -- [Request a
        Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
-   Download the recurrent invite for this call
    -- [https://aka.ms/m365-dev-call](https://aka.ms/m365-dev-call%C2%A0)
-   Call attention to your great work by using
    the [#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click) on
    Twitter.
Thank you for your continued contributions of your time and talent to
the betterment of this community.  Stay well.  See you soon.  

## Demos

Demos delivered in this session

-   **Microsoft Graph Toolkit Latest Releases --** 2 key new features in
    v2.3 are Teams MSAL2 Authentication Provider (built on top of
    MSAL-browser using more secure Authorization Code Flow with PKCE,
    supports interactive login and SSO) and a file upload feature added
    to File List component (allows users to upload items to a location
    in OneDrive/SharePoint).   This is the first MGT release where all
    major features were contributed by community!

-   **Getting started with Microsoft Lists templates** -- how to and the
    journey ahead.  Rolling out APIs and Tools late September to enable
    community to create, publish and store custom list templates (lists
    from your organization).  8 OOB templates today, help create 40+ by
    year end.   Use PowerShell to connect to SPOService, see Cmdlets to
    extract json from an existing list and use in list template design. 
    Upload/expose new template on site.    Topic related Q&A.

-   **Introduction to Microsoft Graph CLI** -- learn about a
    non-PowerShell, cross platform alternative command line experience
    for accessing the Graph.  The development journey -- today - Public
    Preview v0.1.6 (Windows) to GA (Win, Mac, Linux, Docker).  CLI
    demo - get the CLI msi from the Repo, install it, help to see
    commands, authenticate against Graph, use scopes, list users in
    tenant, specify output parameters -- select or JsonPath queries.   

Thank you for your work. Samples are often showcased in Demos.

## Topics

Topics covered in this call

-   Latest updates and news on the Microsoft 365 platform -- [Brian T.
    Jackett](https://twitter.com/BrianTJackett) (Microsoft) |
    @BrianTJackett --
    [4:05](https://youtu.be/gf00sxZvK5M?t=245)
-   **Demo:**  Microsoft Graph Toolkit Latest Releases -- [Elise
    Yang](https://twitter.com/elisenyang) (Microsoft) |
    @elisenyang, [André
    Lage](https://twitter.com/aaclage) (Datalynx AG) |
    @aaclage --
    [6:20](https://youtu.be/gf00sxZvK5M?t=380)
-   **Demo:**  Getting started with Microsoft Lists templates -- [Harini
    Saladi](https://twitter.com/HariniSaladi) (Microsoft) |
    @HariniSaladi -- [14:32](https://youtu.be/gf00sxZvK5M?t=872)
-   **Demo:**  Introduction to Microsoft Graph CLI -- [Roina
    Ochieng](https://twitter.com/roinochieng) (Microsoft) |
    @roinochieng, [Samwel
    Kanda](https://twitter.com/samwelkanda) (Microsoft) |
    @samwelkanda -- [30:17](https://youtu.be/gf00sxZvK5M?t=1817)


## Resources

Additional resources around the covered topics and links from the
slides.

-   Repo - [Microsoft Graph
    Toolkit](https://github.com/microsoftgraph/microsoft-graph-toolkit) 

-   Documentation - [Microsoft Graph Toolkit: UI Components and
    Authentication Providers for Microsoft
    Graph](https://learn.microsoft.com/graph/toolkit/overview) 

-   Sandbox -- [Microsoft Graph Toolkit
    Playground](https://mgt.dev/?path=/story/components-mgt-agenda--simple) 

-   Resources - [Microsoft Lists Resource
    Center](https://resources.techcommunity.microsoft.com/microsoft-lists/) 

-   Documentation - [Creating custom list
    templates](https://learn.microsoft.com/sharepoint/lists-custom-template)
    |

-   Repo - [Microsoft Graph
    CLI](https://github.com/microsoftgraph/msgraph-cli) 

-   PnP Weekly -- Episode 133 (September 6th) with Helsinki-based
    Software Designer and MVP - [Gautam
    Sheth](https://twitter.com/gautamdsheth) (Valo) | @gautamdsheth |
    [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-133-gautam-sheth-valo/ba-p/2728148)
    | [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-133-7th-of-september-2021)

-   [Microsoft 365 Developer Podcast](https://m365devpodcast.com)
    focused  exclusively on Microsoft 365 dev topics -- hosted by
    [Jeremy Thake](https://twitter.com/jthake) (Microsoft) |

    @jthake and [Paul Schaeflein](https://twitter.com/paulschaeflein)
    (Addin365)
    | @paulschaeflein

## General resources

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
    documentation](https://learn.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-tenant-templates?WT.mc_id=m365-24198-cxa)
-   [SharePoint Page Transformation webcast
    series](https://developer.microsoft.com/sharepoint/blogs/sharepoint-page-transformation-webcast-series?WT.mc_id=m365-24198-cxa)
-   [PnP Power Shell](https://aka.ms/sppnp-powershell)
-   [SharePoint Modernization
    Tools](https://github.com/SharePoint/sp-dev-modernization/tree/dev/Tools)

## Upcoming Calls | Recurrent Invites


-   **Office add-in monthly call** -- September 8th at 8:00 am PDT
    | <https://aka.ms/officeaddinscall>
-   **SharePoint Framework call** -- September 9th at 7:00 am PDT
    | <https://aka.ms/spdev-spfx-call>
-   **Adaptive Cards monthly call** --September 9th at 9:00 am PDT
| <https://aka.ms/adaptivecardscommunitycall>

-   **Microsoft 365 platform call** -- September 14th at 8:00 am PDT
    | <https://aka.ms/m365-dev-call>
-   **Power Apps monthly call**-- September 15th at 8:00 am PDT
    | <https://aka.ms/PowerAppsMonthlyCall>
-   **M365 General Dev call** -- September 16th at 7:00 am PDT
    | <https://aka.ms/m365-dev-sig>
-   **Microsoft Identity Platform call** -- September 16th at 9:00 am
    PDT | <https://aka.ms/IDDevCommunityCalendar>
Microsoft 365 Platform community call focuses on latest Microsoft 365
Platform updates and demos delivered by Microsoft presenters and takes
place weekly on Tuesday.  The alternating Special Interest Group
community calls each Thursday focus on SharePoint Framework (client-side
development/implementation) and Microsoft 365 Platform (includes
Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning,
PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, PowerApps,
Column Formatting, list formatting, etc. topics.) with demos commonly
delivered by community members. 

 More details on the Microsoft 365
community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). 
You can download recurrent invite for this call
from <https://aka.ms/m365-dev-call>. 

Welcome and join in the
discussion. If you have any questions, comments, or feedback, feel free
to provide your input as comments to this post as well. More details on
the Microsoft 365 community and options to get involved are available
from [https://aka.ms/m365pnp](https://aka.ms/sppnp).


*"Sharing is caring"*

------------------------------------------------------------------------

*Microsoft 365 PnP team, Microsoft - 8th of September 2021*
