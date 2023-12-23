---
title: "Microsoft 365 Developer Community Call recording – 3rd of February, 2022"
date: 2022-02-04T03:09:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-3rd-feb.png
tags: ["Office Add-ins", "SPFx Extensions","Microsoft 365", "Microsoft Graph","Microsoft Teams","SharePoint","SharePoint Framework (SPFx)"]
type: "regular"
summary: "One location the Microsoft 365 tenant – script samples gallery (136 scenarios and 187 scripts) including recently added Teams PowerShell support!  Sign up and attend an AMA and other events this month hosted by Sharing is Caring.  Get the recognition you deserve, sign up for the PnP Recognition Program.  Heads down on PnP projects.  Expecting to ship Microsoft Graph Toolkit v2.3.2 on Friday!  To see current releases and latest updates/nightly builds, access the Repos via the links in table below.  There were 5 new/updated script, 5 Power Platform samples delivered this week."
videos:
- https://www.youtube.com/watch?v=1zeXVvcBIJo
---


## Call summary

One location the Microsoft 365 tenant – [script samples gallery](https://aka.ms/script-samples) (136 scenarios and 187 scripts) including recently added Teams PowerShell support!  Sign up and attend an AMA and other events this month hosted by [Sharing is Caring](https://pnp.github.io/sharing-is-caring/).  Get the recognition you deserve, sign up for the [PnP Recognition Program](https://aka.ms/m365pnp-recognition).  Heads down on PnP projects.  Expecting to ship **Microsoft Graph Toolkit** v2.3.2 on Friday!  To see current releases and latest updates/nightly builds, access the Repos via the links in table below.  There were 5 new/updated script, 5 Power Platform samples delivered this week.  

## Open-source project status

(**Bold** indicates new this call)**

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.8.0 GA with .NET 6.0 support added|Prepping v1.9
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.5.0 GA with .NET 6.0 support added|Prepping v1.6
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.9.0 GA|In progress: V2 POC, Prepping for v1.8, nightly releases
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v3.5.0 GA|v4.0.0-next
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.5.0 GA, Next: v1.6.0-next.1|
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.1.0 GA
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.3.1 GA, TeamsFx authentication provider preview!|**Shipping v2.3.2 on Friday!**  Working on v3.0.0 - Aligning all Toolkit components to Fluent UI Web Components

{{< notice note>}}
While version releases are periodic, nightly releases are nightly!  Subscribe to nightly releases for the latest capabilities.
{{< /notice >}}


The host of this call was [David Warner II](https://twitter.com/DavidWarnerII) (Catapult Systems) | @DavidWarnerII.   Q&A takes place in chat throughout the call.

{{< youtube 1zeXVvcBIJo >}}

## Actions

*   Opt into PnP Recognition Program | [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
*   Join us at the next **Microsoft 365 platform call 8th of February @ 8 AM PT**
    *   Latest news from Microsoft engineering on Microsoft 365 topics
    *   Demos: 
        *   **Dave Randall** - Introduction to Intune APIs on Microsoft Graph
        *   **Patrick Rogers** - Creating engaging and dynamic Viva Connections mobile experiences
        *   **Sébastien Levert** - Using the MGT Files Components in your solutions
*   **Register for Sharing is Caring Events:** 
    *   PnP Sharing is Caring - AMA (Ask Me Anything) - SPFx React Controls – [Tuesday, February 22nd, 9am PST](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNjg1UVhPV0JHTjRLNDZISkM4MEI0VDZWSC4u)
    *   PnP Sharing is Caring - AMA (Ask Me Anything) -- Microsoft Graph Toolkit - [Tuesday, March 1st, 9am PST](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNVNHNlhNTkczNjRKM0hZR1NWVUw2QUhRQi4u)
    *   First Time Contributor Session – TBS soon
    *   Community Docs Session – TBS soon 
    *   Power Platform Samples – First Time Contributor – [Monday, February 14th, 1pm PST](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMTFJWFFGVUxBNUFZQjZWRUdaOE5BMFkwNS4u)
    *   PnP – SPFx Developer Workstation Setup – [Tuesday, February 8th, 2pm PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
    *   PnP SPFx Samples – Solving SPFx version differences using Node Version Manager – TBS soon
    *   First Time Presenter – [Wednesday, February 9th, 9am PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    *   More than Code with VSCode – [Tuesday, February 15th, 2pm PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
    *   Maturity Model Practitioners – [Tuesday, February 15th, 7am PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u) (every 3rd Tuesday of month, 7:00am PT)
    *   Getting Started with Viva Connection ACEs (2-part session) – TBS soon
    *   PnP Office Hours – 1:1 session – [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    *   PnP Buddy System – [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
*   Download the recurrent invite for this call – [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig)
*   Call attention to your great work by using the [#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click) on Twitter.

## Microsoft Teams Development Samples

<https://aka.ms/TeamsSampleBrowser>

*   Samples Wanted!  

## Microsoft Power Platform Samples

<https://aka.ms/powerplatform-samples>

*   **Create M365 Groups using Graph\* -** [Michel Mendes](https://twitter.com/michelcarlo) | @michelcarlo
*   **Hide List from Site Contents\* -** [Michel Mendes](https://twitter.com/michelcarlo) | @michelcarlo
*   **[Breadcrumb Component](https://github.com/pashasongz/powerapps-samples/tree/main/samples/breadcrumb-component) -** [Pavel Kovalevskij](https://www.linkedin.com/in/pavel-kovalevskij-4a55b41b2)
*   **SelfService Portal for Microsoft 365\* -** [Jan Bakker](https://twitter.com/janbakker_) | @janbakker\_
    [Albert-Jan Schot](https://twitter.com/appieschot) | @appieschot
*   **Users and Groups Directory\* -** [Siddharth Vaghasia](https://twitter.com/siddh_me) | @siddh\_me

\*These latest samples should show on site shortly after this call

## Script Samples

<https://aka.ms/script-samples>

2 New Scenarios and 3 Script Updates:

*   **[Delete a library exceeding the list threshold limit. Remove the files and folders before deleting th...](https://pnp.github.io/script-samples/spo-remove-large-library/README.html?tabs=pnpps)** \- [Adam Wójcik](https://twitter.com/Adam25858782) | @Adam25858782   
*   **[Get All Apps From The App Catalog And Export It To CSV](https://pnp.github.io/script-samples/spo-get-all-apps-from-appcatalog/README.html?tabs=pnpps)** - [Adam Wójcik](https://twitter.com/Adam25858782) | @Adam25858782   
*   **[Sample on a report showing how much SharePoint Storage you can save by trimming document versions on...](https://pnp.github.io/script-samples/spo-generate-sp-storage-savings-report/README.html?tabs=pnpps)** - [Kasper Bo Larsen](https://twitter.com/kasperbolarsen) | @kasperbolarsen   
*   **[Empty the tenant recycle bin](https://pnp.github.io/script-samples/spo-empty-tenant-recyclebin/README.html?tabs=cli-m365-ps)** - [Leon Armston](https://twitter.com/LeonArmston) | @LeonArmston 
*   **[Flow run status list dashboard](https://pnp.github.io/script-samples/flow-runs-status-list-dashboard/README.html?tabs=cli-m365-ps)** - [Ryan Healy](https://www.linkedin.com/in/ryanjonhealy/)         

Article:  [Getting started with PnP Script Samples](https://aka.ms/script-samples/getting-started) – aka.ms/script-samples/getting-started

– Many thanks!

## Demos

**Make a simple bot using Webhooks in Microsoft Teams** – this simple (request/response capability) Teams bot gets weather using an outgoing webhook.  A user @ mentions the webhook (@weather) and a location (London) triggering an Azure function, that calls the [OpenWeatherMap API](https://openweathermap.org/api) for local weather information.  An Adaptive Card is returned to user with weather conditions.   Technically, any member of a Team can create this simple webhook, not creating and registering a full-fledged bot.

**Use the Power Platform and Microsoft Teams to quiz yourself** – on details of what you read 3 months ago?  Happen to keep a list of what you read in SharePoint?  Want to create a no code solution to quiz yourself on past reads using Power Automate that pulls details transformed into questions from your list, shuffles the array of questions (for quiz experience), and renders them on an Adaptive Card that also evaluates your response?   

**Updates on Independent Publisher Connectors & Cloverly / Ecologi Connector Demo** – 72 connectors now in production more than half created by presenter – Troy.  29 connectors in the pipeline!  Shown are 2 connectors for accessing environmental sustainability data.  Access Cloverely’s API to calculate cost of carbon emitting activities and Ecologi for reports.  From both, users may purchase trees and carbon offsets.  Presenter’s Power App has buttons for purchasing trees, offsets, reports.  Connectors to be available soon.    

Thank you for your work. Samples are often showcased in Demos.    Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)

## Topics

*   PnP .NET library updates - [Bert Jansen](https://twitter.com/O365bert) (Microsoft) | @O365bert – [6:44](https://youtu.be/1zeXVvcBIJo?t=404)
*   PnP PowerShell updates \- [Bert Jansen](https://twitter.com/O365bert) (Microsoft) | @O365bert – [8:17](https://youtu.be/1zeXVvcBIJo?t=497)
*   yo Teams updates - [David Warner II](https://twitter.com/DavidWarnerII) (Catapult Systems) | @DavidWarnerII – [9:08](https://youtu.be/1zeXVvcBIJo?t=548)
*   Microsoft Graph Toolkit updates - [Sébastien Levert](https://twitter.com/sebastienlevert) (Microsoft) | [@sebastienlevert](/t5/user/viewprofilepage/user-id/926766) – [9:48](https://youtu.be/1zeXVvcBIJo?t=588)
*   Microsoft Script Samples - [Paul Bullock](https://twitter.com/pkbullock) (CaPa Creative Ltd) | @pkbullock – [2:47](https://youtu.be/1zeXVvcBIJo?t=167)
*   Microsoft Teams Samples - [Bob German](https://twitter.com/Bob1German) (Microsoft) | @Bob1German – [11:29](https://youtu.be/1zeXVvcBIJo?t=689)
*   Microsoft Power Platform Samples - [April Dunnam](https://twitter.com/aprildunnam) (Microsoft) | @aprildunnam – [12:05](https://youtu.be/1zeXVvcBIJo?t=725)
*   **Demo 1**:  Make a simple bot using Webhooks in Microsoft Teams – [Lee Ford](https://twitter.com/lee_ford) (Symity Ltd) | @lee\_ford – [14:32](https://youtu.be/1zeXVvcBIJo?t=872)
*   **Demo 2**:  Use the Power Platform and Microsoft Teams to quiz yourself – [Albert-Jan Schot](https://twitter.com/appieschot) (BLIS.digital) | @appieschot – [24:15](https://youtu.be/1zeXVvcBIJo?t=1455)
*   **Demo 3**:  Updates on Independent Publisher Connectors & Cloverly / Ecologi Connector Demo – [Natalie Pienkowska](https://twitter.com/NataliePienkow1) (Microsoft) | @NataliePienkow1 & [Troy Taylor](https://twitter.com/troystaylor) (Hitachi Solutions) | @troystaylor – [36:08](https://youtu.be/1zeXVvcBIJo?t=2168)

## Resources

Additional resources around the covered topics and links from the slides.

*   **D1**:  Article - [Make a bot for simple interactions in Teams using a Webhook](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/make-a-bot-for-simple-interactions-in-teams-using-a-webhook/ba-p/3064378) 
*   **D1**:  Sample - [teams-webhook-weatherbot-sample](https://github.com/leeford/teams-webhook-weatherbot-sample) 
*   **D2**:  Article - [Shuffle an array with Power Automate](https://www.cloudappie.nl/shuffle-array-power-automate/) 
*   **D3**:  Documentation - [Power Platform and Azure Logic Apps connectors documentation](https://docs.microsoft.com/connectors/) 
*   **D3**:  Connectors - [Welcome to the Independent Publisher Connector Directory!](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) 
*   **Microsoft 365 PnP Weekly – Episode 151** (January 31st) with UK-based SharePoint developer, architect and MVP, [Paul Bullock](https://twitter.com/pkbullock) | @pkbullock | [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-151-paul-bullock/ba-p/3091966) | [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-151-%E2%80%93-31st-of-january-2022/)
*   **Microsoft 365 PnP Weekly – Episode 150** (January 24th) with London, UK-based SharePoint developer architect and MVP, [Anoop Tatti](https://twitter.com/anooptells) (Content+Cloud) | @anooptells | [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-150-anoop-tatti-content-cloud/ba-p/3070120) | [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-150-%E2%80%93-24th-of-january-2022/)

## General resources

*   Script Samples - [Getting started with PnP Script Samples](https://aka.ms/script-samples/getting-started) – aka.ms/script-samples/getting-started
*   Samples - [Power Platform Samples](https://aka.ms/powerplatform-samples) | [aka.ms/](https://aka.ms/powerplatform-samples)[powerplatform](https://aka.ms/powerplatform-samples)[\-samples](https://aka.ms/powerplatform-samples)
*   Microsoft 365 tenant – [Script Samples Gallery](https://aka.ms/script-samples) | aka.ms/script-samples
*   [Microsoft Teams Samples Gallery](https://pnp.github.io/teams-dev-samples/) | aka.ms/teams-samples
*   [Microsoft 365 Extensibility look book gallery](https://adoption.microsoft.com/extensibility-look-book?WT.mc_id=m365-24198-cxa) | aka.ms/m365/extensibility
*   Archives - Microsoft 365 PnP Weekly - [Videos](https://www.youtube.com/playlist?list=PLR9nK3mnD-OVYI-St_CBiFfuL4CZbBpkC), [Podcasts](https://pnpweekly.podbean.com/)  
*   PnP Teams Quickstart | [aka.ms/pnp-teams-quickstart](https://aka.ms/pnp-teams-quickstart)
*   Microsoft Teams Toolkit v3.x | [https://aka.ms/teams-toolkit](https://aka.ms/teams-toolkit)
*   [Microsoft 365 PnP Community hub](https://techcommunity.microsoft.com/t5/microsoft-365-pnp/ct-p/Microsoft365PnP) | aka.ms/m365pnp/community 
*   Microsoft Graph Toolkit in Microsoft Learn | [https://aka.ms/learn-mgt](https://aka.ms/learn-mgt)
*   Viva Connections [https://aka.ms/VivaConnections](https://aka.ms/VivaConnections)
*   [SharePoint look book](https://lookbook.microsoft.com/?WT.mc_id=m365-24198-cxa)
*   [Yo Teams video training package](https://aka.ms/yoteams-training)
*   [.NET Standard 2.0 version of SharePoint Online CSOM API](https://developer.microsoft.com/microsoft-365/blogs/net-standard-version-of-sharepoint-online-csom-apis?WT.mc_id=m365-24198-cxa)
*   [Microsoft 365 community (PnP) videos](https://aka.ms/m365pnp-videos) | aka.ms/m365pnp-videos
*   [Microsoft Teams Toolkit for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension)
*   [yo Teams](https://aka.ms/yoteams) | aka.ms/yoteams
*   Video - [Getting started using yo Teams](https://youtu.be/w0OrFkzNC10) | [Wictor Wilén](https://twitter.com/wictor) (Avanade)| @wictor
*   [Build a crisis management site to connect people and information](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/build-a-crisis-management-site-to-connect-people-and-information/ba-p/1216791?WT.mc_id=m365-24198-cxa)
*   [Developer documentation](https://aka.ms/spdev-docs) | [https://aka.ms/spdev-docs](https://aka.ms/spdev-docs)
*   [PnP Power Shell](https://aka.ms/sppnp-powershell)
*   [SharePoint Modernization Partner Guidance](https://aka.ms/sppnp-modernization-partnerguidance) \- Feedback welcome
*   Solution - [Building a modern search experiences with SharePoint Framework web parts](https://aka.ms/pnp-modern-search)
*   [Page transformation guidance](https://aka.ms/sppnp-pagetransformation)
*   [Page transformation videos](https://aka.ms/sppnp-pagetransformationvideos)
*   [Modernization scanner](https://aka.ms/sppnp-modernizationscanner)
*   [Microsoft 365 developer program site](https://developer.microsoft.com/office/dev-program?WT.mc_id=m365-24198-cxa) \- Need to become a Tenant Admin to test look book capabilities? Get a Microsoft 365 E5 developer subscription (free tenant for 90 days)
*   [SharePoint Page Transformation webcast series](https://developer.microsoft.com/sharepoint/blogs/sharepoint-page-transformation-webcast-series?WT.mc_id=m365-24198-cxa)
*   [PnP Power Shell](https://aka.ms/sppnp-powershell)
*   [SharePoint Modernization Tools](https://github.com/SharePoint/sp-dev-modernization/tree/dev/Tools)

## Upcoming Calls | Recurrent Invites

*   **Microsoft 365 platform call** **–** February 8th at 8:00 am PST | [https://aka.ms/m365-dev-call](https://aka.ms/m365-dev-call)
*   **Office add-in monthly call –** February 9th at 8:00 am PST | [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscall)
*   **Viva Connections & SharePoint Framework call –** February 10th at 7:00 am PST | [https://aka.ms/spdev-spfx-call](https://aka.ms/spdev-spfx-call)
*   **Adaptive Cards monthly call –** February 10th at 9:00 am PST | [https://aka.ms/adaptivecardscommunitycall](https://aka.ms/adaptivecardscommunitycall)
*   **Power Apps monthly call** – February 16th at 8:00 am PST | [https://aka.ms/PowerAppsMonthlyCall](https://aka.ms/PowerAppsMonthlyCall)
*   **M365 General Dev call –** February 17th at 7:00 am PST | [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig)
*   **Microsoft Identity Platform call –** February 17th at 9:00 am PST | [https://aka.ms/IDDevCommunityCalendar](https://aka.ms/IDDevCommunityCalendar)

General Microsoft 365 Dev Special Interest Group bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, PowerApps, Column Formatting, list formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments to this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/sppnp).


{{< attachments >}}{{< /attachments >}}

* * *

_“Sharing is caring”_

_Microsoft 365 Community (PnP) team, Microsoft - 4th of February 2022_
