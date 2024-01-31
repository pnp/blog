---
title: "Microsoft 365 Developer Community Call recording -- 16th of September, 2021"
date: 2021-09-16T03:34:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/call-16th-sep-recording.png
tags: []
type: "regular"
---



## Call Summary




Have a look at Microsoft 365 tenant -- [script samples
gallery](https://aka.ms/script-samples) (84 scenarios and 111
scripts)*. * Sign up and attend an event hosted by [Sharing is
Caring](https://pnp.github.io/sharing-is-caring/).  Have you signed up
for the [PnP Recognition Program](https://aka.ms/m365pnp-recognition)? 
 Do it.  Project releases this week include **Yo teams -
generator-teams** v3.3.0 Preview2, **-- yoteams-build-core** v1.2.1 GA +
v1.3.0 Preview and **- yoteams-deploy** v1.0.1 GA, and also **Microsoft
Graph Toolkit (MGT)** v2.3.0 GA.  All key features in this release of
MGT were contributed by the community!
**Open-source project status:  (Bold indicates new this call)**
  ----------------------------------------- --------------------------------------------------- ------------------------------------
  **Project**                               **Current Version**                                 **Release/Status**
  PnP .NET Libraries - PnP Framework        v1.6.0 GA, PnP Provisioning Engine Schema v202103   Prepping for Version 1.7.0 release
  PnP .NET Libraries - PnP Core SDK         v1.3.0 GA                                           Prepping for Version 1.4.0 release
  PnP PowerShell                            v1.7.0 GA                                           **52nd nightly release\***
  Yo teams - generator-teams                v3.2.0 GA, **v3.3.0 Preview2**                       
  Yo teams - yoteams-build-core             **v1.2.1 GA, v1.3.0 Preview**                        
  Yo teams -- yoteams-deploy                **v1.0.1 GA**                                        
  Yo teams - msteams-react-base-component   v3.1.0                                               
  Microsoft Graph Toolkit (MGT)             **v2.3.0 GA**                                        
  ----------------------------------------- --------------------------------------------------- ------------------------------------

**\* Note:  While version releases are periodic, nightly releases are
nightly!  Subscribe to nightly releases for the latest capabilities. 
    **

There were 3 new script samples this week.  The host of this call was
[David Warner II](https://twitter.com/DavidWarnerII) (Catapult Systems)
@DavidWarnerII.   Q&A takes place in chat throughout the call.

## Actions





-   Create a Teams Sample - [Microsoft Teams Samples Wish
    list](https://github.com/pnp/teams-dev-samples/issues) -- 10
    opportunities to share your Teams Dev prowess with the community
    | [<https://aka.ms/teams-sample-wishlist>]{.underline}
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
    -   Ask Me anything (AMA) -- Recognition Program -- [September
        7th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNzVJQTEyMkw4VVBIVjc3NE9PWDFDM1M3My4u)
    -   Ask Me anything (AMA) -- Script Samples -- [September
        14th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURjNZTDA4VEJGNUYyMVlCNkZUVzlYQ0FaQy4u)
    -   Ask Me Anything (AMA) -- Power Platform Development & Samples
        -- [September
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNFJZNThMWFk0QlEzWFJNVE5aNVMzM1UwUi4u)
    -   Ask Me Anything (AMA) -- List Formatting -- [October
        5th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNTVHSFFMRDdDSjA0MklUSUtTQ0IxMFpPNS4u)
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
    -- <https://aka.ms/m365-dev-sig>
-   Call attention to your great work by using
    the [#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click) on
    Twitter.
**Microsoft Teams Development
Samples:  **(<https://aka.ms/TeamsSampleBrowser>)

-   **[Teams Tab with SSO and Microsoft Graph Toolkit
    usage](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-mgt-person)** - [Markus
    Möller](https://twitter.com/Moeller2_0) (Avanade) | @Moeller2_0
-   **[Teams Tab Single Sign-on (SSO)
    Sample](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-sso) **(updated) **- **Doğan
    Erişen (Microsoft)
**Microsoft Power Platform
Samples:  **([https://aka.ms/powerplatform-samples)](https://aka.ms/powerplatform-samples)

-   No new Power Platform samples this week
**Script
Samples: ** ([https://aka.ms/script-samples)](https://aka.ms/script-samples)

-   **[Provision Home Page to a SharePoint
    site](https://pnp.github.io/script-samples/spo-provision-homepage/README.html?tabs=pnpps)
    -** [Reshmee Auckloo](https://twitter.com/ReshmeeAuckloo) |
    @reshmeeauckloo
-   **[Extract Modern Pages to Individual Provisioning
    Files](https://pnp.github.io/script-samples/spo-extract-modern-pages/README.html?tabs=pnpps)
    -** [Paul Bullock](https://twitter.com/pkbullock) (CaPa Creative Ltd)
    | @pkbullock
-   **[Generate Demo Events for SharePoint Events
    List](https://pnp.github.io/script-samples/spo-generate-demo-events/README.html?tabs=pnpps)
    -** [Paul Bullock](https://twitter.com/pkbullock) (CaPa Creative Ltd)
    | @pkbullock

## Demos

Demos delivered in this session

-   **List Formatting Magic Tips & Tricks​** -- create a list, add and
    format a location column.  Add a location with link to a map and
    then add multiple sub properties (street, state, country) under the
    Location's name.  Add a weather column and formatting to display an
    image and details for weather.  When list items are updated, then
    weather entries will be updated.   Implement this today -- get the
    address and weather samples.

-   **Build your first conversational chatbot for Teams** -- create a
    new bot in Composer (use Core Bot with Language template), set up
    Language Understanding in Azure, install the Teams package into the
    new project (in Composer), add triggers to operate in Teams and to
    receive and respond to orders.  Conduct your Pizza business via an
    Adaptive Card and task modules.  Build task modules using Bot
    Framework Composer without writing (almost) any code!   

-   **Updates on the Independent Publishing Connectors for Power
    Platform** -- beginning with a report on number of connectors
    delivered to date and in the pipeline followed by an experiential
    show-and-tell of the Yelp connector.   Yelp connector services --
    get business details, get reviews, search business phones and search
    businesses, allows users to search for business by location, phone,
    and product and more from millions of businesses across 32
    countries.   

Thank you for your work. Samples are often showcased in Demos.   
Request a Demo spot on the call -- <https://aka.ms/m365pnp/request/demo>

## Topics

Topics covered in this call

-   PnP .NET library updates - [Bert
    Jansen](https://twitter.com/O365bert) (Microsoft)
    @O365bert - [6:32](https://youtu.be/PpjPCt00W9A?t=392)
-   PnP PowerShell - [Erwin van Hunen](https://twitter.com/erwinvanhunen)
    (Valo Intranet) | @erwinvanhunen -
    [8:20](https://youtu.be/PpjPCt00W9A?t=500)
-   yo Teams updates - [Wictor Wilén](https://twitter.com/wictor)
    (Microsoft) | @wictor - [9:57](https://youtu.be/PpjPCt00W9A?t=597)
-   Microsoft Graph Toolkit updates - [Elise
    Yang](https://twitter.com/elisenyang) (Microsoft) |
    @elisenyang
-   Microsoft Teams Samples - [David Warner
    II](https://twitter.com/DavidWarnerII) (Catapult Systems)
    | @DavidWarnerII - [14:00](https://youtu.be/PpjPCt00W9A?t=840)
-   Microsoft Power Platform Samples - [April
    Dunnam](https://twitter.com/aprildunnam) (Microsoft) | @aprildunnam
     - [14:28](https://youtu.be/PpjPCt00W9A?t=868)
-   **D1:**  List formatting magic tips and tricks -- [Chris
    Kent](https://twitter.com/theChrisKent) (DMI) | @theChrisKent -
    [16:06](https://youtu.be/PpjPCt00W9A?t=966)
-   **D2:**  Getting started with Bot Framework Composer for building
    Teams Task Modules -- [Stephan
    Bisser](https://twitter.com/stephanbisser) (Solvion) |
    @stephanbisser - [29:27](https://youtu.be/PpjPCt00W9A?t=1767)
-   **D3:**  Updates on Independent Publisher Connectors for Power
    Platform & Yelp Connector Demo -- [Natalie
    Pienkowska](https://twitter.com/NataliePienkow1) (Microsoft) |
    @NataliePienkow1 & [Ahmad Najjar](https://twitter.com/ahmadn82)
    (Infoworker) | @ahmadn82 -
    [43:33](https://youtu.be/PpjPCt00W9A?t=2613) 



## Resources

Additional resources around the covered topics and links from the
slides.

-   D1:  Sample - [Display Location Address
    Details](https://github.com/pnp/List-Formatting/tree/master/column-samples/location-address) 

-   D1:  Sample - [Display Location Weather
    Details](https://github.com/pnp/List-Formatting/tree/master/column-samples/location-weather) 

-   [D2:  Documentation - ][Bot Framework
    Composer
    documentation](https://aka.ms/bfcomposer)

-   [D2:  Article - ][Bot Framework
    Composer Series - 3 - Teams Task
    Modules](https://bisser.io/bot-framework-composer-series-3-teams-task-modules/)

-   [D2:  Repo -
    ][microsoft/BotFramework-Composer](https://github.com/microsoft/BotFramework-Composer)

-   [D3:  Website --
    ][Yelp](https://www.yelp.com/)

-   [D3:  Website -- ][Yelp
    Developers](https://www.yelp.com/developers)

-   [D3:  Website -- ][Yelp Fusion
    API](https://www.yelp.com/fusion)

-   [[D3:  Documentation - ][Yelp
    (Independent Publisher)
    (Preview)](https://learn.microsoft.com/connectors/yelpip/)]

-   D3:  Repo -
    [PowerPlatformConnectors/independent-publisher-connectors/Yelp/](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Yelp)

-   D3:  Connectors - [Microsoft Power Platform
    Connectors](https://github.com/microsoft/PowerPlatformConnectors) 

-   D3:  Demo - [Publish a connector to the Power
    Platform](https://youtu.be/ulTBvCHw8MU) -- [Natalie
    Pienkowska](https://twitter.com/NataliePienkow1) (Microsoft)  |
    @NataliePienkow1

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
    documentation](https://learn.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-tenant-templates?WT.mc_id=m365-24198-cxa)
-   [SharePoint Page Transformation webcast
    series](https://developer.microsoft.com/sharepoint/blogs/sharepoint-page-transformation-webcast-series?WT.mc_id=m365-24198-cxa)
-   [PnP Power Shell](https://aka.ms/sppnp-powershell)
-   [SharePoint Modernization
    Tools](https://github.com/SharePoint/sp-dev-modernization/tree/dev/Tools)

## Upcoming Calls | Recurrent Invites


-   **Microsoft 365 platform call** -- September 21st at 8:00 am PDT
    | <https://aka.ms/m365-dev-call>
-   **SharePoint Framework call** -- September 23rd at 7:00 am PDT
    | <https://aka.ms/spdev-spfx-call>
-   **M365 General Dev call** -- September 30th at 7:00 am PDT
    | <https://aka.ms/m365-dev-sig>
-   **Office add-in monthly call** -- October 13th at 8:00 am PDT
    | <https://aka.ms/officeaddinscall>
-   **Adaptive Cards monthly call** -- October14th at 9:00 am PDT
| <https://aka.ms/adaptivecardscommunitycall>

-   **Power Apps monthly call**-- October 20th at 8:00 am PDT
    | <https://aka.ms/PowerAppsMonthlyCall>
-   **Microsoft Identity Platform call** -- October 21st at 9:00 am
    PDT | <https://aka.ms/IDDevCommunityCalendar>
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

*Microsoft 365 PnP team, Microsoft - 17th of September 2021*
