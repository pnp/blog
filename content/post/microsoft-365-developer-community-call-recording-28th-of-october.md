---
title: "Microsoft 365 Developer Community Call recording -- 28th of October, 2021"
date: 2021-10-29T05:40:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 Developer Community Call Recordings"]
images:
- images/blog/microsoft-365-developer-community-call-recording-28th-of-october/recording-28th-oct.png
tags: []
type: "regular"


---

{{< image alt="recording-28th-oct.png" src="images/blog/microsoft-365-developer-community-call-recording-28th-of-october/recording-28th-oct.png" >}}
 

## Call summary

SharePoint Framework v1.13 is now generally available!  Have you visited
the Microsoft 365 tenant -- [script samples
gallery](https://aka.ms/script-samples) (106 scenarios and 142 scripts,
using CLI for Microsoft 365, PnP PowerShell, SPO Management Shell
tooling and more...)?   Last chance to register for [Hacktoberfest
2021](https://hacktoberfest.digitalocean.com) -- submit pull requests by
October 31st.  Sign up and attend a session in November hosted by
[Sharing is Caring](https://pnp.github.io/sharing-is-caring/).  At the
same time, sign up for the [PnP Recognition
Program](https://aka.ms/m365pnp-recognition).  Join your community mates
during the [Microsoft 365 platform call](https://aka.ms/m365-dev-call)
on November 2nd @ 8 AM PT for a Microsoft Ignite watch party.    Project
releases this week include **Yo teams - generator-teams** - v3.4.0 GA
and **Yo teams - yoteams-build-core** - v1.4.0.  
**Open-source project status:  (Bold indicates new this call)**

  ----------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------- ----------------------------------------------------------
  **Project**                                                                                                       **Current Version**                                                 **Release/Status**
  PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)                                         v1.7.0 GA, PnP Provisioning Engine Schema v202103                   Prepping for v1.8.0 - Winter 2022
  PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)                                      v1.4.0 GA, PnP Transformation Framework: Public Preview released!   Prepping for v1.5.0 - Winter 2022
  [PnP PowerShell](https://github.com/pnp/PnP-PowerShell)                                                           v1.8.0 GA                                                           In progress: V2 POC, Prepping for v1.8, nightly releases
  [Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)         **v3.4.0 GA**                                                        
  [Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)   **v1.4.0 GA**                                                        
  [Yo teams -- yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)          v1.0.1 GA                                                            
  [Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)            v3.1.1                                                               
  [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)                        v2.3.0 GA                                                           Working on v3.0.0
  ----------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------- ----------------------------------------------------------
**\* Note:  While version releases are periodic, nightly releases are
nightly!  Subscribe to nightly releases for the latest capabilities. **



As well, there were 12 new/updated script samples and 1 Power Platform
Samples this week.  The host of this call was [David Warner
II](http://twitter.com/DavidWarnerII) (Catapult Systems) |
\@DavidWarnerII.   Q&A takes place in chat throughout the call.



-   Next Tuesday, **join us during the [Microsoft 365 platform
    call](https://aka.ms/m365-dev-call) for the PnP Community Ignite
    watch party** -- Satya Nadella's keynote @ 8 AM PT.  Note:  Possible
    daylight savings time changes in your country.   Call created in US
    Pacific Time Zone.
-   Register today for Hacktoberfest 2021 --
    <https://hacktoberfest.digitalocean.com> -- Event closes October
    31st.
-   Register for [Microsoft Ignite 2021](https://ignite.microsoft.com)
    (Digital event) - November 2-4, 2021 
-   Opt into PnP Recognition Program |
    <https://aka.ms/m365pnp-recognition>
-   **Register for Sharing is Caring Events:**
    -   First Time Contributor Session -- [November
        3rd](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
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
    -   More than Code with VSCode -- [November
        9th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)  
    -   Maturity Model Practitioners -- [November
        16th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u) 
        (every 3rd Tuesday of month, 7:00am PT)
    -   PnP Office Hours -- 1:1 session --
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    -   PnP Buddy System -- [Request a
        Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
-   Download the recurrent invite for this call
    -- <http://aka.ms/m365-dev-sig>
-   Call attention to your great work by using
    the [#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click) on
    Twitter.
**Microsoft Teams Development
Samples:  **(<https://aka.ms/TeamsSampleBrowser>)

-   Operators standing by for your sample
**Microsoft Power Platform
Samples:  **([https://aka.ms/powerplatform-samples)](https://aka.ms/powerplatform-samples)

-   **Covid Vaccine Survey**\* -
    [Siddharth Vaghasia](http://twitter.com/siddh_me) | \@siddh_me
\*Check the site for this latest sample
**Script
Samples: ** ([https://aka.ms/script-samples)](https://aka.ms/script-samples)

-   11 New Samples + 6 Updated Samples🤩  -- WOW!  Contributed by
    -   [Valeras Narbutas](http://twitter.com/ValerasNarbutas) (Macaw)
        | [\@ValerasNarbutas](https://techcommunity.microsoft.com/t5/user/viewprofilepage/user-id/142422)
    -   [Adam Wójcik](http://twitter.com/Adam25858782) | \@Adam25858782
    -   [Rodrigo Pinto](http://twitter.com/ScoutmanPt) (Storm
        Technology) | \@ScoutmanPt
    -   [Marc D Anderson](http://twitter.com/sympmarc) (Sympraxis
        Consulting LLC) | \@sympmarc
    -   [Russell Gove](http://twitter.com/russgove) (Tronox) |
        [\@russgove](https://techcommunity.microsoft.com/t5/user/viewprofilepage/user-id/670687)

-- Thank you :clapping_hands:
**Together Mode!**
{{< image alt="211028-together-mode.gif" src="images/blog/microsoft-365-developer-community-call-recording-28th-of-october/211028-together-mode.gif" >}}
Are there ghosts or shadows occupying seats in this week's Together
Mode photo?  Mention during call about people \"beaming up/down\" to the
theater today?  
**Demos** delivered in this session

-   **Configuration-as-Code for Microsoft 365 with Microsoft365DSC
    -- **Desire State Configuration -- a PowerShell Module that
    represents your entire Microsoft 365 tenant's configuration as code
    and allows DevOps to monitor and control configuration
    discrepancies.  Capabilities include automate, export, synchronize,
    access, monitor, and report.   Learn what it is, how to use
    PowerShell script to find/create a policy, import/export a
    configuration, monitor config drift, ways to maintain a desired
    state, etc.  Q&A throughout.

-   **Automatically recognize your team champions** **:trophy: with CLI
    for Microsoft 365 --** with existing cmdlets in CLI, query criteria
    and a business objective (ID champions), Tenant Admins can modify
    general site wide reporting (i.e., chat, file activity) to identify
    top active Microsoft Teams contributors or SharePoint users within a
    timeframe.   For chat ranking in a channel - count messages,
    replies, likes, comments by contributor, return top 3.  Via Webhook,
    send Adaptive Card to communicate champion status.   

-   **Updates on Independent Publisher Connectors & Care Quality
    Commissions Connector Demo -- ** 13 custom connectors added in
    October.  Create a connector earn a Credly badge.  Get a look at the
    CQC connector that takes data from the Care Quality Commission in
    England - independently gathers data on care service providers.   A
    Power App elegantly displays care provider rankings by location
    calling 2 flows that get location details via the connector in the
    back-end.       

     

Thank you for your work. Samples are often showcased in Demos.   
Request a Demo spot on the call <https://aka.ms/m365pnp/request/demo>
**Topics** covered in this call

-   PnP .NET library updates -[ Bert
    Jansen](http://twitter.com/O365bert) (Microsoft) | \@O365bert --
    [7:39](https://youtu.be/PFMUygySS3I?t=459)

-   yo Teams updates - [Albert-Jan Schot](http://twitter.com/appieschot)
    (BLIS.digital) |
    \@appieschot -- [9:30](https://youtu.be/PFMUygySS3I?t=570)

-   Microsoft Graph Toolkit updates - [Sébastien
    Levert](http://twitter.com/sebastienlevert) (Microsoft)
    | [sebastienlevert](https://github.com/sebastienlevert) -- [11:27](https://youtu.be/PFMUygySS3I?t=687)

-   Microsoft Script Samples -  [David Warner
    II](http://twitter.com/DavidWarnerII) (Catapult Systems) |
    \@DavidWarnerII -- [3:17](https://youtu.be/PFMUygySS3I?t=197)

-   Microsoft Teams Samples - [David Warner
    II](http://twitter.com/DavidWarnerII) (Catapult Systems) |
    \@DavidWarnerII -- [13:14](https://youtu.be/PFMUygySS3I?t=794)

-   Microsoft Power Platform Samples - [April
    Dunnam](http://twitter.com/aprildunnam) (Microsoft) |
    \@aprildunnam -- [13:50](https://youtu.be/PFMUygySS3I?t=830)

-   **D1:**  Configuration-as-Code for Microsoft 365 with
    Microsoft365DSC -- [Nik
    Charlebois](http://twitter.com/NikCharlebois) (Microsoft) |
    \@NikCharlebois [--][ [16:02](https://youtu.be/PFMUygySS3I?t=962)]

-   **D2:**  Automatically recognize your team champions :trophy: with
    CLI for Microsoft 365 -- [Albert-Jan
    Schot](http://twitter.com/appieschot) (BLIS.digital) |
    \@appieschot [--][ [35:42](https://youtu.be/PFMUygySS3I?t=2142)]

-   **D3:**  Updates on Independent Publisher Connectors & Care Quality
    Commissions Connector Demo -- [Natalie
    Pienkowska](http://twitter.com/NataliePienkow1) (Microsoft) |
    \@NataliePienkow1 & Martyn Lesbirel (Dynamiti) --
    [48:09](https://youtu.be/PFMUygySS3I?t=2889)
## Resources

Additional resources around the covered topics and links from the
slides.

-   D1:  Repo -
    [Microsoft365DSC](https://github.com/Microsoft/Microsoft365DSC) 
-   D1:  Repo -- [Microsoft365DSC Resources
    List](https://github.com/microsoft/Microsoft365DSC/wiki/Resources-List) 
-   D1:  Tool - [Microsoft365DSC - Configuration-as-Code for the
    Cloud](https://export.microsoft365dsc.com/) 
-   D2:  Tools - [CLI for Microsoft
    365](https://pnp.github.io/cli-microsoft365/) |
    <https://aka.ms/cli-m365>
-   D2:  Repo - [CLI for Microsoft
    365](https://github.com/pnp/cli-microsoft365) 
-   D2:  Article - [Recognize active team members with the CLI for
    Microsoft
    365](https://www.cloudappie.nl/recognize-active-team-members-cli-microsoft-365/) 
-   D2:  Article - [Recognize contributions using the CLI for Microsoft
    365](https://www.cloudappie.nl/recognize-contributions-clim365/) 
-   D2:  Article - [How to send Adaptive Cards with CLI Microsoft
    365](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/how-to-send-adaptive-cards-with-cli-microsoft-365/ba-p/2143466) 
-   D2:  Tool -- [Adaptive Cards IO
    Designer](https://www.adaptivecards.io/designer/) 
-   D3:  Repo - [Microsoft Power Platform
    Connectors](https://github.com/Microsoft/PowerPlatformConnectors) 
-   D3:  Article - [Power Apps Loading Spinners, Saving Spinners and
    Progress
    Bars](https://matthewdevaney.com/power-apps-loading-spinners-saving-spinners-and-progress-bars/) 
-   **PnP Weekly -- Episode 140** (October 25th) with Sweden based MVP
    and Chief Technical Architect at Advania - [Simon
    Ågren](http://twitter.com/agrenpoint) |
    [\@AgrenPoint](https://techcommunity.microsoft.com/t5/user/viewprofilepage/user-id/271184). | [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-140-simon-%C3%A5gren-advania/ba-p/2881228) | [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-140-%e2%80%93-25th-of-october-2021/)
**General resources**:

-   Samples - [Power Platform
    Samples](https://aka.ms/powerplatform-samples) | [aka.ms/](http://aka.ms/powerplatform-samples)[powerplatform](http://aka.ms/powerplatform-samples)[-samples](http://aka.ms/powerplatform-samples)
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
    | <http://aka.ms/learn-mgt>
-   Viva Connections <https://aka.ms/VivaConnections>
-   [SharePoint look
    book](https://lookbook.microsoft.com/?WT.mc_id=m365-24198-cxa)
-   [Yo Teams video training package](http://aka.ms/yoteams-training)
-   [.NET Standard 2.0 version of SharePoint Online CSOM
    API](https://developer.microsoft.com/en-us/microsoft-365/blogs/net-standard-version-of-sharepoint-online-csom-apis?WT.mc_id=m365-24198-cxa)
-   [Microsoft 365 community (PnP)
    videos](http://aka.ms/m365pnp-videos) | aka.ms/m365pnp-videos
-   [Microsoft Teams Toolkit for Visual Studio
    Code](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension)
-   [yo Teams](http://aka.ms/yoteams) | aka.ms/yoteams
-   Video - [Getting started using yo
    Teams](https://youtu.be/w0OrFkzNC10) | [Wictor
    Wilén](https://twitter.com/wictor) (Avanade)| \@wictor
-   [Build a crisis management site to connect people and
    information](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/build-a-crisis-management-site-to-connect-people-and-information/ba-p/1216791?WT.mc_id=m365-24198-cxa)
-   [Developer
    documentation](http://aka.ms/spdev-docs) | <https://aka.ms/spdev-docs>
-   [PnP Power Shell](https://aka.ms/sppnp-powershell)
-   [SharePoint Modernization Partner
    Guidance](http://aka.ms/sppnp-modernization-partnerguidance) -
    Feedback welcome
-   Solution - [Building a modern search experiences with SharePoint
    Framework web parts](https://aka.ms/pnp-modern-search)
-   [Page transformation
    guidance](https://aka.ms/sppnp-pagetransformation)
-   [Page transformation
    videos](https://aka.ms/sppnp-pagetransformationvideos)
-   [Modernization scanner](https://aka.ms/sppnp-modernizationscanner)
-   [Microsoft 365 developer program
    site](https://developer.microsoft.com/en-us/office/dev-program?WT.mc_id=m365-24198-cxa) -
    Need to become a Tenant Admin to test look book capabilities? Get a
    Microsoft 365 E5 developer subscription (free tenant for 90 days)
-   [SharePoint Provisioning
    Service ](https://provisioning.sharepointpnp.com/)- Easily provision
    look book designs to any tenant in the world
-   [SharePoint Provisioning templates on
    GitHub](https://github.com/SharePoint/sp-dev-provisioning-templates)
-   [PnP Provisioning Tenant Templates
    documentation](https://docs.microsoft.com/en-us/sharepoint/dev/solution-guidance/pnp-provisioning-tenant-templates?WT.mc_id=m365-24198-cxa)
-   [SharePoint Page Transformation webcast
    series](https://developer.microsoft.com/en-us/sharepoint/blogs/sharepoint-page-transformation-webcast-series?WT.mc_id=m365-24198-cxa)
-   [PnP Power Shell](https://aka.ms/sppnp-powershell)
-   [SharePoint Modernization
    Tools](https://github.com/SharePoint/sp-dev-modernization/tree/dev/Tools)
**Upcoming Calls | Recurrent Invites:**

-   **Microsoft 365 platform call** **-- **November 2nd at 8:00 am PDT
    | <https://aka.ms/m365-dev-call>
-   **SharePoint Framework call --** November 4th at 7:00 am PDT
    | <https://aka.ms/spdev-spfx-call>
-   **Office add-in monthly call -- **November10th at 8:00 am PDT
    | <https://aka.ms/officeaddinscall>
-   **M365 General Dev call -- **November 11th at 7:00 am PDT
    | <https://aka.ms/m365-dev-sig>
-   **Adaptive Cards monthly call -- **November 11th at 9:00 am PDT
    | <https://aka.ms/adaptivecardscommunitycall>
-   **Power Apps monthly call **-- November 17th at 8:00 am PDT
    | <https://aka.ms/PowerAppsMonthlyCall>
-   **Microsoft Identity Platform call --** November 18th at 9:00 am
    PDT | <https://aka.ms/IDDevCommunityCalendar>
General Microsoft 365 Dev Special Interest Group bi-weekly calls are
targeted at anyone who's interested in the general Microsoft 365
development topics. This includes Microsoft Teams, Bots, Microsoft
Graph, CSOM, REST, site provisioning, PnP PowerShell, PnP Sites Core,
Site Designs, Microsoft Flow, PowerApps, Column Formatting, list
formatting, etc. topics. More details on the Microsoft 365 community
from [http://aka.ms/m365pnp](http://aka.ms/sppnp). We also welcome
community demos, if you are interested in doing a live demo in these
calls!
You can download recurrent invite from <http://aka.ms/m365-dev-sig>.
Welcome and join in the discussion. If you have any questions, comments,
or feedback, feel free to provide your input as comments to this post as
well. More details on the Microsoft 365 community and options to get
involved are available
from [http://aka.ms/m365pnp](http://aka.ms/sppnp).

------------------------------------------------------------------------
*"Sharing is caring"*

*Microsoft 365 PnP team, Microsoft - 29th of October 2021*
