---
title: "Microsoft 365 & Power Platform Development Community call - 2nd of March, 2023"
date: 2023-03-02T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-230302.png
tags: []
type: "regular"
summary: "Demos: Build task automation solution between Planner and GitHub using Microsoft Graph and Improve your test strategy with Microsoft Graph Developer Proxy. Released: Microsoft Teams Toolkit, Yo teams, MGT, 7 connectors, 6 scripts, 3 samples, 6 conversations."
videos:
- https://www.youtube.com/watch?v=8kTtDbuW7-s
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Announcements
    * Microsoft Graph and .NET – March Hack Together – March 1st to 15th - aka.ms/hack-together - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR0ktYAUCTtVIvJkJdFsfkalUMlM0SVBXRjIyTEFJQVFYOUMzTDE2SEY1WS4u)
    * Agenda set for next [Microsoft 365 & Power Platform weekly call](https://aka.ms/m365-dev-call) - Tuesday, March 7th, 8:00 am PT.
        * Latest news from Microsoft engineering on Microsoft 365 topics
        * Demo - **Ayça Baş** – Dynamically Create an Azure Communication Services Identity and Token
        * Demo - **Garry Trinder** – Teams Toolkit Learn Path - Build a Microsoft Teams tab app using Teams Toolkit for Visual Studio Code
        * Demo - **Waldek Mastykarz** – Microsoft Graph Hackathon – Recap on the first week
* Project releases
    * [Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx) – v4.2.4 (GA) VS Code Extension
    * [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit) – v2.9.1 (GA)
    * [Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams) – v4.1.0 (GA)
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) submissions
    * [1pt](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/1pt) - [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * Jservice - [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * [Affirmations](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Affirmations) - [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * [APITemplate](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/APITemplate) - [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * [Airlabs](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Airlabs) - [Andras Fordos](https://github.com/fordosa90)
    * [TAGGUN Receipt OCR Scanning](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/TAGGUN%20Receipt%20OCR%20Scanning) - [Amjed Ayoub](https://github.com/AmjedAyoub)
    * [PaySpace](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/PaySpace) - [Mint Management Technologies](https://github.com/mint-virgil)
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
    * Good Flow story? Tell us. [FlowOfTheWeek](https://aka.ms/FlowOfTheWeekForm) – aka.ms/FlowOfTheWeekForm
* [Script samples](https://pnp.github.io/script-samples/)
    * New – Microsoft Graph SDK (PowerShell) – [Add users to follow SharePoint Sites](https://pnp.github.io/script-samples/spo-add-user-follow-site/README.html?tabs=graphps) - [André Lage](https://twitter.com/aaclage) (Datalynx AG) \| @aaclage
    * New – Microsoft Graph SDK (PowerShell) – [Multilingual SharePoint Page Summarization with Open AI API and Microsoft Graph PowerShell SDK](https://pnp.github.io/script-samples/graph-openai-get-page-summary/README.html?tabs=graphps) - [Anoop Tatti](https://twitter.com/anooptells) (Content+Cloud) \| @anooptells
    * New – PnP PowerShell – [Remove Title Area from SharePoint Page](https://pnp.github.io/script-samples/spo-remove-page-title-area/README.html?tabs=pnpps) - [Ganesh Sanap](https://ganeshsanapblogs.wordpress.com/about/)
    * New – PnP PowerShell – [Use Invoke-PnPSiteTemplate with parameters](https://pnp.github.io/script-samples/spo-apply-pnptemplate-with-parameters/README.html?tabs=pnpps) - [Kasper Bo Larsen](http://twitter.com/kasperbolarsen) \| @kasperbolarsen
    * New – PnP PowerShell – [Export access shared links from SharePoint Library](https://pnp.github.io/script-samples/spo-export-file-shared-links/README.html?tabs=pnpps) - [André Lage](https://twitter.com/aaclage) (Datalynx AG) \| @aaclage
    * New – PnP PowerShell – [Associate Multiple Site Collections to Hub Site](https://pnp.github.io/script-samples/spo-associate-multiple-sites-to-hub/README.html?tabs=pnpps) - [Siddharth Vaghasia](http://twitter.com/siddh_me) \| @siddh_me
    * [Good first issue asks](https://github.com/pnp/script-samples)
    * Power Platform Integrations / Connectors LABs Participant Calls. [Complete this form](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR0BHMrjhL0hDmckROosW6AFUOUVHNTlRRlAxQUI5S0hJNFdIWkZBRzlaTy4u)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/) – Featured Teams App Samples with Full Tutorials
    * Who’s Next Meeting App - [Rabia Williams](https://twitter.com/williamsrabia) (Microsoft) \| @williamsrabia & [Bob German](https://twitter.com/Bob1German) (Microsoft) \| @Bob1German
        * Sample - [How to use this Who's Next In-meeting app](https://github.com/OfficeDev/TeamsFx-Samples/tree/dev/whos-next-meeting-app) \| aka.ms/who-is-next
        * Article - [Build a "Who's Next" Teams meeting app with Fluid Framework and the Live Share SDK](https://pnp.github.io/blog/post/build-a-teams-meeting-app-with-liveshare-sdk/) \| aka.ms/who-is-next-article
        * Video - [Build a "Who's Next" Teams Meeting app](https://www.youtube.com/watch?v=rHnd4g8uLTA) \| aka.ms/who-is-next-video
    * ISV’S BUILDING MONETIZED TEAMS APPS - The ecosystem team wants to support you! \| aka.ms/TeamsApp/Support
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* [Power Platform Samples](https://pnp.github.io/powerplatform-samples/) & [Power Apps Samples](https://github.com/pnp/powerapps-samples)
    * Power Apps – [PowerApps Quality Assurance Assessment Solution](https://github.com/pnp/powerapps-samples/tree/main/samples/power-apps-quality-assurance-assessment) - [Nati Turtledove](https://twitter.com/NatiTurts) \| @NatiTurts
    * Power Apps – [Company Pulse – Creator Kit](https://github.com/pnp/powerapps-samples/tree/main/samples/Company%20Pulse%20-%20Creator%20Kit) - [Angelo Gulisano](https://twitter.com/angelog1908) \| @angelog1908
* [Conversations](https://aka.ms/pnpweekly)
    * Microsoft 365 Developer Podcast – Partner showcase: Building nBold with Guillaume Meyer (February 26th) \| [podcast](https://m365devpodcast.com/e/partner-series-building-nbold-with-guillaume-meyer/)
    * Microsoft 365 Developer Podcast – Kiota and Microsoft Graph SDKs with Vincent Biret and Rabeb Othmani (February 21st) \| [podcast](https://m365devpodcast.com/e/kiota-and-microsoft-graph-sdks-with-vincent-biret-and-rabeb-othmani/)
    * Microsoft 365 PnP Weekly – Episode 199 (February 27th) with reflections from [Vesa Juvonen](http://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen and [Waldek Mastykarz](http://twitter.com/waldekm) (Microsoft) \| @waldekm \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-199/) \| [podcast](http://pnpweekly.podbean.com)
    * Microsoft 365 PnP Weekly – Episode 198 (February 21st) with Bosnia and Herzegovina-based Speaker, Author, Cloud Solutions Architect, Azure MVP at Devoteam M Cloud - [Mustafa Toroman](https://twitter.com/toromust) \| @toromust \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-198/) \| [podcast](https://www.podbean.com/eas/pb-hfy3i-13965d2)
    * Power Platform Connections - Power Platform Connections Ep 2 - Scott Durow (February 23rd) \| [video](https://www.youtube.com/watch?v=CINlK7F3Nhg)
    * Power Platform Connections - Hugo loves the Ribbon Workbench Tool! (February 23rd) \| [video](https://www.youtube.com/watch?v=wY1-gVy1Tvg)

### Demos

* **Build task automation solution between Planner and GitHub using Microsoft Graph** – looks at interactions between GitHub (or any app) and Planner via Microsoft Graph. Use case – create a PR (pull request) that lands as actionable Planner task for repo’s owner. PR initiates workflow that calls a GitHub action. Graph handles authentication and Planner task creation. Task in Planner contains link to PR. Code walk-through - node.js project, 3 .ts files, uses MSAL, app reg in Azure AD. Conversation - [aka.ms/Mar2-Demo1](https://aka.ms/Mar2-Demo1)
* **Improve your test strategy with Microsoft Graph Developer Proxy** – a review affirming capabilities of Proxy to test the untestable and to improve the quality of your desktop apps by simulating responses to any API (Graph, not Graph). Run through UI automated and manual test scenarios in this demo. Review available parameters including ability to mock. Test results presented along with tips to fix. Test client applications without additional web APIs. Feedback always welcome. Conversation - [aka.ms/Mar2-Demo2](https://aka.ms/Mar2-Demo2)

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube 8kTtDbuW7-s >}}

## Agenda items

[00:00](https://youtu.be/8kTtDbuW7-s?t=0) – Intro - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[07:06](https://youtu.be/8kTtDbuW7-s?t=426) – PnP .NET library updates - [Bert Jansen](http://twitter.com/O365bert) (Microsoft) @O365bert

[09:00](https://youtu.be/8kTtDbuW7-s?t=540) – PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Valo Intranet) \| @gautamdsheth

[10:56](https://youtu.be/8kTtDbuW7-s?t=656) – yo Teams updates - [Stephan Bisser](https://twitter.com/stephanbisser) (Solvion) \| @stephanbisser

[12:18](https://youtu.be/8kTtDbuW7-s?t=738) – Microsoft Teams Toolkit updates - [Vesa Juvonen](https://twitter.com/VesaJuvonen)<http://twitter.com/DavidWarnerII> (Microsoft) \| @VesaJuvonen

[12:57](https://youtu.be/8kTtDbuW7-s?t=777) – Microsoft Graph Toolkit updates - [Sébastien Levert](http://twitter.com/sebastienlevert) (Microsoft) \| @sebastienlevert

[15:18](https://youtu.be/8kTtDbuW7-s?t=918) – Independent Publisher Connectors - [Jocelyn Panchal](https://twitter.com/JocelynP_PM) (Microsoft) \| @JocelynP_PM

[17:16](https://youtu.be/8kTtDbuW7-s?t=1036) – Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock

[19:23](https://youtu.be/8kTtDbuW7-s?t=1163) – Microsoft Teams Samples - [Bob German](https://twitter.com/Bob1German) (Microsoft) @Bob1German

[22:08](https://youtu.be/8kTtDbuW7-s?t=1328) – Microsoft Power Platform Samples - Hugo Bernier (Microsoft) \| @bernierh

[23:02](https://youtu.be/8kTtDbuW7-s?t=1382) – Together mode picture

[24:02](https://youtu.be/8kTtDbuW7-s?t=1442) – Demo - Build task automation solution between Planner and GitHub using Microsoft Graph – [Anoop Tatti](https://twitter.com/anooptells) (Content+Cloud) \| @anooptells

[40:01](https://youtu.be/8kTtDbuW7-s?t=2401) – Demo - Improve your test strategy with Microsoft Graph Developer Proxy - [Adam Wójcik](https://twitter.com/Adam25858782) (Hitachi Energy) \| @Adam25858782

[59:40](https://youtu.be/8kTtDbuW7-s?t=3580) – Closing

## Together Mode

![together-230302.png](images/together-230302.png)

Thank you everyone for joining the call today. Awesome to see you here and hopefully many of you will be able to attend one of the upcoming in-person conferences this year.

## Actions

* Microsoft Graph and .NET – March Hack Together - aka.ms/hack-together - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR0ktYAUCTtVIvJkJdFsfkalUMlM0SVBXRjIyTEFJQVFYOUMzTDE2SEY1WS4u)
* [Request to Present a demo](https://aka.ms/community/request/demo) during Microsoft 365 & Power Platform community calls - aka.ms/community/request/demo
* Chime into a Community Calls Conversation – chat about demos anytime. Links and QR Codes associated to every demo – see in call deck and in demo summaries.
* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Power Platform Samples Contributor \| Wednesday, March 15th, 10:00am PT \| 1:00pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
    * Maturity Model Practitioners \| Tuesday, March 21st, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Join the next monthly Power Platform Integrations / Connectors LABs Participant call. [Complete this form](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR0BHMrjhL0hDmckROosW6AFUOUVHNTlRRlAxQUI5S0hJNFdIWkZBRzlaTy4u).
* What key scenarios are missing from the PnP Core SDK? Let us know and/or view the latest changes at [PnP Core SDK Changelog](https://github.com/pnp/pnpcore/blob/dev/src/sdk/CHANGELOG.md).
* Ideas for Microsoft Lists? aka.ms/Feedback/Lists
* Suggestions for yo teams? [Discussions](https://github.com/pnp/generator-teams/discussions)
* Create a connector – [Top Power Platform Independent Publisher Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* ISV’S BUILDING MONETIZED TEAMS APPS - The ecosystem team wants to support you! \| aka.ms/TeamsApp/Support
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) with more than 1500 samples from Microsoft and community.
* Download the recurrent invite for this call – <http://aka.ms/spdev-sig-call>

## Demo references

* **Build task automation solution between Planner and GitHub using Microsoft Graph**
    * Article - [New Microsoft Graph Planner API capabilities now available](https://devblogs.microsoft.com/microsoft365dev/new-microsoft-planner-api-capabilities-now-available-in-microsoft-graph/)
    * Code snippet - [create_task_on_pull_request.yaml](https://gist.github.com/anoopt/21a5ed9a251d7ae8eb991a310380a194)
    * Article - [Create a task with Microsoft Graph using MSAL](https://github.com/marketplace/actions/create-a-task-with-microsoft-graph-using-msal)
* **Improve your test strategy with Microsoft Graph Developer Proxy**
    * Tool Repo - [Microsoft Graph Developer Proxy](https://github.com/microsoftgraph/msgraph-developer-proxy)
    * Article - [Join us for Hack Together: Microsoft Graph and .NET](https://devblogs.microsoft.com/dotnet/hack-together-microsoft-graph-dotnet/)
    * Demo - [Introduction to Microsoft Graph Developer Proxy](https://youtu.be/jsXliaZCGqg)
    * Demo - [Test how your SPFx solutions respond to throttling with Graph Developer Proxy](https://www.youtube.com/watch?v=ljsMwf36lOY)

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)

## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.11.0 GA| 
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.8.0 GA|
[Microsoft 365 Assessment tool](https://docs.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool                                     
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.12.0 GA|v2.x is available in nightly builds !!!
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v4.1.0 GA, v4.1.1-preview.2|
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.8.0 GA, v1.8.1-preview
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.2.0 GA, v1.4.0-preview
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1 GA
[Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx)|v4.2.4 GA (VS Code), v17.4 (VS), v17.5-preview-2 (VS)|New builds daily                          
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.9.1 GA, v3.0 Preview|v3.0 “official” updated preview out week of March 6th

## General resources

*   Script Samples - [Getting started with PnP Script Samples](https://aka.ms/script-samples/getting-started) – aka.ms/script-samples/getting-started
*   Samples - [Power Platform Samples](https://aka.ms/powerplatform-samples) | [aka.ms/](https://aka.ms/powerplatform-samples)[powerplatform](https://aka.ms/powerplatform-samples)[\-samples](https://aka.ms/powerplatform-samples)
*   Microsoft 365 tenant – [Script Samples Gallery](https://aka.ms/script-samples) | aka.ms/script-samples
*   [Microsoft Teams Samples Gallery](https://pnp.github.io/teams-dev-samples/) | aka.ms/teams-samples
*   [Microsoft 365 Extensibility look book gallery](https://adoption.microsoft.com/extensibility-look-book?WT.mc_id=m365-24198-cxa) | aka.ms/m365/extensibility
*   Archives - Microsoft 365 PnP Weekly - [Videos](https://www.youtube.com/playlist?list=PLR9nK3mnD-OVYI-St_CBiFfuL4CZbBpkC), [Podcasts](https://pnpweekly.podbean.com/)  
*   PnP Teams Quickstart | [aka.ms/pnp-teams-quickstart](https://aka.ms/pnp-teams-quickstart)
*   Microsoft Teams Toolkit v3.x | [https://aka.ms/teams-toolkit](https://aka.ms/teams-toolkit)
*   [Microsoft 365 and Power Platform Community Blog](https://pnp.github.io/blog) | aka.ms/m365pnp/blog
*   Microsoft Graph Toolkit in Microsoft Learn | [https://aka.ms/learn-mgt](https://aka.ms/learn-mgt)
*   Viva Connections [https://aka.ms/VivaConnections](https://aka.ms/VivaConnections)
*   [SharePoint look book](https://lookbook.microsoft.com/?WT.mc_id=m365-24198-cxa)
*   [Yo Teams video training package](https://aka.ms/yoteams-training)
*   [.NET Standard 2.0 version of SharePoint Online CSOM API](https://developer.microsoft.com/microsoft-365/blogs/net-standard-version-of-sharepoint-online-csom-apis?WT.mc_id=m365-24198-cxa)
*   [Microsoft 365 community (PnP) videos](https://aka.ms/m365pnp-videos) | aka.ms/m365pnp-videos
*   [Microsoft Teams Toolkit for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension)
*   [yo Teams](https://aka.ms/yoteams) | aka.ms/yoteams
*   Video - [Getting started using yo Teams](https://youtu.be/w0OrFkzNC10) | [Wictor Wilén](https://twitter.com/wictor) (Microsoft)| @wictor
*   [Build a crisis management site to connect people and information](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/build-a-crisis-management-site-to-connect-people-and-information/ba-p/1216791?WT.mc_id=m365-24198-cxa)
*   [Developer documentation](https://aka.ms/spdev-docs) | [https://aka.ms/spdev-docs](https://aka.ms/spdev-docs)
*   [PnP Power Shell](https://aka.ms/sppnp-powershell)
*   [SharePoint Modernization Partner Guidance](https://aka.ms/sppnp-modernization-partnerguidance) \- Feedback welcome
*   Solution - [Building a modern search experiences with SharePoint Framework web parts](https://aka.ms/pnp-modern-search)
*   [Page transformation guidance](https://aka.ms/sppnp-pagetransformation)
*   [Page transformation videos](https://aka.ms/sppnp-pagetransformationvideos)
*   [Modernization scanner](https://aka.ms/sppnp-modernizationscanner)
*   [Microsoft 365 developer program site](https://developer.microsoft.com/office/dev-program?WT.mc_id=m365-24198-cxa) \- Need to become a Tenant Admin to test look book capabilities? Get a Microsoft 365 E5 developer subscription (free tenant for 90 days)
*   [SharePoint Page Transformation webcast series](https://developer.microsoft.com/sharepoint/blogs/sharepoint-page-transformation-webcast-series?WT.mc_id=m365-24198-cxa)
*   [PnP PowerShell](https://aka.ms/sppnp-powershell)
*   [SharePoint Modernization Tools](https://github.com/SharePoint/sp-dev-modernization/tree/dev/Tools)

## Upcoming calls | Recurrent invites

* Microsoft 365 platform call \| Tuesday, March 7, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Office add-in monthly call \| Wednesday, March 8, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, March 9, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Power Platform monthly call \| Wednesday, March 15, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft 365 General Dev call \| Thursday, March 16, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, March 16, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 2nd of March 2023*

{{< attachments >}}
