---
title: "Viva Connections & SharePoint Framework Community Call – 2nd of June, 2022"
date: 2022-06-03T02:00:00-05:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-2nd-june.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Demos: Building FAQs web part with Property Field Collection Data, Solve Teams and SharePoint Theme problems with the 'Enhanced Theme Provider' control, and Building custom list form components with SPFx v1.15. Released SPFx v1.15 (RC), 6 web part, 4 ACE samples."
videos:
- https://www.youtube.com/watch?v=XvZz75q8vag
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Agenda set for Microsoft 365 platform call - Tuesday, June 7, 8:00 am PT \| aka.ms/m365-dev-call
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * Monthly community contributors
    * **Zac Sun** - Migrate your SharePoint workflows to Power Automate with migration tooling (preview)
    * **Dan Wahlin** - Send a SMS message with Azure Communication Services
    * **Bob German** - TeamsJS SDK V2 to extend your Microsoft Teams solutions to Outlook and Office
* Project releases
    * [SharePoint Framework (SPFx)](https://aka.ms/spfx) - v1.15 (RC) – includes list and library form extensibility
    * [PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/) - v3.4.0 to be released June 10th
    * [PnP Modern Search](https://microsoft-search.github.io/pnp-modern-search/) - Adaptive Card support in the dev branch
* Web part samples
    * [Frequently Asked Questions with Property Field Collection Data](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-faqs) - [Arun Kumar Perumal](http://twitter.com/arun_perumal16) \| @arun_perumal16
    * [Pages Hierarchy](https://github.com/pnp/sp-dev-fx-webparts/blob/main/samples/react-page-navigator) - [Nick Brown](http://twitter.com/techienickb) \| @techienickb
    * [My Awards](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-graph-profile-awards/README.md) - [Luis Mañez](http://twitter.com/luismanez) \| @luismanez
    * [Filterable Image Gallery](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-image-gallery/README.md) - [Ari Gunawan](http://twitter.com/arigunawan3023) \| @arigunawan3023
    * [Page Navigator](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-page-navigator) - [Jasey Waegebaert](http://twitter.com/JWaegebaert) \| @JWaegebaert
    * [ACE Strategy Pattern](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/ace-strategy-pattern) - [Marcin Wojciechowski](http://twitter.com/mgwojciech) \| @mgwojciech
* ACE samples
    * Updated - [Office Locations](https://adoption.microsoft.com/sample-solution-gallery/pnp-sp-fx-aces-officelocations) – Image Card – [Nick Brown](http://twitter.com/techienickb) \| @techienickb
    * Updated - [Unread Emails](https://adoption.microsoft.com/sample-solution-gallery/pnp-sp-fx-aces-graph-unreademails) – Primary Text Card – [Nick Brown](http://twitter.com/techienickb) \| @techienickb
    * Updated - [My Calendar Plan](https://adoption.microsoft.com/sample-solution-gallery/pnp-sp-fx-aces-my-calendar) – Primary Text Card - [Nick Brown](http://twitter.com/techienickb) \| @techienickb
    * Updated - [News Feed](https://github.com/pnp/sp-dev-fx-aces/tree/main/samples/PrimaryTextCard-NewsFeed) – Primary Text Card - [Nick Brown](http://twitter.com/techienickb) \| @techienickb
* Microsoft 365 PnP Weekly – Episode 168 (May 30th) with Montréal based Sr Product Manager on the Microsoft Graph team [Sébastien Levert](http://twitter.com/sebastienlevert) \| @sebastienlevert \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-168/) \| [podcast](https://www.podbean.com/media/share/pb-yvgjv-123b062)
* Microsoft 365 PnP Weekly – Episode 167 (May 23rd) with Helsinki-based software engineer, PowerShell maintainer and Office Apps and Services MVP Gautam Sheth (Valo Solutions) \| @gautamdsheth. \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-167/) \| [podcast](https://www.podbean.com/media/share/pb-2jtm9-1232f34)

### Demos

* **Building Frequently Asked Questions web part with Property Field Collection Data** – configure the FAQ web part’s layout in property pane - select accordion or tab, colors and themes. Create categories and sort conditions. Use the rich text editor to easily answer questions. Uses Office UI Fabric Search Box - search by question, searched term highlighted in results. See code for the 2 components (FAQ and Accordion) in web part. Accordion is a custom component.
* **Solve Teams and SharePoint Theme problems with the "Enhanced Theme Provider" control for SPFx solutions** – introduction to the “Enhanced Theme Provider” control, what problem it solves (lack of support for Teams high contrast theme and basic styles), how it’s implemented, and how to use it in SPFx. Extends functionality of the Fluent UI ThemeProvider control by adding some logic and considered as a sort-of wrapper for all react and non-react controls that you want to add to the WebPart.
* **Getting started on building custom list form components with SPFx v1.15** – introducing a new component type in v1.15 called Form customizer. Enabling development of custom modern forms with custom edit experience. Delivering API level support for content types with 6 new properties for separately configuring new form, edit form and display form. Look at how to debug your form customizer and how form customizer will work in your production environment. Review List extensibility roadmap.

The host of this call is [Patrick Rodgers](http://twitter.com/mediocrebowler)
(Microsoft) \| @mediocrebowler. Q&A takes place as always in chat throughout the
call.

{{< youtube XvZz75q8vag >}}

## Agenda items

* SharePoint Framework - [Vesa Juvonen](http://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen – [6:19](https://youtu.be/XvZz75q8vag?t=379)
* PnPjs Client-Side Libraries - [Julie Turner](http://twitter.com/jfj1997) (Sympraxis Consulting) \| @jfj1997 – [9:04](https://youtu.be/XvZz75q8vag?t=544)
* CLI for Microsoft 365 - [Patrick Rodgers](http://twitter.com/mediocrebowler) (Microsoft) \| @mediocrebowler – [10:35](https://youtu.be/XvZz75q8vag?t=635)
* PnP SPFx Controls - [Patrick Rodgers](http://twitter.com/mediocrebowler) (Microsoft) \| @mediocrebowler – [11:15](https://youtu.be/XvZz75q8vag?t=675)
* PnP Modern Search - [Patrick Rodgers](http://twitter.com/mediocrebowler) (Microsoft) \| @mediocrebowler – [12:09](https://youtu.be/XvZz75q8vag?t=729)
* PnP Samples - [Hugo Bernier](http://twitter.com/bernierh) (Microsoft) \| @bernierh – [13:01](https://youtu.be/XvZz75q8vag?t=781)
* PnP SPFx ACEs Samples - [David Warner II](http://twitter.com/DavidWarnerII) (Microsoft) \| @DavidWarnerII – [15:10](https://youtu.be/XvZz75q8vag?t=910)
* Demo - Building Frequently Asked Questions web part with Property Field Collection Data – [Arun Kumar Perumal](http://twitter.com/arun_perumal16) \| @arun_perumal16 – [17:08](https://youtu.be/XvZz75q8vag?t=1028)
* Demo - Solve Teams and SharePoint Theme problems with the "Enhanced Theme Provider" control for SPFx solutions – [Fabio Franzini](http://twitter.com/franzinifabio) (Apvee Solutions) \| @franzinifabio – [25:58](https://youtu.be/XvZz75q8vag?t=1558)
* Demo - Getting started on building custom list form components with SPFx v1.15 – [Alex Terentiev](http://twitter.com/alexaterentiev) (Microsoft) \| @alexaterentiev & [Vesa Juvonen](http://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen – [36:40](https://youtu.be/XvZz75q8vag?t=2200)


## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Writing for the Web \| Thursday, June 23, 12pm PT \| 3pm ET \| 9pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Writing for the Web \| Monday, June 27, 10am PT \| 1pm ET \| 7pm CET - [Register](https://forms.microsoft.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQkYwOVhZTkg3Rk9TVUI3NlA4R0Y0RTFSTy4u)
    * Maturity Model Practitioners \| [Register](https://aka.ms/mm4m365)
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Sign up to [Share your story](https://aka.ms/share-your-story) in the [Learn from the community](https://aka.ms/LearnFromTheCommunity/ThisWeek) series.
* Request a Demo spot on the call \| <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call \| <https://aka.ms/spdev-spfx-call>

## Demo references

* **Building Frequently Asked Questions web part with Property Field Collection**
    * Sample - [Frequently Asked Questions with Property Field Collection Data](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-faqs)
    * Article - [Community Sample: React FAQs webpart](https://pnp.github.io/blog/post/community-sample-faqs-with-propertyfieldcollectiondata/)
* **Solve Teams and SharePoint Theme problems with the "Enhanced Theme Provider" control for SPFx solutions**
    * Documentation – [Build Microsoft Teams tab using SharePoint Framework – Tutorial](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/using-web-part-as-ms-teams-tab)
    * Documentation - [Isolated web parts](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/isolated-web-parts)
    * npm Tools - [@fluentui/react-theme-provider](https://www.npmjs.com/package/@fluentui/react-theme-provider)
* **Getting started on building custom list form components with SPFx v1.15**
    * Documentation - [SharePoint Framework v1.15 preview release notes](https://docs.microsoft.com/sharepoint/dev/spfx/release-1.15)
    * Documentation - [Build your first Form Customizer extension (preview)](https://docs.microsoft.com/sharepoint/dev/spfx/extensions/get-started/building-form-customizer)
    * Control - [Dynamic Form](https://pnp.github.io/sp-dev-fx-controls-react/controls/DynamicForm/)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
SharePoint Framework (SPFx)|v1.14 GA, v1.15 RC|v1.15 GA in June 2022, v1.16 Beta in July
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v2.13 GA, v3.3.2 GA|v3.4.0 to be released June 10th, Nightly builds.
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v4.3.0 GA, v5.3.0 beta|
[Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)|v3.8.0, v2.9.0 (SPFx v1.11)|
[Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls)|v3.7.0, v2.7.0 (SPFx v1.11)|
[PnP SPFx Generator](https://github.com/pnp/generator-spfx)|v1.16.0|v1.17.0 on the way
[PnP Modern Search](https://microsoft-search.github.io/pnp-modern-search/)|v4.6.1, v3.23.0|Adaptive Card support in the dev branch


## General Resources

*   Viva Connections [https://aka.ms/VivaConnections](https://aka.ms/VivaConnections)
*   Archives - Microsoft 365 PnP Weekly - [Videos](https://www.youtube.com/playlist?list=PLR9nK3mnD-OVYI-St_CBiFfuL4CZbBpkC), [Podcasts](https://pnpweekly.podbean.com/)  
*   Tools - [Teams Toolkit (v2.2 Preview)](https://aka.ms/teams-toolkit) 
*   Tools - [Microsoft Teams Framework (TeamsFx)](https://github.com/officedev/teamsfx) 
*   Gallery - [Microsoft 365 Extensibility look book gallery](https://aka.ms/m365/extensibility)   
*   [Microsoft Build sessions guide](https://aka.ms/modernworkbuildsessions) (Modern Work Digital Brochure) - aka.ms/modernworkbuildsessions
*   SharePoint Framework - v1.12.1 npm install –g @microsoft/generator-sharepoint@next
*   [CLI for Microsoft 365 v3](https://developer.microsoft.com/office/blogs/cli-microsoft-365-3/)
*   [CodeTour](https://aka.ms/codetour)
*   [Sharing is Caring](https://aka.ms/sharing-is-caring) | aka.ms/sharing-is-caring
*   [Tools -](https://aka.ms/pnp-search) [PnP Modern Search v4](https://microsoft-search.github.io/pnp-modern-search/)  [|](https://aka.ms/pnp-search) [https://aka.ms/pnp-search](https://aka.ms/pnp-search)
*   [M365 PnP site](https://aka.ms/m365pnp) | aka.ms/m365pnp
*   [SharePoint Starter Kit v2](https://github.com/pnp/sp-starter-kit/tree/v2)
*   Blog: "[A Lap Around Microsoft Graph Toolkit" blog series](https://aka.ms/mgtLap)
*   [New Microsoft 365 Patterns and Practices (PnP) team model with new community leads](https://developer.microsoft.com/microsoft-365/blogs/new-microsoft-365-patterns-and-practices-pnp-team-model-with-new-community-leads/)
*   [Microsoft 365 Community Content](https://aka.ms/m365-community-docs) (non-Dev docs)
*   [PnP SPFx web part samples](https://aka.ms/spfx-webparts)
*   [PnP SPFx extension samples](https://aka.ms/spfx-extensions)
*   [GitHub PnPjs](https://github.com/pnp/pnpjs/)
*   Tutorials - [Getting started with SharePoint Framework v1.10 Tutorials](https://www.youtube.com/playlist?list=PLR9nK3mnD-OXvSWvS2zglCzz4iplhVrKq) (12 videos)
*   Tutorials - [Getting started with SharePoint Framework v1.10 Extensions](https://www.youtube.com/playlist?list=PLR9nK3mnD-OXtWO5AIIr7nCR3sWutACpV) (6 videos)
*   Docs - [Tutorials and training material for SharePoint Development](https://docs.microsoft.com/sharepoint/dev/training/training/?wt.mc_id=YT_CCrecording)
*   [SPFX Training Package](https://aka.ms/spfx-training)
*   [SPFx Web Parts](https://aka.ms/spfx-webparts)
*   [SPFx Extensions](https://aka.ms/spfx-extensions)
*   [SPFx Library Components](https://aka.ms/spfx-library-components)
*   Documentation - [PnPjs v2 documentation](https://pnp.github.io/pnpjs/)
*   Link - [Microsoft 365 developer training](https://aka.ms/M365DevTraining)
*   Link - [Office 365 Developer Program](https://aka.ms/O365DevProgram)
*   [Latest documentation on SharePoint Framework](https://aka.ms/spdev-docs)
*   Found an issue with SharePoint Dev? - please let us know at [https://aka.ms/spdev-issues](https://aka.ms/spdev-issues)
*   [Reusable web part property controls](https://sharepoint.github.io/sp-dev-fx-property-controls/)
*   [Reusable react controls for SharePoint Framework solutions](https://sharepoint.github.io/sp-dev-fx-controls-react/)
*   [Reusable controls webcast](https://devblogs.microsoft.com/microsoft365dev/webcast-reusable-controls-for-your-sharepoint-framework-solutions/)
*   [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365)
*   [PnP SPFx Yeoman Generator](https://github.com/pnp/generator-spfx) \- Extends the out-of-the-box experience with open-source community capabilities
*   [SharePoint Dev UserVoice](https://aka.ms/spdev-uservoice) \- for new feature requests

## Other mentioned topics

*   [SharePoint dev documentation](https://docs.microsoft.com/sharepoint/dev/)
*   [SharePoint dev issue list](https://github.com/SharePoint/sp-dev-docs/issues)

## Upcoming calls | Recurrent invites

* Microsoft 365 platform call \| Tuesday, June 7, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Office add-in monthly call \| Wednesday, June 8, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* M365 General Dev call \| Thursday, June 9, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Adaptive Cards monthly call \| Thursday, June 9, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Power Platform monthly call \| Wednesday, June 15, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Viva Connections & SharePoint Framework call \| Thursday, June 16, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Microsoft Identity Platform call \| Thursday, June 16, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

## About

Viva Connections & SharePoint Framework bi-weekly calls are targeted at anyone who is interested in the JavaScript-based development towards Microsoft Connections, Microsoft Teams, SharePoint Online, and also on-premises. Calls are used for the following objectives.

*   SharePoint Framework engineering update from Microsoft
*   Talk about PnP JavaScript Core libraries
*   CLI for Microsoft 365 Updates
*   SPFx reusable controls
*   PnP SPFx Yeoman generator
*   Share code samples and best practices
*   Possible engineering asks for the field - input, feedback, and suggestions
*   Cover any open questions on the client-side development
*   Demonstrate SharePoint Framework in practice in Microsoft Viva, Microsoft Teams or SharePoint context
*   You can download a recurrent invite from [https://aka.ms/spdev-spfx-call](https://aka.ms/spdev-spfx-call). Welcome and join the discussion!


*“Sharing is caring”*

* * *

*Microsoft 365 PnP team, Microsoft - 3rd of June 2022*

{{< attachments >}}
