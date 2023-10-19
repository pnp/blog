---
title: "Microsoft 365 & Power Platform Development Community call - 8th of December, 2022"
date: 2022-12-08T02:02:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-8th-december.png
tags: []
type: "regular"
summary: "Demos: How to create or migrate SharePoint pages with Microsoft Graph API and Power Automate and List Formatting Magic – inlineEditField and setValue for making list fields editable. Released Microsoft Graph Toolkit (MGT) – v2.8.0 GA plus 14 samples!"
videos:
- https://www.youtube.com/watch?v=rIVhgzoqBbk
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 platform development topics. In this call, we focus on Microsoft Teams, Microsoft Graph, Power Platform, SharePoint, Microsoft Lists with topics ranging from development tools to list and column formatting, to site design and provisioning, and more.

### New this week

* Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, December 13th, 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * **Patrick Rodgers** – Using dynamic SVG images with Viva ACEs for business charts
    * **Sreekanth Thirthala Venkata** & **Yan Jin** - Introduction to Microsoft 365 App Compliance Automation tool
    * **Sébastien Levert** - Introduction to Microsoft Graph Developer Proxy
* Project releases
    * [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit) – v2.8.0 GA
* Power Platform - [Independent Publisher Connectors](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors) submissions
    * New – GitHub Gists – [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * New – Tumblr – [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * New – [Today in History](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Today%20in%20History) – [Troy Taylor](https://twitter.com/troystaylor) \| @troystaylor
    * New – [Google Photos](https://github.com/juliamuiruri4/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Google%20Photos) – [Julia Muiruri](https://twitter.com/juliamuiruri4) \| @juliamuiruri4
    * New – QuickBooks – Artesian Software
    * New – Time – Artesian Software
    * New – eBay – Artesian Software
    * New – Google BigQuery – [Ashwani Kumar](https://github.com/ashwanidv100)
    * New – [Microsoft Learn Catalog](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/Microsoft%20Learn%20Catalog) – [Sean Kelly](https://github.com/SeanKe11y)
    * New – [Snowflake](https://learn.microsoft.com/connectors/snowflakeip/) – [Rene Koch](https://github.com/rekodus)
    * [Top Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
    * Good Flow story? Tell us. [FlowOfTheWeek](https://aka.ms/FlowOfTheWeekForm) – aka.ms/FlowOfTheWeekForm
* [Script samples](https://pnp.github.io/script-samples/)
    * New - PnP PowerShell – [Remove modern web parts from pages](https://pnp.github.io/script-samples/spo-remove-webpart-from-pages/README.html?tabs=pnpps) - [Ramin Ahmadi](https://twitter.com/raminahmadi1986) \| @raminahmadi1986
    * New - PnP PowerShell – [Create a multi-hub set of communication sites](https://pnp.github.io/script-samples/spo-create-multi-hub-sites/README.html?tabs=pnpps) - [Paul Bullock](https://twitter.com/pkbullock) \| @pkbullock
    * Updated - PnP PowerShell – [Activate a site feature in SharePoint online](https://pnp.github.io/script-samples/spo-activate-site-feature/README.html?tabs=pnpps) - [Dan Toft](https://twitter.com/tanddant) \| @tanddant
    * [Good first issue asks](https://github.com/pnp/script-samples)
* [Microsoft Teams samples](https://pnp.github.io/teams-dev-samples/)
    * [Meeting tab that records names so everyone can pronounce them properly](https://github.com/pnp/teams-dev-samples/tree/main/samples/tab-meeting-record-name) - [Markus Moeller](https://twitter.com/moeller2_0) \| @moeller2_0
    * Wanted – Updated Microsoft Teams JavaScript samples using Teams SDK v2 \| [Microsoft Teams Development Samples](https://pnp.github.io/teams-dev-samples/) \| aka.ms/Teams-Samples
* Conversations
    * Microsoft 365 PnP Weekly – Episode 190 (December 5th) with Germany based developer, architect, business owner, Microsoft MVP, and regional conference event coordinator Adis Jugo \| @adisjugo \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-190/) \| [podcast](https://www.podbean.com/media/share/pb-bfn9g-1330430)
    * Microsoft 365 PnP Weekly – Episode 189 (November 28th) with UK based Microsoft 365 Apps & Services MVP [Brett Lonsdale](https://twitter.com/brettlonsdale) (Lightning Tools) \| @brettlonsdale \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-188/) \| [podcast](https://www.podbean.com/media/share/pb-y67zr-1327137)

### Demos

* **How to create or migrate SharePoint pages with Microsoft Graph API and Power Automate** – new beta capabilities in Graph API targeting SharePoint pages include List, Create, Get, Update, Delete, Publish, Horizontal section, Vertical section, Web part. The new capabilities allow users to migrate the full canvas of SharePoint pages across sites and tenants. Step through a Flow action to GET an existing page and another action to POST a new page in existing site. Page content is a JSON payload.
* **List Formatting Magic – inlineEditField and setValue for making list fields editable** – for most unformatted/basic columns you can slap the inlineEditField: @currentField on existing formats to make the column editable (click and change). For formatted columns or columns with multi-value formatting, use setValue with actionInput and displayValue to accomplish inline editing capability. See how Chris draws from samples - 48 Inline Editing samples, found in the PnP Samples repo to accomplish the objective.

The host of this call was [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII. Q&A takes place in chat throughout the call.

{{< youtube rIVhgzoqBbk >}}

## Agenda items

* [05:45](https://youtu.be/rIVhgzoqBbk?t=345) – PnP .NET library updates - [Bert Jansen](http://twitter.com/O365bert) (Microsoft) @O365bert
* [07:25](https://youtu.be/rIVhgzoqBbk?t=445) – PnP PowerShell updates - [Gautam Sheth](http://twitter.com/gautamdsheth) (Valo Intranet) \| @gautamdsheth
* [09:27](https://youtu.be/rIVhgzoqBbk?t=567) – yo Teams updates - [Rick Van Rousselt](http://twitter.com/rickvanrousselt) (Advantive) \| @rickvanrousselt
* [10:17](https://youtu.be/rIVhgzoqBbk?t=617) – Microsoft Teams Toolkit updates – [John Miller](https://twitter.com/jmillerdev) (Microsoft) \| @jmillerdev
* [11:43](https://youtu.be/rIVhgzoqBbk?t=703) – Microsoft Graph Toolkit updates - [Sébastien Levert](http://twitter.com/sebastienlevert) (Microsoft) \| @sebastienlevert
* [13:25](https://youtu.be/rIVhgzoqBbk?t=805) – Independent Publisher Connectors - [Jocelyn Panchal](https://twitter.com/JocelynP_PM) (Microsoft) \| @JocelynP_PM
* [15:28](https://youtu.be/rIVhgzoqBbk?t=928) – Microsoft Script Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII
* [16:09](https://youtu.be/rIVhgzoqBbk?t=969) – Microsoft Teams Samples – [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII
* [16:42](https://youtu.be/rIVhgzoqBbk?t=1002) – Microsoft Power Platform Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII
* [17:04](https://youtu.be/rIVhgzoqBbk?t=1024) – Together mode picture
* [17:56](https://youtu.be/rIVhgzoqBbk?t=1076) – Demo – How to create or migrate SharePoint pages with Microsoft Graph API and Power Automate – [Giuliano De Luca](https://twitter.com/DeLucaGiulian) \| @DeLucaGiulian
* [26:32](https://youtu.be/rIVhgzoqBbk?t=1592) – Demo – List Formatting Magic – inlineEditField and setValue for making list fields editable – [Chris Kent](https://twitter.com/thechriskent) (DMI) \| @thechriskent

## Together Mode

![together-221208.png](images/together-221208.png)

The excitement is real. We’ve maxed the number of attendees in this photo! Awesome to see everybody in the v-room. Thank you for joining the call today and for keeping the feedback coming.

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Do you have a cool flow? Tell us about it so we can write about it. \#FlowOfTheWeek aka.ms/FlowOfTheWeekForm
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Maturity Model Practitioners \| Tuesday, December 20th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite)
    * Power Platform Samples Contributor \| Tuesday, January 10th, 10:30am PST \| [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN0hMNTRPWVVWTkhFTk9QQzhFSTRIS1JLSC4u)
    * First Time Contributor \| Thursday, January 12th, 10am PT \| 1pm ET \| 7pm CET – [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNjAwRVNETlA1MkxIR1MyTEs5STZFVVRJMC4u)
    * Writing for the Web \| Monday, January 23rd, 10am PT \| 1pm ET \| 7:00pm CET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMFNPNFMyUk9CNFROUjJWTFFGSzdJV0czVC4u)
    * PnP SPFx Samples w/ NVM \| Wednesday, January 25th, 9am PT \| 12pm ET - [Register](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNEE2SUdTOU1UOEtCTFU3MlM1SERDMlNVNi4u)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* What key scenarios are missing from the PnP Core SDK? Let us know and/or view the latest changes at [PnP Core SDK Changelog](https://github.com/pnp/pnpcore/blob/dev/src/sdk/CHANGELOG.md).
* PowerShell – The team is thinking of dropping support for PS 5, any strong objections? Suggestions in general? Please visit [PnP.PowerShell Changelog](https://github.com/pnp/powershell/blob/dev/CHANGELOG.md)
* Ideas for Microsoft Lists? aka.ms/Feedback/Lists
* Suggestions for yo teams? [Discussions](https://github.com/pnp/generator-teams/discussions)
* Create a connector – [Top Power Platform Independent Publisher Connector Asks](https://github.com/microsoft/PowerPlatformConnectors/wiki/Top-Connector-Asks)
* Wish list for [Microsoft Teams](https://github.com/pnp/teams-dev-samples/issues/new/choose)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Request a Demo spot on the call – <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call – <http://aka.ms/spdev-sig-call>

## Demo references

* **How to create or migrate SharePoint pages with Microsoft Graph API and Power Automate**
    * Article - [Announcing the new SharePoint Pages API in Microsoft Graph](https://devblogs.microsoft.com/microsoft365dev/announcing-the-new-sharepoint-pages-api-in-microsoft-graph/)
    * Documentation - [sitePage resource type](https://learn.microsoft.com/graph/api/resources/sitepage?view=graph-rest-beta)
    * Demo - [How to create or migrate SharePoint pages with Microsoft Graph API](https://www.youtube.com/watch?v=Pop7N2ThEDc)
    * YouTube Channel - [Giuliano De Luca](https://www.youtube.com/giulianodeluca)
* **List Formatting Magic – inlineEditField and setValue for making list fields editable**
    * Repo – [PnP List Formatting](https://github.com/pnp/List-Formatting)
    * Library – [Flicon](https://flicon.io/) (Fluent UI icon search)
    * Sample - [Multi-Person Facepile](https://github.com/pnp/List-Formatting/tree/master/column-samples/multi-person-facepile)
    * Sample - [Person Hover Card](https://github.com/pnp/List-Formatting/tree/master/column-samples/person-hover-card)

Thank you for your great work. Samples are often showcased in Demos. Request a Demo spot on the call [https://aka.ms/m365pnp/request/demo](https://aka.ms/m365pnp/request/demo)

## Open-source project status

**Project**|**Current Version**|**Release/Status**
---|---|---
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)|v1.11.0 GA|
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.8.0 GA|
[Microsoft 365 Assessment tool](https://docs.microsoft.com/assessments/)|v1.0.0 (SharePoint Syntex Assessment)|Successor to the Modernization Scanner tool
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.12.0 GA|Prepping v1.12.0 coming soon.  Nightly builds
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v4.0.1 GA|
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.8.0 GA
[Yo teams – yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.2.0 GA
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1 GA
[Microsoft Teams Toolkit](https://github.com/OfficeDev/TeamsFx)|v4.1.3 GA (VS Code), v17.4 (VS)|New builds daily
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.8.0 GA

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

* Microsoft 365 platform call \| Tuesday, December 13, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Office add-in monthly call \| Wednesday, December 14, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, December 15, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, December 15, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)
* Power Platform monthly call \| Wednesday, December 21, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft 365 General Dev call - **(Coffee & Tea with Community)** \| Thursday, December 22, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)

## About

Microsoft 365 Development Community bi-weekly calls are targeted at anyone who's interested in the general Microsoft 365 development topics. This includes Microsoft Teams, Bots, Microsoft Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core, Site Designs, Power Automate, Power Apps, Column Formatting, List formatting, etc. topics. More details on the Microsoft 365 community from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome community demos, if you are interested in doing a live demo in these calls!

You can download recurrent invite from [https://aka.ms/m365-dev-sig](https://aka.ms/m365-dev-sig). Welcome and join in the discussion. If you have any questions, comments, or feedback, feel free to provide your input as comments below this post as well. More details on the Microsoft 365 community and options to get involved are available from [https://aka.ms/m365pnp](https://aka.ms/m365pnp).


*“Sharing is caring”*

*Microsoft 365 Community (PnP) team, Microsoft - 8th of December 2022*

{{< attachments >}}{{< /attachments >}}
