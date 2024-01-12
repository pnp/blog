---
title: "Microsoft 365 Platform Call -- 31st of August, 2021"
date: 2021-09-01T04:16:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 platform call"]
images:
tags: []
type: "regular"
---

Microsoft 365 Platform Community Call - weekly community call recording
from August 31st, is now available from the Microsoft 365 Community
YouTube channel at <https://aka.ms/m365pnp-videos>.

 

## Call summary

Welcome to the first in a new series of weekly calls focused on
capabilities of the all up Microsoft 365 platform.   You are encouraged
to register at [Microsoft 365 Developer
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
from Microsoft on Microsoft 365 platform.  The [Microsoft 365 Community
(PnP) -- August
2021](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-community-august-2021-update/ba-p/2651816),
update is now available!  A hearty thank you goes out to the community
members, organizations and Microsoft employees who have contributed
their time and talents to this community in the last month.   The host
of this call was [Vesa Juvonen](https://twitter.com/vesajuvonen)
(Microsoft) @vesajuvonen.   Q&A takes place in chat throughout the
call.

**Microsoft 365 Platform News Flash**

-   New public preview version of SharePoint Framework v1.13
-   Action required:  Update your Office Add-in dialog for cross-domain
    communication
-   Changes to the Microsoft 365 usage reports API

 

## Actions





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
    -   Ask me anything -- Recognition Program -- [September
        7th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNzVJQTEyMkw4VVBIVjc3NE9PWDFDM1M3My4u)
    -   Ask me anything -- Script Samples -- [September
        14th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURjNZTDA4VEJGNUYyMVlCNkZUVzlYQ0FaQy4u)
    -   Ask Me Anything -- Power Platform Development & Samples --
        [September
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNFJZNThMWFk0QlEzWFJNVE5aNVMzM1UwUi4u)
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
    -- <https://aka.ms/>m365-dev-call
-   Call attention to your great work by using
    the [#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click) on
    Twitter.

## Demos

Demos delivered in this session

-   **Getting started with Microsoft Graph Toolkit** -- there is lots of
    data and insights available to developers via Microsoft Graph.  
    Easily access this content using the Microsoft Graph Toolkit (MGT)
    with authentication providers, web components, utilities and often
    requiring only 1-4 lines of code!    Render agendas, files, people
    and more in your apps courtesy of Microsoft Graph.  ACTION:  Visit
    MGT Playground at <https://mgt.dev> and take the Learn Microsoft
    Graph Learning Path.   

-   **Introduction to Microsoft Graph .NET SDK v4** -- learn about and
    see a subset of new features delivered in the latest .NET SDK. 
    Highlights include streamlined authentication with Azure Identity,
    added support for System.Text.Json, rich notifications that support
    encrypted content, and new Graph Response \<\> object.  Also,
    ODataType is no longer specified by default, improved testability of
    GraphServiceClient and additional fixes.   Visited code for
    authentication, serialization, Graph response, and PageIterator.

-   **Getting started with Microsoft Teams UI Library** -- specifically
    learn about capabilities in the **Microsoft Teams UI Kit** v2.2 that
    includes core components, scenario-based templates, and best
    practices for designing Teams apps that deliver consistent user and
    developer experiences.  Open source React components implement the
    Teams UI kit.   See the fluent UI libraries on GitHub and npm.    

Thank you for your work. Samples are often showcased in Demos.

## Topics

Topics covered in this call

-   Latest updates and news on the Microsoft 365 platform -- [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen -- [8:38](https://youtu.be/OPiBhBf-9PU?t=518)
-   Monthly contributors on the Microsoft 365 platform community assets
    -- [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen -- [11:12](https://youtu.be/OPiBhBf-9PU?t=672)
-   **Demo:**  Getting started with Microsoft Graph Toolkit -- [Waldek
    Mastykarz](https://twitter.com/waldekm) (Microsoft) | @waldekm  --
    [15:30](https://youtu.be/OPiBhBf-9PU?t=930)
-   **Demo:**  Introduction to Microsoft Graph .NET SDK v4 -- Maisa
    Rissi (Microsoft), Andrew Omondi (Microsoft) --
    [28:14](https://youtu.be/OPiBhBf-9PU?t=1694)
-   **Demo:**  Getting started with Microsoft Teams UI Library -- Will
    Shown (Microsoft) -- [42:11](https://youtu.be/OPiBhBf-9PU?t=2531)



## Resources

Additional resources around the covered topics and links from the
slides.

-   Toolkit -- [Microsoft Graph Toolkit](https://aka.ms/mgt) 

-   Sandbox - [Microsoft Graph Toolkit Playground](https://mgt.dev/) 

-   Learn - [Develop apps with the Microsoft Graph
    Toolkit](https://aka.ms/learn-mgt) 

-   Repo --
    [microsoft-graph-toolkit](https://github.com/microsoftgraph/microsoft-graph-toolkit) 

-   Documentation - [Localizing the Microsoft Graph Toolkit
    components](https://learn.microsoft.com/graph/toolkit/customize-components/localization) 

-   Article - [Microsoft Graph .NET SDK v4 now generally available with
    streamlined authentication and
    more](https://developer.microsoft.com/microsoft-365/blogs/microsoft-graph-net-sdk-v4-now-generally-available-with-streamlined-authentication-and-more/) 

-   Documentation - [Get change notifications delivered in different
    ways](https://learn.microsoft.com/graph/change-notifications-delivery) 

-   Community - [Microsoft Teams UI
    Kit](https://www.figma.com/community/file/916836509871353159) 

-   NPM Library -
    [@fluentui/react-teams](https://www.npmjs.com/package/@fluentui/react-teams) 

-   GitHub Library -
    [@fluentui/react-teams](https://github.com/OfficeDev/microsoft-teams-ui-component-library#readme) 

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


-   **M365 General Dev call** -- September 2nd at 7:00 am PDT
    | <https://aka.ms/m365-dev-sig>
-   **Microsoft 365 platform** **-- **September 7that 8 AM
    PDT | <https://aka.ms/m365-dev-call>
-   **Office add-in monthly call** -- September 8th at 8:00 am PDT
    | <https://aka.ms/officeaddinscall>
-   **SharePoint Framework call --**September 9th at 7:00 am PDT
    | <https://aka.ms/spdev-spfx-call>
-   **Adaptive Cards monthly call** --September 9th at 9:00 am PDT
| <https://aka.ms/adaptivecardscommunitycall>

-   **Power Apps monthly call**-- September 15th at 8:00 am PDT
    | <https://aka.ms/PowerAppsMonthlyCall>
-   **Microsoft Identity Platform --**September 16th at 9:00 am PDT
    | <https://aka.ms/IDDevCommunityCalendar>
Microsoft 365 Platform community call focuses on latest Microsoft 365
Platform updates and demos delivered by Microsoft presenters and takes
place weekly on Tuesday.  The alternating Special Interest Group
community calls each Thursday focus on SharePoint Framework (client-side
development/implementation) and Microsoft 365 Platform (includes
Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning,
PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, PowerApps,
Column Formatting, list formatting, etc. topics.) with demos commonly
delivered by community members.   More details on the Microsoft 365
community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). 
You can download recurrent invite for this call from
<https://aka.ms/m365-dev-call>.  Welcome and join in the discussion. If
you have any questions, comments, or feedback, feel free to provide your
input as comments to this post as well. More details on the Microsoft
365 community and options to get involved are available
from [https://aka.ms/m365pnp](https://aka.ms/sppnp).
*"Sharing is caring"*

------------------------------------------------------------------------

*Microsoft 365 PnP team, Microsoft - 31st of August 2021*
