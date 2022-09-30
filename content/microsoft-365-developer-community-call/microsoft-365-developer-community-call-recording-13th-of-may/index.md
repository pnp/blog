---
title: "Microsoft 365 Developer Community Call recording -- 13th of May, 2021"
date: 2021-05-14T02:42:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 Developer Community Call"]
images:
- images/recording-may-13th-call.png
tags: []
type: "regular"
---

Recording of the Microsoft 365 -- General M365 development Special
Interest Group (SIG) community call from May 13, 2021.


## Call summary



Latest news from Microsoft 365 engineering and updates on open-source
projects: PnP .NET libraries, PnP PowerShell, modernization tooling, on
yo Teams, on Microsoft Graph Toolkit, and on Microsoft Teams Samples.
Check out the new [Microsoft 365 Extensibility look book
gallery](https://aka.ms/m365/extensibility), visit the [Microsoft Teams
samples gallery](https://aka.ms/teams-samples) to get started with
Microsoft Teams development, and register now for May trainings
on [Sharing-is-caring](https://pnp.github.io/sharing-is-caring/). 
Open-source project activity is focused on prepping for May releases in
Microsoft Build time frame.   
**Open-source project status:**
  ----------------------------------------- ------------------------------------------------------------- ---------------------------------------
  **Project**                               **Current Version**                                           **Release/Status**
  PnP .NET Libraries - PnP Framework        v1.4.0                                                        Bug fixes, Prepping for v1.5.0 (May)
  PnP .NET Libraries - PnP Core SDK         v1.1.0                                                        Bug fixes, Prepping for v1.2.0 (May)
  PnP PowerShell                            v1.5.0 (just added Cmdlets for Viva Connections and Syntex)   Prepping for v1.6.0 (May)
  Yo teams - generator-teams                v3.0.3 GA, v3.1.0 Preview                                     Preview with Viva Connections support
  Yo teams - yoteams-build-core             v1.1.0                                                         
  Yo teams - msteams-react-base-component   v3.1.0                                                         
  Microsoft Graph Toolkit (MGT)             v2.1.0 GA, v2.2.0 Preview                                     v2.2.0 planned Build release
  ----------------------------------------- ------------------------------------------------------------- ---------------------------------------
Additionally, one new Teams sample delivered.  The host of this call was
[David Warner II](https://twitter.com/DavidWarnerII) (Catapult Systems)
| @DavidWarnerII.   Q&A takes place in chat throughout the call.


-   Register for Sharing is Caring Events:
    -   First Time Contributor Session -- [May
        24th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session
        -- [May](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    -   PnP -- SPFx Developer Workstation Setup -- June 
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [May
        20th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   AMA (Ask Me Anything) -- Microsoft Graph & MGT -- June
    -   AMA (Ask Me Anything) -- Microsoft Teams Dev - June
    -   First Time Presenter -- [May
        25th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- [May
        27th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
         
    -   Maturity Model Practitioners -- [May
        18th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    -   PnP Office Hours -- 1:1 session -
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
-   Download the recurrent invite for this call
    -- <https://aka.ms/m365-dev-sig>
-   Call attention to your great work by using
    the [#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click) on
    Twitter.
**Microsoft Teams Development
Samples:  **(<https://aka.ms/TeamsSampleBrowser>)

-   **[Kudos App (Teams Activity Feed
    API)](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-activity-feed)
    -** [Sébastien Levert](https://twitter.com/sebastienlevert)
    (Microsoft) |
    [sebastienlevert](https://github.com/sebastienlevert)

Great to see all the faces in the community.  Hopefully soon we will get
to see each other in person.   

## Demos

Demos delivered in this session

-   **Inspire, inform and prepare employees transition to the new hybrid
    Workplace transformation site** **-** learn about the customizable
    SharePoint Hybrid Workplace site template (in look book) and new end
    user training (available on support.microsoft.com and in Microsoft
    365 Learning Pathways playlists) to help customers and colleagues'
    transition to a new way of working.   Article insights based on
    customer conversations and research by Microsoft.   Training
    categories (playlists) -- meetings & collaboration, wellness and
    productivity, security & data protection.   

-   **Querying and Paging data with PnP Core SDK** -- after downloading
    the PnPCoreAuth package, installing and configuring the needed
    services, obtain the PnPContext from PnPContextFactory and start
    using the library.  There are multiple options for querying data. 
    PnP Core SDK Query Model options -- Load\*, Get\*, LINQ, and
    Nested/hierarchical queries.  PnP Core SDK Paging Model options -
    Implicit asynchronous paging\*, Full load of data/synchronous
    implicit paging, and Manual paging with Take/Skip.   \*Preferred. 

-   **Advanced tricks for form formatting and customization** -- some
    items in a list should not show up on a form.  You can delete, hide
    or conditionally show values (based on entries in other fields) on a
    form.  Column and Form formatting are vastly different.  Learn ways
    to detect what values are in the list vs what values are on the form
    and also how to create read only sections on a form.

     

Thank you for your work. Samples are often showcased in Demos.

## Topics

Topics covered in this call

-   PnP .NET library updates - [Paolo
    Pialorsi](https://twitter.com/paolopia) (PiaSys.com)
    @paolopia - [4:45](https://youtu.be/pg1M9AuTaO4?t=285)

-   PnP PowerShell updates - [Paolo
    Pialorsi](https://twitter.com/paolopia) (PiaSys.com)
    @paolopia - [6:35](https://youtu.be/pg1M9AuTaO4?t=395)

-   yo Teams updates - [Paolo
    Pialorsi](https://twitter.com/paolopia) (PiaSys.com) @paolopia -
    [7:24](https://youtu.be/pg1M9AuTaO4?t=444)

-   Microsoft Graph Toolkit updates - [Beth
    Pan](https://twitter.com/beth_panx) (Microsoft)
    | [beth-panx](https://github.com/beth-panx) - [8:34](https://youtu.be/pg1M9AuTaO4?t=514)

-   Microsoft Teams Samples - [Bob
    German](https://twitter.com/Bob1German) (Microsoft)
    @Bob1German - [9:46](https://youtu.be/pg1M9AuTaO4?t=586)

-   **Demo:**  Inspire, inform and prepare employees transition to the
    new hybrid Workplace transformation site -- Holland Kaviani
    (Microsoft) & [Matt Wolodarsky](https://twitter.com/mwolodarsky)
    (Microsoft) | @mwolodarsky -
    [12:34](https://youtu.be/pg1M9AuTaO4?t=754)

-   **Demo:**  Querying and Paging data with PnP Core SDK -- [Paolo
    Pialorsi](https://twitter.com/PaoloPia) (PiaSys) | @PaoloPia -
    [25:21](https://youtu.be/pg1M9AuTaO4?t=1521)

-   **Demo:**  Advanced tricks for form formatting and customization --
    [Chris Kent](https://twitter.com/theChrisKent) (DMI) |
    @theChrisKent [-
    [43:22](https://youtu.be/pg1M9AuTaO4?t=2602)



## Resources

Additional resources around the covered topics and links from the
slides.

-   [Slides used in this ​community
    call](https://1drv.ms/p/s!AlposW7ozA_90kl3f0lIJy0IsdJR?e=4BmKBO)

-   Blog post - [Help employees transition to hybrid work using a new
    SharePoint site template and end-user
    training](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/help-employees-transition-to-hybrid-work-using-a-new-sharepoint/ba-p/2181914) 

-   Look book (website template) - [WORKPLACE TRANSFORMATION
    SITE](https://aka.ms/WorkplaceTransformationSite) 

-   Article - [The future of work---the good, the challenging & the
    unknown](https://www.microsoft.com/microsoft-365/blog/2020/07/08/future-work-good-challenging-unknown/) 

-   Support site -- [Hybrid workplace
    guides](https://support.microsoft.com/office/view-usage-data-for-your-sharepoint-site-884b5a0e-ab1d-40a1-8c60-f8e46fb014f3)  

-   Documentation - [PnP Core SDK -- Get
    Data](https://pnp.github.io/pnpcore/using-the-sdk/basics-getdata.html) 

-   Documentation - [PnP Core SDK -- Using
    paging](https://pnp.github.io/pnpcore/using-the-sdk/basics-getdata-paging.html) 

-   SDK - [PnP Core SDK](https://pnp.github.io/pnpcore) 

-   Code sample - [PnP Core SDK Query Model
    sample](https://github.com/PiaSys/Conferences-Samples/tree/master/PnP-Core-SDK/PnPCoreSDKQueryModel01) 

-   [PnP Weekly -- Episode 126] with MVP
    [guest ][D'arce
    Hess](https://twitter.com/DarceHess)[ (TrnDigital) | @ DarceHess|
    ][video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-126-d-arce-hess/ba-p/2341130)[
    |
    ][podcast](https://pnpweekly.podbean.com/e/Microsoft-365-pnp-weekly-episode-126-10th-of-may-2021/)

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


-   **Microsoft Teams monthly call --** May 18th at 8:00 am PDT |
    <https://aka.ms/microsoftteamscommunitycall>
-   **Power Apps monthly call --** May 19th at 8:00 am PDT |
    <https://aka.ms/PowerAppsMonthlyCall>
-   **SharePoint Framework call** -- May 20th at 7:00 am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **Microsoft Identity Platform --** May 20th at 9:00 am PDT
    | <https://aka.ms/IDDevCommunityCalendar> 
-   **M365 General Dev call --** May 27th at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Microsoft Graph call --** June 1st at 8:00 am PDT |
    <https://aka.ms/microsoftgraphcall>
-   **SharePoint monthly call --** June 8th at 8:00am PDT |
    <https://aka.ms/sp-call>
-   **Office add-in monthly call --** June 9th at 8:00 am PDT |
    [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscommunitycall)
-   **Adaptive Cards monthly call --** June 10th at 9:00 am PDT |
    <https://aka.ms/adaptivecardscommunitycall>
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

*Microsoft 365 PnP team, Microsoft - 14th of May 2021*

