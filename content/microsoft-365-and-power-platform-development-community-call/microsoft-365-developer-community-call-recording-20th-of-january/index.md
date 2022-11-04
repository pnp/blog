---
title: "Microsoft 365 Developer Community Call recording -- 20th of January, 2021"
date: 2022-01-21T01:14:00-05:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/recording-20th-jan.png
tags: []
type: "regular"
summary: "One location the Microsoft 365 tenant – script samples gallery (134 scenarios and 182 scripts) including recently added Teams PowerShell support!  Sign up and attend an AMA and other events this month hosted by Sharing is Caring.  At the same time, sign up for the PnP Recognition Program.  Heads down on PnP projects.  Check out the TeamsFx authentication provider preview in MGT!  To see current releases and latest updates/nightly builds, access the Repos via the links in table below.  There were 7 new/updated script, 5 Power Platform samples delivered this week.   Wanted! – Teams Samples."
---

## Call summary

- One location the Microsoft 365 tenant -- [script samples
gallery](https://aka.ms/script-samples) (134 scenarios and 182 scripts)
including recently added Teams PowerShell support!  
- Sign up and attend
an AMA and other events this month hosted by [Sharing is
Caring](https://pnp.github.io/sharing-is-caring/).  At the same time,
sign up for the [PnP Recognition
Program](https://aka.ms/m365pnp-recognition).  
- Heads down on PnP
projects.  
- Check out the TeamsFx authentication provider preview in
**MGT**!  
- To see current releases and latest updates/nightly builds,
access the Repos via the links in table below.  
- There were 7 new/updated
script, 5 Power Platform samples delivered this week.   
- Wanted! -- Teams
Samples.

## Open-source project status

(**Bold** indicates new this call)

**Project**|**Current Version**|**Release/Status**
---|---|--- 
PnP .NET Libraries - [PnP Framework](https://github.com/pnp/pnpframework) |v1.8.0 GA with .NET 6.0 support added|Prepping v1.9
PnP .NET Libraries - [PnP Core SDK](https://github.com/pnp/pnpcore/tree/dev)|v1.5.0 GA with .NET 6.0 support added|Prepping v1.6
[PnP PowerShell](https://github.com/pnp/PnP-PowerShell)|v1.9.0 GA|In progress: V2 POC, Prepping for v1.8, nightly releases
[Yo teams - generator-teams](https://github.com/pnp/generator-teams/tree/master/packages/generator-teams)|v3.5.0 GA|v4.0.0-next
[Yo teams - yoteams-build-core](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-build-core)|v1.5.0 GA, Next: v1.6.0-next.1                             
[Yo teams -- yoteams-deploy](https://github.com/pnp/generator-teams/tree/master/packages/yoteams-deploy)|v1.1.0 GA                                                  
[Yo teams - msteams-react-base-component](https://github.com/wictorwilen/msteams-react-base-component)|v3.1.1                                                     
[Microsoft Graph Toolkit (MGT)](https://github.com/microsoftgraph/microsoft-graph-toolkit)|v2.3.1 GA, **TeamsFx authentication provider preview!**|Preparing v2.3.1 release, working on v3.0.0 - Aligning all Toolkit components to Fluent UI Web Components

{{< notice note>}}
While version releases are periodic, nightly releases are nightly!  Subscribe to nightly releases for the latest capabilities.
{{< /notice >}}

The host of this call was [David Warner
II](https://twitter.com/DavidWarnerII) (Catapult Systems) |
@DavidWarnerII.   Q&A takes place in chat throughout the call.

-   Opt into PnP Recognition Program
    | [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
-   Join us at the next **Microsoft 365 platform call 25th of January
    @ 8 AM PT**
    -   Latest news from Microsoft engineering on Microsoft 365 topics
    -   Demos: 
        -   **Arvind Ravi** -- Latest with Microsoft Graph connectors
        -   **Patrick Rodgers** -- Best practices on building Viva
            Connections extensibility
        -   **Sébastien Levert** -- Introduction to Microsoft Graph
            Toolkit control
- **Register for Sharing is Caring Events:**
    -   PnP Sharing is Caring - AMA (Ask Me Anything) - SPFx React
        Controls -- [Tuesday, February 22nd, 9am
        PST](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNjg1UVhPV0JHTjRLNDZISkM4MEI0VDZWSC4u)
    -   PnP Sharing is Caring - AMA (Ask Me Anything) \-- Microsoft
        Graph Toolkit - [Tuesday, March 1st, 9am
        PST](https://forms.office.com/pages/responsepage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNVNHNlhNTkczNjRKM0hZR1NWVUw2QUhRQi4u)
    -   First Time Contributor Session -- [Tuesday, January 25th, 2pm
        PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
    -   Community Docs Session -- 2022 Sessions Coming Soon  
    -   Power Platform Samples -- First Time Contributor -- [Tuesday,
        January 25th, 2pm
        PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)
    -   PnP -- SPFx Developer Workstation Setup -- [Tuesday, February
        8th, 2pm
        PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [Wednesday, January 26th, 7am
        PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   First Time Presenter -- [Wednesday, February 9th, 9am
        PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- [Tuesday, February 15th, 2pm
        PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
    -   Maturity Model Practitioners -- [Tuesday, February 15th, 7am
        PST](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
        (every 3rd Tuesday of month, 7:00am PT)
    -   Getting Started with Viva Connection ACEs (2-part session) --
        TBS soon
    -   PnP Office Hours -- 1:1 session --
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
    -   PnP Buddy System -- [Request a
        Buddy](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMjRRUVg4NElZUUJLTEY1TVVSVDJFRFpLRS4u)
-   Download the recurrent invite for this call
    -- <https://aka.ms/m365-dev-sig>
-   Call attention to your great work by using
    the [#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click) on
    Twitter.

## Microsoft Teams Development Samples

(<https://aka.ms/TeamsSampleBrowser>)

-   Wanted!  Teams Samples

## Microsoft Power Platform Samples

(<https://aka.ms/powerplatform-samples>)

-   [**COVID Vaccine Survey
    App**](https://github.com/pnp/powerapps-samples/tree/main/samples/covid-vaccine-survey) -
    [Siddharth Vaghasia ](https://twitter.com/siddh_me)| @siddh_me &
    Mayuresh Joshi
-   [**Employee Tip of the Day
    Flow**](https://github.com/pnp/powerautomate-samples/tree/main/samples/new-employee-tip-of-the-day) -
    [Adam Wójcik](https://twitter.com/Adam25858782) | @Adam25858782
-   [**Icon Button
    Component**](https://github.com/pnp/powerapps-samples/tree/main/samples/icon-button-component) -
    Pavel Kovalevskij 
-   **JSON Object to Power Fx Table Function** - [Bartolome
    Sorrentino ](https://twitter.com/bsorrentinoJ)| @bsorrentinoJ
-   [**Power
    Wordle**](https://github.com/pnp/powerapps-samples/tree/main/samples/power-wordle-game) -
    [April Dunnam](https://twitter.com/aprildunnam) | @aprildunnam

## Script Samples

<https://aka.ms/script-samples>

4 new scenarios and 3 script updates contributed by

-   [Adam Wójcik](https://twitter.com/Adam25858782) | @Adam25858782
-   [Chandani Prajapati](https://twitter.com/Chandani_SPD) |
    @Chandani_SPD
-   [Ganesh Sanap](https://twitter.com/GaneshSanap20) | @GaneshSanap20
-   [Kunj Balkrishna Sangani](https://twitter.com/sanganikunj) |
    @sanganikunj
-   [Kasper Bo Larsen](https://twitter.com/kasperbolarsen) |
    @kasperbolarsen
-   [Leon Armston](https://twitter.com/LeonArmston) |
    @LeonArmston
-   [Reshmee Auckloo](https://twitter.com/ReshmeeAuckloo) |
    @reshmeeauckloo

Blog: [Getting started with PnP Script Samples](https://aka.ms/script-samples/getting-started) -- aka.ms/script-samples/getting-started

-- Many thanks!


## Demos

Demos delivered in this session

### Getting started on building a Microsoft Teams bot with yo teams

what is yo teams (a Microsoft Teams app generator) and how to use it to
build a bot.  After installing Yeoman generator and Gulp CLI task
manager, install npm i -g generator-teams.  Create a project.  In VS
Code step through files generated by yo teams.  Use gulp build, gulp
manifest and gulp serve.  Upload created bot to Teams site and
appreciate its out-of-box capabilities.    

### Microsoft List Formatting - Challenges and Solutions

appreciate results of one person's winter lock down -- List
Formatting samples categorized by emotions, multiple person, color
picker, bar option, slider, and Teams Group.  Solutions include
discussion board, events mobile and payment.  Graphical tree along with
LABs (show how handle manual actions from users) for Tic Tac Toe and
roll dice.  UI/script shown on slides, live in demo.   Samples available
in List Formatting Repo soon. 

### Updates on Independent Publisher Connectors & GoQR Connector Demo

49 connectors in production, 40 in pipeline today!  The GoQR connector
generates QR codes.  In Power Apps, render the QR Code image alone or
embed the QR code image in a document or pdf, i.e., an invoice.  Simple
build - a text field, a button (calls connector with action create) and
a flow.   This connector is now available to anyone in the world. 
Thank you for your work. Samples are often showcased in Demos.   
Request a Demo spot on the call <https://aka.ms/m365pnp/request/demo>

## Topics

Topics covered in this call

-   PnP .NET library updates - [Bert
    Jansen](https://twitter.com/O365bert) (Microsoft) | @O365bert --
    [7:01](https://youtu.be/o81Xah0o-xI?t=421)
-   PnP PowerShell updates - [Bert
    Jansen](https://twitter.com/O365bert) (Microsoft) |
    @O365bert -- [8:33](https://youtu.be/o81Xah0o-xI?t=513)
-   yo Teams updates - [Stephan
    Bisser](https://twitter.com/stephanbisser) (Solvion) |
    @stephanbisser -- [9:44](https://youtu.be/o81Xah0o-xI?t=584)
-   Microsoft Graph Toolkit updates - [Sébastien
    Levert](https://twitter.com/sebastienlevert) (Microsoft) |
    @sebastienlevert -- [11:57](https://youtu.be/o81Xah0o-xI?t=717)
-   Microsoft Script Samples - [Paul
    Bullock](https://twitter.com/pkbullock) (CaPa Creative Ltd) |
    @pkbullock -- [2:33](https://youtu.be/o81Xah0o-xI?t=153%20)
-   Microsoft Teams Samples - [David Warner
    II](https://twitter.com/DavidWarnerII) (Catapult Systems) |
    @DavidWarnerII -- [13:39](https://youtu.be/o81Xah0o-xI?t=819)
-   Microsoft Power Platform Samples - [April
    Dunnam](https://twitter.com/aprildunnam) (Microsoft) | @aprildunnam
    -- [13:56](https://youtu.be/o81Xah0o-xI?t=836)
-   **Demo 1**:  Getting started on building a Microsoft Teams bot with
    yo teams -- [Stephan Bisser](https://twitter.com/stephanbisser)[
    (Solvion) | @stephanbisser ]--
    [16:14](https://youtu.be/o81Xah0o-xI?t=974)
-   **Demo 2**[:  Microsoft List Formatting - Challenges and solutions
    --]** **[André
    Lage](https://twitter.com/aaclage)[ (Datalynx AG) | @aaclage --
    [28:44](https://youtu.be/o81Xah0o-xI?t=1724)]
-   [**Demo 3**[:  Updates on Independent Publisher Connectors & GoQR
    Connector Demo -- ][Natalie
    Pienkowska](https://twitter.com/NataliePienkow1)[ (Microsoft) |
    @NataliePienkow1 & ][Rui
    Santos](https://www.linkedin.com/in/ruisantosnor/)[
    (Microsoft) ]]-- [47:41](https://youtu.be/o81Xah0o-xI?t=2861)


## Resources

Additional resources around the covered topics and links from the
slides.

-   **D1**:  Repo - [Microsoft Teams App Project Generator -
    #YoTeams](https://github.com/pnp/generator-teams) | aka.ms/yoteams

-   **D1**:  Documentation - [Yo Teams - the Microsoft Teams app
    generator](https://pnp.github.io/generator-teams/) 

-   **D1**:  Documentation - [Single sign-on (SSO) support for
    bots](https://docs.microsoft.com/microsoftteams/platform/bots/how-to/authentication/auth-aad-sso-bots) 

-   **D2**:  List Formatting Samples - [List Formatting
    Samples](https://pnp.github.io/List-Formatting/) 

-   **D3**:  Documentation - [GoQR (Independent Publisher)
    (Preview)](https://docs.microsoft.com/connectors/goqr/) 

-   **D3**:  Repo --
    [GoQR](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors/GoQR) 

-   **D3**:  Connectors - [Welcome to the Independent Publisher
    Connector
    Directory!](https://github.com/microsoft/PowerPlatformConnectors/tree/dev/independent-publisher-connectors)

-   **PnP Weekly -- Episode 149** (January 17th) with Brisbane,
    Queensland, Australia-based Cloud Developer Advocate for Microsoft
    Teams and Graph, [Rabia
    Williams](https://twitter.com/williamsrabia) (Microsoft) |
    @williamsrabia | [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-149-rabia-williams-microsoft/ba-p/3063869) | [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-149-%E2%80%93-17th-of-january-2022/)

-   **PnP Weekly -- Episode 148** (January 9th) with Belgium-based
    Power Platform Architect and Business Applications MVP, [Carmen
    Ysewijn](https://twitter.com/CarmenYsewijn) (Qubix) |
    @CarmenYsewijn | [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-148-carmen-ysewijn-qubix/ba-p/3056063) | [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-148-%E2%80%93-10th-of-january-2022/) 

## General resources

-   Script Samples - [Getting started with PnP Script
    Samples](https://aka.ms/script-samples/getting-started) --
    aka.ms/script-samples/getting-started
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
-   Microsoft Teams Toolkit v3.x | <https://aka.ms/teams-toolkit>
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
-   [SharePoint Page Transformation webcast
    series](https://developer.microsoft.com/sharepoint/blogs/sharepoint-page-transformation-webcast-series?WT.mc_id=m365-24198-cxa)
-   [PnP Power Shell](https://aka.ms/sppnp-powershell)
-   [SharePoint Modernization
    Tools](https://github.com/SharePoint/sp-dev-modernization/tree/dev/Tools)

## Upcoming Calls | Recurrent Invites


-   **Microsoft 365 platform call** **--** January 25th at 8:00 am PST
    | <https://aka.ms/m365-dev-call>
-   **Viva Connections & SharePoint Framework call --** January
    27th at 7:00 am PST | <https://aka.ms/spdev-spfx-call>
-   **M365 General Dev call** -- February 3rd at 7:00 am PST
    | <https://aka.ms/m365-dev-sig>
-   **Office add-in monthly call** -- February 9th at 8:00 am PST
    | <https://aka.ms/officeaddinscall>
-   **Adaptive Cards monthly call** --February 10th at 9:00 am PST
| <https://aka.ms/adaptivecardscommunitycall>

-   **Power Apps monthly call**-- February 16th at 8:00 am PST
    | <https://aka.ms/PowerAppsMonthlyCall>
-   **Microsoft Identity Platform call** -- February 17th at 9:00 am
    PST | <https://aka.ms/IDDevCommunityCalendar>

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

*Microsoft 365 Community (PnP) team, Microsoft - 21st of January 2022*
