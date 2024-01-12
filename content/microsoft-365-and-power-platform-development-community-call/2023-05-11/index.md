---
title: "Microsoft 365 & Power Platform Development Community call - 11th of May, 2023"
date: 2023-05-11T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-11th-may.png
tags: []
type: "regular"
summary: "Demos: What Three Words - Power Platform Custom Connector, How to automate the process to convert the rows of excel sheets into the rows of Dataverse, and Validating PowerShell parameters with SharePoint Information. Releases: MGT and 15 assets."
videos:
- https://www.youtube.com/watch?v=N1t8EWstUcI
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Announcements
    * Agenda set for next [Microsoft 365 & Power Platform weekly call](https://aka.ms/m365-dev-call) - Tuesday, May 16th, 8:00 am PT.
        * Latest news from Microsoft engineering on Microsoft 365 topics
        * **Srinivas Varukala** & **Rick Shire** – Building a Microsoft Teams Call queue scheduler solution for customers
        * **Supriti Bhan** – Introduction to Live Share SDK for Microsoft Teams apps
        * **Vesa Juvonen** - Latest on building Microsoft Viva extensibility with SPFx
    * Community Calls Conversations - Chime into a Community Calls Conversation – chat about demos anytime. Links and QR Codes associated to every demo – see links in demo summaries.
    * [Monday’s @ Microsoft](https://www.linkedin.com/company/microsoft-community/) – Premier Episode (Mon, May 15th , 8:00 am PT)
    * Event - [HackTogether: The Microsoft Teams Global Hack](https://github.com/microsoft/hack-together-teams) (June 1 – 15, 2023) \| aka.ms/hack-together-teams
* Project releases
    * [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit) – v3.0.0 preview.1
    * Nightly builds for many of the projects
* [Script samples](https://pnp.github.io/script-samples/)
    * New – PnP PowerShell – [Enable Modern creation forms for Document Sets](https://pnp.github.io/script-samples/spo-document-sets-modern-new-form/README.html?tabs=pnpps) - [Dan Toft](https://twitter.com/tanddant) (Evobis ApS) \| @tanddant
    * New – PnP PowerShell – [Enable and Disable App Bar in SharePoint Online](https://pnp.github.io/script-samples/spo-enable-disable-app-bar/README.html?tabs=pnpps) - [Aman Panjwani](https://www.linkedin.com/in/aman-17-panjwani/)
    * Updated – CLI for Microsoft 365 – [Open Office documents in the Client](https://pnp.github.io/script-samples/spo-open-doc-in-client/README.html?tabs=pnpps) - [Ganesh Sanap](https://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Disable SharePoint List Commenting at tenant level](https://pnp.github.io/script-samples/spo-disable-list-comments-tenant/README.html?tabs=spoms-ps) - [Ganesh Sanap](https://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Associate Multiple Site Collections to Hub Site](https://pnp.github.io/script-samples/spo-associate-multiple-sites-to-hub/README.html?tabs=pnpps) - [Ganesh Sanap](https://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Activate a site feature in SharePoint online](https://pnp.github.io/script-samples/spo-activate-site-feature/README.html?tabs=pnpps) - [Ganesh Sanap](https://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Remove Title Area from SharePoint Page](https://pnp.github.io/script-samples/spo-remove-page-title-area/README.html?tabs=pnpps) - [Ganesh Sanap](https://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Update SharePoint Page Banner Image](https://pnp.github.io/script-samples/spo-update-page-banner-image/README.html?tabs=pnpps) - [Ganesh Sanap](https://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Add Page template to Site](https://pnp.github.io/script-samples/spo-add-page-template/README.html?tabs=pnpps) - [Ganesh Sanap](https://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – SPO Management Shell – [Set Home site for SharePoint online tenant](https://pnp.github.io/script-samples/spo-set-home-site/README.html?tabs=spoms-ps) - [Ganesh Sanap](https://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – PnP PowerShell – [SharePoint Modern Page URL Report](https://pnp.github.io/script-samples/spo-modern-page-url-report/README.html?tabs=pnpps) - [Paul Bullock](https://twitter.com/pkbullock) \| @pkbullock with thanks for feedback from David Nelson
    * [Good first issue asks](https://github.com/pnp/script-samples)
    * Power Platform Integrations / Connectors LABs Participant Calls. [Complete this form](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR0BHMrjhL0hDmckROosW6AFUOUVHNTlRRlAxQUI5S0hJNFdIWkZBRzlaTy4u)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/) – Featured Teams App Samples with Full Tutorials
    * Share documents from a SharePoint Document library directly into Microsoft Teams.
        * Article - [Query SharePoint items with Microsoft Graph and Search](https://mmsharepoint.wordpress.com/2021/06/16/query-sharepoint-items-with-microsoft-graph-and-search/) -
        * Sample - [msgext-graph-srch-config-csharp](https://github.com/pnp/teams-dev-samples/tree/main/samples/msgext-graph-action-config-csharp) - [Markus Möller](https://twitter.com/Moeller2_0)​ (Avanade) \| @Moeller2_0
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* Conversations
    * Microsoft 365 PnP Weekly – Episode 209 (May 8th) with Belgium-based Microsoft MVP and Microsoft 365 Consultant - [Milan Holemans](https://www.linkedin.com/in/milan-holemans/) (VanRoey.be) \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-209/) \| [podcast](https://www.podbean.com/eas/pb-9xtah-1402897)
    * Power Platform Connections - Power Platform Connections Ep 12 - MVP Summit Special (May 4th) \| [video](https://www.youtube.com/watch?v=PnR0L0VMhlc)
    * Microsoft 365 Developer Podcast – Hackathon winning Magic Note app by Ahmad Mozaffar (May 8th) \| [podcast](https://m365devpodcast.com/e/hackathon-winning-magic-note-app-by-ahmad-mozaffar/)

### Demos

* **What Three Words - Power Platform Custom Connector** – what is the What3Words independent publisher connector and the related Power App? What are the differences between Independent and Certified connectors and GitHub usage tips. The What3Words connector delivers global location in 3-meter squares using 3 descriptive words. The Power App uses Power FX to collect Lat / Long from user, call the W3W API, and pinpoints location on map and 3 words for location. Discussion at [aka.ms/May11-Demo1](https://aka.ms/May11-Demo1)
* **How to automate the process to convert the rows of excel sheets into the rows of Dataverse** – using Power Platform. See demo of final solution and understand prerequisite tools/access requirements, then step through uploading an xls to OneDrive and the importation of data into a Power Apps table and subsequent movement into Dataverse. Uses Import document and 2 supporting Power Automate flows. See the expressions used in Power Automate along with possible errors (learning opportunities) and explanations. Discussion at [aka.ms/May11-Demo2](https://aka.ms/May11-Demo1)
* **Validating PowerShell parameters with SharePoint Information** – create your own PowerShell cmdlet that allows you to pull and tab through information from a site, list, text file, Azure, Graph, etc. within PowerShell environment. Learn by working through a scenario how ValidateSet and ValidateScript attributes and [ArgumentCompleter] help you deliver a better user experience, reduce bad data and make you a better coder! Bonus insight on working with chatGPT to deliver concise code. Discussion at [aka.ms/May11-Demo3](https://aka.ms/May11-Demo1)

The host of this call was [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube N1t8EWstUcI >}}

## Agenda items

[00:00](https://youtu.be/N1t8EWstUcI?t=0) – Intro - [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[05:30](https://youtu.be/N1t8EWstUcI?t=330) – PnP .NET library updates - [Bert Jansen](https://twitter.com/O365bert) (Microsoft) \| @O365bert

[06:13](https://youtu.be/N1t8EWstUcI?t=373) – PnP PowerShell updates - [Gautam Sheth](https://twitter.com/gautamdsheth) (Staffbase) \| @gautamdsheth

[07:41](https://youtu.be/N1t8EWstUcI?t=461) – yo Teams updates - [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[08:23](https://youtu.be/N1t8EWstUcI?t=503) – Microsoft Teams Toolkit updates - [John Miller](https://twitter.com/jmillerdev) (Microsoft) \| @jmillerdev

[09:56](https://youtu.be/N1t8EWstUcI?t=596) – Microsoft Graph Toolkit updates – [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[10:50](https://youtu.be/N1t8EWstUcI?t=650) – Microsoft Script Samples - [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[11:27](https://youtu.be/N1t8EWstUcI?t=687) – Microsoft Teams Samples - [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[12:27](https://youtu.be/N1t8EWstUcI?t=747) – Microsoft Power Platform Samples - [Hugo Bernier](https://twitter.com/bernierh) (Microsoft) \| @bernierh

[13:18](https://youtu.be/N1t8EWstUcI?t=798) – Together mode picture

[15:02](https://youtu.be/N1t8EWstUcI?t=902) – Demo - What Three Words - Power Platform Custom Connector – [Matt Beard](https://twitter.com/Mattybeard) (Data8 Ltd)​​ \| @Mattybeard

[28:19](https://youtu.be/N1t8EWstUcI?t=1699) – Demo - How to automate the process to convert the rows of excel sheets into the rows of Dataverse – Abdul Wahab (Dynamics Technology Systems)

[41:57](https://youtu.be/N1t8EWstUcI?t=2517) – Demo - Validating PowerShell parameters with SharePoint Information – [Todd Klindt](https://twitter.com/ToddKlindt) (Sympraxis Consulting) \| @ToddKlindt

[54:53](https://youtu.be/N1t8EWstUcI?t=3293) – Closing

## Together Mode

![together-230511.png](images/together-230511.png)

Thank you everyone for joining the call today. Awesome to see you here.  Great demos today.

## Actions

* [Give us feedback about the calls](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR02h_1H9_XFFp4etSzu5JxFUOEc5UkxDN0dGMUgyOTBDVklBREJPRVI1Qi4u) – rate the call content and provide input on how we can improve - aka.ms/community/calls/feedback
* [Request to Present a demo](https://aka.ms/community/request/demo) during Microsoft 365 & Power Platform community calls - aka.ms/community/request/demo
* Chime into a Community Calls Conversation – chat about demos anytime. Links and QR Codes associated to every demo – see in call deck and in demo summaries.
* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Maturity Model Practitioners \| Tuesday, May 16th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
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
* Download the recurrent invite for this call – <https://aka.ms/spdev-sig-call>

## Demo references

* **What Three Words - Power Platform Custom Connector**
* Documentation - [Data8 Data Enrichment](https://learn.microsoft.com/connectors/data8/)
* Documentation - [What3Words (Independent Publisher) (Preview)](https://learn.microsoft.com/connectors/what3wordsip/)
* **How to automate the process to convert the rows of excel sheets into the rows of Dataverse**
* **Validating PowerShell parameters with SharePoint Information**
* Validation Repo – [PoshPnP](https://github.com/ToddKlindt/PoshPnP)
* Project Repo - [PnP PowerShell](https://pnp.github.io/powershell/)

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)

## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.12.0 GA
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.9.0 GA
[Microsoft 365 Assessment tool](https://learn.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool
[PnP PowerShell](https://github.com/pnp/powershell)|v1.12.0 GA, v2.1.1 GA|Nightly builds
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v4.1.0 GA, v4.1.1-preview.2|Prepping v4.2.0
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.8.0 GA, v1.8.1-preview
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.2.0 GA, v1.4.1-preview
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1 GA
[Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx)|v4.2.4 GA (VS Code), v5.0.0 RC (VS Code), v17.4 (VS), v17.5-preview-2 (VS)|New builds daily
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.10.1 GA, v3.0 preview.1|v3.0.0 preview.2  to be released early May

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

* Microsoft 365 platform call \| Tuesday, May 16, 8:00 am PT - <https://aka.ms/m365-dev-call> (weekly)
* Power Platform monthly call \| Wednesday, May 17, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, May 18, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, May 18, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Microsoft 365 & Power Platform Dev call \| Thursday, May 25, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Office add-in monthly call \| Wednesday, June 14, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 11th of May 2023*
