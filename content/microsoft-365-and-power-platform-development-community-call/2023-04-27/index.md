---
title: "Microsoft 365 & Power Platform Development Community call - 27th of April, 2023"
date: 2023-04-27T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-27th-april.png
tags: []
type: "regular"
summary: "Demos: Group voicemail app using SharePoint, Teams, Power Automate & Power Apps and Task management and Timeboxing within the Microsoft ecosystem, driven by a Power Automate flow. Releases: PnP PowerShell, Microsoft Graph Toolkit (MGT), 8 scripts, 1 sample, 3 conversations."
videos:
- https://www.youtube.com/watch?v=eoWS-0Fgo8w
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Announcements
    * Agenda set for next [Microsoft 365 & Power Platform weekly call](https://aka.ms/m365-dev-call) - Tuesday, May 2nd, 8:00 am PT.
        * Latest news from Microsoft engineering on Microsoft 365 topics
        * **Marcus Castro** – Power Platform Solutions in Microsoft Teams – Example scenario deep dive
        * **Ayça Baş** – Build Outlook Add-ins using Teams Toolkit for Visual Studio Code
    * Community Calls Conversations - Chime into a Community Calls Conversation – chat about demos anytime. Links and QR Codes associated to every demo – see in call deck and in demo summaries.
* Project releases
    * [PnP PowerShell](https://github.com/pnp/powershell) – v2.1.1 (GA)
    * [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit) – v2.10.1 (GA)
* [Script samples](https://pnp.github.io/script-samples/)
    * New – PnP PowerShell – [Add Page template to Site](https://pnp.github.io/script-samples/spo-add-page-template/README.html?tabs=pnpps) - [Dennis Goedegebuure](https://twitter.com/expiscornovus) \| @expiscornovus
    * New – PnP PowerShell – [Deploys and Installs SharePoint Framework (SPFx) solutions to Hub and Associated Sites](https://pnp.github.io/script-samples/spo-deploy-install-update-spfx-hubsite-associatedsites/README.html?tabs=pnpps) - [Reshmee Auckloo](https://twitter.com/ReshmeeAuckloo) \| @ReshmeeAuckloo
    * Updated – CLI for Microsoft 365 – [Empty SharePoint Online site recycle bin](https://pnp.github.io/script-samples/spo-empty-recycle-bin/README.html?tabs=pnpps) - [Ganesh Sanap](https://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Delete custom SharePoint site design](https://pnp.github.io/script-samples/spo-remove-site-designs/README.html?tabs=spoms-ps) - [Ganesh Sanap](https://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Add App Catalog to SharePoint site](https://pnp.github.io/script-samples/spo-add-app-catalog/README.html?tabs=pnpps) - [Ganesh Sanap](https://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Delete custom SharePoint site scripts](https://pnp.github.io/script-samples/spo-remove-site-scripts/README.html?tabs=spoms-ps) - [Ganesh Sanap](https://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Disable SharePoint List Commenting at list level](https://pnp.github.io/script-samples/spo-disable-list-comments/README.html?tabs=pnpps) - [Ganesh Sanap](https://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – SPO Management Shell – [Disable SharePoint List Commenting at tenant level](https://pnp.github.io/script-samples/spo-disable-list-comments-tenant/README.html?tabs=spoms-ps) - [Ganesh Sanap](https://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * [Good first issue asks](https://github.com/pnp/script-samples)
    * Power Platform Integrations / Connectors LABs Participant Calls. [Complete this form](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR0BHMrjhL0hDmckROosW6AFUOUVHNTlRRlAxQUI5S0hJNFdIWkZBRzlaTy4u)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/) – Featured Teams App Samples with Full Tutorials
    * Sample - [tab-sso-graph-upload-pdf-csharp](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-sso-graph-upload-as-pdf-csharp) - [Markus Möller](https://twitter.com/Moeller2_0)​ (Avanade) \| @Moeller2_0
    * ISV’S BUILDING MONETIZED TEAMS APPS - The ecosystem team wants to support you! \| aka.ms/TeamsApp/Support
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* Conversations
    * Microsoft 365 PnP Weekly – Episode 207 (April 24th) with India-based Cloud Consultant and Microsoft 365 Developer MVP - [Chandani Prajapati](https://twitter.com/Chandani_SPD) (Rapid Circle) \| @Chandani_SPD \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-207/) \| [podcast](https://www.podbean.com/eas/pb-7pw9n-13ef317)
    * Power Platform Connections - Power Platform Connections Ep 10 - Vivian Voss (April 21st) \| [video](https://www.youtube.com/watch?v=3qc18mvb22c)
    * Power Platform Connections - Power Platform Connections Ep 11 - Chris Huntingford (April 27th) \| [Video](https://www.youtube.com/watch?v=0uo-lZckCJQ)

### Demos

* **Group voicemail app using SharePoint, Teams, Power Automate & Power Apps** – meet the Therapy Playground Voicemail (Power) App that extends Teams (Voice) auto attendant (captures and transcribes messages) by displaying both the mp3 and transcription of message in app. The app tracks responses - who/time/action. This tracking closes the issue/response loop by centralizing and driving response actions. Actions include direct response to customer, forward to another team member. Power Automate flow executes message movement. Discussion at [aka.ms/Apr27-Demo1](https://aka.ms/Apr27-Demo1)
* **Task management and Timeboxing within the Microsoft ecosystem, driven by a Power Automate flow** – presenter uses Planner (business) and To Do (personal) for task management. Problem - how to simplify exposing tasks in Outlook. Solution - Power Automate flow that Syncs entries in To Do, Planner and Outlook calendar. Flow evaluates tasks in Planner, To Do and Outlook, eliminates duplicates and adds new/updated tasks into calendar. Tasks are kept in Planner and To Do (source). Comprehensive flow logic walkthrough. Discussion at [aka.ms/Apr27-Demo2](https://aka.ms/Apr27-Demo2)

The host of this call was [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube eoWS-0Fgo8w >}}

## Agenda items

[00:00](https://youtu.be/eoWS-0Fgo8w?t=0) – Intro - [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[05:01](https://youtu.be/eoWS-0Fgo8w?t=301) – PnP .NET library updates - [Bert Jansen](https://twitter.com/O365bert) (Microsoft) @O365bert

[06:43](https://youtu.be/eoWS-0Fgo8w?t=403) – PnP PowerShell updates - [Gautam Sheth](https://twitter.com/gautamdsheth) (Staffbase) \| @gautamdsheth

[07:50](https://youtu.be/eoWS-0Fgo8w?t=470) – yo Teams updates - [Rick Van Rousselt](https://twitter.com/rickvanrousselt) (Advantive) \| @rickvanrousselt

[08:35](https://youtu.be/eoWS-0Fgo8w?t=515) – Microsoft Teams Toolkit updates - [John Miller](https://twitter.com/jmillerdev) (Microsoft) \| @jmillerdev

[09:49](https://youtu.be/eoWS-0Fgo8w?t=589) – Microsoft Graph Toolkit updates – [Sébastien Levert](https://twitter.com/sebastienlevert) (Microsoft) \| @sebastienlevert

[11:46](https://youtu.be/eoWS-0Fgo8w?t=706) – Microsoft Script Samples - [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[12:20](https://youtu.be/eoWS-0Fgo8w?t=740) – Microsoft Teams Samples - [David Warner II](https://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[12:54](https://youtu.be/eoWS-0Fgo8w?t=774) – Microsoft Power Platform Samples - Hugo Bernier (Microsoft) \| @bernierh

[13:49](https://youtu.be/eoWS-0Fgo8w?t=829) – Together mode picture

[14:42](https://youtu.be/eoWS-0Fgo8w?t=882) – Demo - Group voicemail app using SharePoint, Teams, Power Automate & Power Apps – [Kevin Dibb](https://www.linkedin.com/in/kevindibb/)​ (Dibb Solutions)

[24:05](https://youtu.be/eoWS-0Fgo8w?t=1445) – Demo - Task management and Timeboxing within the Microsoft ecosystem, driven by a Power Automate flow – [Tobias Fenster](https://twitter.com/@tobiasfenster) (4PS Germany) \| @tobiasfenster

[37:10](https://youtu.be/eoWS-0Fgo8w?t=2230) – Closing

## Together Mode

![together-230427.png](images/together-230427.png)

Great high 5s, another packed room, good on you. Thank you everyone for joining the call today. Awesome to see you here and hopefully we will see some of you next week in Las Vegas.

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

* **Group voicemail app using SharePoint, Teams, Power Automate & Power Apps**
    * Documentation - [Set up a Microsoft Teams auto attendant](https://learn.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant?tabs=general-info)
    * Documentation - [Plan your Teams voice solution](https://learn.microsoft.com/microsoftteams/cloud-voice-landing-page)
    * Documentation - [Set up Cloud Voicemail](https://learn.microsoft.com/microsoftteams/set-up-phone-system-voicemail)
* **Task management and Timeboxing within the Microsoft ecosystem, driven by a Power Automate flow**
    * Article - [Adding all your To-Do and Planner tasks to your calendar with Power Automate](https://tobiasfenster.io/adding-all-your-to-do-and-planner-tasks-to-your-calendar-with-power-automate)

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
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.10.1 GA, v3.0 preview.1|v3.0.0 preview.2  to be released first week of May

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

* Microsoft 365 platform call \| Tuesday, May 2, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Viva Connections & SharePoint Framework call \| Thursday, May 4, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Office add-in monthly call \| Wednesday, May 10, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Microsoft 365 & Power Platform Dev call \| Thursday, May 11, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Power Platform monthly call \| Wednesday, May 17, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, May 18, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 27th of April 2023*
