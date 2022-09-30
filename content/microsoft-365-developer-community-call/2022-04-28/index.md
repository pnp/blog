---
title: "Microsoft 365 & Power Platform Development Community call - 28th of April, 2022"
date: 2022-04-28T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 Developer Community Call"]
images:
- images/recording-28th-april.png
tags: []
type: "regular"
summary: "Three demos: Updates on Independent Publisher Connectors & GitLab Connector Demo, List formatting magic - Discussion board formatting, and TeamsFx .NET - Introduction to Teams Explorer Sample.   Released Microsoft 365 Assessment tool 1.0.0 plus 5 script and 1 Teams sample!"
videos:
- https://www.youtube.com/watch?v=6ko2z7RSjTY
---


## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Announcing the new [Microsoft 365 Unified Sample
    Gallery](https://adoption.microsoft.com/sample-solution-gallery) - More than
    1060 samples \| aka.ms/m365/samples consolidated from all sources. Solution
    specific galleries:
    * Microsoft 365 tenant – [script samples
        gallery](https://aka.ms/script-samples) (149 scenarios and 212+ scripts)
    * The MGT samples repository is now LIVE! <https://aka.ms/mgt/samples>

* Agenda set for next [Microsoft 365 platform
    call](https://aka.ms/m365-dev-call) on Tuesday, May 3, 8:00 am PT. Microsoft
    presenters and topics:
    * **Erin Bailie** - Extend your Microsoft Teams app to Outlook and Office
    * **James Eccles & Bert Jansen** - Introducing new M365 Assessment Tool
        with SharePoint Syntex Module
    * **Nancy Wang** - Run Office Scripts with a button - now in Excel for
        Windows
* Project releases
    * [Microsoft 365 Assessment tool
        1.0.0](https://docs.microsoft.com/assessments/) (successor to the
        Modernization Scanner) released \| aka.ms/microsoft365assessment
    * Blog Post - [PnP PowerShell
        v1.10](https://pnp.github.io/blog/pnp-powershell/pnp-powershell-v1-10/)
* Script samples
    * NEW - [Get Hub Sites Details and Export it to
        CSV](https://pnp.github.io/script-samples/spo-export-hub-sites-details-to-csv/README.html?tabs=pnpps)
        \- [Chandani Prajapati](http://twitter.com/Chandani_SPD) \| @Chandani_SPD
    * NEW - [Export OneDrive
        Admins](https://pnp.github.io/script-samples/onedrive-export-admins/README.html?tabs=pnpps)
        \- [Matt Maher](https://github.com/Maher256/) \| Maher256
    * Updated - [Get Hub Sites Details and Export it to
        CSV](https://pnp.github.io/script-samples/spo-export-hub-sites-details-to-csv/README.html?tabs=pnpps)
        – Two additional tool updates
        \- [Jasey Waegebaert](https://github.com/Jwaegebaert) \| Jwaegebaert &
        [Chandani Prajapati](http://twitter.com/Chandani_SPD) \| @Chandani_SPD
    * Updated - [List Guests within Teams in a
        tenant](https://pnp.github.io/script-samples/teams-list-guestusers/README.html?tabs=teamsps)
        \- [Jasey Waegebaert](https://github.com/Jwaegebaert) \| Jwaegebaert
    * Updated - [Export a csv report on all
        Whiteboards](https://pnp.github.io/script-samples/whiteboard-report-usage/README.html?tabs=whiteboard)
        \- [Nanddeep Nachan](http://twitter.com/NanddeepNachan) \|
        @NanddeepNachan
* Microsoft Teams samples
    * [HR Talent App
        Node](https://github.com/OfficeDev/msteams-sample-contoso-hr-talent-app-node)
        \- [Scott Perham](https://github.com/scottperham) \| scottperham and
        [Jack Lewis](https://linkedin.com/in/jacklewis123) \| jacklewis123
* Power Platform samples
    * Join the Power Platform Contributors Sharing is Caring Session – Monday,
        May 9, 10:30 am PT-
        [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMTFJWFFGVUxBNUFZQjZWRUdaOE5BMFkwNS4u)
* Microsoft 365 PnP Weekly – Episode 163 (April 25th) with Oslo, Norway based
    Principal Product Manager, [Mikael
    Svenson](https://twitter.com/mikaelsvenson) (Microsoft) \| @mikaelsvenson \|
    [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-163/) \|
    [podcast](https://www.podbean.com/ew/pb-4qmw4-120e239)

### Demos

* **Updates on Independent Publisher Connectors & GitLab Connector Demo** -
    there are 113 Independent Publisher Connectors in production, 31 in the
    pipeline delivered by 41 outstanding publishers. Use GitLab Dev Ops for
    Power Platform projects using GitLab connector to access GitLabs APIs for
    actions. Step through creating a project in newly provisioned sandbox. Move
    through Dev, Text, Deploy. Canvas app leverages ALM accelerator (Power CAT
    team-built tool), Azure VM and Power Automate flows.
* **List formatting magic - Discussion board formatting** - extend existing
    Kanban Board card view and rendering the Adaptive Cards in SharePoint, Teams
    and Planner. Use JSON formatting to add 3 new features to cards - flags,
    move to top, and expand/collapse. Manage cards with filtering, menu options,
    bots, mail forwarding rules, Power Automate flows, use conditional
    formatting, collect comments, add/delete and mark as complete. Exemplifies
    the build once, render anywhere approach.
* **TeamsFx .NET - Introduction to Teams Explorer Sample** - a sample tab (and
    very useful developer resource) that leverages Graph and SPO API endpoints.
    Authentication by TeamsFx SSO and certificate for PnP Core. The app is built
    using TeamsFX .NET library, Blazor, Microsoft Graph and Visual Studio. From
    tab, select a Team, view the Team’s properties, installed apps, channels,
    team members, etc. No need to go to Postman or Graph Explorer.

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII)
(Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the
call.

{{< youtube 6ko2z7RSjTY >}}

## Agenda items

* PnP .NET library updates - [Bert Jansen](http://twitter.com/O365bert)
    (Microsoft) @O365bert – [6:24](https://youtu.be/6ko2z7RSjTY?t=384)
* PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth)
    (Valo Intranet) \| @gautamdsheth –
    [8:11](https://youtu.be/6ko2z7RSjTY?t=491)
* yo Teams updates - [David Warner II](http://twitter.com/DavidWarnerII)
    (Microsoft) \| @DavidWarnerII – [9:54](https://youtu.be/6ko2z7RSjTY?t=594)
* Microsoft Graph Toolkit updates - [David Warner
    II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII –
    [10:19](https://youtu.be/6ko2z7RSjTY?t=619)
* Microsoft Script Samples - [David Warner
    II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII –
    [4:06](https://youtu.be/6ko2z7RSjTY?t=246)
* Microsoft Teams Samples - [David Warner
    II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII –
    [11:04](https://youtu.be/6ko2z7RSjTY?t=664)
* Microsoft Power Platform Samples - [David Warner
    II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII –
    [11:37](https://youtu.be/6ko2z7RSjTY?t=697)
* Demo - Updates on Independent Publisher Connectors & GitLab Connector Demo -
    [Natalie Pienkowska](http://twitter.com/NataliePienkow1) (Microsoft) \|
    @NataliePienkow1 & [Roy Paar](http://twitter.com/RoyPaar) (Microsoft) \|
    @RoyPaar – [13:52](https://youtu.be/6ko2z7RSjTY?t=832)
* Demo - List formatting magic - Discussion board formatting - [André
    Lage](http://twitter.com/aaclage) (Datalynx AG) \| @aaclage –
    [24:54](https://youtu.be/6ko2z7RSjTY?t=1494)
* Demo - TeamsFx .NET - Introduction to Teams Explorer Sample - [Thomas
    Gölles](http://twitter.com/thomyg) (Solvion) \| @thomyg –
    [42:05](https://youtu.be/6ko2z7RSjTY?t=2525)

## Actions

* Opt into PnP Recognition Program \| <https://aka.ms/m365pnp-recognition>
* Register for [Microsoft Tech Days](https://aka.ms/techdays/m365) \|
    Thursday, May 5, 2022.
* Register for [Microsoft Build](https://mybuild.microsoft.com/) \| May 24-26,
    2022
* Join us at the next Microsoft 365 platform call on Tuesday, May 3, 8:00 am
    PT. [Invite](https://aka.ms/m365-dev-call)
* Register for Sharing is Caring Events:
    * Community Docs Session \| Tuesday, May 17, 10:00 am PT -
        [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    * Power Platform Samples – First Time Contributor \| Monday, May 9, 10:30
        am PT-
        [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMTFJWFFGVUxBNUFZQjZWRUdaOE5BMFkwNS4u)
    * Maturity Model Practitioners \|
        <https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u>[Register](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    * PnP Office Hours – 1:1 session \|
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a
        Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer
    Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn)
    covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution
    Gallery](https://adoption.microsoft.com/sample-solution-gallery) from
    Microsoft and community.
* Sign up to [Share your story](https://aka.ms/share-your-story) in the [Learn
    from the community](https://aka.ms/LearnFromTheCommunity/ThisWeek) series.
* Request a Demo spot on the call – <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call – <https://aka.ms/spdev-sig-call>

## Demo references

* Updates on Independent Publisher Connectors & GitLab Connector Demo
    * Documentation - [GitLab (Independent Publisher)
        (Preview)](https://docs.microsoft.com/connectors/gitlabip/) 
    * Connector Repo –
        [GitLab](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/GitLab)        
    * Requested connector - [Top Connector
        Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)        
    * Documentation - [Independent publisher certification
        process](https://docs.microsoft.com/connectors/custom-connectors/certification-submission-ip)        
    * Documentation - [Create a custom connector from
        scratch](https://docs.microsoft.com/connectors/custom-connectors/define-blank)        
* List formatting magic - Discussion board formatting
    * Sample - [Board tag
        format](https://github.com/pnp/List-Formatting/tree/master/view-samples/board-tag-format)        
    * Samples - [List Formatting
        Samples](https://pnp.github.io/List-Formatting/) 
* TeamsFx .NET - Introduction to Teams Explorer Sample
    * Tools - [Microsoft Teams Framework
        (TeamsFx)](https://github.com/OfficeDev/TeamsFx) 
    * Tools -
        [Blazor](https://dotnet.microsoft.com/apps/aspnet/web-apps/blazor) 
    * Demo - [TeamsFx .NET - Current Updates - April
        2022](https://youtu.be/5yULqXWIz2M?t=801) – [Thomy
        Gölles](http://twitter.com/thomyg) (Solvion) \| @thomyg

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)


## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.9.0 GA|Prepping for v1.10.0
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.6.0 GA|Prepping for v1.7.0
[Microsoft 365 Assessment tool](https://docs.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool                                     
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.10.0 GA|In progress: V2 POC - .NET 6.0 based, Requires PowerShell 7.2
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v3.5.0 GA, v4.0.0-next(.2)|Planning v4.0.0 release in mid-May
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.6.0, 1.6.0-next.1
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.1.0 GA
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1 GA
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.4.0 GA|Working on v3.0.0 - Aligning all Toolkit components to Fluent UI Web Components

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

* Microsoft 365 platform call \| Tuesday, May 3, 8:00 am PT –
    <https://aka.ms/m365-dev-call> (weekly)
* Viva Connections & SharePoint Framework call \| Thursday, May 5, 7:00 am PT –
    <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Office add-in monthly call \| Wednesday, May 11, 8:00 am PT -
    <https://aka.ms/officeaddinscall> (monthly)
* M365 General Dev call \| Thursday, May 12, 7:00 am PT -
    <https://aka.ms/m365-dev-sig> (bi-weekly)
* Adaptive Cards monthly call \| Thursday, May 12, 9:00 am PT -
    <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Power Platform monthly call \| Wednesday, May 18, 8:00 am PT -
    <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, May 19, 9:00 am PT -
    <https://aka.ms/IDDevCommunityCalendar> (monthly)

## About

General Microsoft 365 Dev Special Interest Group bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, PowerApps, Column Formatting, list formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments to this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/sppnp).


_“Sharing is caring”_

_Microsoft 365 Community (PnP) team, Microsoft - 29th of April 2022_

{{< attachments >}}

