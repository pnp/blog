---
title: "Microsoft 365 Developer Community Call recording -- 18th of March, 2021"
date: 2021-03-19T01:49:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/sig-18th-march-recording.png
tags: []
type: "regular"
---

Recording of the Microsoft 365 -- General M365 development Special
Interest Group (SIG) community call from March 18, 2021.




## Call Summary




Latest news from Microsoft 365 engineering and updates on open-source
projects: PnP .NET libraries, PnP PowerShell, modernization tooling, on
yo Teams, on Microsoft Graph Toolkit, and on Microsoft Teams Samples.
Announcing the GA release of **SharePoint Framework** v1.12 along with a
host of other GA releases - **PnP .NET Libraries** - **PnP Framework**
v1.3.0, **PnP Core SDK** v1.0.0 and **PnP PowerShell** v1.4.0.   **yo
Teams** ***generator-teams*** (apps generator) v3.0.3 GA and 3.1.0
Preview, ***yo teams-build-core*** (gulp tasks) v1.0.1 + v1.1.0 Preview,
and ***msteams-react-base-component*** (React UI helpers) v3.1.0, have
been released.    In development - MSAL 2.0 provider and preview of
OneDrive file components in **Microsoft Graph Toolkit**.  Released new
[Microsoft Graph Toolkit training in Microsoft
Learn](https://aka.ms/learn-mgt), Register now for March/April trainings
on [Sharing-is-caring](https://pnp.github.io/sharing-is-caring/).   The
host of this call was [Vesa Juvonen](https://twitter.com/vesajuvonen)
(Microsoft) | @vesajuvonen.  Q&A takes place in chat throughout the
call.

**Actions:    **

-   Get SharePoint Framework v1.12 - <https://aka.ms/spfx>
-   Complete the Developer Success Survey -
    <https://aka.ms/developersuccess>
-   Join the M365 customer success platform panel -
    <https://aka.ms/SuccessPanel>
-   Register for Sharing is Caring Events:
    -   First Time Contributor Session -- [March 22nd, April 6th &
        27th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u) 
         (EMEA, APAC & US friendly times available)
    -   Community Docs Session
        -- [March/April](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    -   PnP -- SPFx Developer Workstation Setup -- [April
        29th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [April 8th &
        15th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   PnP -- AMA (Ask Me Anything) -- CLI for Microsoft 365 Edition --
        [April
        13](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN1ZUQ0tFMTFLVUZaTjZXRjdPRk5XOEdSMy4u)
    -   First Time Presenter - [March 24th, April 7th &
        21st](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- [March 23rd, April 14th &
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
    -   Maturity Model Practitioners -- [April
        20th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    -   PnP Office Hours -- 1:1 session -
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
-   Download the recurrent invite for this call
    -- <https://aka.ms/m365-dev-sig>
-   [Call attention to your great work by using the
    ][#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click)
    on
    Twitter
**Microsoft Teams Development Samples**

(<https://aka.ms/TeamsSampleBrowser>)

-   [Teams SSO with server-side Graph
    calls](https://aka.ms/TabSSO2Graph) - [Hilton
    Giesenow](https://twitter.com/TheMossShow) | @TheMossShow & Doğan
    Erişen.  Supporting Article - [Securely connect to Microsoft Graph
    from Teams tabs using
    SSO](https://blog.mastykarz.nl/securely-connect-microsoft-graph-teams-tabs-sso/)
![CmtyPhoto.png](images/CmtyPhoto.png)
**"Hello Community"     **
**Demos** delivered in this session

-   **Accessing comment information in list formatting and advance form
    adjustments** - draw people's attention to discussions around
    selected list items by more prominently displaying the number of
    comments on each item.   Accomplish this by using CommentCount, a
    fluent UI icon and formatting.   Be aware of and adjust for
    differences between how icon containing number renders slightly
    differently in forms, lists and tiles views.  Use sample script in
    your list today!   

-   **Getting started on using Microsoft Teams Yeoman generator v3** --
    get newest Microsoft Teams App Project Generator - #YoTeams at the
    Repo.  Presenter takes viewer from generator installation, project
    creation -- scaffolding of files, to VS code and explains created
    files.  Note:  not using class based React components but using
    functional components and React hooks.  Then create a build and
    install app -- a configurable tab, in Teams.  New V3 capabilities
    called out through demo.         

-   **The Microsoft Graph Toolkit in Teams with Blazor** -- more
    comfortable in C#, Server-side, .NET development as opposed to
    React, then this Blazor demo is for you.  The demo focuses on using
    the Microsoft Graph Toolkit (MGT) in Server-side Blazor via SignalR
    in Teams App Dev.   Authentication is handled by providers from
    MGT.  Blazor components call Microsoft Graph functions to get list
    of teams, agenda, usernames and roles. 

Thank you for your work. Samples are often showcased in Demos.
**Topics** covered in this call

-   Updates from Microsoft 365 Engineering - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft)
    | @vesajuvonen - [6:29](https://youtu.be/kPGpuGPtKHM?t=389)

-   PnP.NET library updates - [Bert Jansen](https://twitter.com/o365bert)
    (Microsoft) | @O365bert -
    [7:24](https://youtu.be/kPGpuGPtKHM?t=444)

-   PnP PowerShell updates - [Bert Jansen](https://twitter.com/o365bert)
    (Microsoft) | @O365bert -
    [10:29](https://youtu.be/kPGpuGPtKHM?t=629)

-   yo Teams updates - [Wictor Wilén](https://twitter.com/wictor)
    (Avanade) @wictor [-
    [11:42](https://youtu.be/kPGpuGPtKHM?t=702)]{style="float: none; background-color: #ffffff; color: #333333; cursor: text; font-family: Georgia,'Times New Roman','Bitstream Charter',Times,serif; font-size: 16px; font-style: normal; font-variant: normal; font-weight: 400; letter-spacing: normal; text-align: left; text-decoration: none; text-indent: 0px; text-transform: none;"}

-   Microsoft Graph Toolkit updates - [Beth
    Pan](https://twitter.com/beth_panx) (Microsoft) |
    [beth-panx](https://github.com/beth-panx) -
    [13:41](https://youtu.be/kPGpuGPtKHM?t=821)

-   Microsoft Teams Samples - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) | @vesajuvonen -
    [15:21](https://youtu.be/kPGpuGPtKHM?t=921)

-   **Demo:**  Accessing comment information in list formatting and
    advance form adjustments -- [Chris
    Kent](https://twitter.com/theChrisKent) (DMI) | @theChrisKent -
    [16:53](https://youtu.be/kPGpuGPtKHM?t=1013)

-   **Demo:**  Getting started on using Microsoft Teams Yeoman generator
    v3 -- [Wictor Wilén](https://twitter.com/wictor) (Avanade) |
    @wictor - [30:54](https://youtu.be/kPGpuGPtKHM?t=1854)

-   **Demo:**  The Microsoft Graph Toolkit in Teams with Blazor --
    [Thomy Gölles](https://twitter.com/thomyg) (Solvion) | @thomyg

    \- [43:42](https://youtu.be/kPGpuGPtKHM?t=2622)



## Resources

Additional resources around the covered topics and links from the
slides.

-   [Slides used in this ​community
    call](https://1drv.ms/p/s!AlposW7ozA_90jjI88X4mCwv3GAA?e=9BukMz)

-   Microsoft Graph Toolkit in Microsoft Learn |
    <https://aka.ms/learn-mgt> 

-   Microsoft Teams Samples Gallery |
    [aka.ms/teams-samples](https://aka.ms/teams-samples)

-   Documentation - [Use column formatting to customize
    SharePoint](https://aka.ms/spdocs-column-formatting) 

-   Samples -- [SharePoint List Formatting
    Samples](https://github.com/pnp/sp-dev-list-formatting) 

-   Repo -- [Comment
    Count](https://github.com/pnp/sp-dev-list-formatting/tree/master/column-samples/comment-count) 

-   Repo - [Row Index
    Drawing](https://github.com/pnp/sp-dev-list-formatting/tree/master/column-samples/generic-rowIndex-drawing)
     

-   Repo - [Microsoft Teams App Project Generator -
    #YoTeams](https://aka.ms/yoteams) 

-   Blog -  [Thomy Gölles](https://thomy.tech/) 

-   Repo - [Awesome
    Blazor](https://github.com/AdrienTorris/awesome-blazor) 

-   Webinar - [MICROSOFT GRAPH TOOLKIT WITH
    BLAZOR](https://www.selectedtech.show/24microsoft-graph-toolkit-blazor/) 

-   Post -- [How to present at online meetings and events like an ignite
    superstar ](https://thomy.tech/how-to-present-at-online-meetings-and-events-like-an-ignite-superstar/)

-   Video - [Getting started with Microsoft Graph
    Toolkit](https://www.youtube.com/watch?v=TbAZHvB5NEk)

-   PnP Weekly -- Episode 118 **with** dual MVP [Veronique
    Lengelle](https://twitter.com/veronicageek) (CPS) | @veronicageek
    |
    [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-118/ba-p/2211589)
    |
    [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-118-15th-of-march-2021/)

-   Viva Connections <https://aka.ms/VivaConnections>


## General resources

-   [SharePoint look book](https://lookbook.microsoft.com/)
-   [Yo Teams video training package](https://aka.ms/yoteams-training)
-   [.NET Standard 2.0 version of SharePoint Online CSOM
    API](https://developer.microsoft.com/microsoft-365/blogs/net-standard-version-of-sharepoint-online-csom-apis/)
-   [Microsoft 365 community (PnP) videos](https://aka.ms/m365pnp-videos)
    | aka.ms/m365pnp-videos
-   [Microsoft Teams Toolkit for Visual Studio
    Code](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension)
-   [yo Teams](https://aka.ms/yoteams) | aka.ms/yoteams
-   Video - [Getting started using yo
    Teams](https://youtu.be/w0OrFkzNC10) | [Wictor
    Wilén](https://twitter.com/wictor) (Avanade)| @wictor
-   [Build a crisis management site to connect people and
    information](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/build-a-crisis-management-site-to-connect-people-and-information/ba-p/1216791)
-   [Developer documentation](https://aka.ms/spdev-docs) |
    <https://aka.ms/spdev-docs>
-   [PnP Power Shell](https://aka.ms/sppnp-powershell)
-   [SharePoint Modernization Partner
    Guidance](https://aka.ms/sppnp-modernization-partnerguidance) -
    Feedback welcome
-   Solution - [Building a modern search experiences with SharePoint
    Framework web parts](https://aka.ms/pnp-modern-search)
-   [Page transformation
    guidance](https://aka.ms/sppnp-pagetransformation)
-   [Page transformation
    videos](https://aka.ms/sppnp-pagetransformationvideos)
-   [Modernization scanner](https://aka.ms/sppnp-modernizationscanner)
-   [Microsoft 365 developer program
    site](https://developer.microsoft.com/office/dev-program) -
    Need to become a Tenant Admin to test look book capabilities? Get a
    Microsoft 365 E5 developer subscription (free tenant for 90 days)
-   [SharePoint Provisioning
    Service](https://lookbook.microsoft.com/) - Easily provision
    look book designs to any tenant in the world
-   [SharePoint Provisioning templates on
    GitHub](https://github.com/SharePoint/sp-dev-provisioning-templates)
-   [PnP Provisioning Tenant Templates
    documentation](https://learn.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-tenant-templates)
-   [SharePoint Page Transformation webcast
    series](https://developer.microsoft.com/sharepoint/blogs/sharepoint-page-transformation-webcast-series/)
-   [PnP Power Shell](https://aka.ms/sppnp-powershell)
-   [SharePoint Modernization
    Tools](https://github.com/SharePoint/sp-dev-modernization/tree/dev/Tools)

## Upcoming Calls | Recurrent Invites


-   **SharePoint Framework call** -- March 25th at 7:00 am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **M365 General Dev call --** April 1st at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Microsoft Graph call - April** 6th at 8:00 am PDT |
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
General Microsoft 365 Dev Special Interest Group bi-weekly calls are
targeted at anyone who's interested in the general Microsoft 365
development topics. This includes Microsoft Teams, Bots, Microsoft
Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core,
Site Designs, Power Automate, PowerApps, Column Formatting, list
formatting, etc. topics. More details on the Microsoft 365 community
from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome
community demos, if you are interested in doing a live demo in these
calls!
You can download recurrent invite from <https://aka.ms/m365-dev-sig>.
Welcome and join in the discussion. If you have any questions, comments,
or feedback, feel free to provide your input as comments to this post as
well. More details on the Microsoft 365 community and options to get
involved are available from
[https://aka.ms/m365pnp](https://aka.ms/sppnp).
*"Sharing is caring"*

------------------------------------------------------------------------

*Microsoft 365 PnP team, Microsoft - 19th of March 2021*
