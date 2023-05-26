---
title: "Microsoft 365 & Power Platform Development Community call - 25th of May, 2023"
date: 2023-05-25T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-25th-may.png
tags: []
type: "regular"
summary: "Demos: Pi Flows: PowerFx for Internet of Things, Automating DLP Policy Creation in Power Platform from an Existing Policy, and Microsoft Teams Phone Number Management on a Budget with SharePoint Lists and Azure Automation. Releases: MGT and 20 assets!"
videos:
- https://www.youtube.com/watch?v=__gcts_NKrk
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Announcements
    * Agenda set for next [Microsoft 365 & Power Platform weekly call](https://aka.ms/m365-dev-call) - Tuesday, May 30th, 8:00 am PT.
        * Latest news from Microsoft engineering on Microsoft 365 topics
        * **Marc Windl** – Introduction to Repository As A Service (RaaS) feature
        * **Jethro Seghers** – Introducing Microsoft Viva Connections for Education
        * **Vesa Juvonen** - Latest on using SPFx on building extensibility for SharePoint
    * Community Calls Conversations - Chime into a Community Calls Conversation – chat about demos anytime. Links and QR Codes associated to every demo – see in call deck and in demo summaries.
    * Event - [HackTogether: The Microsoft Teams Global Hack](https://github.com/microsoft/hack-together-teams) (June 1 – 15, 2023) \| aka.ms/hack-together-teams
    * Join our official Discord Server – aka.ms/community/discord
* Project releases
    * [Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx) – v5.0.0 GA (VS Code)
    * [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit) – v3.0.0-Preview.2
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) submissions
    * 1028 certified connectors as of today.
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
    * Good Flow story? Tell us. [FlowOfTheWeek](https://aka.ms/FlowOfTheWeekForm) – aka.ms/FlowOfTheWeekForm
* [Script samples](https://pnp.github.io/script-samples/)
    * New – PnP PowerShell – [Find all items with unique permission and export to CSV](https://pnp.github.io/script-samples/spo-get-items-with-custom-permissions/README.html?tabs=pnpps) - [Kasper Larsen](https://twitter.com/kasperbolarsen) \| @kasperbolarsen
    * New – PnP PowerShell – File Version Trimmer - [Kasper Larsen](https://twitter.com/kasperbolarsen) \| @kasperbolarsen
    * Updated – CLI for Microsoft 365 – [List all Microsoft Team’s Owners and Members](https://pnp.github.io/script-samples/teams-list-teams-owners-and-members/README.html?tabs=pnpps) - [Ganesh Sanap](http://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Add/Update Image in SharePoint Image Column](https://pnp.github.io/script-samples/spo-add-update-image-column/README.html?tabs=pnpps) - [Ganesh Sanap](http://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Delete Custom Color Themes from SharePoint](https://pnp.github.io/script-samples/spo-remove-custom-themes/README.html?tabs=pnpps) - [Ganesh Sanap](http://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Download all the content type document templates file associated with a library](https://pnp.github.io/script-samples/spo-list-download-contenttype-documenttemplate/README.html?tabs=pnpps) - [Ganesh Sanap](http://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Create SharePoint Groups in Bulk using CSV File](https://pnp.github.io/script-samples/spo-create-sharepoint-groups-bulk-csv/README.html?tabs=pnpps) - [Ganesh Sanap](http://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Empty the tenant recycle bin](https://pnp.github.io/script-samples/spo-empty-tenant-recyclebin/README.html?tabs=pnpps) - [Ganesh Sanap](http://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – CLI for Microsoft 365 – [Hide SharePoint list from Site Contents](https://pnp.github.io/script-samples/spo-hide-list-from-site-contents/README.html?tabs=pnpps) - [Ganesh Sanap](http://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – SPO Management Shell – Enable Disable App Bar in SharePoint Online - [Ganesh Sanap](http://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – PnP PowerShell – Request Reindex of SharePoint User Profile Properties – LotsaMocha01
    * [Good first issue asks](https://github.com/pnp/script-samples)
    * Power Platform Integrations / Connectors LABs Participant Calls. [Complete this form](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR0BHMrjhL0hDmckROosW6AFUOUVHNTlRRlAxQUI5S0hJNFdIWkZBRzlaTy4u)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/) – Featured Teams App Samples with Full Tutorials
    * Teams AI Library
        * Tutorial - [Build your first app using Teams AI library](https://learn.microsoft.com/microsoftteams/platform/sbs-botbuilder-conversation-ai?tabs=vscode%2Cviscode) \| aka.ms/ai-chef-bot
        * Sample - Soon
    * New App Campo labs \| aka.ms/app-camp-new
        * Workshop - Build Microsoft Teams apps leveraging existing software investments
        * Hands on Lab - [From Web Services to Teams Apps using Teams Toolkit v5.0](https://build.microsoft.com/sessions/e5152be8-46ae-4b51-8c18-6b01416cb261?source=/schedule)
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* [Power Platform Samples](https://pnp.github.io/powerplatform-samples/) & [Power Apps Samples](https://github.com/pnp/powerapps-samples)
    * New Power App - Instagram Basic Display - [Reshmee Auckloo](http://twitter.com/ReshmeeAuckloo) \| @ReshmeeAuckloo
    * New Power App - Teams Team Request Form - [Katerina Chernevskaya](https://www.linkedin.com/in/katerinachernevskaya/)
    * New Power App - KPI Sample - [Nathalie Leenders](https://twitter.com/NathLeenders) \| @NathLeenders
* Conversations
    * Microsoft 365 PnP Weekly – Episode 211 (May 22nd) with Belgium-based consultant - [Elio Struyf](https://twitter.com/eliostruyf) (Struyf Consulting) \| @eliostruyf \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-211/) \| [podcast](https://www.podbean.com/eas/pb-2uy4b-141643c)
    * Jocelyn Panchal - Power Platform Connections Ep 14 (May 19th) \| [video](https://www.youtube.com/watch?v=zFFTeYiKFTw)
    * Microsoft 365 Developer Podcast – Open AI Chat GPT, Azure Communication Services and Microsoft Graph with Dan Wahlin (May 22nd) \| [podcast](https://m365devpodcast.com/e/open-ai-chat-gpt-azure-communication-services-and-microsoft-graph-with-dan-wahlin/)
    * [Monday’s @ Microsoft](https://www.linkedin.com/company/microsoft-community/) 

### Demos

* **Pi Flows: PowerFx for Internet of Things** – challenged with writing software for IoT hardware devices? Remotely control hardware via Canvas app. On site, create a web app (Pi Flow) with an internal API that understands Power FX language, has local storage and controls hardware device. At the control center, create a Canvas App that communicates with the web app’s API via a custom connector. Join the 2 environments using Azure Hybrid Connections. Conversation at [aka.ms/May25-Demo1](https://aka.ms/May25-Demo1)
* **Automating DLP Policy Creation in Power Platform from an Existing Policy** – see 3 options for cloning an existing Data Loss Prevention (DLP) policy in your tenant. 1. use the Power Platform Management Connector (a flow), 2. use the DLP Editor App in the CoE Starter Kit, or 3. use Power Shell using the Power Apps Administration Module that when used with a flow completely automates the process. For each option, the DLP with all connectors are copied. Conversation at [aka.ms/May25-Demo3](https://aka.ms/May25-Demo3)
* **Microsoft Teams Phone Number Management on a Budget with SharePoint Lists and Azure Automation** – elephant in the room - phone number management in Teams Admin Center is lacking. Here is the in-house alternative you may want to consider. Uses SharePoint Online, Microsoft List (names and numbers), Azure Automation, PowerShell, CLI for Microsoft 365, and Power Automate. 1-click deployment - the Environment.json script’s Runbook delivers the magic in 5-10 minutes. Customization options using Power Automate. Demo adding/removing users and phone numbers. Conversation at [aka.ms/May25-Demo2](https://aka.ms/May25-Demo2)

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube __gcts_NKrk >}}

## Agenda items

[00:00](https://youtu.be/__gcts_NKrk?t=0) – Intro - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[06:20](https://youtu.be/__gcts_NKrk?t=380) – PnP .NET library updates - [Bert Jansen](http://twitter.com/O365bert) (Microsoft) \| @O365bert

[07:49](https://youtu.be/__gcts_NKrk?t=469) – PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Staffbase) \| @gautamdsheth

[08:53](https://youtu.be/__gcts_NKrk?t=533) – yo Teams updates - [Stephan Bisser](https://twitter.com/stephanbisser) (Solvion) \| @stephanbisser

[10:00](https://youtu.be/__gcts_NKrk?t=600) – Microsoft Teams Toolkit updates - [John Miller](https://twitter.com/jmillerdev) (Microsoft) \| @jmillerdev

[11:22](https://youtu.be/__gcts_NKrk?t=682) – Microsoft Graph Toolkit updates – [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[11:55](https://youtu.be/__gcts_NKrk?t=715) – Independent Publisher Connectors - [Natalie Pienkowska](http://twitter.com/NataliePienkow1) (Microsoft) \| @NataliePienkow1

[13:30](https://youtu.be/__gcts_NKrk?t=810) – Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock

[15:04](https://youtu.be/__gcts_NKrk?t=904) – Microsoft Teams Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[15:33](https://youtu.be/__gcts_NKrk?t=933) – Microsoft Power Platform Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[16:03](https://youtu.be/__gcts_NKrk?t=963) – Together mode picture

[17:11](https://youtu.be/__gcts_NKrk?t=1031) – Demo - Pi Flows: PowerFx for Internet of Things – [Eswar Prakash](https://twitter.com/eswaratwork)​​ (Resonate) \| @eswaratwork

[29:55](https://youtu.be/__gcts_NKrk?t=1795) – Demo - Automating DLP Policy Creation in Power Platform from an Existing Policy – [Mohammed Ashiq Faleel](https://twitter.com/AshiqFaleel) (Avanade) \| @AshiqFaleel

[43:36](https://youtu.be/__gcts_NKrk?t=2616) – Demo - Microsoft Teams Phone Number Management on a Budget with SharePoint Lists and Azure Automation – [Martin Heusser](https://twitter.com/mozzeph) (Houlihan Lokey) \| @mozzeph

[59:54](https://youtu.be/__gcts_NKrk?t=3594) – Closing


## Together Mode

![together-230525.png](images/together-230525.png)

Thank you everyone for joining the call today. It was great seeing some of you in person at ECS last week.     

## Actions

* [Join our official Discord Server](https://aka.ms/community/discord) – aka.ms/community/discord
* [Give us feedback about the calls](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR02h_1H9_XFFp4etSzu5JxFUOEc5UkxDN0dGMUgyOTBDVklBREJPRVI1Qi4u) – rate the call content and provide input on how we can improve - aka.ms/community/calls/feedback
* [Request to Present a demo](https://aka.ms/community/request/demo) during Microsoft 365 & Power Platform community calls - aka.ms/community/request/demo
* Chime into a Community Calls Conversation – chat about demos anytime. Links and QR Codes associated to every demo – see in call deck and in demo summaries.
* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Maturity Model Practitioners \| Tuesday, June 20th, 7am PST - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
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

* **Pi Flows: PowerFx for Internet of Things**
    * Playlist - [Physical Computing with Power Platform](https://www.youtube.com/playlist?list=PLB6bnbyeFRLlU1lcmhLU861OnuDeW-4IH)
* **Automating DLP Policy Creation in Power Platform from an Existing Policy**
    * Article - [How to copy an existing DLP Policy in Power Platform](https://ashiqf.com/2023/03/19/how-to-copy-an-existing-dlp-policy-in-power-platform/)
    * Connectors - [Power Platform for Admins](https://learn.microsoft.com/connectors/powerplatformforadmins/)
    * Documentation - [Use core components](https://learn.microsoft.com/power-platform/guidance/coe/core-components)
    * Documentation - [Microsoft.PowerApps.Administration.PowerShell](https://learn.microsoft.com/powershell/module/microsoft.powerapps.administration.powershell)
    * Documentation - [Power Platform data loss prevention (DLP) SDK](https://learn.microsoft.com/power-platform/admin/data-loss-prevention-sdk)
    * Documentation – [Azure Automation runbook types](https://learn.microsoft.com/azure/automation/automation-runbook-types)
    * Article – [How to copy an existing DLP Policy in Power Platform](https://ashiqf.com/2023/03/19/how-to-copy-an-existing-dlp-policy-in-power-platform/)
    * Blog - [Mohamed Ashiq Faleel](https://ashiqf.com/)
* **Microsoft Teams Phone Number Management on a Budget with SharePoint Lists and Azure Automation**
    * Article - [Teams Phone Number Management on a Budget](https://medium.com/@mozzeph/teams-phone-number-management-on-a-budget-e25d53f65caf) (Part 1)
    * Article - [Teams Phone Number Management List Part 2](https://medium.com/@mozzeph/teams-phone-number-management-list-part-2-b5385e348a3a)
    * Repo - [Teams Phone Automation](https://github.com/mozziemozz/TeamsPhoneAutomation)

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)

## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.12.0 GA
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.9.0 GA
[Microsoft 365 Assessment tool](https://docs.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool
[PnP PowerShell](https://github.com/pnp/powershell)|v1.12.0 GA, v2.1.1 GA|Nightly builds
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v4.1.0 GA, v4.1.1-preview.2|Prepping v4.2.0 
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.8.0 GA, v1.8.1-preview
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.2.0 GA, v1.4.0-preview
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1 GA
[Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx)|v4.2.4 GA (VS Code), v5.0.0 GA (VS Code), v17.4 (VS), v17.5-preview-2 (VS)|New builds daily
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.10.1 GA, v3.0 preview.2|v3.0.0 preview.2  to be released early May

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
*   Join our official Discord Server – aka.ms/community/discord

## Upcoming calls | Recurrent invites

* Microsoft 365 platform call \| Tuesday, May 30, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Viva Connections & SharePoint Framework call \| Thursday, June 1, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft 365 & Power Platform Dev call \| Thursday, June 8, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Office add-in monthly call \| Wednesday, June 14, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Microsoft Identity Platform call \| Thursday, June 15, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Power Platform monthly call \| Wednesday, June 21, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 25th of May 2023*
