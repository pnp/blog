---
title: "Microsoft 365 Developer Community Call recording -- 1st of April, 2021"
date: 2021-04-02T06:27:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/sig-1st-april-recording.png
tags: []
type: "regular"
---

Recording of the Microsoft 365 -- General M365 development Special
Interest Group (SIG) community call from April 1, 2021.


## Call summary



Latest news from Microsoft 365 engineering and updates on open-source
projects: PnP .NET libraries, PnP PowerShell, modernization tooling, on
yo Teams, on Microsoft Graph Toolkit, and on Microsoft Teams Samples.
An update on **SharePoint Framework** v1.12.1 release plan.  Recent PnP
project releases include - **PnP .NET Libraries** - **PnP Framework**
v1.4.0 and **PnP Core SDK** v1.1.0 and **PnP PowerShell** v1.5.0 (new
commandlets for Microsoft Viva Connections and Syntex).   **yo Teams**
***generator-teams*** (apps generator) v3.0.3 GA and 3.1.0 Preview,
***yo teams-build-core*** (gulp tasks) v1.0.1 + v1.1.0 Preview, and
***msteams-react-base-component*** (React UI helpers) v3.1.0, have been
released.   **Microsoft Graph Toolkit** in the works MSAL 2.0 provider
and preview of OneDrive file components.  Delivered 1 new Microsoft
Teams sample -- the first SPFx Teams Meeting sample from the community! 
Register now for March/April trainings on
[Sharing-is-caring](https://pnp.github.io/sharing-is-caring/). 
 [Register to join fellow community
members](https://aka.ms/pnpwatchparty) to watch the 2-hour livestream -
Building Apps with Microsoft Graph, on the 14th of April. The host of
this call was [Vesa Juvonen](https://twitter.com/vesajuvonen) (Microsoft)
| @vesajuvonen.  Q&A takes place in chat throughout the call

## Actions

-   Register for both:

    -   Register to watch the Microsoft Graph livestream with your
        community at:  <https://aka.ms/pnpwatchparty>
    -   RSVP to attend the 2-hour livestream -- Building Apps for with
        Microsoft Graph.  2 sessions -- 2:00pm AEST (Asia Pacific
        Region) and 8:30am PDT (North America & Europe Regions) |
        <https://aka.ms/learntogether-graph>
-   Complete the Developer Success Survey -
    <https://aka.ms/developersuccess>
-   Join the M365 customer success platform panel -
    <https://aka.ms/SuccessPanel>
-   Register for Sharing is Caring Events:
    -   PnP Office Hours -- 1:1 session -
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    -   Maturity Model Practitioners -- [April
        20th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    -   More than Code with VSCode -- [April 14th &
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
    -   First Time Presenter - [April 7th &
        21st](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   PnP -- AMA (Ask Me Anything) -- CLI for Microsoft 365 Edition --
        [April
        13th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [April 8th &
        15th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   PnP -- SPFx Developer Workstation Setup -- [April
        29th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
    -   Community Docs Session
        -- [April](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    -   First Time Contributor Session -- [April 6th &
        27th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)  
        (EMEA, APAC & US friendly times available)
-   Download the recurrent invite for this call
    -- <https://aka.ms/m365-dev-sig>
-   Call attention to your great work by using
    the [#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click) on
    Twitter.
**Microsoft Teams Development
Samples:  **(<https://aka.ms/TeamsSampleBrowser>)

-   [**Questionnaire Teams Meeting
    App**](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-teams-meeting-app-questionnaire) -
    [Nanddeep Nachan](https://twitter.com/NanddeepNachan) |
    [nanddeepn](https://github.com/nanddeepn), Ravi
    Kulkarni, and Smita Nachan
 

## Demos


Demos delivered in this session

-   **List group header formatting options** -- new list formatting
    options in JSON using use groupProps for Group header and footer
    formatters.  Conditional formatting - colors, counts, icons, for all
    list items now available for groups of list items.  Formatting
    capabilities in both list and gallery views.  There are new tokens
    for group headers and footers.   Copy and paste code chunks from
    docs.microsoft.com into Format View pane.    

-   **Introduction to PnP Core SDK - Getting started** -- see how PnP
    Core works and how a mixture of APIs -- Microsoft Graph GA and Beta,
    Rest, CSOM, Microsoft Teams, are called behind the scenes,
    transparent to developer.  Create basic .NET console application,
    add NuGet, PnP.Core and/or PnP.Core.Auth and
    Microsoft.Injection.Hosting packages, minimum code.  Add more code
    to get data.  Create list, add items, query the data, update data
    and delete list.  

-   **Customer scenario -- Microsoft Teams integration with external
    systems -** appreciate the power of Teams to deliver a SSO personal
    app experience to consume and share data and analytics from an
    external data catalog in a Microsoft 365 environment.   This
    Proof-of-Concept solution includes search and message composition
    capabilities.  App created in yoTeams v3.0, .NET back-end, Security
    Vault, consuming Alation (data catalog) APIs   Uses Fluent and React
    Northstar library components for Teams.    


Thank you for your work. Samples are often showcased in Demos.


## Topics

Topics covered in this call

-   Updates from Microsoft 365 Engineering - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft)
    | @vesajuvonen - [7:23](https://youtu.be/BDkZqbL2YAk?t=443)

-   PnP.NET library updates - [Bert
    Jansen](https://twitter.com/o365bert) (Microsoft) | @O365bert
    - [9:06](https://youtu.be/BDkZqbL2YAk?t=546)

-   PnP PowerShell updates - [Erwin van
    Hunen](https://twitter.com/erwinvanhunen) (Valo Intranet) |
    @erwinvanhunen - [11:08](https://youtu.be/BDkZqbL2YAk?t=668)

-   yo Teams updates - [Wictor
    Wilén](https://twitter.com/wictor) (Avanade) @wictor -
    [13:07](https://youtu.be/BDkZqbL2YAk?t=787)

-   Microsoft Graph Toolkit updates - [Beth
    Pan](https://twitter.com/beth_panx) (Microsoft)
    | [beth-panx](https://github.com/beth-panx) - [14:23](https://youtu.be/BDkZqbL2YAk?t=863)

-   Microsoft Teams Samples - [Bob
    German](https://twitter.com/Bob1German) (Microsoft) |
    @Bob1German - [16:17](https://youtu.be/BDkZqbL2YAk?t=977)

-   **Demo:**  List group header formatting options -- Naveed Ahmed
    (Microsoft) - [17:56](https://youtu.be/BDkZqbL2YAk?t=1076)

-   **Demo:**  Introduction to PnP Core SDK - Getting started -- [Bert
    Jansen](https://twitter.com/O365Bert) (Microsoft) | @O365Bert -
    [25:54](https://youtu.be/BDkZqbL2YAk?t=1554)

-   **Demo:**  Customer scenario - Microsoft Teams integration with
    external systems -- Kathy (Qingyu) Xu (Pfizer) and [Paolo
    Pialorsi](https://twitter.com/PaoloPia) (PiaSys) | @PaoloPia -
    [43:43](https://youtu.be/BDkZqbL2YAk?t=2623)


## Resources

Additional resources around the covered topics and links from the
slides.

-   [Slides used in this ​community
    call](https://1drv.ms/p/s!AlposW7ozA_90jxX2fV4s9TIDfha?e=TgkQJ8)
-   Documentation - [Use view formatting to customize
    SharePoint](https://docs.microsoft.com/sharepoint/dev/declarative-customization/view-formatting) 
-   Repo - [PnP Core
    SDK](https://github.com/pnp/pnpcore)
-   Library - [PnP Core
    SDK](https://pnp.github.io/pnpcore/)
-   [Documentation - [Getting started with the PnP Core
    SDK](https://pnp.github.io/pnpcore/using-the-sdk/readme.html)
-   Tech Community Blog - [Getting started with PnP Core
    SDK](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/getting-started-with-pnp-core-sdk/ba-p/2207918) 
-   Documentation - [Create your first Microsoft Teams app using the
    Yeoman
    generator](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/using-web-part-as-ms-teams-tab)
-   Documentation - [Single sign-on (SSO) support for
    tabs](https://docs.microsoft.com/microsoftteams/platform/tabs/how-to/authentication/auth-aad-sso)
-   Documentation - [Microsoft identity platform and OAuth 2.0
    On-Behalf-Of
    flow](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-on-behalf-of-flow)
-   Library - [Fluent UI - React
    Northstar](https://fluentsite.z22.web.core.windows.net/0.53.0)
-   Templates & Components - [Teams React UI
    Library](https://learn.microsoft.com/microsoftteams/platform/concepts/design/design-teams-app-basic-ui-components)
-   PnP Weekly -- Episode 120 with guest MVP [Paolo
    Pialorsi](https://twitter.com/paolopia) (PiaSys) | @paolopia |
    [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-120/ba-p/2242545)
    |
    [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-120-29th-of-march-2021/)
-   [Microsoft Teams Samples
    Gallery](https://pnp.github.io/teams-dev-samples/) |
    aka.ms/teams-samples
-   Viva Connections <https://aka.ms/VivaConnections>


## General resources

-   [SharePoint look book](https://lookbook.microsoft.com/)
-   [Yo Teams video training package](https://aka.ms/yoteams-training)
-   [.NET Standard 2.0 version of SharePoint Online CSOM
    API](https://developer.microsoft.com/microsoft-365/blogs/net-standard-version-of-sharepoint-online-csom-apis/)
-   [Microsoft 365 community (PnP)
    videos](https://aka.ms/m365pnp-videos) | aka.ms/m365pnp-videos
-   [Microsoft Teams Toolkit for Visual Studio
    Code](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension)
-   [yo Teams](https://aka.ms/yoteams) | aka.ms/yoteams
-   Video - [Getting started using yo
    Teams](https://youtu.be/w0OrFkzNC10) | [Wictor
    Wilén](https://twitter.com/wictor) (Avanade)| @wictor
-   [Build a crisis management site to connect people and
    information](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/build-a-crisis-management-site-to-connect-people-and-information/ba-p/1216791)
-   [Developer
    documentation](https://aka.ms/spdev-docs) | <https://aka.ms/spdev-docs>
-   [PnP Power Shell](https://aka.ms/sppnp-powershell)
-   [SharePoint Modernization Partner
    Guidance](https://aka.ms/sppnp-modernization-partnerguidance) -
    Feedback welcome
-   Solution - [Building a modern search experiences with SharePoint
    Framework web parts](https://aka.ms/pnp-modern-search)
-   [Page transformation
    guidance](https://aka.ms/sppnp-pagetransformation)
-   [Page transformation
    videos](https://aka.ms/sppnp-pagetransformationvideos)
-   [Modernization scanner](https://aka.ms/sppnp-modernizationscanner)
-   [Microsoft 365 developer program
    site](https://developer.microsoft.com/office/dev-program) -
    Need to become a Tenant Admin to test look book capabilities? Get a
    Microsoft 365 E5 developer subscription (free tenant for 90 days)
-   [SharePoint Provisioning
    Service ](https://lookbook.microsoft.com/)- Easily provision
    look book designs to any tenant in the world
-   [SharePoint Provisioning templates on
    GitHub](https://github.com/SharePoint/sp-dev-provisioning-templates)
-   [PnP Provisioning Tenant Templates
    documentation](https://docs.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-tenant-templates)
-   [SharePoint Page Transformation webcast
    series](https://developer.microsoft.com/sharepoint/blogs/sharepoint-page-transformation-webcast-series/)
-   [PnP Power Shell](https://aka.ms/sppnp-powershell)
-   [SharePoint Modernization
    Tools](https://github.com/SharePoint/sp-dev-modernization/tree/dev/Tools)


## Upcoming Calls | Recurrent Invites


-   **Microsoft Graph call - April** 6th at 8:00 am PDT |
    <https://aka.ms/microsoftgraphcall>
-   **SharePoint Framework call** -- April 8th at 7:00 am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **Adaptive Cards monthly call --** April 8th at 9:00 am PDT |
    <https://aka.ms/adaptivecardscommunitycall>
-   **SharePoint monthly call --** April 13th at 8:00am PDT |
    <https://aka.ms/sp-call>
-   **Office add-in monthly call --** April 14th at 8:00 am PDT |
    [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscommunitycall)
-   **M365 General Dev call --** April 15th at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Microsoft Identity Platform --** April 15th at 9:00 am PDT
    |<https://aka.ms/IDDevCommunityCalendar> 
-   **Microsoft Teams monthly call --** April 20th at 8:00 am PDT |
    <https://aka.ms/microsoftteamscommunitycall>
-   **Power Apps monthly call --** April 21st at 8:00 am PDT |
    <https://aka.ms/PowerAppsMonthlyCall>


General Microsoft 365 Dev Special Interest Group bi-weekly calls are
targeted at anyone who's interested in the general Microsoft 365
development topics. This includes Microsoft Teams, Bots, Microsoft
Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core,
Site Designs, Power Automate, PowerApps, Column Formatting, list
formatting, etc. topics. More details on the Microsoft 365 community
from [https://aka.ms/m365pnp](https://aka.ms/sppnp). We also welcome
community demos, if you are interested in doing a live demo in these
calls!
You can download recurrent invite from <https://aka.ms/m365-dev-sig>.
Welcome and join in the discussion. If you have any questions, comments,
or feedback, feel free to provide your input as comments to this post as
well. More details on the Microsoft 365 community and options to get
involved are available
from [https://aka.ms/m365pnp](https://aka.ms/sppnp).


*"Sharing is caring"*

------------------------------------------------------------------------

*Microsoft 365 PnP team, Microsoft - 2nd of April 2021*
