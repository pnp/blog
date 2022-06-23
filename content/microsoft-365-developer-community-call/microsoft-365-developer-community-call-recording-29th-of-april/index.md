---
title: "Microsoft 365 Developer Community Call recording -- 29th of April, 2021"
date: 2021-04-30T04:15:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 Developer Community Call"]
images:
- images/sig-29th-apr-recording.png
tags: []
type: "regular"
---
 


## Call summary



Latest news from Microsoft 365 engineering and updates on open-source
projects: PnP .NET libraries, PnP PowerShell, modernization tooling, on
yo Teams, on Microsoft Graph Toolkit, and on Microsoft Teams Samples.
Announcing the release of SharePoint Framework v1.12.1, check out the
new [Microsoft 365 Extensibility look book
gallery](https://aka.ms/m365/extensibility), visit the [Microsoft Teams
samples gallery](https://aka.ms/teams-samples) to get started with
Microsoft Teams development, please complete the [Microsoft 365
developer community survey](https://aka.ms/m365pnp/survey), and register
now for May trainings on
[Sharing-is-caring](https://pnp.github.io/sharing-is-caring/). 
Open-source project activity is focused on prepping for May releases.   
**Open-source project status:**
  ----------------------------------------- --------------------------- ---------------------------------------
  **Project**                               **Current Version**         **Release/Status**
  PnP .NET Libraries - PnP Framework        v1.4.0                      Bug fixes, Prepping for v1.5.0 (May)
  PnP .NET Libraries - PnP Core SDK         v1.1.0                      Bug fixes, Prepping for v1.2.0 (May)
  PnP PowerShell                            v1.5.0                      Prepping for v1.6.0 (May)
  Yo teams - generator-teams                v3.0.3 GA, v3.1.0 Preview   Preview with Viva Connections support
  Yo teams - yoteams-build-core             v1.1.0                       
  Yo teams - msteams-react-base-component   v3.1.0                       
  Microsoft Graph Toolkit (MGT)             v2.1.0 GA, v2.2.0 Preview   Bug fixes and v2.2.0 preview updates
  ----------------------------------------- --------------------------- ---------------------------------------
Additionally, one new Teams sample delivered.  The host of this call was
[Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
@vesajuvonen.  Q&A takes place in chat throughout the call.


-   Last week to complete the Microsoft 365 Developer Community Survey
    -- <https://aka.ms/m365pnp/survey>
-   Try the public beta of SPFx v1.12.1. 
-   Reserve date - SharePoint Monthly community call - 11th of May 8
    AM PDT | <https://aka.ms/sp-call>
-   Register for Sharing is Caring Events:
    -   First Time Contributor Session -- [May
        24th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session
        -- [April](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    -   PnP -- SPFx Developer Workstation Setup -- [May
        13th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
         
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [May
        20th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   AMA (Ask Me Anything) -- Power Platform Samples -- [May
        5th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMUIxSldXNDdTOFJWTENSTTM0QlBLWUM3NS4u)
    -   AMA (Ask Me Anything) -- Tech Community -- [May
        11th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQlpKUUlUUUtFR1VTSUxUVzI3NUs5SzhNWC4u)
    -   First Time Presenter -- [May
        25th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VS Code -- [May
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

-   Document manager sample app using messaging -- Sathya Raveendran,
    Varaprasa\...
![210429-together-mode.gif](images/210429-together-mode.gif)
Thank you for being part of the community and for helping others to
succeed.  You are awesome!
 

## Demos

Demos delivered in this session

-   **Delegated and application permissions in the Microsoft Identity
    Platform** -- demystifies the identity model with a clearly
    delivered 100 level overview of app permissions - operation and
    terminology, i.e., delegation, requests, grants, consent, tokens,
    etc.    How app/services permission delegation works, how tokens are
    aligned to a machine or to a person. Is the app or person authorized
    to access resources?  How and when machines dynamically/statically
    request permissions and more.

-   **Localization check inside SharePoint Framework projects -- VS Code
    extension to increase your productivity** -- a VS Code and Node.js
    extension that keeps resources in sync by making sure all
    localization labels inside SharePoint Framework project files across
    organization are consistent.   The extension is automatically
    activated for your SPFx solutions and checks, whether localization
    resource files (en-us.js, nl-nl.js, etc.) follow the pattern,
    defined in the corresponding strings.d.ts. Prevents accidental or
    refactoring errors in SPFx solutions.

-   **Using field lookups with list formatting** -- Field Type =
    "Lookup."  Lookups get values from a list and have limited
    formatting options.  Of horse, this limitation does not deter Chris
    from showing crazy, crazier, craziest formatting options for
    lookups.   Approach = format the lookup column into which content
    from the list will flow.  Use advanced forEach property.   In this
    demo, Chris shows formatting capabilities available in a referenced
    sample.   

     

Thank you for your work. Samples are often showcased in Demos.

## Topics

Topics covered in this call

-   PnP .NET library updates - [Bert
    Jansen](https://twitter.com/o365bert) (Microsoft) | @O365bert
    - [6:59](https://youtu.be/1NE_uMlpD08?t=419)

-   PnP PowerShell updates - [Bert
    Jansen](https://twitter.com/o365bert) (Microsoft) |
    @O365bert - [8:43](https://youtu.be/1NE_uMlpD08?t=523)

-   yo Teams updates - [Wictor
    Wilén](https://twitter.com/wictor) (Avanade) | @wictor -
    [9:53](https://youtu.be/1NE_uMlpD08?t=593)

-   Microsoft Graph Toolkit updates - [Beth
    Pan](https://twitter.com/beth_panx) (Microsoft)
    | [beth-panx](https://github.com/beth-panx) - [11:10](https://youtu.be/1NE_uMlpD08?t=670)

-   Microsoft Teams Samples - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen - [12:33](https://youtu.be/1NE_uMlpD08?t=753)

-   **Demo:**  Delegated and application permissions in the Microsoft
    Identity Platform -- [Philippe
    Signoret](https://twitter.com/psignoret) (Microsoft) | @psignoret -
    [14:48](https://youtu.be/1NE_uMlpD08?t=888)

-   **Demo:**  Localization check inside SharePoint Framework projects
    -- VS Code extension to increase your productivity -- [Sergei
    Sergeev](https://twitter.com/sergeev_srg) (Mastaq) | @sergeev_srg -
    [30:22](https://youtu.be/1NE_uMlpD08?t=1822)

-   **Demo:**  Using field lookups with list formatting -- [Chris
    Kent](https://twitter.com/theChrisKent) (DMI) | @theChrisKent [-
    [42:48](https://youtu.be/1NE_uMlpD08?t=2568)][ ]

## Resources

Additional resources around the covered topics and links from the
slides.

-   [Slides used in this ​community
    call](https://1drv.ms/p/s!AlposW7ozA_90kZjiGKQhUYlcnca?e=DksKJ7)

-   Blog - [SPFx Check Locale - a nice option to check your localization
    consistency across SharePoint
    Framework\...](https://spblog.net/post/2021/04/29/spfx-check-locale-a-nice-option-to-check-your-localization-consistency-across-sharepoint-framework-solution) 

-   VS Code Extension - [SPFx Check
    Locale](https://marketplace.visualstudio.com/items?itemName=s-kainet.spfx-check-locale)

-   [Repo - ][Checks that your
    localization files match the schema inside
    mystrings.d.ts](https://github.com/s-KaiNet/spfx-check-locale)

-   Repo - [Multi-lookup fields and projected
    fields](https://github.com/pnp/List-Formatting/tree/master/column-samples/multi-lookup-projected-field) 

-   Demos -- [Other formatting demos from
    Chris](https://www.youtube.com/c/Microsoft365Community/search?query=format%20flow) 

-   Documentation -- [Create list relationships by using unique and
    lookup
    columns](https://support.microsoft.com/office/create-list-relationships-by-using-unique-and-lookup-columns-80a3e0a6-8016-41fb-ad09-8bf16d490632?ui=en-US&rs=en-US&ad=US) 

-   [PnP Weekly -- Episode 124] with[
    guest MVP from Sympraxis
    Consulting ][Emily
    Mancini](https://twitter.com/EEMancini)[ |@EEMancini |
    ][video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-124/ba-p/2294147)[
    |
    ][podcast](https://pnpweekly.podbean.com/e/pnp-weekly-episode-124-26th-of-april-2021/)

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

-   **Microsoft Graph call -** May 4th at 8:00 am PDT |
    <https://aka.ms/microsoftgraphcall>
-   **SharePoint Framework call** -- May 6th at 7:00 am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **SharePoint monthly call --** May 11th at 8:00am PDT |
    <https://aka.ms/sp-call>
-   **Office add-in monthly call --** May 12th at 8:00 am PDT |
    [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscommunitycall)
-   **M365 General Dev call --** May 13th at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Adaptive Cards monthly call --** May 13th at 9:00 am PDT |
    <https://aka.ms/adaptivecardscommunitycall>
-   **Microsoft Teams monthly call --** May 18th at 8:00 am PDT |
    <https://aka.ms/microsoftteamscommunitycall>
-   **Power Apps monthly call --** May 19th at 8:00 am PDT |
    <https://aka.ms/PowerAppsMonthlyCall>
-   **Microsoft Identity Platform** **--** May 20th at 9:00 am PDT |
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

*Microsoft 365 PnP team, Microsoft - 30th of April 2021*
 