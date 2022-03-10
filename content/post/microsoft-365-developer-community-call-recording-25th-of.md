---
title: "Microsoft 365 Developer Community Call recording -- 25th of November, 2021"
date: 2021-11-26T03:33:00-05:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 Developer Community Call Recordings"]
images:
- images/blog/microsoft-365-developer-community-call-recording-25th-of/recording-25th-nov.png
tags: []
type: "regular"
---



## Call Summary




Have you visited the Microsoft 365 tenant -- [script samples
gallery](https://aka.ms/script-samples) (116 scenarios and 160 scripts,
using CLI for Microsoft 365, PnP PowerShell, SPO Management Shell
tooling and more...)?   Sign up and attend an AMA and other events in
November-December hosted by [Sharing is
Caring](https://pnp.github.io/sharing-is-caring/).  At the same time,
sign up for the [PnP Recognition
Program](https://aka.ms/m365pnp-recognition).   Welcome to 9 new members
to the Microsoft 365 PnP Team!  We're thrilled you have joined us.  

-   [Geetha
    Sivasailam](http://twitter.com/GSiVed) | [@GSiVed](https://techcommunity.microsoft.comhttps://techcommunity.microsoft.com/t5/user/viewprofilepage/user-id/384388)
-   [João Mendes](http://twitter.com/joaojmendes) (independent/Storm
    Technologies Ltd)
    | [@joaojmendes](https://techcommunity.microsoft.comhttps://techcommunity.microsoft.com/t5/user/viewprofilepage/user-id/442957)
-   [Stephan Bisser](http://twitter.com/stephanbisser) (Solvion) |
    @stephanbisser  
-   [Natalie Pienkowska](http://twitter.com/NataliePienkow1) (Microsoft)
    | @NataliePienkow1
-   [Joel Rodrigues](http://twitter.com/JoelFMRodrigues) (Storm
    Technology Ltd) | @JoelFMRodrigues
-   [Tetsuya Kawahara](http://twitter.com/techan_k) (MVP) | @techan_k
-   [Derek Cash-Peterson](http://twitter.com/spdcp) (Sympraxis
    Consulting)
    | [@Spdcp](https://techcommunity.microsoft.comhttps://techcommunity.microsoft.com/t5/user/viewprofilepage/user-id/386549)
-   [Rick Van Rousselt](http://twitter.com/rickvanrousselt) (Advantive)
    | @rickvanrousselt
-   [Thomy Gölles](http://twitter.com/thomyg) (Solvion) | @thomyg
Project releases this week include **Yo teams - generator-teams** -
v3.5.0 GA, **Yo teams - yoteams-build-core** - v1.5.0 GA, **Yo teams --
yoteams-deploy** - v1.1.0 GA and **Microsoft Graph Toolkit (MGT)** -
v2.3.1 GA.  Also added .NET 6 support to **PnP .NET libraries**.
**Open-source project status: (Bold indicates new this call)**

  ----------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------- -----------------------------------------------------------------------------------------------------------
  **Project**                                                                                                       **Current Version**                                                 **Release/Status**
  PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework)                                         v1.7.0 GA, PnP Provisioning Engine Schema v202103                   Prepping for v1.8.0 - Winter 2022, .NET 6 support 
  PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)                                      v1.4.0 GA, PnP Transformation Framework: Public Preview released!   Prepping for v1.5.0 - Winter 2022, .NET 6 support 
  [PnP PowerShell](https://github.com/pnp/PnP-PowerShell)                                                           v1.8.0 GA                                                           In progress: V2 POC, Prepping for v1.8, nightly releases
  [Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)         **v3.5.0 GA**                                                       **v4.0.0-next**
  [Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)   **v1.5.0 GA**                                                        
  [Yo teams -- yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)          **v1.1.0 GA**                                                        
  [Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)            v3.1.1                                                               
  [Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)                        **v2.3.1 GA**                                                       Preparing v2.3.1 release, Working on v3.0.0 - Aligning all Toolkit components to Fluent UI Web Components
  ----------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------- -----------------------------------------------------------------------------------------------------------
**\* Note:  While version releases are periodic, nightly releases are
nightly!  Subscribe to nightly releases for the latest capabilities. **


As well, there were 6 new/updated script samples this week!  The host of
this call was [David Warner II](http://twitter.com/DavidWarnerII)
(Catapult Systems) | @DavidWarnerII.   Q&A takes place in chat
throughout the call.



-   Opt into PnP Recognition Program
    | <https://aka.ms/m365pnp-recognition>

-   Join us at the next **Microsoft 365 platform call 30th of November
    @ 8 AM PT**

    -   Latest news from Microsoft engineering on Microsoft 365 topics
    -   Demos: 
    -   **Arpitha Dhanapathi** - Microsoft 365 Application Certification
    -   **Vesa Juvonen & Paolo Pialorsi** -- Building a Viva Connections
        partner solution using multi-tenant APIs and Adaptive Card
        Extensions (ACEs)
    -   **Maisa Rissi & Vincent Biret** - Introduction to Microsoft
        Graph Go SDK

-   Submit Samples

-   Give us feedback on the new consolidated [M365 sample
    gallery](https://aka.ms/m365/samples) 

-   **Register for Sharing is Caring Events:**
    -   Ask me anything (AMA) MGT -- [November
        30th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNlY2U1hHTjZHTlExNDRYVEhaVkQxUjgyMC4u)
    -   Ask me anything (AMA) PnP Search -- [January
        11th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOFpKRjdQQVlWOEdaRlk2WkI3WUVQWFVNUC4u)
    -   First Time Contributor Session -- [December
        15th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session -- TBS  
    -   Power Platform Samples -- First Time Contributor -- [December
        15th](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMTFJWFFGVUxBNUFZQjZWRUdaOE5BMFkwNS4u)
    -   PnP -- SPFx Developer Workstation Setup -- TBS
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [November
        30th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)  
    -   First Time Presenter -- TBS
    -   More than Code with VSCode -- TBS 
    -   Maturity Model Practitioners -- [January
        18th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
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

-   Please do share your great work.  
**Microsoft Power Platform
Samples:  **([https://aka.ms/powerplatform-samples)](https://aka.ms/powerplatform-samples)

-   Please do share your great work.  

\*Check the site for this latest sample
**Script
Samples: ** ([https://aka.ms/script-samples)](https://aka.ms/script-samples)

-   2 New Samples + 4 Updated Samples🤩 -- WOW!  Contributed by
    -   [Adam Wójcik](http://twitter.com/Adam25858782) | @Adam25858782
    -   [Leon Armston](http://twitter.com/LeonArmston) |
        [@LeonArmston](https://techcommunity.microsoft.com/t5/user/viewprofilepage/user-id/855621)

-- Fabulous!
**Together Mode!**
{{< image alt="211125-together-mode.gif" src="images/blog/microsoft-365-developer-community-call-recording-25th-of/211125-together-mode.gif" >}}
Great seeing everyone today. See you at the [European Collaboration and
Cloud Summit](https://collabsummit.eu/) in Düsseldorf, Germany or
perhaps at the [Microsoft 365 Collaboration
Conference](https://sharepointna.com/#!/) in Las Vegas, Nevada, US.     
   

## Demos
Demos delivered in this session

-   **Contributors Corner - GitHub Contributions using the VS Code Web
    Editor --** interactively step through the creation of your first
    Pull Request using a new simplified GitHub contribution tool. Create
    an account in GitHub and scan the Barcode from demo to pull up a
    page and repository to edit. Open VS Code in Web Editor, create a
    ReadMe-UserName.md (Markdown) file, commit (save) changes to GitHub,
    open and update Pull Request (PR) template and submit your PR!

-   **Create an event page in SharePoint with SharePoint Spaces and
    custom Lists --** see how Spaces, 4 lists, a timer web part and a
    quick links web part for UI supported by an Events list in the
    backend are blended to create a sharp Event page in SharePoint.
     Step through the Spaces embed, column formatting, list and list
    view set up for Sessions, Tracks, People and About Event.
    Informational pop ups, event filtering, registration and more.  

-   **Using Randomization with List Formatting --** render a randomly
    generated stack of informational cards with the last card in the
    list showing up at the top of the stack.  Whenever one visits the
    page hosting this list view - a "randomly shown fact card" will
    render. Randomization is based on the calculation of time in
    milliseconds - Number(@now) function. The resulting value is used
    to select an image.     

Thank you for your work. Samples are often showcased in Demos.   
Request a Demo spot on the call <https://aka.ms/m365pnp/request/demo>
## Topics
Topics covered in this call

-   PnP .NET library updates - [Bert
    Jansen](http://twitter.com/O365bert) (Microsoft) | @O365bert --
    [7:11](https://youtu.be/GW7THadNYtQ?t=431)
-   PnP PowerShell updates - [Bert Jansen](http://twitter.com/O365bert)
    (Microsoft) | @O365bert --
    [8:49](https://youtu.be/GW7THadNYtQ?t=529)
-   yo Teams updates - [Wictor Wilén](http://twitter.com/wictor)
    (Microsoft) |
    @wictor -- [10:28](https://youtu.be/GW7THadNYtQ?t=628)
-   Microsoft Graph Toolkit updates -[ Sébastien
    Levert](http://twitter.com/sebastienlevert) (Microsoft)
    | [sebastienlevert](https://github.com/sebastienlevert) -- [13:00](https://youtu.be/GW7THadNYtQ?t=780)
-   Microsoft Script Samples -[ Paul
    Bullock](http://twitter.com/pkbullock) (CaPa Creative Ltd) |
    @pkbullock -- [2:30](https://youtu.be/GW7THadNYtQ?t=150)
-   Microsoft Teams Samples - [David Warner
    II](http://twitter.com/DavidWarnerII) (Catapult Systems) |
    @DavidWarnerII -- [15:12](https://youtu.be/GW7THadNYtQ?t=912)
-   Microsoft Power Platform Samples - [David Warner
    II](http://twitter.com/DavidWarnerII) (Catapult Systems) |
    @DavidWarnerII -- [15:40](https://youtu.be/GW7THadNYtQ?t=940)
-   **Demo 1:  **[Contributors Corner - GitHub Contributions using the
    VS Code Web Editor -- ][David
    Warner](http://twitter.com/DavidWarnerII)[ (Catapult) |
    @DavidWarnerII ]--
    [17:26](https://youtu.be/GW7THadNYtQ?t=1046)
-   **Demo 2:**[  Create an event page in SharePoint with SharePoint
    Spaces and custom Lists -- ][Anand
    Ragav](http://twitter.com/anandVragav)[ |
    [@AnandVRagav](https://techcommunity.microsoft.com/t5/user/viewprofilepage/user-id/1101372) ]--
    [31:59](https://youtu.be/GW7THadNYtQ?t=1919)
-   [**Demo 3:**[  Using Randomization with List Formatting --
    ][Chris Kent](http://twitter.com/thechriskent)[
    (DMI) |
    @thechriskent ]]--
    [45:34](https://youtu.be/GW7THadNYtQ?t=2734)


## Resources

Additional resources around the covered topics and links from the
slides.

-   D1:  First Time Contributor training --
    [sharing-is-caring](https://github.com/pnp/sharing-is-caring) 

-   D1:  Website -- [Sharing Is
    Caring](https://pnp.github.io/sharing-is-caring/) |
    [pnp.github.io/sharing-is-caring/](https://pnp.github.io/sharing-is-caring/) 

-   D1:  Extension - [GitHub
    Repositories](https://marketplace.visualstudio.com/items?itemName=GitHub.remotehub) 

-   D2:  Article - [Create an event page with SharePoint, SharePoint
    Spaces and formatted
    Lists](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/create-an-event-page-with-sharepoint-sharepoint-spaces-and/ba-p/2994438) 

-   D3: Documentation -- [Use column formatting to customize
    SharePoint](https://docs.microsoft.com/sharepoint/dev/declarative-customization/column-formatting) 

-   D3:  Samples -- [List formatting
    samples](https://github.com/pnp/List-Formatting/tree/master/view-samples)
    \> random-item 

-   **PnP Weekly -- Episode 144** (November 22nd ) with Atlanta,
    US-based Senior Program Manager on the Viva Connections Platform
    team - [Catherine
    Chuaga](https://www.linkedin.com/in/wanjiru-chuaga/) | [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-144-catherine-chuaga-microsoft/ba-p/2994387) | [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-144-%e2%80%93-22nd-of-november-2021/)

-   **PnP Weekly -- Episode 143** (November 15th) with Nairobi,
    Kenya-based Program Manager at Microsoft - [Roina
    Ochieng](http://twitter.com/roinochieng) |
    @roinochieng | [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-143-roina-ochieng-microsoft/ba-p/2965580) | [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-143-%e2%80%93-15th-of-november-2021/)

## General resources

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
    API](https://developer.microsoft.com/microsoft-365/blogs/net-standard-version-of-sharepoint-online-csom-apis?WT.mc_id=m365-24198-cxa)
-   [Microsoft 365 community (PnP)
    videos](http://aka.ms/m365pnp-videos) | aka.ms/m365pnp-videos
-   [Microsoft Teams Toolkit for Visual Studio
    Code](https://marketplace.visualstudio.com/items?itemName=TeamsDevApp.ms-teams-vscode-extension)
-   [yo Teams](http://aka.ms/yoteams) | aka.ms/yoteams
-   Video - [Getting started using yo
    Teams](https://youtu.be/w0OrFkzNC10) | [Wictor
    Wilén](https://twitter.com/wictor) (Avanade)| @wictor
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


-   **Microsoft 365 platform call** -- November 30th at 8:00 am PST
    | <https://aka.ms/m365-dev-call>
-   **SharePoint Framework call** -- December 2nd at 7:00 am PST
    | <https://aka.ms/spdev-spfx-call>
-   **Office add-in monthly call** -- December 8th at 8:00 am PST
    | <https://aka.ms/officeaddinscall>
-   **M365 General Dev call** -- December 9th at 7:00 am PST
    | <https://aka.ms/m365-dev-sig>
-   **Adaptive Cards monthly call** --December 9th at 9:00 am PST
| <https://aka.ms/adaptivecardscommunitycall>

-   **Power Apps monthly call**-- December 15th at 8:00 am PST
    | <https://aka.ms/PowerAppsMonthlyCall>
-   **Microsoft Identity Platform call** -- December 16th at 9:00 am
    PST | <https://aka.ms/IDDevCommunityCalendar>
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

*Microsoft 365 PnP team, Microsoft - 26th of November 2021*
