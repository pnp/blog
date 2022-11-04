---
title: "Microsoft 365 Developer Community Call recording -- 15th of April, 2021"
date: 2021-04-16T04:18:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft 365 and Power Platform Development Community Call"]
images:
- images/sig-agenda-15th-recording.png
tags: []
type: "regular"
---



## Call summary




Latest news from Microsoft 365 engineering and updates on open-source
projects: PnP .NET libraries, PnP PowerShell, modernization tooling, on
yo Teams, on Microsoft Graph Toolkit, and on Microsoft Teams Samples.
The [Microsoft 365 developer community
survey](https://aka.ms/m365pnp/survey) is now open, visit the [Microsoft
Teams samples gallery](https://aka.ms/teams-samples) to get started with
Microsoft Teams development, preview the new [Microsoft 365
Extensibility look book gallery](https://aka.ms/m365/extensibility), and
register now for April trainings on
[Sharing-is-caring](https://pnp.github.io/sharing-is-caring/).  Recent
PnP project updates include - **PnP .NET Libraries** - **PnP Framework**
v1.4.0 and **PnP Core SDK** v1.1.0 and **PnP PowerShell** v1.5.0 (new
commandlets for Microsoft Viva Connections and Syntex).   **yo Teams**
***generator-teams*** (apps generator) v3.0.3 GA and 3.1.0 Preview,
***yo teams-build-core*** (gulp tasks) v1.0.1 + v1.1.0 Preview, and
***msteams-react-base-component*** (React UI helpers) v3.1.0, have been
released.   **Microsoft Graph Toolkit** try out the new OneDrive file
components (Preview).   The host of this call was [Vesa
Juvonen](https://twitter.com/vesajuvonen) (Microsoft) | @vesajuvonen.
 Q&A takes place in chat throughout the call.

## Actions

-   [Microsoft 365 Developer Community
    Survey](https://aka.ms/m365pnp/survey) --
    <https://aka.ms/m365pnp/survey>
-   Try public beta of SPFx v1.12.1. 
-   Register for Sharing is Caring Events:
    -   First Time Contributor Session -- [April
        27th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)  
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session
        -- [April](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    -   PnP -- SPFx Developer Workstation Setup -- [April
        29th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- May
    -   AMA (Ask Me Anything) -- May 2021 -- Tech Community -- [May
        11th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUQlpKUUlUUUtFR1VTSUxUVzI3NUs5SzhNWC4u)
    -   First Time Presenter - [April
        21st](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- [April
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
    -   Maturity Model Practitioners -- [April
        20th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    -   PnP Office Hours -- 1:1 session -
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
-   Download the recurrent invite for this call
    -- <https://aka.ms/m365-dev-sig>
-   Call attention to your great work by using
    the [#PnPWeekly](https://twitter.com/hashtag/PnPWeekly?src=hashtag_click) on
    Twitter.
**Microsoft Teams Development
Samples:  **(<https://aka.ms/TeamsSampleBrowser>)

## Demos

Demos delivered in this session

-   **SharePoint Content Type APIs in Microsoft Graph** - Classic
    SharePoint APIs are now showing up in Microsoft Graph.   In this
    demo, step through beta API methods, properties and responses for
    creating a content type (CT), adding CT to list, adding a column,
    copying to default location, updating a CT, publishing a CT, and
    associating CT to a hub site.  API permission requirements are
    called out and differ slightly by API.    

-   **Live London Underground Line Status Bot in Microsoft Dataverse for
    Teams** -- the next stage in the evolution of the presenter's Tube
    Status solution.  An interactive Tube bot in Power Virtual Agents,
    using Power Automate, and configuring your Azure environment for
    Azure API Management and Azure Functions.  Dataverse for Teams
    allows users to leverage Azure API Management service using a custom
    connector in Power Platform.   See solution architecture, execution
    triggers, rules, calls and more.   

-   **Microsoft list formatting with header and footer settings** -- we
    are reminded that there are layers of formatting options for lists
    and that there is sample code for each layer.  Here we look at
    header and footer settings, for groups and entire list, beyond the
    vanilla capabilities delivered 2 weeks ago.   This session looks at
    Collapsed Simple formatting used for Q&A.  Uses groupProps,
    aggregates, hiding, tips on double nesting and more.      

Thank you for your work. Samples are often showcased in Demos.

## Topics

Topics covered in this call

-   PnP .NET library updates - [Bert
    Jansen](https://twitter.com/o365bert) (Microsoft) | @O365bert
    - [6:51](https://youtu.be/HarfeUb-3TY?t=411)

-   PnP PowerShell updates - [Bert
    Jansen](https://twitter.com/o365bert) (Microsoft) |
    @O365bert - [9:26](https://youtu.be/HarfeUb-3TY?t=566)

-   yo Teams updates - [Wictor
    Wilén](https://twitter.com/wictor) (Avanade) @wictor -
    [10:42](https://youtu.be/HarfeUb-3TY?t=642)

-   Microsoft Graph Toolkit updates - [Beth
    Pan](https://twitter.com/beth_panx) (Microsoft)
    | [beth-panx](https://github.com/beth-panx) - [12:16](https://youtu.be/HarfeUb-3TY?t=736)

-   Microsoft Teams Samples - [Bob
    German](https://twitter.com/Bob1German) (Microsoft) |
    @Bob1German - [13:53](https://youtu.be/HarfeUb-3TY?t=833)

-   **Demo:**  SharePoint Content Type APIs in Microsoft Graph - Swapnil
    Shrivastava (Microsoft) -
    [16:07](https://youtu.be/HarfeUb-3TY?t=967)

-   **Demo:**  Live London Underground Line Status Bot in Microsoft
    Dataverse for Teams - [Leon Armston](https://twitter.com/LeonArmston)
    (Intelogy) |
    @LeonArmston -
    [25:18](https://youtu.be/HarfeUb-3TY?t=1518)

-   **Demo:**  Microsoft list formatting with header and footer
    settings - [Chris Kent](https://twitter.com/theChrisKent) (DMI) |
    @theChrisKent - [41:29](https://youtu.be/HarfeUb-3TY?t=2489)

     


## Resources

Additional resources around the covered topics and links from the
slides.

-   [Slides used in this ​community
    call](https://1drv.ms/p/s!AlposW7ozA_90j_0wCE_XEVxYoZQ?e=5YX8v4)

-   Documentation - [contentType resource
    type](https://docs.microsoft.com/graph/api/resources/contenttype?view=graph-rest-beta?WT.mc_id=m365-24198-cxa) 

-   Blog -- [Create a London Underground Line Status Bot using Power
    Virtual Agents & Azure Management API in
    Dat\...](https://www.leonarmston.com/2021/02/create-a-london-underground-line-status-bot-power-virtual-agents-azure-azure-management-api-in-dataverse-for-teams/) 

-   Blog - [Azure API Management connector on the Power
    Platform](https://powerapps.microsoft.com/blog/azure-api-management-connector-on-the-power-platform/) 

-   Documentation - [Use column formatting to customize
    SharePoint](https://docs.microsoft.com/sharepoint/dev/declarative-customization/column-formatting?WT.mc_id=m365-15744-cxa) 

-   Documentation - [Use view formatting to customize
    SharePoint](https://docs.microsoft.com/sharepoint/dev/declarative-customization/view-formatting?WT.mc_id=m365-24198-cxa) 

-   Repo - [SharePoint List Formatting
    Samples](https://github.com/pnp/List-Formatting) 

-   PnP Weekly -- Episode 122 with guest MVP [Mark
    Rackley](https://twitter.com/mrackley) (PAIT Group) | @mrackley|
    [video](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/microsoft-365-pnp-weekly-episode-122/ba-p/2268519)
    |
    [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-122-12th-of-april-2021/)

-   Microsoft Graph Toolkit in Microsoft Learn |
    <https://aka.ms/learn-mgt>

-   [Microsoft 365 PnP Community
    hub](https://techcommunity.microsoft.com/t5/microsoft-365-pnp/ct-p/Microsoft365PnP)
    | aka.ms/m365pnp/community 

-   [Microsoft 365 Extensibility look book
    gallery](https://adoption.microsoft.com/extensibility-look-book?WT.mc_id=m365-24198-cxa)
    | aka.ms/m365/extensibility

-   [Microsoft Teams Samples
    Gallery](https://pnp.github.io/teams-dev-samples/) |
    aka.ms/teams-samples

-   Viva Connections <https://aka.ms/VivaConnections>


## General resources

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


-   **M365 General Dev call --** April 15th at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Microsoft Identity Platform --** April 15th at 9:00 am PDT
    |<https://aka.ms/IDDevCommunityCalendar> 
-   **Microsoft Teams monthly call --** April 20th at 8:00 am PDT |
    <https://aka.ms/microsoftteamscommunitycall>
-   **Power Apps monthly call --** April 21st at 8:00 am PDT |
    <https://aka.ms/PowerAppsMonthlyCall>
-   **SharePoint Framework call** -- April 22nd at 7:00 am PDT |
    <https://aka.ms/spdev-spfx-call>
-   **M365 General Dev call --** April 29th at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Microsoft Graph call -** May 4th at 8:00 am PDT |
    <https://aka.ms/microsoftgraphcall>
-   **SharePoint monthly call --** May 11th at 8:00am PDT |
    <https://aka.ms/sp-call>
-   **Office add-in monthly call --** May 12th at 8:00 am PDT |
    [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscommunitycall)
-   **Adaptive Cards monthly call --** May 13th at 9:00 am PDT |
    <https://aka.ms/adaptivecardscommunitycall>

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

*Microsoft 365 PnP team, Microsoft - 16th of April 2021*
