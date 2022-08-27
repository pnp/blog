---
title: "Microsoft 365 & Power Platform Development Community call - 21st of July, 2022"
date: 2022-07-21T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 Developer Community Call"]
images:
- images/recording-2022-07-21.png
tags: []
type: "regular"
summary: "Demos: Document automation using Microsoft SharePoint Syntex Content Assembly, Building a conversational tab in a Microsoft Teams app that captures external event conversations, and List formatting tips. Released [Microsoft Graph Toolkit](https://github.com/microsoftgraph/microsoft-graph-toolkit) – v2.6.0, 8 connectors, 5 script, 1 Teams, 3 Power Platform samples."
videos:
- https://www.youtube.com/watch?v=k2yKGOCj4Ck
draft: false
---


## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Project releases
    * [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit) – v2.6.0 GA
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) submissions
    * New - [SOS Inventory](https://github.com/Harold-Anderson/Power-Automate-SOS-Inventory-Custom-Connector) – [Harold Anderson](https://github.com/Harold-Anderson)
    * New - [ConvertKit](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/ConvertKit) - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * New – [Every](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Every) - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * New – File.io - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * New – [RescueGroups.org](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/RescueGroups) - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * New – [SchoolDigger](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/SchoolDigger) - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * New - SignUpGenius - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * New – Zenler - [Troy Taylor](https://github.com/troystaylor/PowerPlatformConnectors)
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* [Script samples](https://pnp.github.io/script-samples/)
    * New PowerShell – [Update web part properties on modern pages](https://pnp.github.io/script-samples/spo-update-modern-webpart-properties/README.html?tabs=pnpps) - [Ramin Ahmadi](https://twitter.com/raminahmadi1986) \| @raminahmadi1986
    * New PowerShell – [Export SharePoint Term Store terms to CSV](https://pnp.github.io/script-samples/spo-export-termstore-terms-to-csv/README.html?tabs=pnpps) - [Ramin Ahmadi](https://twitter.com/raminahmadi1986) \| @raminahmadi1986
    * New CLI – [List external users across all sites and in what site groups](https://pnp.github.io/script-samples/spo-list-site-externalusers-in-groups/README.html?tabs=cli-m365-ps) - [Martin Lingstuyl](https://github.com/martinlingstuyl)
    * Updated CLI – [List all external users in all site collections](https://pnp.github.io/script-samples/spo-list-site-externalusers/README.html?tabs=cli-m365-ps) - [Martin Lingstuyl](https://github.com/martinlingstuyl)
    * Updated Power App PowerShell – [Copy Planner plan](https://pnp.github.io/script-samples/planner-copy-planner-plan/README.html?tabs=cli-m365-ps) - [Reshmee Auckloo](http://twitter.com/ReshmeeAuckloo) \| @ReshmeeAuckloo
    * [Good first issue asks](https://github.com/pnp/script-samples)
* [Microsoft Teams samples](https://adoption.microsoft.com/sample-solution-gallery/?sortby=creationDateTime-true&keyword=&product=Teams&action=ajax_plugin_call_sample_solution_gallery)
    * New sample - [Tab Meeting StageView Vote Movie Fluid - Microsoft Teams App](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-meeting-stageview-vote-movie-fluid) and article [Use FluidFramework in a Microsoft Teams app](https://mmsharepoint.wordpress.com) - [Markus Moeller](http://twitter.com/Moeller2_0) \| @Moeller2_0
* [Power Platform Samples](https://pnp.github.io/powerplatform-samples/)
    * Updated - [Accessibility color checker](https://github.com/LuiseFreese/powerapps-samples/tree/main/samples/accessibility-color-contrast-checker) - [Luise Freese](https://twitter.com/LuiseFreese) \| @LuiseFreese
    * New - Keyword Tagger - [Matt Schuessler](https://twitter.com/MattSchues) \| @MattSchues
    * New - SharePoint Site Creation Bot - [Michel Mendes](https://twitter.com/michelcarlo) \| @michelcarlo

### Demos

* **Document automation using Microsoft SharePoint Syntex Content Assembly** - the content lifecycle broadly includes content understanding, discovery and assembly.  Today’s Syntax AI assisted focus is on content assembly capabilities namely content use/response generation and content creation from extracted insights. Build a content assembly contract template. In template, add content placeholders – for name, address. Road map includes reuse placeholders, templatizing tables and images, using field values as document metadata, and automating document generation with Power Automate.
* **Building a conversational tab in a Microsoft Teams app that captures external event conversations** – in a Microsoft Teams channel tab, create a conversation about an external event like an incident ticket including conversation’s context. Implementation - get Service URL from bot install activity, create a conversation using a Bot ConnectorClient, send conversationId to tab to be used in conversational tabs, and open conversation in Tab side panel. CodeTour walk through of presenter’s proof-of-concept sample.
* **Use folders to create a dynamic list filter and Power Automate to populate folders and create pages** - receive e-mail, add details to list, display item details in manually formatted page. Automate this process with a flow that creates a folder for each new list item and moves the list item into the folder using the Power Automate template - When a new item is added in SharePoint, complete a custom action. Presenter configures flow that includes updating list with page URL and metadata.

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII)
(Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the
call.

{{< youtube k2yKGOCj4Ck >}}

## Agenda items

* PnP .NET library updates - [Paolo Pialorsi](http://twitter.com/paolopia) (PiaSys.com) \| @paolopia – [5:28](https://youtu.be/k2yKGOCj4Ck?t=328)
* Microsoft Graph Toolkit updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [6:31](https://youtu.be/k2yKGOCj4Ck?t=391)
* Independent Publisher Connectors - [Natalie Pienkowska](http://twitter.com/NataliePienkow1) (Microsoft) \| @NataliePienkow1 – [7:07](https://youtu.be/k2yKGOCj4Ck?t=427)
* Microsoft Script Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [8:41](https://youtu.be/k2yKGOCj4Ck?t=521)
* Microsoft Teams Samples - [Bob German](https://twitter.com/Bob1German) (Microsoft) @Bob1German – [9:23](https://youtu.be/k2yKGOCj4Ck?t=563)
* Microsoft Power Platform Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [10:35](https://youtu.be/k2yKGOCj4Ck?t=635)
* Demo - Document automation using Microsoft SharePoint Syntex Content Assembly – Ankit Rastogi (Microsoft) – [12:14](https://youtu.be/k2yKGOCj4Ck?t=734)
* Demo - Building a conversational tab in a Microsoft Teams app that captures external event conversations - [Eoin O'Brien](https://www.linkedin.com/in/obrieneoin/) (Microsoft) – [20:53](https://youtu.be/k2yKGOCj4Ck?t=1253)
* Demo - Use folders to create a dynamic list filter and Power Automate to populate folders and create pages - [Chris Kent](https://twitter.com/theChrisKent) (DMI) \| @theChrisKent – [34:18](https://youtu.be/k2yKGOCj4Ck?t=2058)

## Together Mode

![220721-together-mode.gif](images/220721-together-mode.gif)

It is a pleasure as always to see many who joined the call today and if you have yet to view the session, enjoy the top-notch content.

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Writing for the Web \| Tuesday, August 2nd, 9:30am PT \| 12:30pm ET \| 6:30pm CET- [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Writing for the Web \| Tuesday, September 6th, 9:30am PT \| 12:30pm ET \| 6:30pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Maturity Model Practitioners \| Tuesday, September 20th, 7am PST - [Register](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* What do you need from PnP Core SDK? Let us know and/or view the latest changes at [PnP Core SDK Changelog](https://github.com/pnp/pnpcore/blob/dev/src/sdk/CHANGELOG.md).
* PowerShell suggestions? Please visit [PnP.PowerShell Changelog](https://github.com/pnp/powershell/blob/dev/CHANGELOG.md)
* Ideas for Microsoft Lists? aka.ms/Feedback/Lists
* Create a connector – [Top Power Platform Independent Publisher Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Request a Demo spot on the call – <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call – <http://aka.ms/spdev-sig-call>

## Demo references

* **Document automation using Microsoft SharePoint Syntex Content Assembly**
    * Article – [Automate creation of new documents with SharePoint Syntex Content Assembly](https://www.sharepointnutsandbolts.com/2022/05/Syntex-Content-Assembly.html)
* **Building a conversational tab in a Microsoft Teams app that captures external event conversations**
    * Sample - [Proactive Tab Conversations](https://github.com/OfficeDev/Microsoft-Teams-Samples/tree/main/samples/bot-tab-conversations/csharp)
    * Documentation - [Create conversational tabs](https://docs.microsoft.com/microsoftteams/platform/tabs/how-to/conversational-tabs)
    * Documentation - [Messages in bot conversations](https://docs.microsoft.com/microsoftteams/platform/bots/how-to/conversations/conversation-messages)
    * Documentation - [ConversationsExtensions.CreateConversationAsync Method](https://docs.microsoft.com/dotnet/api/microsoft.bot.connector.conversationsextensions.createconversationasync)
* **Use folders to create a dynamic list filter and Power Automate to populate folders and create pages**
* Documentation - [Use column formatting to customize SharePoint](https://docs.microsoft.com/sharepoint/dev/declarative-customization/column-formatting) \| [aka.ms/spdev-column-formatting](https://aka.ms/spdev-column-formatting)
* Icons - [Flicon.io](https://flicon.io/)
* Repo - [Community-tooling](https://github.com/pnp/community-tooling)
* Samples - [SharePoint List Formatting Samples](https://github.com/pnp/List-Formatting)
* Flow – [When a new item is added in SharePoint, complete a custom action](https://powerautomate.microsoft.com/templates/details/3999d042ec7a49c5b91ae2229037fdb7/when-a-new-item-is-added-in-sharepoint-complete-a-custom-action/)
* Demo - [Microsoft Forms to SharePoint List: Create SharePoint List from Excel](https://www.youtube.com/watch?v=9hBeckKMlrg)

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)


## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.10.0 GA|Prepping 1.11.0 (after summer break)
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.7.0 GA|Prepping for 1.8.0 (after summer break)
[Microsoft 365 Assessment tool](https://docs.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool                                     
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.11.0 GA|
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v4.0.0 GA
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.7.0 GA
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.2.0 GA
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1 GA
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.6.0 GA

## General resources

*   Script Samples - [Getting started with PnP Script Samples](https://aka.ms/script-samples/getting-started) – aka.ms/script-samples/getting-started
*   Samples - [Power Platform Samples](https://aka.ms/powerplatform-samples) | [aka.ms/](https://aka.ms/powerplatform-samples)[powerplatform](https://aka.ms/powerplatform-samples)[\-samples](https://aka.ms/powerplatform-samples)
*   Microsoft 365 tenant – [Script Samples Gallery](https://aka.ms/script-samples) | aka.ms/script-samples
*   [Microsoft Teams Samples Gallery](https://pnp.github.io/teams-dev-samples/) | aka.ms/teams-samples
*   [Microsoft 365 Extensibility look book gallery](https://adoption.microsoft.com/extensibility-look-book?WT.mc_id=m365-24198-cxa) | aka.ms/m365/extensibility
*   Archives - Microsoft 365 PnP Weekly - [Videos](https://www.youtube.com/playlist?list=PLR9nK3mnD-OVYI-St_CBiFfuL4CZbBpkC), [Podcasts](https://pnpweekly.podbean.com/)  
*   PnP Teams Quickstart | [aka.ms/pnp-teams-quickstart](https://aka.ms/pnp-teams-quickstart)
*   Microsoft Teams Toolkit v3.x | [https://aka.ms/teams-toolkit](https://aka.ms/teams-toolkit)
*   [Microsoft 365 platform community blog](https://pnp.github.io/blog) | aka.ms/m365pnp/blog
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

* Viva Connections & SharePoint Framework call \| Thursday, July 28, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* M365 General Dev call \| Thursday, August 4, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Office add-in monthly call \| Wednesday, August 10, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Adaptive Cards monthly call \| Thursday, August 11, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Power Platform monthly call \| Wednesday, August 17, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, August 18, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Microsoft 365 platform call \| Tuesday, September 6, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 21st of July 2022*

{{< attachments >}}

