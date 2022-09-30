---
title: "Microsoft 365 Developer Community Call recording -- 22nd of July, 2021"
date: 2021-07-22T05:41:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 Developer Community Call"]
images:
- images/sig-recordingly-22nd-july.png
tags: []
type: "regular"
---

## Call summary



Summer break and community call schedule updates reviewed. Preview the
new [Microsoft 365 Extensibility look book
gallery](https://adoption.microsoft.com/extensibility-look-book). 
Looking to get started with Microsoft Teams development?  Don't miss out
on our [Teams samples gallery](https://aka.ms/teams-samples) (updated
sample browser in June), and the new Microsoft 365 tenant -- [script
samples gallery](https://aka.ms/script-samples) - s*cripts for
PowerShell and CLIs. * Sign up and attend one of a growing list of
events hosted by [Sharing is
Caring](https://pnp.github.io/sharing-is-caring/) this month.  Announced
[PnP Recognition Program](https://aka.ms/m365pnp-recognition) and
availability of [Power Platform
Samples](https://aka.ms/powerplatform-samples).  Heads down on PnP
project bug fixes, new idea prototyping, and vacationing this month.  
**Open-source project status:  (Bold indicates new this call)**
  ----------------------------------------- ---------------------------------------------------------------- ------------------------------
  **Project**                               **Current Version**                                              **Release/Status**
  PnP .NET Libraries - PnP Framework        v1.5.0 GA, **PnP Provisioning Engine Schema v202103 released**   Version 1.6.0 -- Summer 2021
  PnP .NET Libraries - PnP Core SDK         v1.2.0 GA                                                        Version 1.3.0 -- Summer 2021
  PnP PowerShell                            v1.6.0  GA                                                        
  Yo teams - generator-teams                v3.2.0 GA                                                        v3.3.0 Preview soonish
  Yo teams - yoteams-build-core             v1.2.0 GA, v1.2.1 Preview                                         
  Yo teams -- yoteams-deploy                v1.1.0 GA                                                         
  Yo teams - msteams-react-base-component   v3.1.0                                                            
  Microsoft Graph Toolkit (MGT)             v2.2.0 GA                                                        Bug fixes and Updates
  ----------------------------------------- ---------------------------------------------------------------- ------------------------------
Two new Teams samples showcasing Adaptive Cards Universal Action Model. 
Great work!  The host of this call was [David Warner
II](https://twitter.com/DavidWarnerII) (Catapult Systems)
@DavidWarnerII.   Q&A takes place in chat throughout the call.


**Register for Sharing is Caring Events**:

-   Register for Sharing is Caring Events:
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
    -   Ask Me Anything -- Power Platform Development & Samples --
        [September
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNFJZNThMWFk0QlEzWFJNVE5aNVMzM1UwUi4u)
    -   First Time Presenter -- [August
        30th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- TBS
    -   Maturity Model Practitioners -- [August
        17th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
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

-   [**[Card Bot - Bot showcasing the Adaptive Card Universal Action
    Model in Node/TypeScript](https://aka.ms/bot-uam-cardbot)** - [Rabia
    Williams](https://twitter.com/williamsrabia) |
    [rabwill](https://github.com/rabwill)]{style="font-size: 10.5pt; font-family: 'Segoe UI',sans-serif;"}

-   [[**MS Teams Incident Management
    Bot**](https://aka.ms/bot-teams-incidentmanagement) - [Nanddeep
    Nachan](https://twitter.com/NanddeepNachan) |
    [nanddeepn](https://github.com/nanddeepn)]{style="font-size: 10.5pt; font-family: 'Segoe UI',sans-serif;"}

## Demos

Demos delivered in this session

-   **Publish a connector to the Power Platform** -- announcement July
    19, anyone can submit a connector to the Microsoft Power Platform,
    need not be the API owner.  Hear about the mission, goals and
    benefits of the Independent Publisher Connector Program.  See a demo
    of the Airtable connector in Power Automate.   Learn about the
    certification process in GitHub, connectors being developed
    presently and about how to get plugged into program communications
    channels. 

-   **How to update an Adaptive Card with a Teams Messaging Extension
    and MessagePreview** -- call on an action-based messaging extension
    created with the Teams Yeoman Generator to post a simple adaptive
    card to a Microsoft Team's news channel.  Post 'as a bot' and
    with an action to update the same adaptive card again and again, as
    opposed to a 1-time action.  Use workflow to cap number of
    permissible card updates, if necessary.

-   **ACS -- Teams InterOp with Call Routing** -- see the seamless
    interoperation between Azure Communication Services (ACS) and
    Microsoft Teams that enables a business user with a Teams license to
    have a video call/chat with a citizen consumer who doesn't have a
    Teams license.   The B2C solution uses a Bot for agent routing,
    adaptive cards for communications, and ACS for a web-based video
    call from desktop or mobile.    Sample in PnP samples repository.   

Thank you for your work. Samples are often showcased in Demos.

## Topics

Topics covered in this call

-   PnP .NET library updates - [Paolo
    Pialorsi](https://twitter.com/paolopia) (PiaSys.com) |
    @paolopia - [7:46](https://youtu.be/ebOtM8LpAK4?t=466)

-   PnP PowerShell - [Paolo
    Pialorsi](https://twitter.com/paolopia) (PiaSys.com) | @paolopia -
    [9:01](https://youtu.be/ebOtM8LpAK4?t=541)

-   yo Teams updates - [Paolo
    Pialorsi](https://twitter.com/paolopia) (PiaSys.com) | @paolopia -
    [9:50](https://youtu.be/ebOtM8LpAK4?t=590)

-   Microsoft Graph Toolkit updates - [Beth
    Pan](https://twitter.com/beth_panx) (Microsoft)
    | [beth-panx](https://github.com/beth-panx) - [10:37](https://youtu.be/ebOtM8LpAK4?t=637)

-   Microsoft Teams Samples - [Bob
    German](https://twitter.com/Bob1German) (Microsoft) | @Bob1German -
    [11:55](https://youtu.be/ebOtM8LpAK4?t=715)

-   Microsoft Power Platform Samples - [April
    Dunnam](https://twitter.com/aprildunnam) (Microsoft) |
    @aprildunnam - [13:05](https://youtu.be/ebOtM8LpAK4?t=785)

-   **Demo:**  Publish a connector to the Power Platform -- Natalie
    Pienkowska (Microsoft) - [14:54](https://youtu.be/ebOtM8LpAK4?t=894)

-   **Demo:**  How to update an Adaptive Card with a Teams Messaging
    Extension and MessagePreview -- [Markus
    Möller](https://twitter.com/Moeller2_0) (Avanade) | @Moeller2_0 -
    [24:29](https://youtu.be/ebOtM8LpAK4?t=1469)

-   **Demo:**  ACS -- Teams InterOp with Call Routing -- Sathya
    Raveendran
    (Microsoft) [-][ [34:56](https://youtu.be/ebOtM8LpAK4?t=2096)][ ]

## Resources

Additional resources around the covered topics and links from the
slides.

-   Repo - [Welcome to the Independent Publisher Connector
    Directory!](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) 

-   Blog - [New connectors through the Independent Publisher connector
    program](https://flow.microsoft.com/blog/new-connectors-through-the-independent-publisher-connector-program/) 

-   Blog - [Submit a connector to the Power Platform as an Independent
    Publisher](https://flow.microsoft.com/blog/submit-a-connector-to-the-power-platform-as-an-independent-publisher/) 

-   Documentation - [Independent publisher certification
    process](https://docs.microsoft.com/connectors/custom-connectors/certification-submission-ip) 

-   Video - [Independent Publisher Connector
    Program](https://channel9.msdn.com/Shows/POWERful-Devs/Power-Platform-Community-Connectors) 

-   Blog - [How to update an Adaptive Card with a Teams Messaging
    Extension](https://mmsharepoint.wordpress.com/2021/05/05/how-to-update-an-adaptivecard-with-a-teams-messaging-extension/) 

-   Sample - [Action Preview - Microsoft Teams
    App](https://github.com/pnp/teams-dev-samples/tree/main/samples/msgext-action-preview) 

-   Sample - [Azure Communication Services -- Teams InterOp with Call
    Routing](https://github.com/pnp/teams-dev-samples/tree/main/samples/app-acs-calling) 

-   Archives - Microsoft 365 PnP Weekly -
    [Videos](https://www.youtube.com/playlist?list=PLR9nK3mnD-OVYI-St_CBiFfuL4CZbBpkC),
    [Podcasts](https://pnpweekly.podbean.com/)  

-   Samples - [Power Platform
    Samples](https://aka.ms/powerplatform-samples) |
    [aka.ms/](https://aka.ms/powerplatform-samples)[powerplatform](https://aka.ms/powerplatform-samples)[-samples](https://aka.ms/powerplatform-samples)

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


-   **SharePoint Framework call** -- July 29th at 7:00 am PDT
    **| **<https://aka.ms/spdev-spfx-call>
-   **M365 General Dev call** -- August 5th at 7:00 am PDT
    **| **<https://aka.ms/m365-dev-sig>
-   **Office add-in monthly call** -- August 11th at 8:00 am PDT
    **| **<https://aka.ms/officeaddinscall>
-   **Adaptive Cards monthly call** -- August 12th at 9:00 am PDT
    **| **<https://aka.ms/adaptivecardscommunitycall>
-   **Power Apps monthly call** -- August 18th at 8:00 am PDT
    **| **<https://aka.ms/PowerAppsMonthlyCall>
-   **Microsoft Identity Platform** -- August 19th at 9:00 am PDT
    **| **<https://aka.ms/IDDevCommunityCalendar>
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

*Microsoft 365 PnP team, Microsoft - 22nd of July 2021*
