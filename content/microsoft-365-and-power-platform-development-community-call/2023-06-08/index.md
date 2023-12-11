---
title: "Microsoft 365 & Power Platform Development Community call - 8th of June, 2023"
date: 2023-06-08T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-230608.png
tags: []
type: "regular"
summary: "Demos: Power Platform Custom Connector for Chat GPT, Tracking workflow runs and errors using Power Automate and SharePoint, and Build your own Documentation Website with DocFX on SharePoint. Released: MGT version updates and 7 assets!"
videos:
- https://www.youtube.com/watch?v=H_dklzRYcFc
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### Releases

* Projects
    * [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit) – v2.11.1 (GA) and v3.0.0 RC.3
* [Script samples](https://pnp.github.io/script-samples/)
    * New – PnP PowerShell – [Allow custom scripts in SharePoint online site](https://pnp.github.io/script-samples/spo-allow-custom-scripts/README.html?tabs=spoms-ps) - [Ganesh Sanap](http://twitter.com/GaneshSanap20) \| @GaneshSanap20
    * Updated – PnP PowerShell – [SharePoint List Item Version History Retrieval](https://pnp.github.io/script-samples/spo-get-list-item-version-history/README.html?tabs=pnpps) – [Kasper Larsen](https://twitter.com/kasperbolarsen) \| @kasperbolarsen
    * New sample structure with all the supporting files - **New-Sample.ps1** - Located in the root of the repo
    * [Good first issue asks](https://github.com/pnp/script-samples)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/) – Featured Teams App Samples with Full Tutorials
    * [Bookmark Bot for Microsoft Teams](https://github.com/pnp/teams-dev-samples/tree/main/samples/bot-graph-bookmark) - [Ejaz Hussain](https://twitter.com/EjazHussain_) (Content and Code) \| @EjazHussain\_
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* Power platform
    * Check out the new [Power Platform Prompt Library Repo](https://aka.ms/powerplatformprompts) – aka.ms/powerplatformprompts
* Conversations
    * Microsoft 365 PnP Weekly – Episode 213 (June 5th) with Portugal-based Developer, Microsoft 365 Architect, and Microsoft MVP - [Rodrigo Pinto](https://twitter.com/ScoutmanPt) (Storm Technology Ltd) \| @ScoutmanPt \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-213/) \| [podcast](https://www.podbean.com/eas/pb-ptcmt-1428749)
    * Power Platform Connections - Lewis Baybutt \| Power Platform Connections Ep 15 (June 2nd) \| [video](https://www.youtube.com/watch?v=BOwTYzfxZvo&t=1650s)
    * Microsoft 365 Developer Podcast – Microsoft Graph Developer Proxy with Garry Trinder and Waldek Mastykarz (June 5th) \| [podcast](https://m365devpodcast.com/e/microsoft-graph-developer-proxy-with-garry-trinder-and-waldek-mastykarz/)
    * Microsoft 365 Developer Podcast – Teams Toolkit v5 with John Miller (June 1st) \| [podcast](https://m365devpodcast.com/e/teams-toolkit-v5-with-john-miller/)

### Demos

* **Power Platform Custom Connector for Chat GPT** – create a connector and use it in a Power App in less than 15 minutes. In this two-phase demo, create and configure a custom Power Platform connector (open template, set authentication, add OpenAPI key, define an action and test) and in Phase 2 - use connector in a Power Apps. Create a simple canvas app, add connector, add call to access OpenAI via connector. Conversation at aka.ms/June8-Demo1
* **Tracking workflow runs and errors using Power Automate and SharePoint** – yes Approval Workflows sometimes break? Here’s a Power Automate solution that tracks run failures enabling you to quickly fix and resubmit them. Log workflows in Power Automate using SharePoint or visa versa. Session covers why this solution, creating a Global SP Site/List, creating a Power Automate Flow, Scope Actions (containers in Power Automate), and getting workflow info. Review a workflow framework flow in Power Automate. Tips shared throughout. Conversation at aka.ms/June8-Demo2
* **Build your own Documentation Website with DocFX on SharePoint** – with help and scripts from an experienced pro. What is the DocFX tool, why is it awesome, setup challenges, where is a DocFx generated static website hosted? Let’s see. Clone repo, create project, generate out-of-box site. Then, run Initialize-AwesomeDocFx.ps1 script that yields a more robust site. Add docs/images. Want your site on SPO? Run BuildDocFxForSPO.ps1, create a document library, compare and upload new files. Conversation at aka.ms/June8-Demo3

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube H_dklzRYcFc >}}

## Agenda items

[00:00](https://youtu.be/H_dklzRYcFc?t=0) – Intro - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[05:15](https://youtu.be/H_dklzRYcFc?t=315) – PnP .NET library updates - [Bert Jansen](http://twitter.com/O365bert) (Microsoft) \| @O365bert

[06:12](https://youtu.be/H_dklzRYcFc?t=372) – PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Staffbase) \| @gautamdsheth

[06:57](https://youtu.be/H_dklzRYcFc?t=417) – yo Teams updates - [Rick Van Rousselt](http://twitter.com/rickvanrousselt) (Advantive) \| @rickvanrousselt

[07:54](https://youtu.be/H_dklzRYcFc?t=474) – Microsoft Teams Toolkit updates - [Vesa Juvonen](https://twitter.com/VesaJuvonen) (Microsoft) \| @VesaJuvonen

[08:34](https://youtu.be/H_dklzRYcFc?t=514) – Microsoft Graph Toolkit updates – [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII

[09:11](https://youtu.be/H_dklzRYcFc?t=551) – Independent Publisher Connectors - [Jocelyn Panchal](https://twitter.com/JocelynP_PM) (Microsoft) @JocelynP_PM

[10:06](https://youtu.be/H_dklzRYcFc?t=606) – Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock

[11:37](https://youtu.be/H_dklzRYcFc?t=697) – Microsoft Teams Samples - [Bob German](https://twitter.com/Bob1German) (Microsoft) @Bob1German

[12:41](https://youtu.be/H_dklzRYcFc?t=761) – Microsoft Power Platform Samples - [April Dunnam](http://twitter.com/aprildunnam) (Microsoft) \| @aprildunnam

[14:00](https://youtu.be/H_dklzRYcFc?t=840) – Together mode picture

[15:29](https://youtu.be/H_dklzRYcFc?t=929) – Demo - Power Platform Custom Connector for Chat GPT – Samir Daoudi (LogiSam)​

[27:29](https://youtu.be/H_dklzRYcFc?t=1649) – Demo - Tracking workflow runs and errors using Power Automate and SharePoint – [Jonathan Weaver](https://twitter.com/j_weaver74)​ (WaterOne) \| @j_weaver74

[41:23](https://youtu.be/H_dklzRYcFc?t=2483) – Demo - Build your own Documentation Website with DocFX on SharePoint – [Martin Heusser](https://twitter.com/mozzeph)​ (Houlihan Lokey) \| @mozzeph

[56:04](https://youtu.be/H_dklzRYcFc?t=3364) – Closing

## Together Mode

![together-230608.png](images/together-230608.png)

Thank you everyone for joining the call today. Have a great rest of the day, week, month, year, decade…    

## Activities & Actions

* Check out the new [Power Platform Prompt Library Repo](https://aka.ms/powerplatformprompts) – aka.ms/powerplatformprompts
* Agenda set for next [Microsoft 365 & Power Platform weekly call](https://aka.ms/m365-dev-call) - Tuesday, June 13th, 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * **Marc Windl** – How Microsoft Syntex Repository Services powers Microsoft Loop
    * **Lan Li & Kishor Subedi** – Introduction to Power Automate Copilot
    * **Paolo Pialorsi** - Exposing Microsoft Teams apps in Microsoft Viva with SPFx cards
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

* **Power Platform Custom Connector for Chat GPT​**
    * Article - [Power Platform – ChatGPT Custom Connector](https://daoudisamir.com/power-platform-chatgpt-custom-connector/)
* **Tracking workflow runs and errors using Power Automate and SharePoint**
    * Article - [Workflow Logging](https://jonathanmweaver.wordpress.com/2023/06/05/workflow-logging/)
* **Build your own Documentation Website with DocFX on SharePoint**
    * Documentation – [docfx Quick Start](https://dotnet.github.io/docfx/)
    * Organization - .[NET Foundation](https://dotnetfoundation.org/)
    * Organization - [Microsoft Learn. Spark possibility](https://learn.microsoft.com)
    * Documentation - [Awesome Docs](https://delightful-bush-073e2f403.3.azurestaticapps.net/index.html)
    * Repo – [Docs (template)](https://github.com/mozziemozz/awesome-docfx-template)

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
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.11.1 GA, v3.0.0 RC3

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

## Recurrent call invites

* Microsoft 365 platform call \| *weekly* - Tuesday, 8:00 am PT - <https://aka.ms/m365-dev-call> (**Note:** This call will be on holiday from Tuesday July 4th through Tuesday August 15th)
* Microsoft 365 & Power Platform Dev call \| *bi-weekly* - Thursday, 7:00 am PT - <https://aka.ms/m365-dev-sig>
* Viva Connections & SharePoint Framework call \| *bi-weekly* - Thursday, 7:00 am PT - <https://aka.ms/spdev-spfx-call>
* Office add-in call \| *monthly* - 2nd Wednesday, 8:00 am PT - <https://aka.ms/officeaddinscall>
* Power Platform call \| *monthly* - 3rd Wednesday, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall>

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 8th of June 2023*
