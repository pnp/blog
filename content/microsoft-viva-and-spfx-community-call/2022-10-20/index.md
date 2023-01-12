---
title: "Viva Connections & SharePoint Framework Community Call – 20th of October, 2022"
date: 2022-10-20T02:00:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/recording-20th-october.png
tags: ["SPFx Adaptive Card Extensions", "Office Add-ins", "SPFx Extensions", "Microsoft 365", "Microsoft Graph", "Microsoft Teams", "SharePoint", "SharePoint Framework (SPFx)", "Viva Connections"]
type: "regular"
summary: "Two demos: Copy Views SharePoint Framework Web Part and Using the Azure AD on-behalf-of flow within your SharePoint Framework solution. Project releases for PnPjs Client-Side Libraries and CLI for Microsoft 365. Announced extending SPFx solutions to Outlook and Office.com."
videos:
- https://www.youtube.com/watch?v=aV9I6XTzd0M
draft: false
---

## Call summary

Welcome to the bi-weekly call focused on Microsoft 365 client-side development.  In this call, we focus on using Viva Connections and SharePoint Framework to build solutions for Microsoft Teams and SharePoint Online.

### New this week

* Agenda set for next [Microsoft 365 platform call](https://aka.ms/m365-dev-call) - Tuesday, October 25th, 8:00 am PT.
    * Latest news from Microsoft engineering on Microsoft 365 topics
    * Monthly community contributors
    * **Sheena Makker** – Extend Microsoft Teams apps to Office and Outlook Mobile
    * **Hugo Bernier** – Power Pages – General Availability
    * **Vesa Juvonen** & **Alex Terentiev** - Using your SPFx solutions also at Microsoft Teams, Outlook and Office.com
* Announced
    * [Extending your SharePoint Framework (SPFx) solutions also to Outlook and Office.com](https://www.youtube.com/watch?v=UZensJzonbw) \| aka.ms/spfx-ignite2022
* Project releases
    * [PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/) – v3.8 (GA)
    * [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/about/release-notes/#v580) – v5.9.0 (beta)
* Conversations
    * Microsoft 365 PnP Weekly – Episode 183 (October 17th) with Italy based Solution Architect [Paolo Pialorsi](https://twitter.com/paolopia) (PiaSys) \| @paolopia \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-183/) \| [podcast](https://www.podbean.com/media/share/pb-xzpj6-12ee995)
    * Microsoft 365 PnP Weekly – Episode 182 (October 10th) with Netherlands based Microsoft 365 Architect [Martin Lingstuyl](https://twitter.com/martinlingstuyl) (I4-YOU Business Solutions) \| @martinlingstuyl \| [video](https://pnp.github.io/blog/microsoft-365-pnp-weekly/episode-182/) \| [podcast](https://www.podbean.com/media/share/pb-6kawv-12e502f)

### Demos

* **Copy Views SharePoint Framework Web Part** – copy views from one list/library to another using either the new web part or extension. Copy columns, sorting, group by, view formatting and filtering. Web part displayed on specific site/page for view management purposes. Extension is a dialog opened by ListView Command set extension on any list/library - tenant wide or site scoped. Code - see component structure and PnPjs copy functionality.
* **Using the Azure AD on-behalf-of flow within your SharePoint Framework solution** – overview of On-Behalf-Of (OBO) flow, tokens, permissions and use in SharePoint Framework. OBO is great for when you need a background task running (in middleware that needs to consume another back-end service like Microsoft Graph) on-behalf-of a user that triggers the middleware from a SharePoint Framework app. 2 OBO scenarios shown - get my personal data via OBO and send Teams chat message via OBO.

The host of this call is [Garry Trinder](https://twitter.com/garrytrinder) (Microsoft) \| @garrytrinder. Q&A takes place as always in chat throughout the call.

{{< youtube aV9I6XTzd0M >}}

## Agenda items

* SharePoint Framework – [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft) \| @vesajuvonen – [6:28](https://youtu.be/aV9I6XTzd0M?t=388)
* PnPjs Client-Side Libraries - [Julie Turner](http://twitter.com/jfj1997) (Sympraxis Consulting) \| @jfj1997 – [9:29](https://youtu.be/aV9I6XTzd0M?t=569)
* CLI for Microsoft 365 - [Garry Trinder](https://twitter.com/garrytrinder) (CPS Solutions) \| @garrytrinder – [11:14](https://youtu.be/aV9I6XTzd0M?t=674)
* PnP SPFx Controls - [Alex Terentiev](https://twitter.com/alexaterentiev) (Microsoft) \| @alexaterentiev – [13:24](https://youtu.be/aV9I6XTzd0M?t=804)
* PnP Modern Search - [Garry Trinder](https://twitter.com/garrytrinder) (CPS Solutions) \| @garrytrinder – [13:55](https://youtu.be/aV9I6XTzd0M?t=835)
* PnP Samples - [Garry Trinder](https://twitter.com/garrytrinder) (CPS Solutions) \| @garrytrinder – [14:24](https://youtu.be/aV9I6XTzd0M?t=864)
* Demo – Copy Views SharePoint Framework Web Part – [Martin Lingstuyl](https://twitter.com/martinlingstuyl) (I4-YOU) \| @martinlingstuyl – [16:21](https://youtu.be/aV9I6XTzd0M?t=981)
* Using the Azure AD on-behalf-of flow within your SharePoint Framework solution – [Paolo Pialorsi](https://twitter.com/PaoloPia) (PiaSys) \| @PaoloPia – [30:03](https://youtu.be/aV9I6XTzd0M?t=1803)

## Together Mode

![together-221020.png](images/together-221020.png)

Thank you everyone for joining and being part of this community. It’s really great to have you on the call. Please keep the feedback coming.

## Actions

* Opt into the [PnP Recognition Program](https://aka.ms/m365pnp-recognition) \| aka.ms/m365pnp-recognition
* Register for upcoming [Sharing is Caring](https://pnp.github.io/sharing-is-caring/) events:
    * Maturity Model Practitioners \| Tuesday, November 15th, 7am PST – [Download reoccurring invite](https://aka.ms/mm4m365/invite).
    * PnP Office Hours – 1:1 session \| [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    * PnP Buddy System \| [Request a Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities.
* Visit the [Microsoft 365 Unified Sample Solution Gallery](https://adoption.microsoft.com/sample-solution-gallery) from Microsoft and community.
* Request a Demo spot on the call \| <https://aka.ms/m365pnp/request/demo>
* Download the recurrent invite for this call \| <https://aka.ms/spdev-spfx-call>

## Demo references

* **Copy Views SharePoint Framework Web Part**
    * Sample – [react-copy-views](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-copy-views)
    * Library – [PnPjs - @pnp/sp/views](https://pnp.github.io/pnpjs/sp/views/)
    * Documentation – [DOMParser](https://developer.mozilla.org/docs/Web/API/DOMParser)
* **Using the Azure AD on-behalf-of flow within your SharePoint Framework solution**
    * Documentation - [Microsoft identity platform and OAuth 2.0 On-Behalf-Of flow](https://learn.microsoft.com/azure/active-directory/develop/v2-oauth2-on-behalf-of-flow)
    * Sample - [SPFx On-Behalf-Of flow](https://adoption.microsoft.com/sample-solution-gallery/sample/pnp-spfx-reference-scenarios-spfx-obo/)

Thank you for your great work. Samples are often showcased in Demos.

## Open-source project status

**PnP Project**|**Current version**|**Release/Status**
---|---|---
[SharePoint Framework (SPFx)](https://aka.ms/spfx)|v1.15.2 GA, v1.16 (Preview)|v1.16 (GA) planned in November 2022, v1.17 Preview December/January
[PnPjs Client-Side Libraries](https://pnp.github.io/pnpjs/)|v3.8.0 GA, v2.13 GA|
[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)|v4.3.0 GA, v5.8.0 GA, v5.9.0 (beta)|v6.0.0 ETA November 2022
[Reusable SPFx React Controls](https://github.com/pnp/sp-dev-fx-controls-react)|v3.11.0, v2.9.0 (SPFx v1.11)|new version in 2 weeks
[Reusable SPFx React Property Controls](https://github.com/pnp/sp-dev-fx-property-controls)|v3.10.0, v2.7.0 (SPFx v1.11)|new version in 2 weeks
[PnP SPFx Generator](https://github.com/pnp/generator-spfx)|v1.16.0|v1.17.0 on the way
[PnP Modern Search](https://microsoft-search.github.io/pnp-modern-search/)|v4.7.0 (GA), v4.8.0 (beta), v3.23.0 (GA)|


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

* Microsoft 365 platform call \| Tuesday, October 25, 8:00 am PT – <https://aka.ms/m365-dev-call> (weekly)
* Microsoft 365 General Dev call \| Thursday, October 27, 7:00 am PT - <https://aka.ms/m365-dev-sig> (bi-weekly)
* Viva Connections & SharePoint Framework call \| Thursday, November 3, 7:00 am PT - <https://aka.ms/spdev-spfx-call> (bi-weekly)
* Office add-in monthly call \| Wednesday, November 9, 8:00 am PT - <https://aka.ms/officeaddinscall> (monthly)
* Adaptive Cards monthly call \| Thursday, November 10, 9:00 am PT - <https://aka.ms/adaptivecardscommunitycall> (monthly)
* Power Platform monthly call \| Wednesday, November 16, 8:00 am PT - <https://aka.ms/PowerAppsMonthlyCall> (monthly)
* Microsoft Identity Platform call \| Thursday, November 17, 9:00 am PT - <https://aka.ms/IDDevCommunityCalendar> (monthly)

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

*Microsoft 365 PnP team, Microsoft - 20th of October 2022*

{{< attachments >}}
