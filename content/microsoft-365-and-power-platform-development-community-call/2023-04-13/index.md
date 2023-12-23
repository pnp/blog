---
title: "Microsoft 365 & Power Platform Development Community call - 13th of April, 2023"
date: 2023-04-13T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-13th-april.png
tags: []
type: "regular"
summary: "Demos: A SharePoint document generator as Microsoft 365 app as Microsoft Teams native app, Build a training request solution with Power Platform, and Using dynamic SVGs with List Formatting for SharePoint and Microsoft Lists. Releases: PowerShall, Teams Toolkit, MGT, 17 assets."
videos:
- https://www.youtube.com/watch?v=IAngVFxtje0
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Announcements
    * Agenda set for next [Microsoft 365 & Power Platform weekly call](https://aka.ms/m365-dev-call) - Tuesday, April 18th, 8:00 am PT.
        * **Srinivas Varukala** & **Rick Shire** – Building a Microsoft Teams Call queue scheduler solution for customers
        * **John Miller** – Introduction to Microsoft Teams Toolkit v5 - New features and capabilities
        * **To be announced** – Microsoft Graph Hackathon - Winner demo \#3
    * ISV’S BUILDING MONETIZED TEAMS APPS - The ecosystem team wants to support you! \| aka.ms/TeamsApp/Support
    * Community Calls Conversations - Chime into a Community Calls Conversation – chat about demos anytime. Links and QR Codes associated to every demo – see in call deck and in demo summaries.
    * Community updates in LinkedIn - aka.ms/community/li
* Project releases
    * PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework) – v1.12.0 (GA)
    * PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev) – v1.9.0 (GA)
    * [PnP PowerShell](https://github.com/pnp/PnP-PowerShell) – v2.1.1 preview
    * [Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx) – v5.0.0 RC (VS Code)
    * [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit) – v2.10.0 (GA)
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) submissions
    * Indep Pub - [Instatus](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Instatus) - [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * Indep Pub -ScrappingBee - [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * 1st party - Microsoft Search
    * 1st party - [Resco Reports](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/certified-connectors/RescoReports)
    * 1st party - [SmartCOMM DocGen](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/certified-connectors/SmartCOMM%20Doc-Gen)
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
    * Good Flow story? Tell us. [FlowOfTheWeek](https://aka.ms/FlowOfTheWeekForm) – aka.ms/FlowOfTheWeekForm
* [Script samples](https://pnp.github.io/script-samples/)
    * New – PnP PowerShell – [SharePoint List Item Version History Retrieval](https://pnp.github.io/script-samples/spo-get-list-item-version-history/README.html?tabs=pnpps) - [Michał Romiszewski](https://github.com/mromiszewski)
    * New – PnP PowerShell – [Download sppkgs from App Catalog](https://pnp.github.io/script-samples/spo-download-sppkgs/README.html?tabs=pnpps) - [Matteo Serpi](https://github.com/srpmtt)
    * New – PnP PowerShell – [Get Content Usage within a site collection](https://pnp.github.io/script-samples/spo-get-contenttype-usage-listitem-listversion/README.html?tabs=pnpps) - [Reshmee Auckloo](http://twitter.com/ReshmeeAuckloo) \| @ReshmeeAuckloo
    * New – PnP PowerShell – [Apply SharePoint JSON view formatting](https://pnp.github.io/script-samples/spo-apply-json-view-formatting/README.html?tabs=pnpps) - [Ganesh Sanap](http://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * New – PnP PowerShell – [Getting checked-out files in the tenant using Search](https://pnp.github.io/script-samples/spo-export-checked-out-files-in-tenant-using-search/README.html?tabs=pnpps) - [Kasper Bo Larsen](http://twitter.com/kasperbolarsen) \| @kasperbolarsen
    * New – PnP PowerShell – [Empty SharePoint Online site recycle bin](https://pnp.github.io/script-samples/spo-empty-recycle-bin/README.html?tabs=pnpps) - [Ganesh Sanap](http://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Reset files permissions unique to inherited](https://pnp.github.io/script-samples/reset-files-permission-unique-to-inherited/README.html?tabs=pnpps) - [Valeras Narbutas](http://twitter.com/ValerasNarbutas) (Macaw) \| @ValerasNarbutas
    * Updated – PnP PowerShell – [Reset files permissions unique to inherited](https://pnp.github.io/script-samples/reset-files-permission-unique-to-inherited/README.html?tabs=pnpps) - [Valeras Narbutas](http://twitter.com/ValerasNarbutas) (Macaw) \| @ValerasNarbutas
    * [Good first issue asks](https://github.com/pnp/script-samples)
    * Power Platform Integrations / Connectors LABs Participant Calls. [Complete this form](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR0BHMrjhL0hDmckROosW6AFUOUVHNTlRRlAxQUI5S0hJNFdIWkZBRzlaTy4u)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/) – Featured Teams App Samples with Full Tutorials
    * Sample - [tab-sso-graph-upload-pdf-csharp](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-sso-graph-upload-as-pdf-csharp) - [Markus Möller](https://twitter.com/Moeller2_0)​ (Avanade) \| @Moeller2_0
    * ISV’S BUILDING MONETIZED TEAMS APPS - The ecosystem team wants to support you! \| aka.ms/TeamsApp/Support
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* Conversations
    * Microsoft 365 PnP Weekly – Episode 205 (April 10th) with by US-based Principal Power Platform Advocacy Team Lead at Microsoft - [April Dunnam](https://twitter.com/aprildunnam) \| @aprildunnam \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-205/) \| [podcast](https://www.podbean.com/eas/pb-fn7za-13dd530)
    * Microsoft 365 Developer Podcast – Build once, deploy efficiently, connect across Microsoft 365 (April 10th) \| [podcast](https://m365devpodcast.com/e/build-once-deploy-efficiently-connect-across-microsoft-365/)
    * Power Platform Connections - Power Platform Connections Ep 8 - Hugo Bernier (April 7th) \| [video](https://www.youtube.com/watch?v=HuKLj12NMk0&t=32s)

### Demos

* **A SharePoint document generator as Microsoft 365 app as Microsoft Teams native app** – this week Option B - use a single app to generate, publish and review template-based documents from any Microsoft 365 product - Teams, Outlook, Microsoft 365, SharePoint, with ONE Teams solution. Last week, Option A generated a document using SPFx. Option B uses yoteams (native app) not only for generation, but also enables publish & review (using search-based messaging extensions). Option evaluation criteria considers hosting, authentication, privacy. Discussion at [aka.ms/Apr13-Demo1](https://aka.ms/Apr13-Demo1)
* **Build a training request solution with Power Platform** – objective – automate training request acceptance, approval routing and reporting. Uses Power App (Canvas app) request form, Power Automate flow with Adaptive Cards for request approvals/rejections, Dataverse and Power BI to store, view and refine activity results. Step through entire process - request form, validation, approval routing and interactive Power BI reporting dashboard with refiners for delivering desired request/training metrics. Discussion at [aka.ms/Apr13-Demo2](https://aka.ms/Apr13-Demo2)
* **Using dynamic SVGs with List Formatting for SharePoint and Microsoft Lists** – create a radar chart to help visualize list data. Create an SVG (use Inkscape) - modify paths and apply transforms (Transforms extension), edit some XML. Convert XML to JSON (with HTML To Formatter). Paste SVG JSON into custom List formatting view. Tips on preparing SVG for List Formatting include using absolute paths and only paths, viewBox, and currentColor to utilize theme colors. Discussion at [aka.ms/Apr13-Demo3](https://aka.ms/Apr13-Demo3)

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube IAngVFxtje0 >}}

## Agenda items

[00:00](https://youtu.be/IAngVFxtje0?t=0) – Intro - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[04:56](https://youtu.be/IAngVFxtje0?t=296) – PnP .NET library updates - [Bert Jansen](http://twitter.com/O365bert) (Microsoft) @O365bert

[06:54](https://youtu.be/IAngVFxtje0?t=414) – PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Staffbase) \| @gautamdsheth

[08:34](https://youtu.be/IAngVFxtje0?t=514) – yo Teams updates - [Stephan Bisser](https://twitter.com/stephanbisser) (Solvion) \| @stephanbisser

[09:46](https://youtu.be/IAngVFxtje0?t=586) – Microsoft Teams Toolkit updates - [John Miller](https://twitter.com/jmillerdev) (Microsoft) \| @jmillerdev

[10:54](https://youtu.be/IAngVFxtje0?t=654) – Microsoft Graph Toolkit updates – [Gavin Barron](https://twitter.com/gavinbarron) (Microsoft) \| @gavinbarron

[12:14](https://youtu.be/IAngVFxtje0?t=734) – Independent Publisher Connectors - [Jocelyn Panchal](https://twitter.com/JocelynP_PM) (Microsoft) \| @JocelynP_PM

[13:37](https://youtu.be/IAngVFxtje0?t=817) – Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock

[15:40](https://youtu.be/IAngVFxtje0?t=940) – Microsoft Teams Samples - [Bob German](https://twitter.com/Bob1German) (Microsoft) @Bob1German

[17:19](https://youtu.be/IAngVFxtje0?t=1039) – Microsoft Power Platform Samples - [April Dunnam](http://twitter.com/aprildunnam) (Microsoft) \| @aprildunnam

[17:54](https://youtu.be/IAngVFxtje0?t=1074) – Together mode picture

[19:00](https://youtu.be/IAngVFxtje0?t=1140) – Demo - A SharePoint document generator as Microsoft 365 app as Microsoft Teams native app – [Markus Möller](https://twitter.com/Moeller2_0)​ (Avanade) \| @Moeller2_0

[31:48](https://youtu.be/IAngVFxtje0?t=1908) – Demo - Build a training request solution with Power Platform – Phiwayinkosi Khanya Dludlu​​

[43:36](https://youtu.be/IAngVFxtje0?t=2616) – Demo - Using dynamic SVGs with List Formatting for SharePoint and Microsoft Lists – [Chris Kent​](https://twitter.com/theChrisKent) (Takeda) \| @theChrisKent

[58:09](https://youtu.be/IAngVFxtje0?t=3489) – Closing

## Together Mode

![together-230413.png](images/together-230413.png)

Did anyone see the cat on the table? Thank you again for joining the call today or for viewing is as convenient. Hope to see you at an in-person conference sometime soon.

## Actions

* [Give us feedback about the calls](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR02h_1H9_XFFp4etSzu5JxFUOEc5UkxDN0dGMUgyOTBDVklBREJPRVI1Qi4u) – rate the call content and provide input on how we can improve - aka.ms/community/calls/feedback
* [Request to Present a demo](https://aka.ms/community/request/demo) during Microsoft 365 & Power Platform community calls - aka.ms/community/request/demo
* Chime into a Community Calls Conversation – chat about demos anytime. Links and QR Codes associated to every demo – see in call deck and in demo summaries.
* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Maturity Model Practitioners \| Tuesday, April 18th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
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

* **A SharePoint document generator as Microsoft 365 app as Microsoft Teams native app**
    * Article - [SharePoint document review in Outlook or Teams](https://mmsharepoint.wordpress.com/2023/02/07/sharepoint-document-review-in-outlook-or-teams/) \| <https://mmsharepoint.wordpress.com/2023/02/07/sharepoint-document-review-in-outlook-or-teams/>
    * Article - [A SharePoint document generator as Microsoft 365 app I (yoteams)](https://mmsharepoint.wordpress.com/2022/12/28/a-sharepoint-document-generator-as-microsoft-365-app-i-yoteams/) \| <https://mmsharepoint.wordpress.com/2022/12/28/a-sharepoint-document-generator-as-microsoft-365-app-i-yoteams/>
    * Sample - [Offer Creation (yoteams) - Microsoft Teams App](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-office-offer-creation) \| <https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-office-offer-creation>
    * Documentation - [Extend Teams apps across Microsoft 365](https://learn.microsoft.com/microsoftteams/platform/m365-apps/overview) \| <https://learn.microsoft.com/microsoftteams/platform/m365-apps/overview>
    * Demo – [A SharePoint document generator as Microsoft 365 app with SPFx](https://youtu.be/bdVBHcrYjno?t=1181) – [Markus Möller](https://twitter.com/Moeller2_0) (Avanade) \| @Moeller2_0
* **Using dynamic SVGs with List Formatting for SharePoint and Microsoft Lists**
    * Documentation - [Use column formatting to customize SharePoint](https://learn.microsoft.com/sharepoint/dev/declarative-customization/column-formatting?WT.mc_id=m365-15744-cxa) \| aka.ms/spdocs-column-formatting
    * Samples - [List Formatting Samples](https://pnp.github.io/List-Formatting/) \| aka.ms/List-Formatting
    * Tool – [Inkscape](https://inkscape.org/) \| <https://inkscape.org/>
    * Extension - [inkscape-applytransforms](https://github.com/Klowner/inkscape-applytransforms) \| <https://github.com/Klowner/inkscape-applytransforms>
    * Tool – [HTML To Formatter](https://pnp.github.io/List-Formatting/tools/html-formatter-generator/) - <https://pnp.github.io/List-Formatting/tools/html-formatter-generator/>

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)

## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.12.0 GA
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.9.0 GA
[Microsoft 365 Assessment tool](https://docs.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.12.0 GA, v2.1.1 preview|Nightly builds
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v4.1.0 GA, v4.1.1-preview.2|Prepping v4.2.0 
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.8.0 GA, v1.8.1-preview
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.2.0 GA, v1.4.1-preview
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1 GA
[Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx)|v4.2.4 GA (VS Code), v5.0.0 RC (VS Code), v17.4 (VS), v17.5-preview-2 (VS)|New builds daily
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.9.2 GA, v3.0 preview.1

## Links referenced in call

* Microsoft 365 & Power Platform community videos - aka.ms/community/videos
* LinkedIn group for discussions and updates - aka.ms/community/Li
* Open-source assets
    * github.com/pnp
    * github.com/officedev
    * github.com/sharepoint
    * github.com/microsoftgraph
* Unified Sample gallery - aka.ms/community/samples
* Product sample galleries
    * aka.ms/teams-samples
    * aka.ms/spfx-webparts
    * aka.ms/spfx-extensions
    * aka.ms/powerplatform-samples
    * aka.ms/list-formatting
* One place for Open-source initiatives and samples - aka.ms/community/home
* Microsoft 365 & Power Platform community calls - aka.ms/community/calls
* Community call agendas - aka.ms/community/meetup
* Request to Present - aka.ms/community/request/demo
* Invite (ics) for the Microsoft 3656 & Power Platform call - aka.ms/community/ms-speakers-call-invite
* Learn how to get started in the open-source PnP community! – aka.ms/sharing-is-caring
* Community Recognition Program – aka.ms/community/recognition
* Project Specific
    * PnP Core SDK – aka.ms/pnp/coresdk
    * PnP Framework – aka.ms/pnp/framework
    * PnP .NET Libraries Change Log - github.com/pnp/pnpcore/blob/dev/src/sdk/CHANGELOG.md
    * PnP PowerShell - github.com/pnp/powershell
    * PowerShell Change Log - github.com/pnp/powershell/blob/dev/CHANGELOG.md
    * yo teams – aka.ms/yoteams
    * Microsoft Teams Toolkit – aka.ms/ttk-chat
    * Microsoft Graph Toolkit – aka.ms/MGT
    * MGT Samples - aka.ms/mgt/samples
    * MGT Issues - aka.ms/mgt/issues
    * Independent Publisher Connectors wiki - microsoft/PowerPlatformConnectors Wiki (github.com)
    * Script Samples – aka.ms/script-samples
    * Teams Samples – aka.ms/teams-samples
    * Teams App Support – aka.ms/TeamsApp/Support
    * Power Platform Samples – aka.ms/powerplatform-samples
* Community Calls Conversations - powerusers.microsoft.com/t5/Community-Calls-Conversations/bd-p/pa_community_calls
* Feedback on this call - aka.ms/community/calls/feedback
* Follow us on Twitter for updates - @m365pnp

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

* Microsoft 365 platform call \| Tuesday, April 18, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Power Platform monthly call \| Wednesday, April 19, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, April 20, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, April 20, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Microsoft 365 & Power Platform Dev call \| Thursday, April 27, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Office add-in monthly call \| Wednesday, May 10, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 13th of April 2023*
