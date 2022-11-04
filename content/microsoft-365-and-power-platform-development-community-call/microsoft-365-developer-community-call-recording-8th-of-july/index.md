---
title: "Microsoft 365 Developer Community Call recording -- 8th of July, 2021"
date: 2021-07-08T05:08:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/8th-july-recording-m365dev.png
tags: []
type: "regular"
---



## Call Summary




Summer and Fall community call schedule updates reviewed. Preview the
new [Microsoft 365 Extensibility look book
gallery](https://adoption.microsoft.com/extensibility-look-book). 
Looking to get started with Microsoft Teams development?  Don't miss out
on our [Teams samples gallery](https://aka.ms/teams-samples) (updated
sample browser in June), and the new Microsoft 365 tenant -- [script
samples gallery](https://aka.ms/script-samples) - s*cripts for
PowerShell and CLIs. * Sign up and attend one of a growing list of
events hosted by [Sharing is
Caring](https://pnp.github.io/sharing-is-caring/) this month.  Announced
[PnP Recognition Program](https://aka.ms/m365pnp-recognition).  Heads
down on PnP project bug fixes, new idea prototyping, and vacationing
this month.  This is a great time to give the project teams feedback as
members are working on new integrations and previews now.  
**Open-source project status:  (Bold indicates new this call)**
  ----------------------------------------- --------------------------- -------------------------------------
  **Project**                               **Current Version**         **Release/Status**
  PnP .NET Libraries - PnP Framework        v1.5.0 GA                   Version 1.6.0 -- Summer 2021
  PnP .NET Libraries - PnP Core SDK         v1.2.0 GA                   Version 1.3.0 -- Summer 2021
  PnP PowerShell                            v1.6.0  GA                   
  Yo teams - generator-teams                v3.2.0 GA                   v3.3.0 Preview soon
  Yo teams - yoteams-build-core             v1.2.0 GA, v1.2.1 Preview    
  Yo teams -- yoteams-deploy                v1.1.0 GA                    
  Yo teams - msteams-react-base-component   v3.1.0                       
  Microsoft Graph Toolkit (MGT)             v2.2.0 GA                   Added Teams SSO Provider in Preview
  ----------------------------------------- --------------------------- -------------------------------------
One new Teams sample was delivered.  Great work!  The host of this call
was Paolo Pialorsi (PiaSys.com) | @paolopia   Q&A takes place in chat
throughout the call.

## Actions

-   **Register for Sharing is Caring Events**:

    -   First Time Contributor Session -- [August
        31st](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
        (EMEA, APAC & US friendly times available)


    -   Community Docs Session -- [August
        23rd](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    -   PnP -- SPFx Developer Workstation Setup -- [August
        24th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
          
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [July 27th, August
        25th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   Ask Me Anything -- Teams Dev -- [July
        13th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNFJZNThMWFk0QlEzWFJNVE5aNVMzM1UwUi4u)
    -   First Time Presenter -- [August
        30th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- [July
        20th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
    -   Maturity Model Practitioners -- [July
        20th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
        and every 3rd Tuesday of month, 7:00am PT
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

-   **[ReporterPlus -- Teams Device Capabilities
    Application](https://github.com/pnp/teams-dev-samples/tree/main/samples/app-ReporterPlus)
    -** Sathya Raveendran (Microsoft) and Veera Venkata Sai Pothan Thota

## Demos

Demos delivered in this session

-   **Image Column Type formatting in Microsoft 365** -- upload images
    to Site Assets and automatically expose them in a list's Image
    column, no manual linking necessary!  Format Image column appearance
    using sub-properties.  Shown is the sub-property - thumbnailRenderer
    and size selection - *drive thumbnail sizes* provided by Microsoft
    Graph.   All formatting code is found in referenced image-lightbox
    sample.   Hover card and dynamic picture sizing is shown here as
    well. 

-   **Configure Teams Applications with Azure App Configuration and
    Azure Key Vault** -- use *Action Config in Azure configuration*
    extension to configure Microsoft Teams apps hosted in Azure App
    Service that leverage Azure App Configuration and Azure Key Vault
    (credential/secrets storage) and authenticates against Microsoft
    Graph via SSO.   The example - configure an action-based document
    review messaging extension that retrieves and controls access to
    retrieved documents.   Walk through block architecture, code and
    slides.     

     

Thank you for your work. Samples are often showcased in Demos.

## Topics

Topics covered in this call

-   PnP .NET library updates - [Paolo
    Pialorsi](https://twitter.com/paolopia) (PiaSys.com) |
    @paolopia - [9:57](https://youtu.be/rOHSrG1n43Y?t=597)

-   PnP PowerShell - [Erwin van Hunen](https://twitter.com/erwinvanhunen)
    (Valo Intranet) | @erwinvanhunen -
    [12:13](https://youtu.be/rOHSrG1n43Y?t=733)

-   yo Teams updates - [Wictor
    Wilén](https://twitter.com/wictor) (Avanade) | @wictor -
    [14:37](https://youtu.be/rOHSrG1n43Y?t=877)

-   Microsoft Graph Toolkit updates - [Beth
    Pan](https://twitter.com/beth_panx) (Microsoft)
    | [beth-panx](https://github.com/beth-panx) - [15:44](https://youtu.be/rOHSrG1n43Y?t=944)

-   Microsoft Teams Samples - [Bob
    German](https://twitter.com/Bob1German) (Microsoft) | @Bob1German -
    [16:49](https://youtu.be/rOHSrG1n43Y?t=1009)

-   **Demo: ** Image Column Type formatting in Microsoft 365 - [Chris
    Kent](https://twitter.com/theChrisKent) (DMI) | @theChrisKent -
    [19:09](https://youtu.be/rOHSrG1n43Y?t=1149)

-   **Demo: ** Configure Teams Applications with Azure App Configuration
    and Azure Key Vault - [Markus
    Moeller](https://twitter.com/Moeller2_0) (Avanade) | @Moeller2_0 -
    [33:04](https://youtu.be/rOHSrG1n43Y?t=1984) 


## Resources

Additional resources around the covered topics and links from the
slides.

-   Documentation - [List thumbnails for a
    DriveItem](https://docs.microsoft.com/graph/api/driveitem-list-thumbnails?view=graph-rest-1.0&tabs=http) 

-   Sample - [Image
    Lightbox](https://github.com/pnp/List-Formatting/tree/master/column-samples/image-lightbox) 

-   Sample -- [Microsoft Graph Action Configuration
    extension](https://github.com/pnp/teams-dev-samples/tree/main/samples/msgext-graph-action-config) 

-   Blog post - [Configure Teams Applications with Azure App
    Configuration
    (nodeJS)](https://mmsharepoint.wordpress.com/2021/05/17/configure-teams-applications-with-azure-app-configuration-nodejs/) 

-   Documentation - [Azure App Configuration
    documentation](https://docs.microsoft.com/azure/azure-app-configuration/) 

-   Documentation - [Azure Key Vault Developer's
    Guide](https://docs.microsoft.com/azure/key-vault/general/developers-guide) 

-   Blog post - [Microsoft Teams Tabs SSO and Microsoft Graph - the
    'on-behalf-of' blog
    post](https://www.wictorwilen.se/blog/microsoft-teams-tabs-sso-and-microsoft-graph-the-on-behalf-of-blog-post/) 

-   Blog post - [Query SharePoint items with Microsoft Graph and
    Search](https://mmsharepoint.wordpress.com/2021/06/16/query-sharepoint-items-with-microsoft-graph-and-search/) 

-   Sample - [Document Review Msg Extension Action - Microsoft Teams
    App](https://github.com/mmsharepoint/teams-dev-samples/tree/contribspfx/samples/msgext-graph-action-docreview) 

-   PnP Weekly -- Episode 132 with Seattle-based Program Manager from
    OneDrive and SharePoint (ODSP) engineering - [Nicole
    Woon](https://twitter.com/NovelNicole) (Microsoft) |
    @NovelNicole | [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-132-nicole-woon-microsoft/ba-p/2466409) | [podcast](https://pnpweekly.podbean.com/e/Microsoft-365-pnp-weekly-episode-132-21st-of-june-2021/)

-   Microsoft 365 tenant -- [Script Samples
    Gallery](https://aka.ms/script-samples) | aka.ms/script-samples

-   [Microsoft 365 Extensibility look book
    gallery](https://adoption.microsoft.com/extensibility-look-book?WT.mc_id=m365-24198-cxa) |
    aka.ms/m365/extensibility

-   [Microsoft Teams Samples
    Gallery](https://pnp.github.io/teams-dev-samples/) |
    aka.ms/teams-samples

## General resources

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

-   **Office add-in monthly call --** July 14th at 8:00 am PDT |
    [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscommunitycall)
-   **SharePoint Framework call** **--** July 15th at 7:00 am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **Microsoft Identity Platform** -- July 15th at 9:00 am PDT |
    <https://aka.ms/IDDevCommunityCalendar>
-   **Power Apps monthly call** **--** July 21st at 8:00 am PDT |
    <https://aka.ms/PowerAppsMonthlyCall>
-   **M365 General Dev call** **--** July 22nd at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Adaptive Cards monthly call** **--** August 12th at 9:00 am PDT
    | <https://aka.ms/adaptivecardscommunitycall>
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

*Microsoft 365 PnP team, Microsoft - 8th of July 2021*
