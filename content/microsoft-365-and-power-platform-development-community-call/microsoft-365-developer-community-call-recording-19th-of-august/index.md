---
title: "Microsoft 365 Developer Community Call recording -- 19th of August, 2021"
date: 2021-08-20T03:41:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-august-19th.png
tags: []
type: "regular"
---

 


## Call summary



Summer break and community call schedule updates reviewed.  Microsoft
365 tenant -- [script samples gallery](https://aka.ms/script-samples) -
s*cripts for PowerShell and CLIs. * Sign up and attend one of a growing
list of events hosted by [Sharing is
Caring](https://pnp.github.io/sharing-is-caring/) this month.  Announced
[PnP Recognition Program](https://aka.ms/m365pnp-recognition) and more
and more [Microsoft Teams Samples](https://aka.ms/teams-samples) and
[Power Platform Samples](https://aka.ms/powerplatform-samples).  Project
releases this week - Yo teams -- **yoteams-deploy** v1.0.1 Preview.   
**Open-source project status:  (Bold indicates new this call)**
  ----------------------------------------- --------------------------------------------------- -----------------------------------------------
  **Project**                               **Current Version**                                 **Release/Status**
  PnP .NET Libraries - PnP Framework        v1.6.0 GA, PnP Provisioning Engine Schema v202103   Version 1.7.0 -- Late Summer 2021
  PnP .NET Libraries - PnP Core SDK         v1.3.0 GA                                           Version 1.4.0 -- Late Summer 2021
  PnP PowerShell                            v1.7.0 GA                                            
  Yo teams - generator-teams                v3.2.0 GA                                           v3.3.0 Preview soonish
  Yo teams - yoteams-build-core             v1.2.0 GA, v1.2.1 Preview                            
  Yo teams -- yoteams-deploy                v1.1.0 GA, **v1.0.1 Preview**                        
  Yo teams - msteams-react-base-component   v3.1.0                                               
  Microsoft Graph Toolkit (MGT)             v2.2.0 GA                                           Bug fixes and Updates, v2.3.0 later in August
  ----------------------------------------- --------------------------------------------------- -----------------------------------------------
Four Script and three Power Platform samples were delivered and no new
Teams samples in the last two weeks.  But wait, we have a [Teams Samples
wish list](https://aka.ms/teams-sample-wishlist).  Need an idea for a
Teams sample?  Feel like granting wishes?  Collaborate with Teams
Engineering to create a sample and earn a Credly badge.   The host of
this call was [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft)
@vesajuvonen.   Q&A takes place in chat throughout the call.



-   Create a Teams Sample - [Microsoft Teams Samples Wish
    list](https://github.com/pnp/teams-dev-samples/issues) -- 10
    opportunities to share your Teams Dev prowess with the community |
    [<https://aka.ms/teams-sample-wishlist>]{.underline}
-   Opt in to PnP Recognition Program |
    <https://aka.ms/m365pnp-recognition>
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
    -   Ask me anything -- Recognition Program -- [September
        7th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNzVJQTEyMkw4VVBIVjc3NE9PWDFDM1M3My4u)
    -   Ask me anything -- Script Samples -- [September
        14th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURjNZTDA4VEJGNUYyMVlCNkZUVzlYQ0FaQy4u)
    -   Ask Me Anything -- Power Platform Development & Samples --
        [September
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNFJZNThMWFk0QlEzWFJNVE5aNVMzM1UwUi4u)
    -   First Time Presenter -- [August
        30th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- TBS
    -   Maturity Model Practitioners -- [August
        17th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
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

-   No new Teams samples this week
**Microsoft Power Platform
Samples:  **([https://aka.ms/powerplatform-samples)](https://aka.ms/powerplatform-samples)

-   **[Power Automate: SharePoint Collect
    Feedback](https://github.com/pnp/powerautomate-samples/tree/main/samples/sharepoint-collect-feedback)** -
    [April Dunnam](https://twitter.com/aprildunnam) (Microsoft) |
    @aprildunnam (link will be good by Aug 24)
-   [**Power Automate: Get Graph API Data within Power BI
    Reports**](https://github.com/pnp/powerautomate-samples/tree/main/samples/graph_api_in_power_bi) -
    [Scott McKenzie](https://twitter.com/365EDUBI) | @365EDUBI (link
    will be good by Aug 24)
-   [**Fluent UI Custom
    Theme**](https://github.com/pnp/powerapps-samples/tree/main/samples/fluentui-custom-theme) -
    [Fabio Franzini](https://twitter.com/franzinifabio) |
    @franzinifabio

**Script Samples: **
([https://aka.ms/script-samples)](https://aka.ms/script-samples)

-   **[Download contents of Document library as
    PDF](https://pnp.github.io/script-samples/graph-download-office-documents-as-pdf/README.html?tabs=pnpps)**
    -- [Russell Gove](https://twitter.com/russgove) (Tronox) |
    @russgove
-   **[Assign Graph permissions to a Managed
    Identity](https://pnp.github.io/script-samples/graph-assign-permissions-managed-identity/README.html?tabs=azure-cli)**
    -- [Luise Freese](https://twitter.com/LuiseFreese) | @LuiseFreese
-   **[Reset files permissions unique to
    Inherited](https://pnp.github.io/script-samples/reset-files-permission-unique-to-inherited/README.html?tabs=pnpps)**
    -- [Dipen Shah](https://twitter.com/Dips_365) (Rapid Circle) |
    @Dips_365
-   **[Import taxonomy terms and labels into a term
    set](https://pnp.github.io/script-samples/spo-import-taxonomy-terms-labels/README.html?tabs=pnpps)**
    -- [Reshmee Auckloo](https://twitter.com/ReshmeeAuckloo) |
    @ReshmeeAuckloo


## Demos

Demos delivered in this session

-   **Building your first Power Platform community connector** -- start
    with this brilliant lay-of-the-land overview.   Presenter advises
    learning by looking at configurations of existing connectors, of
    code samples, and by reviewing best practices documentation.   Build
    your connector in the UI - naming, security (authentication
    requirement), definition (actions, triggers, references,
    responses...), code, and test operations.   Then download it - the
    swagger or Open API file, using Paconn CLI.        

-   **Operators for Precision within List Formatting** -- Microsoft
    Excel like formatting in a SharePoint list is possible.   Once you
    understand what you have -- numbers or strings, precision formatting
    is easily achieved.  Learn how to display folder and file sizes or
    numbers generally in lists with 2-digit precision / formatting
    (0.00), using various operators - toString, indexOf, substring,
    padStart, padEnd, ceiling, floor AND/OR with formulas in sample
    code.   

-   **Getting stated with Microsoft Teams Toolkit and Blazor** --
    focusing on how to use Web Technologies to create a tab (Blazor app)
    inside of Teams using Visual Studio.  Open new project (Microsoft
    Teams App) in Visual Studio.   Install/open the Teams Toolkit
    (Preview) for Visual Studio.  Configure for SSO.   Select F5. 
    Presto, a default page/tab is created with sample code and
    implements GraphClient.   Register the AAD app and modify it as you
    please.      

Thank you for your work. Samples are often showcased in Demos.

## Topics

Topics covered in this call

-   PnP .NET library updates - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen - [6:44](https://youtu.be/_8BBaIJK2RM?t=404)

-   PnP PowerShell - [Vesa Juvonen](https://twitter.com/vesajuvonen)
    (Microsoft) | @vesajuvonen -
    [7:30](https://youtu.be/_8BBaIJK2RM?t=450)

-   yo Teams updates - [Wictor Wilén](https://twitter.com/wictor)
    (Microsoft) | @wictor - [8:04](https://youtu.be/_8BBaIJK2RM?t=484)

-   Microsoft Graph Toolkit updates - [Beth
    Pan](https://twitter.com/beth_panx) (Microsoft)
    | [beth-panx](https://github.com/beth-panx) - [9:11](https://youtu.be/_8BBaIJK2RM?t=551)

-   Microsoft Script Samples - [Paul
    Bullock](https://twitter.com/pkbullock) (CaPa Creative Ltd) |
    @pkbullock - [3:15](https://youtu.be/_8BBaIJK2RM?t=195)

-   Microsoft Teams Samples - [Bob
    German](https://twitter.com/Bob1German) (Microsoft) | @Bob1German -
    [11:24](https://youtu.be/_8BBaIJK2RM?t=684)

-   Microsoft Power Platform Samples - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen - [14:05](https://youtu.be/_8BBaIJK2RM?t=845)

-   **Demo:**  Building your first Power Platform community connector
    **--** [Daniel Laskewitz](https://twitter.com/laskewitz) (Sogeti) |
    @laskewitz [-][ [16:21](https://youtu.be/_8BBaIJK2RM?t=981)]

-   **Demo:**  Operators for Precision within List Formatting -- [Chris
    Kent](http;/twitter.com/theChrisKent) (DMI) |
    @theChrisKent [-][ [30:23](https://youtu.be/_8BBaIJK2RM?t=1823)]

-   [**Demo:**  Getting stated with Microsoft Teams Toolkit and Blazor
    -- [Thomas Gölles](https://twitter.com/thomyg) (Solvion) | @thomyg
    -][ [44:13](https://youtu.be/_8BBaIJK2RM?t=2653)]



## Resources

Additional resources around the covered topics and links from the
slides.

-   Repository - [Microsoft Power Platform
    Connectors](https://github.com/microsoft/PowerPlatformConnectors) 
-   Documentation - [Extend an OpenAPI definition for a custom
    connector](https://learn.microsoft.com/connectors/custom-connectors/openapi-extensions) 
-   Article - [Using Dynamic Values in Microsoft
    Flow](https://www.schaeflein.net/using-dynamic-values-in-microsoft-flow/) 
-   Documentation - [Microsoft Power Platform Connectors
    CLI](https://learn.microsoft.com/connectors/custom-connectors/paconn-cli) 
-   Demo - [Publish a connector to the Power Platform with Independent
    Publisher Connector
    Program](https://www.youtube.com/watch?v=ulTBvCHw8MU) Natalie
    Pienkowska (Microsoft) 
-   [Documentation --
    ][Operators](https://learn.microsoft.com/sharepoint/dev/declarative-customization/column-formatting#operators)
-   Documentation - [Use column formatting to customize
    SharePoint](https://learn.microsoft.com/sharepoint/dev/declarative-customization/column-formatting) 
-   All Samples - [SharePoint List Formatting
    Samples](https://github.com/pnp/List-Formatting) 
-   Videos - [Microsoft Lists](https://bit.ly/lf-videos) 
-   Documentation - [Prerequisites: Get started with Microsoft Teams app
    development](https://learn.microsoft.com/microsoftteams/platform/get-started/prerequisites?tabs=vs) 
-   Issues List -
    [OfficeDev/TeamsFx](https://github.com/OfficeDev/TeamsFx/issues) 
-   Tool -- [Graph Explorer](https://aka.ms/ge) 
-   Repo -- [Demo code](https://github.com/thomyg/PnPDemo190821Backup) 
-   Sample Project -
    [TeamsLeaderboard](https://github.com/thomyg/TeamsLeaderboard) 
-   Samples - [Power Platform
    Samples](https://aka.ms/powerplatform-samples) | [aka.ms/](https://aka.ms/powerplatform-samples)[powerplatform](https://aka.ms/powerplatform-samples)[-samples](https://aka.ms/powerplatform-samples)
-   Microsoft 365 tenant -- [Script Samples
    Gallery](https://aka.ms/script-samples) | aka.ms/script-samples
-   [Microsoft Teams Samples
    Gallery](https://pnp.github.io/teams-dev-samples/) |
    aka.ms/teams-samples

## General resources

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
    documentation](https://learn.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-tenant-templates?WT.mc_id=m365-24198-cxa)
-   [SharePoint Page Transformation webcast
    series](https://developer.microsoft.com/sharepoint/blogs/sharepoint-page-transformation-webcast-series?WT.mc_id=m365-24198-cxa)
-   [PnP Power Shell](https://aka.ms/sppnp-powershell)
-   [SharePoint Modernization
    Tools](https://github.com/SharePoint/sp-dev-modernization/tree/dev/Tools)

## Upcoming Calls | Recurrent Invites

-   **SharePoint Framework call** -- August 26th at 7:00 am PDT
    |[ https://aka.ms/spdev-spfx-call](https://aka.ms/spdev-spfx-call)
-   **Microsoft 365 platform** -- August 31st at 8 AM
    PDT | <https://aka.ms/m365-dev-call>  (Starts from the 31st of
    August as weekly cycle)
-   **M365 General Dev call** -- September 2nd at 7:00 am PDT
    |[ https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig)
-   **Office add-in monthly call --** September 8th at 8:00 am PDT
    | <https://aka.ms/officeaddinscall>
-   **Adaptive Cards monthly call** -- September 9th at 9:00 am PDT |
    <https://aka.ms/adaptivecardscommunitycall>
-   **Power Apps monthly call** -- September 15th at 8:00 am PDT |
    <https://aka.ms/PowerAppsMonthlyCall>
-   **Microsoft Identity Platform** -- September 16th at 9:00 am PDT
    | <https://aka.ms/IDDevCommunityCalendar>
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

*Microsoft 365 PnP team, Microsoft - 20th of August 2021*
