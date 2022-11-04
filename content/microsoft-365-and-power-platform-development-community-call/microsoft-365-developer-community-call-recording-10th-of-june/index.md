---
title: "Microsoft 365 Developer Community Call recording -- 10th of June, 2021"
date: 2021-06-10T11:24:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/m365-general-10th-june-recording.png
tags: []
type: "regular"
---

Recording of the Microsoft 365 -- General M365 development Special
Interest Group (SIG) community call from June 10, 2021.


## Call summary



Summer break and community call schedule updates reviewed. You are
invited to join the [Viva Connections private
preview](https://aka.ms/viva/connections/preview/register)!   Preview
the new [Microsoft 365 Extensibility look book
gallery](https://adoption.microsoft.com/extensibility-look-book). 
Looking to get started with Microsoft Teams development?  Don't miss out
our [Teams samples gallery](https://aka.ms/teams-samples), and the new
Microsoft 365 tenant -- [script samples
gallery](https://aka.ms/script-samples) - s*cripts for PowerShell and
CLIs. * Sign up and attend one of a growing list of events hosted by
[Sharing is Caring](https://pnp.github.io/sharing-is-caring/) this
month.   Check out the new [PnP Teams
Quickstart](https://aka.ms/pnp-teams-quickstart). 
Recent PnP project releases include:  PnP Core SDK v1.2.0 GA, PnP
Framework v1.5.0 GA, PnP PowerShell v1.6.0 GA, Yo teams -
generator-teams v3.2.0 GA, yoteams-build-core V1.2.0 GA + v1.2.1
Preview, yoteams-deploy v1.0.0 GA and finally component updates to
Microsoft Graph Toolkit (MGT) v.2.2.0 GA.   
**Open-source project status:  (Bold indicates new this call)**
  ----------------------------------------- ------------------------------- ----------------------------------
  **Project**                               **Current Version**             **Release/Status**
  PnP .NET Libraries - PnP Framework        **v1.5.0 GA**                   **Version 1.6.0 -- Summer 2021**
  PnP .NET Libraries - PnP Core SDK         **v1.2.0 GA**                   **Version 1.3.0 -- Summer 2021**
  PnP PowerShell                            **v1.6.0  GA**                   
  Yo teams - generator-teams                **v3.2.0 GA**                    
  Yo teams - yoteams-build-core             **v1.2.0 GA, v1.2.1 Preview**    
  Yo teams -- yoteams-deploy                **v1.1.0 GA**                    
  Yo teams - msteams-react-base-component   v3.1.0                           
  Microsoft Graph Toolkit (MGT)             v2.2.0 GA                       Regular component updates
  ----------------------------------------- ------------------------------- ----------------------------------
Additionally, 1 new Teams samples were delivered in the last 2 weeks. 
The host of this call was Vesa Juvonen (Microsoft) |@vesajuvonen.  Q&A
takes place in chat throughout the call.


-   Join on the Viva Connections private preview!
    | [aka.ms/viva/connections/preview/register](https://aka.ms/viva/connections/preview/register)
-   **Feedback wanted:  Regarding PnP PowerShell** -- "What if we did
    not return classic CSOM objects from the cmdlets?"  Comments to: 
    @erwinvanhunen.    
-   Save the date to the Microsoft Teams monthly community call on the
    15th of June @ 8 AM PT |
    <https://aka.ms/microsoftteamscommunitycall>  
-   **Register for Sharing is Caring Events**:

    -   First Time Contributor Session -- [June
        29th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session -- [June
        23rd](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
         
    -   PnP -- SPFx Developer Workstation Setup -- [June
        17th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
         
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [June
        24th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   Ask Me Anything -- Teams Dev - July
    -   First Time Presenter -- [June
        30th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- [June
        16th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
    -   Maturity Model Practitioners -- [June
        15th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    -   PnP Office Hours -- 1:1 session -
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
-   Download the recurrent invite for this call
    -- <https://aka.ms/m365-dev-sig>
-   Call attention to your great work by using
    the [#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click) on
    Twitter.
**Microsoft Teams Development
Samples:  **(<https://aka.ms/TeamsSampleBrowser>)

-   **[Configure Teams applications with Azure App
    Configuration](https://aka.ms/msgext-graph-action-config) -**
    [Markus Moeller](https://twitter.com/Moeller2_0) | @Moeller2_0 


## Demos

Demos delivered in this session

-   **Remote Event Receiver Manager solution in SPFx for managing list
    events** -

    A very simple web part that lets users view, add and delete remote
    event receivers in lists.   Review what is a Remote Event Receiver,
    Strengths and Weaknesses, and when/not to consider using Power
    Automate to accomplish task.   Use the sample to quickly identify
    Event Receivers in lists across a tenant without having to connect
    to PowerShell or go to a REST API.

-   **Preview on list formatting demo site template** -- as an
    alternative to going to GitHub to pull samples, the Community team
    is experimenting with an additional layout option -- List Formatting
    Sample Showcase pages that display fully functional samples Power
    Users can manipulate, drill in to view/customize data, and get
    additional details in GitHub - from within a browser!   You may even
    adopt this formatting in your own tenant.  Available soon. 

-   **Getting started on using Time Clock Microsoft Graph APIs to
    clock in and out of a shift** -- the time tracking component (Time
    Clock APIs) in the Teams Shifts Application provides clock in / out,
    timesheet edit and more capabilities that auto-syncs to Payroll /
    T&A apps like Cronos, Workday, ADP, Ceridian SAP.  Call the APIs to
    integrate with your customer's payroll and T&A systems using Time
    Clock APIs (beta).  Supports CRUD operations and WebHooks.  Request
    handling guidance in the documentation.

     

Thank you for your work. Samples are often showcased in Demos.

## Topics

Topics covered in this call

-   PnP .NET library updates - [Bert
    Jansen](https://twitter.com/O365bert) (Microsoft) | @O365bert
    - [10:31](https://youtu.be/qOgH82b5Jw4?t=631)

-   PnP PowerShell updates -[ Erwin van
    Hunen](https://twitter.com/erwinvanhunen) (Valo Intranet)
    | @erwinvanhunen - [12:59](https://youtu.be/qOgH82b5Jw4?t=779)

-   yo Teams updates - [Wictor Wilén](https://twitter.com/wictor)
    (Avanade) | @wictor - [14:23](https://youtu.be/qOgH82b5Jw4?t=863)

-   Microsoft Graph Toolkit updates - [Beth
    Pan](https://twitter.com/beth_panx) (Microsoft)
    | [beth-panx](https://github.com/beth-panx) - [16:42](https://youtu.be/qOgH82b5Jw4?t=1002)

-   Microsoft Teams Samples - [Bob
    German](https://twitter.com/Bob1German) (Microsoft) | @Bob1German -
    [18:22](https://youtu.be/qOgH82b5Jw4?t=1102)

-   **Demo: ** Remote Event Receiver Manager solution in SPFx for
    managing list events -- [Dan Toft](https://twitter.com/tanddant)
    (Evobis ApS) | @tanddant -
    [20:22](https://youtu.be/qOgH82b5Jw4?t=1222)

-   **Demo: ** Preview on list formatting demo site template -- [Chris
    Kent](https://twitter.com/theChrisKent) (DMI) | @theChrisKent -
    [31:32](https://youtu.be/qOgH82b5Jw4?t=1892)

-   **Demo: ** Getting started on using Time Clock Microsoft Graph APIs
    to clock in and out of a shift -- Aarthi Kumar
    (Microsoft) [-][ [41:20](https://youtu.be/qOgH82b5Jw4?t=2480)][[ ]](https://youtu.be/qOgH82b5Jw4?t=2480)


## Resources


Additional resources around the covered topics and links from the
slides.

-   Samples - [Remote Event Receiver
    Manager](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-remote-event-receiver-manager) 

-   Documentation - [Use remote event receivers in
    SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/use-remote-event-receivers-in-sharepoint)

-   Repo - [SharePoint List Formatting
    Samples](https://github.com/pnp/List-Formatting) 

-   GitHub - [SharePoint List Formatting
    Samples](https://pnp.github.io/List-Formatting/)

-   Documentation - [shift resource
    type](https://docs.microsoft.com/graph/api/resources/shift?view=graph-rest-1.0) 

-   Documentation - [timecard resource
    type](https://docs.microsoft.com/graph/api/resources/timecard?view=graph-rest-beta) 

-   Documentation -- [Webhook to Shifts
    changes](https://docs.microsoft.com/graph/api/resources/workforceintegration?view=graph-rest-1.0) 

-   PnP Weekly -- Episode 130 with the Software Engineer behind the
    Microsoft Graph Toolkit, [Nikola
    Metulev](https://twitter.com/metulev) (Microsoft) | @metulev. |
    [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-130/ba-p/2422722)
    |
    [podcast](https://pnpweekly.podbean.com/e/Microsoft-365-pnp-weekly-episode-130-7th-of-june-2021/)

-   [Microsoft 365 tenant -- ][Script
    Samples Gallery](https://aka.ms/script-samples)[ |
    aka.ms/script-samples]

-   PnP Teams Quickstart |
    [aka.ms/pnp-teams-quickstart](https://aka.ms/pnp-teams-quickstart)

-   [Microsoft 365 Extensibility look book
    gallery](https://adoption.microsoft.com/extensibility-look-book?WT.mc_id=m365-24198-cxa) |
    aka.ms/m365/extensibility

-   [Microsoft Teams Samples
    Gallery](https://pnp.github.io/teams-dev-samples/) |
    aka.ms/teams-samples

## General resources

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
-   [eloper program
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

-   **Microsoft Teams monthly call --** June 15th at 8:00 am PDT |
    <https://aka.ms/microsoftteamscommunitycall>
-   **Power Apps monthly call --** June 16th at 8:00 am PDT |
    <https://aka.ms/PowerAppsMonthlyCall>
-   **SharePoint Framework call** -- June 17that 7:00 am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **Microsoft Identity Platform --** June 17th at 9:00 am PDT |
    <https://aka.ms/IDDevCommunityCalendar>
-   **M365 General Dev call --** June 24th at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Office add-in monthly call --** July 14th at 8:00 am PDT |
    [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscommunitycall)
-   **Adaptive Cards monthly call --** [July
    8]th[ at 9:00 am PDT |
    ]<https://aka.ms/adaptivecardscommunitycall>
General  Special Interest Group bi-weekly calls are
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

*Microsoft 365 PnP team, Microsoft - 11th of June 2021*

