---
title: "Microsoft 365 Developer Community Call recording – 17th of February, 2022"
date: 2022-02-18T02:55:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-17th-feb.png
tags: ["Office Add-ins","SPFx Extensions","Microsoft 365","Microsoft Graph","Microsoft Teams","SharePoint","SharePoint Framework (SPFx)"]
type: "regular"
summary: "One location the Microsoft 365 tenant – script samples gallery (138 scenarios and 193 scripts) now integrated into Sample Solution Gallery!  Sign up and attend an AMA and other events this month hosted by Sharing is Caring.  Added today - Ask me anything (PnPjs 3.0 – March 15th) and don’t forget the AMA on February 22 – PnP React Controls.  Get the recognition you deserve, sign up for the PnP Recognition Program.  Released Yo teams - yoteams-build-core v1.6.0 and Microsoft Graph Toolkit (MGT) v2.3.2, and Refreshed the MGT playground!   To see current releases and latest updates/nightly builds, access the Repos via the links in table below.  There were 6 new/updated script, 46 Bot samples, 2 Power Platform samples delivered this week.   Wanted! – Teams Samples."
videos:
- https://www.youtube.com/watch?v=NqwmtJyDEo8
---


## Call summary

One location the Microsoft 365 tenant – [script samples gallery](https://aka.ms/script-samples) (138 scenarios and 193 scripts) now integrated into Sample Solution Gallery!  Sign up and attend an AMA and other events this month hosted by [Sharing is Caring](https://pnp.github.io/sharing-is-caring/).  Added today - [Ask me anything (PnPjs 3.0 – March 15th)](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMkhOOUY2U1QwVElZV0tPQzUyVVQ5RFdKWC4u) and don’t forget the [AMA on February 22 – PnP React Controls](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNjg1UVhPV0JHTjRLNDZISkM4MEI0VDZWSC4u&wdLOR=c3207784F-8F0C-40A4-BB85-8D907412024C).  Get the recognition you deserve, sign up for the [PnP Recognition Program](https://aka.ms/m365pnp-recognition).  Released [Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core) v1.6.0 and [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit) v2.3.2, and Refreshed the [MGT playground](https://aka.ms/mgt/dev)!   To see current releases and latest updates/nightly builds, access the Repos via the links in table below.  There were 6 new/updated script, 46 Bot samples, 2 Power Platform samples delivered this week.   Wanted! – Teams Samples.

## Open-source project status

(**Bold** indicates new this call)**

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.8.0 GA with .NET 6.0 support added|Prepping v1.9
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.5.0 GA with .NET 6.0 support added|Prepping v1.6
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.9.0 GA|Release v1.10.0 imminent (next week?), In progress: V2 POC - .NET 6.0 based, Requires PowerShell 7.2
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v3.5.0 GA|v4.0.0-next
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|**v1.6.0**
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.1.0 GA
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|**v2.3.2 GA**|**Shipping v2.3.2 on Friday!**  Working on v3.0.0 - Aligning all Toolkit components to Fluent UI Web Components

{{< notice note>}}
While version releases are periodic, nightly releases are nightly!  Subscribe to nightly releases for the latest capabilities.
{{< /notice >}}

The host of this call was [David Warner II](https://twitter.com/DavidWarnerII) (Catapult Systems) | @DavidWarnerII.   Q&A takes place in chat throughout the call.

{{< youtube NqwmtJyDEo8 >}}

## Actions

*   Opt into PnP Recognition Program | [https://aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
*   Join us at the next **Microsoft 365 platform call 22nd of February @ 8 AM PT**
    *   Latest news from Microsoft engineering on Microsoft 365 topics
    *   Demos: 
        *   **Rabeb Othmani** - PowerShell Snippets for Microsoft Graph Docs
        *   **Ayca Bas** - Learn from the Community – Introduction to new weekly initiative
        *   **Sébastien Levert** - Customizing MGT Components in your solution
*   Register for Sharing is Caring Events: 
    *   PnP Sharing is Caring - AMA (Ask Me Anything) - SPFx React Controls – [Tuesday, February 22nd, 9am PST](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNjg1UVhPV0JHTjRLNDZISkM4MEI0VDZWSC4u)
    *   PnP Sharing is Caring - AMA (Ask Me Anything) – Microsoft Graph Toolkit - [Tuesday, March 1st, 9am PST](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNVNHNlhNTkczNjRKM0hZR1NWVUw2QUhRQi4u)
    *   PnP Sharing is Caring - AMA (Ask Me Anything) – PnPjs – [Tuesday, March 15th, 9am PST](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMkhOOUY2U1QwVElZV0tPQzUyVVQ5RFdKWC4u)
    *   First Time Contributor Session – TBS soon
    *   Community Docs Session – [Tuesday, March 1st, 2:00pm PT](https://teams.microsoft.com/registration/KtIy2vgLW0SOgZbwvQuRaQ,QOLjRXl28USAJnSCHIUPeQ,HDVmWWtKO0SQPVjQ6nNxjg,c8NCFgwtU06aDn5pQQC4UQ,VNWSt-VeWkOdbZ5RgSEteA,5akHs_jJ9EaNLsDbXJ42dQ?mode=read&tenantId=da32d22a-0bf8-445b-8e81-96f0bd0b9169&skipauthstrap=1)
    *   Power Platform Samples – First Time Contributor – [Tuesday, March 8th, 2:00pm PT](https://teams.microsoft.com/registration/KtIy2vgLW0SOgZbwvQuRaQ,QOLjRXl28USAJnSCHIUPeQ,HDVmWWtKO0SQPVjQ6nNxjg,j-Hmd31eYUCs62n_EreJlA,XGwnxI7P0E-2pg0AHz2Veg,8arnsbX0J0iSRgujep3dlA?mode=read&tenantId=da32d22a-0bf8-445b-8e81-96f0bd0b9169&skipauthstrap=1)
    *   PnP – SPFx Developer Workstation Setup – TBS soon
    *   PnP SPFx Samples – Solving SPFx version differences using Node Version Manager – [Tuesday, March 15th, 2pm PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    *   First Time Presenter – TBS soon
    *   More than Code with VSCode – TBS soon
    *   Maturity Model Practitioners – TBS soon (every 3rd Tuesday of month, 7:00am PT)
    *   Getting Started with Viva Connection ACEs (2-part session) – TBS soon
    *   PnP Office Hours – 1:1 session – [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    *   PnP Buddy System – [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
*   Download the recurrent invite for this call – [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig)
*   Call attention to your great work by using the [#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click) on Twitter.

## Microsoft Teams Development Samples

<https://aka.ms/TeamsSampleBrowser>

Delivered - 46 Bot samples from the Microsoft Bot Framework Team – each sample shows a single activity, in a specific language – Typescript, C#, Python, .NET, Javascript, Java.

*   Bot with Teams authentication
*   Search messaging extension
*   Action messaging extension
*   Search messaging extension w/Auth and Config page
*   Bot w/task module, adaptive card buttons
*   Link unfurling
*   File Upload
*   Conversation Flow
*   Start new thread in channel

## Microsoft Power Platform Samples

<https://aka.ms/powerplatform-samples>

*   **Teams Adaptive Card Reminders From Lists\* -** [Norm Young](https://twitter.com/stormin_30) | [@stormin\_30](/t5/user/viewprofilepage/user-id/764913)
*   [**SharePoint event registration Power App**](https://github.com/alexc-MSFT/sharepoint-events-powerapp) - [Alex Clark](https://twitter.com/sharepointalex) | @sharepointalex

\*These latest samples should show on site shortly after this call

**Script Samples:** ([https://aka.ms/script-samples)](https://aka.ms/script-samples)

2 New Scenarios and 4 Script Updates:

*   **_New Scenarios_**
    *   [**Analyze users for known data breaches with have I been pwned**](https://pnp.github.io/script-samples/aad-analyze-users-hibp/README.html?tabs=cli-m365-ps) - [Albert-Jan Schot](https://twitter.com/appieschot) | @appieschot
    *   [**Delete orphaned temporary site pages**](https://pnp.github.io/script-samples/spo-delete-orphaned-temporary-sitepages/README.html?tabs=pnpps) - [Brian McCullough](https://twitter.com/bpmccullough) | @bpmccullough
*   **_Updates or scenarios implemented with alterative tools_**
    *   [**Get Site Usage Reports And Export It To CSV**](https://pnp.github.io/script-samples/spo-export-site-usage-reports/README.html?tabs=pnpps) - [Reshmee Auckloo](https://twitter.com/ReshmeeAuckloo) | [@reshmeeauckloo](/t5/user/viewprofilepage/user-id/1145036)
    *   [**List all external users in all site collections**](https://pnp.github.io/script-samples/spo-list-site-externalusers/README.html?tabs=cli-m365-ps) - [Chandani Prajapati](https://twitter.com/Chandani_SPD) | @Chandani\_SPD
    *   [**Modernizing classic pages from on-premises sites**](https://pnp.github.io/script-samples/modernize-classic-pages-from-publishing-sites/README.html?tabs=pnpps) - [Paul Bullock](https://twitter.com/pkbullock) | @pkbullock
    *   [**Remove orphaned redirect sites**](https://pnp.github.io/script-samples/spo-remove-orphaned-redirect-sites/README.html?tabs=cli-m365-ps) - [Leon Armston](https://twitter.com/LeonArmston) | [@LeonArmston](/t5/user/viewprofilepage/user-id/855621)

Article:  [Getting started with PnP Script Samples](https://aka.ms/script-samples/getting-started) – aka.ms/script-samples/getting-started

– Many thanks!

## Demos

**Introduction to Adaptive Card Studio VS Code extension** – step through the Visual Code extension that makes it easy to add to and work with Adaptive Cards in your project. The Adaptive Cards button exposes all Adaptive Cards resident in your workspace.  Within the extension, you can see and download samples (code, example, snippets, container) from AdaptiveCards.io.  Today you can send a card (layout, sample, json) to recipient in Outlook and soon Teams.    

**Solving reCaptcha with Power Automate Desktop** – resolves Google Captcha challenges using Power Automate Desktop for RPA (robotic process automation) and Outlook Actionable Messages.  User need not go to remote (unattended) machine.   Bot captures image of screen, sends mail to user, user responds, and bot executes instructions.  Manages repeated challenges, timeouts, and user contact attempts.   Uses an adaptive Card, 2 Cloud flows and Dataverse.  Learn how in this demo.

**Bringing in your own data to Microsoft Search** – using Azure Logic Apps and Graph connectors (Microsoft and Ecosystem Partner built, or Graph Search API) for pulling in external data sources.  Use Graph search API - Create connector in Graph, Register connector in search, Create an Adaptive Card for viewing results, and Add items into indexes.   Demo shows pulling content from Trello, using Graph calls in 3 Logic Apps (Search, Setup and Trigger).  

Thank you for your work. Samples are often showcased in Demos.    Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)

## Topics

*   PnP .NET library updates - [Bert Jansen](https://twitter.com/O365bert) (Microsoft) | @O365bert – [6:32](https://youtu.be/NqwmtJyDEo8?t=392)
*   PnP PowerShell updates \- [Bert Jansen](https://twitter.com/O365bert) (Microsoft) | @O365bert – [8:24](https://youtu.be/NqwmtJyDEo8?t=504)
*   yo Teams updates - [Wictor Wilén](https://twitter.com/wictor) (Microsoft) | @wictor – [9:08](https://youtu.be/NqwmtJyDEo8?t=548)
*   Microsoft Graph Toolkit updates - [David Warner II](https://twitter.com/DavidWarnerII) (Catapult Systems) | @DavidWarnerII – [10:35](https://youtu.be/NqwmtJyDEo8?t=635)
*   Microsoft Script Samples - [David Warner II](https://twitter.com/DavidWarnerII) (Catapult Systems) | @DavidWarnerII – [2:35](https://youtu.be/NqwmtJyDEo8?t=155)
*   Microsoft Teams Samples - [Bob German](https://twitter.com/Bob1German) (Microsoft) | @Bob1German – [11:17](https://youtu.be/NqwmtJyDEo8?t=677)
*   Microsoft Power Platform Samples - [April Dunnam](https://twitter.com/aprildunnam) (Microsoft) | @aprildunnam – [12:32](https://youtu.be/NqwmtJyDEo8?t=752)
*   **Demo 1**:  Introduction to Adaptive Card Studio VS Code extension – [Tim Cadenbach](https://twitter.com/TimCadenbach) | @TimCadenbach – [15:18](https://youtu.be/NqwmtJyDEo8?t=918)
*   **Demo 2**:  Solving reCaptcha with Power Automate Desktop – [Tomasz Poszytek](https://twitter.com/TomaszPoszytek) | [@TomaszPoszytek](/t5/user/viewprofilepage/user-id/335682) – [21:33](https://youtu.be/NqwmtJyDEo8?t=1293)
*   **Demo 3**:  Bringing in your own data to Microsoft Search – [Kevin McDonnell](https://twitter.com/kevmcdonk) | @kevmcdonk
    – [34:25](https://youtu.be/NqwmtJyDEo8?t=2065)

## Resources

Additional resources around the covered topics and links from the slides.

*   **D1**:  Community site - [MadeWithCards.io](https://www.madewithcards.io/) 
*   **D1**:  Site – [MAXIMAGO](https://maximago.de/) 
*   **D1**:  Visual Studio Marketplace - [Adaptive Card Studio](https://marketplace.visualstudio.com/items?itemName=madewithcardsio.adaptivecardsstudiobeta)  
*   **D2**:  Demo - [Solving reCaptcha v2 challenge with Power Automate Desktop](https://www.youtube.com/watch?v=9pgC02Co2rQ) 
*   **D2**:  Demo – [Actionable Messages using Adaptive Cards - ultimate guide](https://www.youtube.com/watch?v=x5IXd-g8OXw&t=0s) 
*   **D2**:  Documentation - [Send physical clicks on a web element](https://learn.microsoft.com/power-automate/desktop-flows/how-to/send-physical-clicks-web-element) 
*   **D2**:  Documentation - [Introduction to Power Automate for desktop](https://learn.microsoft.com/power-automate/desktop-flows/introduction) 
*   **D2**:  Demo - [Adaptive Cards and the Power Platform to solve captchas](https://www.youtube.com/watch?v=7xIIjrHoqq0) 
*   **D3**:  Documentation - [externalConnection resource type](https://learn.microsoft.com/graph/api/resources/externalconnectors-externalconnection?view=graph-rest-1.0) 
*   **D3**:  Repo – [Create Schema example](https://github.com/kevmcdonk/S4MSC-Twitter/blob/main/schema.json) 
*   **D3**:  Article - Creating a custom Microsoft Search connector with Logic Apps
*   **D3**:  Templates - [Search Layout designer](https://searchlayoutdesigner.azurewebsites.net/chooseLayout) 
*   **D3**:  Samples - [MSSearch-Samples](https://github.com/kevmcdonk/MSSearch-Samples) 
*   **D3**:  Samples - [Samples for Microsoft Search Connectors – Twitter](https://github.com/kevmcdonk/S4MSC-Twitter) 
*   **D3**:  Demo – [Latest on Cloud Hybrid Search (SSA) & Graph connectors​ for indexing content from on-premises](https://youtu.be/9w2L3-7sCDI?t=1705) – Harshit Kumar (Microsoft) 
*   **Microsoft 365 PnP Weekly – Episode 153** (February 14th) with Redmond, Washington, US-based Senior Program Manager in the OneDrive and SharePoint organization responsible of the Power Platform integration, [Sudha Narayanan](https://www.linkedin.com/in/sudha-narayanan-3295326a/) (Microsoft) | [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-153-sudha-narayanan/ba-p/3164026) | [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-153-%E2%80%93-14th-of-february-2022/)
*   **Microsoft 365 PnP Weekly – Episode 152** (February 7th) with Toronto, Ontario, Canada-based Microsoft Cloud Solution Architect and MVP Alum, [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) | @bernierh | [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-152-hugo-bernier/ba-p/3131722) | [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-152-%E2%80%93-7th-of-february-2022/)

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

*   **Microsoft 365 platform call** **–** February 22nd at 8:00 am PST | [https://aka.ms/m365-dev-call](https://aka.ms/m365-dev-call)
*   **Viva Connections & SharePoint Framework call –** February 24th at 7:00 am PST | [https://aka.ms/spdev-spfx-call](https://aka.ms/spdev-spfx-call)
*   **M365 General Dev call –** March 3rd at 7:00 am PST | [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig)
*   **Office add-in monthly call –** March 9th at 8:00 am PST | [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscall)
*   **Adaptive Cards monthly call –** March 10th at 9:00 am PST | [https://aka.ms/adaptivecardscommunitycall](https://aka.ms/adaptivecardscommunitycall)
*   **Power Apps monthly call** – March 16th at 8:00 am PST | [https://aka.ms/PowerAppsMonthlyCall](https://aka.ms/PowerAppsMonthlyCall)
*   **Microsoft Identity Platform call –** March 17th at 9:00 am PST | [https://aka.ms/IDDevCommunityCalendar](https://aka.ms/IDDevCommunityCalendar)

General Microsoft 365 Dev Special Interest Group bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, PowerApps, Column Formatting, list formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments to this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/sppnp).


{{< attachments >}}{{< /attachments >}}

* * *

_“Sharing is caring”_

_Microsoft 365 Community (PnP) team, Microsoft - 18th of February 2022_
