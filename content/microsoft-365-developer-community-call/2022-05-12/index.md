---
title: "Microsoft 365 & Power Platform Development Community call - 12th of May, 2022"
date: 2022-05-12T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 Developer Community Call"]
images:
- images/recording-12th-may.png
tags: []
type: "regular"
summary: "Demos:  How to build a SSO bot using yo teams for Microsoft Teams, List formatting magic – Advance discussion board formatting with Power Automate, and Taking advantage of new multi-lingual capabilities in list formatting.  Released Yo teams previews, 3 scripts, 1 Teams sample!"
videos:
- https://www.youtube.com/watch?v=SM_KlEcefcw
draft: false
---


## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, May 17, 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * **Mounika Narayanan** - Integrate Graph connector content on Office.com
    * **Waldek Mastykarz** and **Paolo Pialorsi** - Your Microsoft 365 app within the fingertips of employees with Viva Connections
* Project releases
    * Yo teams - generator-teams - v4.0.0-preview.1
    * [Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core) - v1.7.0-preview.2
    * [Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy) - v1.2.0-preview.2
* Script samples
    * Updated - [Testing user preferred language of SharePoint Site](https://pnp.github.io/script-samples/user-language-for-site/README.html?tabs=pnpps) - [Adam Wójcik](http://twitter.com/Adam25858782) \| @Adam25858782
    * Updated - [Update User Profile Properties](https://pnp.github.io/script-samples/spo-update-user-profile-properties/README.html?tabs=pnpps) - [Jasey Waegebaert](https://github.com/Jwaegebaert) \| Jwaegebaert
    * Updated - [Flow run day summary](https://pnp.github.io/script-samples/flow-runs-day-summary/README.html?tabs=cli-m365-ps) - [Leon Armston](http://twitter.com/LeonArmston) \| @LeonArmston
* Microsoft Teams samples
    * [HR Talent App Node](https://github.com/OfficeDev/msteams-sample-contoso-hr-talent-app-node) - [Scott Perham](https://github.com/scottperham) \| scottperham and [Jack Lewis](https://linkedin.com/in/jacklewis123) \| jacklewis123
* Microsoft 365 PnP Weekly – Episode 165 (May 2nd) Finland-based software architect and Office Developer MVP [Laura Kokkarinen](http://twitter.com/LauraKokkarinen) (Sulava) \| @LauraKokkarinen \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-165/) \| [podcast](https://www.podbean.com/media/share/pb-96zpk-12216e6)

### Demos

* **How to build a SSO bot using yo teams for Microsoft Teams** – for your SSO-based bot, start with yo Teams, an Azure bot service instance and an Azure AD App registration. In Azure add a new OAuth setting (Configuration), select API permissions, and Expose an API. Build your bot using yo teams, update Teams app manifest, etc. This bot starts by authenticating user – token from Azure AD or Teams, then calls Graph for user related information.
* **List formatting magic – Advance discussion board formatting with Power Automate** - using JSON formatting to transform out-of-box discussion board to next level discussion view. Add menu with support features (permission checker, default editing, comments & responses to post), add a custom discussion board timeline view, support information lookup (discussion answers list), and add voting with Emoji’s. leverages existing capabilities – SharePoint page, filter web parts, Microsoft Power Automate (declarative JSON for Flow), and Microsoft Teams.
* **List formatting magic – Taking advantage of new multi-lingual capabilities in list formatting** - jazz up percentage amounts in a column using a number level bar and then add a localizable textual interpretation to the amounts. Localize the text using the @lcid token (magic). Localizing text in a list side-steps complicated page translations and ensures users in various regions can use your formats without issue. Observe simplicity of copying JSON from sample into the column’s Advance mode formatting box.

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII)
(Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the
call.

{{< youtube SM_KlEcefcw >}}

## Agenda items

* PnP .NET library updates - [Bert Jansen](http://twitter.com/O365bert) (Microsoft) @O365bert – [6:24](https://www.youtube.com/watch?v=SM_KlEcefcw?t=384)
* PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Valo Intranet) \| @gautamdsheth – [8:11](https://www.youtube.com/watch?v=SM_KlEcefcw?t=491)
* yo Teams updates - [Wictor Wilén](http://twitter.com/wictor) (Microsoft) @wictor – [9:54](https://www.youtube.com/watch?v=SM_KlEcefcw?t=594)
* Microsoft Graph Toolkit updates - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [10:19](https://www.youtube.com/watch?v=SM_KlEcefcw?t=619)
* Microsoft Script Samples - [Paul Bullock](http://twitter.com/pkbullock) \| @pkbullock – [4:06](https://www.youtube.com/watch?v=SM_KlEcefcw?t=246)
* Microsoft Teams Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [11:04](https://www.youtube.com/watch?v=SM_KlEcefcw?t=664)
* Microsoft Power Platform Samples - [April Dunnam](http://twitter.com/aprildunnam) (Microsoft) \| @aprildunnam – [11:37](https://www.youtube.com/watch?v=SM_KlEcefcw?t=697)
* Demo - How to build a SSO bot using yo teams for Microsoft Teams – [Stephan Bisser](http://twitter.com/stephanbisser) (Solvion) \| @stephanbisser – [15:08](https://www.youtube.com/watch?v=SM_KlEcefcw?t=908)
* Demo - List formatting magic – Advance discussion board formatting with Power Automate – [André Lage](http://twitter.com/aaclage) (Datalynx AG) \| @aaclage – [26:24](https://www.youtube.com/watch?v=SM_KlEcefcw?t=1588)
* Demo - List formatting magic – Taking advantage of new multi-lingual capabilities in list formatting – [Chris Kent](http://twitter.com/theChrisKent) (DMI) \| @theChrisKent – [43:25](https://www.youtube.com/watch?v=SM_KlEcefcw?t=2628)

## Actions

* Opt into PnP Recognition Program \| <https://aka.ms/m365pnp-recognition>
* Register for [Microsoft Build](https://mybuild.microsoft.com/) \| May 24-26, 2022
* Join us at the next Microsoft 365 platform call on Tuesday, May 17, 8:00 am PT. [Invite](https://aka.ms/m365-dev-call)
* Register for Sharing is Caring Events:
    * Community Docs Session \| Tuesday, May 17, 10:00 am PT - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    * Power Platform Samples – First Time Contributor \| Monday, May 31, 9:30 am PT- [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN09VTVU2QzRLNE0yVERQMklHSDBMUTJGWC4u)
    * Maturity Model Practitioners \| [Register](https://aka.ms/mm4m365)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* What do you need from PnP Core SDK? Let us know and/or view the latest changes at [PnP Core SDK Changelog](https://github.com/pnp/pnpcore/blob/dev/src/sdk/CHANGELOG.md).
* PowerShell suggestions? Please visit [PnP.PowerShell Changelog](https://github.com/pnp/powershell/blob/dev/CHANGELOG.md)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Sign up to [Share your story](https://aka.ms/share-your-story) in the [Learn from the community](https://aka.ms/LearnFromTheCommunity/ThisWeek) series.
* Request a Demo spot on the call – <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call – <https://aka.ms/spdev-sig-call>

## Demo references

* **How to build an SSO bot using yo teams for Microsoft Teams**
    * Tool - [Microsoft Teams App Project Generator - \#YoTeams](https://github.com/pnp/generator-teams)
    * Documentation - [Single sign-on (SSO) with Microsoft Teams bots](https://docs.microsoft.com/learn/modules/msteams-sso/6-bots-sso)
    * Training - [SSO Teams Bot - Microsoft Teams App](https://github.com/OfficeDev/TrainingContent/tree/master/Teams/80%20Using%20Single%20Sign-On%20with%20Microsoft%20Teams/Demos/02-learn-msteams-sso-bot)
    * Documentation - [Single sign-on (SSO) support for bots](https://docs.microsoft.com/microsoftteams/platform/bots/how-to/authentication/auth-aad-sso-bots)
* **List formatting magic – Advance discussion board formatting with Power Automate**
    * Sample - [Discussion board format](https://github.com/pnp/List-Formatting/tree/master/view-samples/discussion-board-format)
    * Sample - [Calculator sample](https://github.com/pnp/List-Formatting/tree/master/column-samples/generic-calculator)
    * Sample - [Percent chart format](https://github.com/pnp/List-Formatting/tree/master/view-samples/percent-chart-format)
    * Samples - [List Formatting Samples](https://pnp.github.io/List-Formatting/) \| aka.ms/list-formatting
* **List formatting magic – Taking advantage of new multi-lingual capabilities in list formatting**
    * Sample - [Number Level Bar](https://github.com/pnp/List-Formatting/tree/master/column-samples/number-level-bar)
    * Sample – [Number Localization](https://github.com/pnp/List-Formatting/tree/master/column-samples/number-localization)
    * Sample – [Person Localization](https://github.com/pnp/List-Formatting/tree/master/column-samples/person-localization)
    * Samples - [List Formatting Samples](https://pnp.github.io/List-Formatting/) \| aka.ms/list-formatting

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)


## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.9.0 GA|Prepping for v1.10.0
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.6.0 GA|Prepping for v1.7.0
[Microsoft 365 Assessment tool](https://docs.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool                                     
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.10.0 GA|In progress: V2 POC - .NET 6.0 based, Requires PowerShell 7.2
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v3.5.0 GA,v4.0.0-preview.1
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.6.0 GA, v1.7.0-preview.2
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.1.0 GA, v1.2.0-preview.2
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

* Microsoft 365 platform call \| Tuesday, May 17, 8:00 am PT - <https://aka.ms/m365-dev-call> (weekly)
* Power Platform monthly call \| Wednesday, May 18, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, May 19, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, May 19, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* M365 General Dev call \| Thursday, May 26, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Office add-in monthly call \| Wednesday, June 8, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Adaptive Cards monthly call \| Thursday, June 9, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


_“Sharing is caring”_

_Microsoft 365 Community (PnP) team, Microsoft - 12th of May 2022_

{{< attachments >}}

