---
title: "Microsoft 365 Developer Community Call recording -- 11th of November, 2021"
date: 2021-11-12T02:20:00-05:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 Developer Community Call"]
images:
- images/recording-11th-november.png
tags: []
type: "regular"
---



## Call summary



Visit the Microsoft 365 tenant -- [script samples
gallery](https://aka.ms/script-samples) (114 scenarios and 156 scripts,
using CLI for Microsoft 365, PnP PowerShell, SPO Management Shell
tooling and more...)?   Sign up and attend an AMA and other events in
November-December hosted by [Sharing is
Caring](https://pnp.github.io/sharing-is-caring/).  At the same time,
sign up for the [PnP Recognition
Program](https://aka.ms/m365pnp-recognition). Welcome to 9 new members
to the Microsoft 365 PnP Team!  We're thrilled you have joined us.  

-   [Geetha Sivasailam](https://twitter.com/GSiVed) |
    @GSiVed
-   [João Mendes](https://twitter.com/joaojmendes) (independent/Storm
    Technologies Ltd) |
    [joaojmendes](https://github.com/joaojmendes)
-   [Stephan Bisser](https://twitter.com/stephanbisser) (Solvion) |
    @stephanbisser  
-   [Natalie Pienkowska](https://twitter.com/NataliePienkow1) (Microsoft)
    | @NataliePienkow1
-   [Joel Rodrigues](https://twitter.com/JoelFMRodrigues) (Storm
    Technology Ltd) | @JoelFMRodrigues
-   [Tetsuya Kawahara](https://twitter.com/techan_k) (MVP) | @techan_k
-   [Derek Cash-Peterson](https://twitter.com/spdcp) (Sympraxis
    Consulting) | @Spdcp
-   [Rick Van Rousselt](https://twitter.com/rickvanrousselt) (Advantive)
    | @rickvanrousselt
-   [Thomy Gölles](https://twitter.com/thomyg) (Solvion) | @thomyg

Project releases this week include **Yo teams - generator-teams** -
v3.5.0 Preview and **Yo teams - yoteams-build-core** - v1.5.0 Preview2,
and **Yo teams -- yoteams-deploy** - v1.1.0 Preview2.  
**Open-source project status:  (Bold indicates new this call)**

  ----------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------- -----------------------------------------------------------------------------------------------------------
  **Project**                                                                                                       **Current Version**                                                 **Release/Status**
  PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)                                         v1.7.0 GA, PnP Provisioning Engine Schema v202103                   Prepping for v1.8.0 - Winter 2022
  PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)                                      v1.4.0 GA, PnP Transformation Framework: Public Preview released!   Prepping for v1.5.0 - Winter 2022, .NET 6 support 
  [PnP PowerShell](https://github.com/pnp/PnP-PowerShell)                                                           v1.8.0 GA                                                           In progress: V2 POC, Prepping for v1.8, nightly releases
  [Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)         v3.4.0 GA, **v3.5.0 Preview**                                       Support for Teams JS SDK v2.0
  [Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)   v1.4.0 GA, **v1.5.0 Preview2**                                       
  [Yo teams -- yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)          v1.0.1 GA, **v1.1.0 Preview2**                                       
  [Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)            v3.1.1                                                               
  [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)                        v2.3.0 GA                                                           Preparing v2.3.1 release, Working on v3.0.0 - Aligning all Toolkit components to Fluent UI Web Components
  ----------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------- -----------------------------------------------------------------------------------------------------------
{{< notice note>}}
While version releases are periodic, nightly releases are nightly!  Subscribe to nightly releases for the latest capabilities.
{{< /notice >}}

**    **

As well, there were 14 new/updated script samples and 2 Power Platform
Samples this week!  The host of this call was [Paolo
Pialorsi](https://twitter.com/paolopia) (PiaSys.com) | @paolopia.   Q&A
takes place in chat throughout the call.



-   Opt into PnP Recognition Program |
    <https://aka.ms/m365pnp-recognition>
-   Give us feedback on the new consolidated [M365 sample
    gallery](https://aka.ms/m365/samples) 
-   **Register for Sharing is Caring Events:**
    -   Ask me anything (AMA) PnPjs -- [November
        16th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQjBYTFZFR1ZBQjIzUDdLUFNaVUFXMUowTC4u)
    -   Ask me anything (AMA) MGT -- [November
        30th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNlY2U1hHTjZHTlExNDRYVEhaVkQxUjgyMC4u)
    -   Ask me anything (AMA) PnP Search -- [January
        11th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOFpKRjdQQVlWOEdaRlk2WkI3WUVQWFVNUC4u)
    -   First Time Contributor Session -- [December
        15th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session -- [November
        17th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)  
    -   Power Platform Samples -- First Time Contributor -- [November
        24th](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMTFJWFFGVUxBNUFZQjZWRUdaOE5BMFkwNS4u),
        [December
        15th](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMTFJWFFGVUxBNUFZQjZWRUdaOE5BMFkwNS4u)
    -   PnP -- SPFx Developer Workstation Setup -- [November
        16th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [November
        30th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)  
    -   First Time Presenter -- TBS
    -   More than Code with VSCode -- TBS 
    -   Maturity Model Practitioners -- [November
        16th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u) 
        (every 3rd Tuesday of month, 7:00am PT)
    -   PnP Office Hours -- 1:1 session --
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    -   PnP Buddy System -- [Request a
        Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
-   Download the recurrent invite for this call
    -- <https://aka.ms/m365-dev-sig>
-   Call attention to your great work by using
    the [#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click) on
    Twitter.
**Microsoft Teams Development
Samples:  **(<https://aka.ms/TeamsSampleBrowser>)

-   Please do share your great work.  
**Microsoft Power Platform
Samples:  **([https://aka.ms/powerplatform-samples)](https://aka.ms/powerplatform-samples)

-   **Template HelpDesk 2021\***- Neiy Darry 
-   **Power Fx Date Functions\*** - [Matthew
    Devaney](https://twitter.com/mattbdevaney) | @mattbdevaney &\
    [Loïc Cimon](https://twitter.com/LoicCimon) | @LoicCimon

\*Check the site for this latest sample
**Script
Samples: ** ([https://aka.ms/script-samples)](https://aka.ms/script-samples)

-   8 New Samples + 6 Updated Samples🤩  -- WOW!  Contributed by
    -   [Adam Wójcik](https://twitter.com/Adam25858782) | @Adam25858782
    -   [Valeras Narbutas](https://twitter.com/ValerasNarbutas) (Macaw)
        | @ValerasNarbutas
    -   [Rodrigo Pinto](https://twitter.com/ScoutmanPt) (Storm
        Technology) | @ScoutmanPt
    -   [Srinivas Varukala](https://twitter.com/svarukala) (Microsoft) |
        @svarukala
    -   [Jim Love](https://twitter.com/jimmywim) | @jimmywim
    -   [Reshmee Auckloo](https://twitter.com/ReshmeeAuckloo) |
        @reshmeeauckloo

-- Fabulous!

## Demos

Demos delivered in this session

-   **ProvisionGenie - a Teams provisioning engine on Power Apps and
    Azure Logic Apps -- **ProvisionGenie blends learning with the
    provisioning process. Elegantly and non-technically prompts user
    through Group, Site and Channel configuration. Team owner  adds
    members and owners, libraries, columns and lists.  Uses Logic Apps
    behind scenes to provision resources. Integrates Power Apps for UI,
    Azure Logic Apps (flows - actions), Managed Identity
    (authentication), Dataverse (data storage), Deployment (script and
    ARM template files) and has great documentation.

-   **List item filtering on modern pages with complex dynamic view
    formatting --** make a list with topics and lengthy descriptions
    more readable and interactive.  Create 2 new views (list and
    gallery) for the same list. Gallery view for button like navigation
    (topics), and List view to create mini navigation -- to move up/down
    through item descriptions.  Use "ID" attribute that links everything
    together with anchors.  Expose views on webpage.  All bowser -
    client-side with out-of-the-box formatting.

-   **Updates on Independent Publisher Connectors & myStrom Connector
    Demo --**

    presently there are 38 MVP produced certified connectors in
    production and 19 in the pipeline. Connectors are used by Power
    Automate, Power Apps, Azure Logic Apps.  The myStrom connector
    handles authentication and basic switching capabilities (on/off,
    trigger automations) for home control system devices.  Presenter's
    solution triggers home control system actions based on current
    weather and air quality - displayed on a PowerBI dashboard. 

     

Thank you for your work. Samples are often showcased in Demos.   
Request a Demo spot on the call <https://aka.ms/m365pnp/request/demo>

## Topics

Topics covered in this call

-   PnP .NET library updates -[Paolo
    Pialorsi](https://twitter.com/paolopia) (PiaSys.com) | @paolopia --
    [6:53](https://youtu.be/frJnxOITmSU?t=413)
-   PnP PowerShell updates - [Paolo
    Pialorsi](https://twitter.com/paolopia) (PiaSys.com) |
    @paolopia -- [8:51](https://youtu.be/frJnxOITmSU?t=531)
-   yo Teams updates - [Stephan
    Bisser](https://twitter.com/stephanbisser) (Solvion) |
    @stephanbisser -- [10:05](https://youtu.be/frJnxOITmSU?t=605)
-   Microsoft Graph Toolkit updates -[ Sébastien
    Levert](https://twitter.com/sebastienlevert) (Microsoft)
    | [sebastienlevert](https://github.com/sebastienlevert) -- [11:14](https://youtu.be/frJnxOITmSU?t=674)
-   Microsoft Script Samples -  [Paul
    Bullock](https://twitter.com/pkbullock) (CaPa Creative Ltd) |
    @pkbullock -- [2:36](https://youtu.be/frJnxOITmSU?t=156)
-   Microsoft Teams Samples - [Paolo
    Pialorsi](https://twitter.com/paolopia) (PiaSys.com) |
    @paolopia -- [13:12](https://youtu.be/frJnxOITmSU?t=792)
-   Microsoft Power Platform Samples - [April
    Dunnam](https://twitter.com/aprildunnam) (Microsoft) |
    @aprildunnam -- [13:51](https://youtu.be/frJnxOITmSU?t=831)
-   **Demo 1:**  ProvisionGenie - a Teams provisioning engine on Power
    Apps and Azure Logic Apps -- [Luise
    Freese](https://twitter.com/LuiseFreese) | @LuiseFreese  & [Carmen
    Ysewijn](https://twitter.com/CarmenYsewijn) (Qubix) |
    @CarmenYsewijn [--][ [15:56](https://youtu.be/frJnxOITmSU?t=956)]
-   **Demo 2:**[  List item filtering on modern pages with complex
    dynamic view formatting -- ][Chris
    Kent](https://twitter.com/theChrisKent)[ (DMI) | @theChrisKent
    -- [29:05](https://youtu.be/frJnxOITmSU?t=1745)]
-   **Demo 3:**[  Updates on Independent Publisher Connectors & myStrom
    Connector Demo -- ][Natalie
    Pienkowska](https://twitter.com/NataliePienkow1)[ (Microsoft) |
    @NataliePienkow1 & ][Tomasz
    Poszytek](https://twitter.com/TomaszPoszytek)[ |
    @TomaszPoszytek ][--][ [41:46](https://youtu.be/frJnxOITmSU?t=2506)]
    


## Resources

Additional resources around the covered topics and links from the
slides.

-   D1:  Repo --
    [ProvisionGenie](https://github.com/ProvisionGenie/ProvisionGenie) 
-   D1:  Documentation - [ProvisionGenie](https://provisiongenie.com/) 
-   D2:  Documentation - [Use column formatting to customize
    SharePoint](https://docs.microsoft.com/sharepoint/dev/declarative-customization/column-formatting?WT.mc_id=m365-15744-cxa) 
-   D2:  Samples -- [List
    Formatting](https://github.com/pnp/List-Formatting) (View samples \>
    Content-browser) | (Sample available very soon)
-   D3:  Repo - [Microsoft Power Platform
    Connectors](https://github.com/Microsoft/PowerPlatformConnectors) 
-   D3:  Guidance - [INDEPENDENT PUBLISHER CONNECTOR STEP BY
    STEP](https://poszytek.eu/en/microsoft-en/office-365-en/powerautomate-en/independent-publisher-connector-step-by-step/#more-3186) 
-   D3:  Video - [Independent Publisher connector step by
    step](https://www.youtube.com/watch?v=wGFWZqsxIBQ) 
-   D3:  Article - [Power Automate IS NOT ONLY FOR
    BUSINESS](https://poszytek.eu/en/microsoft-en/office-365-en/microsoft-flow-is-not-only-for-business/) 
-   D3:  Website -- [MyStrom API for
    Developers](https://mystrom.com/mystrom-for-developers/) 
-   **PnP Weekly -- Episode 142** (November 8th) with New York, US /
    Porto, Portugal-based Program Manager at Microsoft - [Natalie
    Pienkowska](https://twitter.com/NataliePienkow1) | @
    NataliePienkow1. | [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-142-natalie-pienkowska/ba-p/2939019) | [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-142-%e2%80%93-8th-of-november-2021/)


## General resources

-   Samples - [Power Platform
    Samples](https://aka.ms/powerplatform-samples) | [aka.ms/](https://aka.ms/powerplatform-samples)[powerplatform](https://aka.ms/powerplatform-samples)[-samples](https://aka.ms/powerplatform-samples)
-   Microsoft 365 tenant -- [Script Samples
    Gallery](https://aka.ms/script-samples) | aka.ms/script-samples
-   [Microsoft Teams Samples
    Gallery](https://pnp.github.io/teams-dev-samples/) |
    aka.ms/teams-samples
-   [Microsoft 365 Extensibility look book
    gallery](https://adoption.microsoft.com/extensibility-look-book?WT.mc_id=m365-24198-cxa) |
    aka.ms/m365/extensibility
-   Archives - Microsoft 365 PnP Weekly
    - [Videos](https://www.youtube.com/playlist?list=PLR9nK3mnD-OVYI-St_CBiFfuL4CZbBpkC), [Podcasts](https://pnpweekly.podbean.com/)  
-   PnP Teams Quickstart
    | [aka.ms/pnp-teams-quickstart](https://aka.ms/pnp-teams-quickstart)
-   Microsoft Teams Toolkit v2.2 | <https://aka.ms/teams-toolkit>
-   [Microsoft 365 PnP Community
    hub](https://techcommunity.microsoft.com/t5/microsoft-365-pnp/ct-p/Microsoft365PnP) |
    aka.ms/m365pnp/community 
-   Microsoft Graph Toolkit in Microsoft Learn
    | <https://aka.ms/learn-mgt>
-   Viva Connections <https://aka.ms/VivaConnections>
-   [SharePoint look
    book](https://lookbook.microsoft.com/?WT.mc_id=m365-24198-cxa)
-   [Yo Teams video training package](https://aka.ms/yoteams-training)
-   [.NET Standard 2.0 version of SharePoint Online CSOM
    API](https://developer.microsoft.com/microsoft-365/blogs/net-standard-version-of-sharepoint-online-csom-apis?WT.mc_id=m365-24198-cxa)
-   [Microsoft 365 community (PnP)
    videos](https://aka.ms/m365pnp-videos) | aka.ms/m365pnp-videos
-   [Microsoft Teams Toolkit for Visual Studio
    Code](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension)
-   [yo Teams](https://aka.ms/yoteams) | aka.ms/yoteams
-   Video - [Getting started using yo
    Teams](https://youtu.be/w0OrFkzNC10) | [Wictor
    Wilén](https://twitter.com/wictor) (Avanade)| @wictor
-   [Build a crisis management site to connect people and
    information](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/build-a-crisis-management-site-to-connect-people-and-information/ba-p/1216791?WT.mc_id=m365-24198-cxa)
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
    site](https://developer.microsoft.com/office/dev-program?WT.mc_id=m365-24198-cxa) -
    Need to become a Tenant Admin to test look book capabilities? Get a
    Microsoft 365 E5 developer subscription (free tenant for 90 days)
-   [SharePoint Provisioning
    Service ](https://lookbook.microsoft.com/)- Easily provision
    look book designs to any tenant in the world
-   [SharePoint Provisioning templates on
    GitHub](https://github.com/SharePoint/sp-dev-provisioning-templates)
-   [PnP Provisioning Tenant Templates
    documentation](https://docs.microsoft.com/sharepoint/dev/solution-guidance/pnp-provisioning-tenant-templates?WT.mc_id=m365-24198-cxa)
-   [SharePoint Page Transformation webcast
    series](https://developer.microsoft.com/sharepoint/blogs/sharepoint-page-transformation-webcast-series?WT.mc_id=m365-24198-cxa)
-   [PnP Power Shell](https://aka.ms/sppnp-powershell)
-   [SharePoint Modernization
    Tools](https://github.com/SharePoint/sp-dev-modernization/tree/dev/Tools)

## Upcoming Calls | Recurrent Invites


-   **Microsoft 365 platform call** **--** November 16th at 8:00 am
    PDT | <https://aka.ms/m365-dev-call>
-   **Power Apps monthly call**-- November 17th at 8:00 am PDT
    | <https://aka.ms/PowerAppsMonthlyCall>
-   **SharePoint Framework call** -- November 18th at 7:00 am PDT
    | <https://aka.ms/spdev-spfx-call>
-   **Microsoft Identity Platform call** -- November 18th at 9:00 am
    PDT | <https://aka.ms/IDDevCommunityCalendar>
-   **M365 General Dev call** -- November 25th at 7:00 am PDT
    | <https://aka.ms/m365-dev-sig>
-   **Office add-in monthly call** -- December 8th at 8:00 am PDT
    | <https://aka.ms/officeaddinscall>
-   **Adaptive Cards monthly call** --December 9th at 9:00 am PDT
| <https://aka.ms/adaptivecardscommunitycall>

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

------------------------------------------------------------------------
*"Sharing is caring"*

*Microsoft 365 PnP team, Microsoft - 12th of November 2021*
