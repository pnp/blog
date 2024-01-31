---
title: "Microsoft 365 Platform Community Call - 10th of January, 2023"
summary: "Demos - Introduction Microsoft Graph PowerShell v2 preview release, Test how your SPFx solutions respond to throttling with Graph Developer Proxy, and Introduction to Microsoft Viva ACE development learn module - Getting started."
date: 2023-01-11T04:00:00.000Z
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 platform call"]
images:
- images/recording-10th-january.png
tags: []
type: regular
videos:
- https://www.youtube.com/watch?v=vCFnqq690p8
draft: false
---

## Call summary

Welcome to the weekly call focused on capabilities of the Microsoft 365 platform.  In this call, we highlight recently announced and key existing developer resources, news, community events and three demos.

### New this week

* Announcements
    * Samples – [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) - aka.ms/m365/samples now with more than 1450 samples from Microsoft and community.
* News
    * Article – [SharePoint Pages Microsoft Graph API is now available for public preview](https://devblogs.microsoft.com/microsoft365dev/sharepoint-pages-microsoft-graph-api-is-now-available-for-public-preview/) \| SharePoint team
    * Article – [New Microsoft Graph Developer Proxy preview v0.3 with support for all APIs](https://devblogs.microsoft.com/microsoft365dev/microsoft-graph-developer-proxy-v0-3/) - [Waldek Mastykarz](https://twitter.com/waldekm) (Microsoft) \| @waldekm & [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder
    * Article – [New year, new rituals with Microsoft Viva Insights](https://techcommunity.microsoft.com/t5/microsoft-viva-blog/new-year-new-rituals-with-microsoft-viva-insights/ba-p/3708902) - Sakshi Budhraja (Microsoft)
* Microsoft Teams Platform Updates
    * Feedback – [Frequently asked questions](https://learn.microsoft.com/microsoftteams/platform/teams-faq)
* Conversations
    * Microsoft 365 PnP Weekly – Episode 192 (January 9th) with Netherlands based CTO Low-Code Solutions and Microsoft MVP - [Albert-Jan Schot](https://twitter.com/appieschot) (BLIS.digital) \| @appieschot \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-192/) \| [podcast](https://pnpweekly.podbean.com/)
    * Microsoft 365 DDeveloper Podcast – [Partner Showcase: Integratin Yasoon with Tobias Viehweger](https://www.m365devpodcast.com/e/partner-showcase-integrating-yasoon-with-tobias-viehweger/)

### Demos

* **Introduction Microsoft Graph PowerShell v2 preview release** – review features/improvements from v1 to v2 modules. Understand scripting for and how endpoints are targeted by modules, improvements to and support for more auth scenarios (managed identity support), and other improvements. In Azure Cloud Shell, appreciate the ease of installing a module, authentication, getting users, grouping users and deleting users/groups. Uses new managed identity to make calls without certificates and secrets. Feedback welcome.
* **Test how your SPFx solutions respond to throttling with Graph Developer Proxy** – in SharePoint Workbench, in your tenant of 1, keeping you’re app code as is, simulate your app’s resilience under heavy load. Example: Test specifically for 429 errors. See configuring Proxy for scenario and then see how Proxy simulates/identifies 429s on a Microsoft Graph API. Once issue identified, remediate - add a sleep function, use PnPjs that handles 429s for you, etc.
* **Introduction to Microsoft Viva ACE development learn module - Getting started** – learn about the new module in general and do 1st Exercise - Create a SPFx Basic Card ACE showing SharePoint list data. This ACE reads and writes to a SharePoint List. In hands-on lab, open your Workbench and site and add ACE to page. Look at operation of Card View, Quick View and at the target SharePoint list. Step through the AdaptiveCardExtension.ts, CardView.ts and QuickView.ts files.

The host of this call was [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen. Q&A takes place in chat throughout the call.

{{< youtube vCFnqq690p8 >}}

## Agenda items

* [08:44](https://youtu.be/vCFnqq690p8?t=524) – Latest updates and news on the Microsoft 365 platform – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen
* [09:55](https://youtu.be/vCFnqq690p8?t=595) – Microsoft Teams Platform updates – Surbhi Gupta (Microsoft)
* [10:48](https://youtu.be/vCFnqq690p8?t=648) – Together mode picture
* [11:58](https://youtu.be/vCFnqq690p8?t=718) – Demo Introduction Microsoft Graph PowerShell v2 preview release – [Maisa Rissi](https://twitter.com/maisarissi_msft) (Microsoft) \| @maisarissi_msft and [Peter Ombwa](https://www.linkedin.com/in/peterombwa/) (Microsoft)
* [26:16](https://youtu.be/vCFnqq690p8?t=1576) – Demo Test how your SPFx solutions respond to throttling with Graph Developer Proxy – [Waldek Mastykarz](https://twitter.com/waldekm) (Microsoft) \| @waldekm
* [36:40](https://youtu.be/vCFnqq690p8?t=2200) – Demo Introduction to Microsoft Viva ACE development learn module - Getting started – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen & [Andrew Connell](https://twitter.com/andrewconnell) (Voitanos) \| @andrewconnell

Thank you for your creativity and work execution. Samples are often showcased in Demos.

## Together Mode

![together-230110.png](images/together-230110.png)

Great to see so many familiar faces in this new year. Welcome to 2023! Awesome to have you here.

## Actions

* Opt into PnP Recognition Program – aka.ms/m365pnp-recognition
* Register for upcoming [Sharing Is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * First Time Contributor \| Thursday, January 12th, 10am PT \| 1pm ET \| 7pm CET – [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNjAwRVNETlA1MkxIR1MyTEs5STZFVVRJMC4u)
    * Maturity Model Practitioners \| Tuesday, January 17th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * Writing for the Web \| Monday, January 23rd, 10am PT \| 1pm ET \| 7:00pm CET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMFNPNFMyUk9CNFROUjJWTFFGSzdJV0czVC4u)
    * PnP SPFx Samples w/NVM \| Wednesday, January 25th, 9am PT \| 12pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNEE2SUdTOU1UOEtCTFU3MlM1SERDMlNVNi4u)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) with more than 1400 samples from Microsoft and community.
* Request a Demo spot on the call – aka.ms/m365pnp/request/demo
* Download the recurrent invite for this call – aka.ms/m365-dev-call

## Demo references

* **Introduction Microsoft Graph PowerShell v2 preview release**
    * Article - [Microsoft Graph PowerShell v2 is now in public preview, half the size and speeds up automation](https://devblogs.microsoft.com/microsoft365dev/microsoft-graph-powershell-v2-is-now-in-public-preview-half-the-size-and-will-speed-up-your-automations/) \| aka.ms/graph/preview-psv2
    * Documentation - [Microsoft Graph PowerShell V2 Changelog and Upgrade Guide](https://github.com/microsoftgraph/msgraph-sdk-powershell/blob/features/2.0/docs/upgrade-to-v2.md) \| aka.ms/graph/sdk/powershell/upgrade-to-v2
    * Feedback/Issues - [msgraph-sdk-powershell/issues](https://github.com/microsoftgraph/msgraph-sdk-powershell/issues/new)
    * Discussion - [Is it a good idea to have different cmdlet names in the V2 SDK? \#1705](https://github.com/microsoftgraph/msgraph-sdk-powershell/discussions/1705)
* **Test how your SPFx solutions respond to throttling with Graph Developer Proxy**
    * Tool - [Microsoft Graph Developer Proxy v0.3.0](https://github.com/microsoftgraph/msgraph-developer-proxy/releases/tag/v0.3.0) \| aka.ms/graph/proxy/download
    * Demo - [Introduction to Microsoft Graph Developer Proxy](https://youtu.be/jsXliaZCGqg) - Sébastien Levert (Microsoft) @sebastienlevert
* **Introduction to Microsoft Viva ACE development learn module - Getting started**
    * Exercise - [Exercise - Create SPFx Basic Card ACE showing SharePoint list data](https://learn.microsoft.com/training/modules/sharepoint-spfx-adaptive-card-extension-card-types/3-exercise-ace-basic-card-rest)
    * Learn Module - [Create Adaptive Card Extensions (ACE) for Microsoft Viva Connections](https://learn.microsoft.com/training/modules/sharepoint-spfx-adaptive-card-extension-card-types/) \| aka.ms/viva/ace/learn

## General resources

* Archives - Microsoft 365 PnP Weekly - [Videos](https://www.youtube.com/playlist?list=PLR9nK3mnD-OVYI-St_CBiFfuL4CZbBpkC), [Podcasts](https://pnpweekly.podbean.com/)
* Microsoft Teams Toolkit | [https://aka.ms/teams-toolkit](https://aka.ms/teams-toolkit)
* Microsoft Graph Toolkit in Microsoft Learn | [https://aka.ms/learn-mgt](https://aka.ms/learn-mgt)
* Viva Connections [https://aka.ms/VivaConnections](https://aka.ms/VivaConnections)
* [SharePoint look book](https://lookbook.microsoft.com/?WT.mc_id=m365-24198-cxa)
* [Yo Teams video training package](https://aka.ms/yoteams-training)
* [.NET Standard 2.0 version of SharePoint Online CSOM API](https://developer.microsoft.com/microsoft-365/blogs/net-standard-version-of-sharepoint-online-csom-apis?WT.mc_id=m365-24198-cxa)
* [Microsoft 365 Platform Community (PnP) videos](https://aka.ms/m365/videos) | aka.ms/m365/videos
* [Microsoft Teams Toolkit for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension)
* [yo Teams](https://aka.ms/yoteams) | aka.ms/yoteams
* [SPFx Developer documentation](https://aka.ms/spfx) | <https://aka.ms/spfx>
* [Microsoft 365 developer program site](https://developer.microsoft.com/office/dev-program?WT.mc_id=m365-24198-cxa) - Need to become a Tenant Admin to test look book capabilities? Get a Microsoft 365 E5 developer subscription - free tenant for 90 days with automatic renewal if used for dev purposes

## Upcoming Calls | Recurrent Invites

* Office add-in monthly call \| Wednesday, January 11, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, January 12, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft 365 platform call \| Tuesday, January 17, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Power Platform monthly call \| Wednesday, January 18, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft 365 General Dev call \| Thursday, January 19, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, January 19, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

Microsoft 365 Platform community call focuses on latest Microsoft 365 Platform updates and demos delivered by Microsoft presenters and takes place weekly on Tuesday.  The alternating Special Interest Group community calls each Thursday focus on SharePoint Framework (client-side development/implementation) and Microsoft 365 Platform (includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, PowerApps, Column Formatting, list formatting, etc. topics.) with demos commonly delivered by community members.

More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp).

You can download recurrent invite for this call from [https://aka.ms/m365-dev-call](https://aka.ms/m365-dev-call).  Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments to this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/sppnp).


&quot;_Sharing is caring&quot;_

_Microsoft 365 Platform Community team, Microsoft - 10th of January 2023_

{{< attachments >}}{{< /attachments >}}
