---
title: "SharePoint Framework Community Call Recording -- 8th of April, 2021"
date: 2021-04-09T12:44:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Microsoft Viva and SPFx community call"]
images:
- images/8th-april-together-mode.gif
tags: []
type: "regular"
---

SharePoint Framework bi-weekly community call recording from April 8th
is now available from the Microsoft 365 Community YouTube channel
at <https://aka.ms/m365pnp-videos>. You can use SharePoint Framework for
building solutions for **Microsoft Viva**, **Microsoft Teams** and
for **SharePoint** Online.


## Call summary


Preview the new [Microsoft 365
Extensibility](https://aka.ms/m365/extensibility) look book gallery --
cross platform extensibility.  Update on upcoming SharePoint Framework
v1.12.1 features, preview, beta and release.  Register now for April
trainings on
[Sharing-is-caring](https://pnp.github.io/sharing-is-caring/).  Latest
project updates include:  **PnPjs Client-Side Libraries** v2.4.0 release
scheduled for April 9, and please provide feedback on v3.0 Hub planning
and discussion issues posted - [issue
1636](https://github.com/pnp/pnpjs/issues/1636) by April 15th.  **CLI
for Microsoft 365** Beta v3.9 delivered.   **Reusable SPFx React
Controls** -- v2.6.0 and v3.0.0 (on hold for SPFx v1.12.1) and
**Reusable SPFx React Property Controls** -- v2.5.0 and v3.0.0 (on hold
for SPFx v1.12.1).   **PnP SPFx Generator** v1.16.0 (Angular 11
supported), **PnP Modern Search** v3.19 to be released shortly and
v4.1.0 released March 20th.     There were eight **PnP SPFx web part
samples** delivered last 2 weeks.  Great work!    The host of this call
is [Patrick Rodgers](https://twitter.com/mediocrebowler) (Microsoft)
@mediocrebowler.  Q&A takes place in chat throughout the call.
![8th-april-together-mode.gif](images/8th-april-together-mode.gif)
 

-   Register for both:
        community at:  <https://aka.ms/pnpwatchparty>
    -   RSVP to attend - 2-hour livestream -- Building Apps for with
        Microsoft Graph -- 2 sessions -- 2:00pm AEST (Asia Pacific
        Region) and 8:30am PDT (North America & Europe Regions) |
        <https://aka.ms/learntogether-graph>
-   Reserve date - SharePoint Monthly community call - 13th of April,
    8 AM PDT | <https://aka.ms/sp-call>
-   Complete the Developer Success Survey -
    <https://aka.ms/developersuccess>
-   Join the M365 customer success platform panel -
    <https://aka.ms/SuccessPanel>
-   Register for Sharing is Caring Events:
    -   First Time Contributor Session -- [April
        27th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUREZVRDVYUUJLT1VNRDM4SjhGMlpUNzBORy4u)  
        (EMEA, APAC & US friendly times available)
    -   Community Docs Session
        -- [April](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUOUdFR0U1STdGS0lXUDA2Sk1YSE1WMEtHSy4u)
    -   PnP -- SPFx Developer Workstation Setup -- [April
        29th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUM0xJTFJZN01MWlZQVFc3UjgxRUxQQkhDSS4u)
    -   PnP SPFx Samples -- Solving SPFx version differences using Node
        Version Manager -- [April
        15th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUMDdKSjQxRDhKVzhCVUQ4VDdIQVZRVTZOSi4u)
    -   PnP -- AMA (Ask Me Anything) -- CLI for Microsoft 365 Edition --
        [April
        13](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUN1ZUQ0tFMTFLVUZaTjZXRjdPRk5XOEdSMy4u)th
    -   First Time Presenter - [April
        21st](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUNDJOOU5JREc2TUhCVzNGTTJFUldSUUNUSy4u)
    -   More than Code with VSCode -- [April 14th &
        28th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdURFZPM00xREdYMzVIOEJCWUhWRzBVMlRJWS4u)
    -   Maturity Model Practitioners -- [April
        20th](https://forms.office.com/Pages/ResponsePage.aspx?id=KtIy2vgLW0SOgZbwvQuRaXDXyCl9DkBHq4A2OG7uLpdUODY3NVRFQ0E4SFg5WlI1TU83WFJQRklZSy4u)
    -   PnP Office Hours -- 1:1 session -
        [Register](https://outlook.office365.com/owa/calendar/PnPSharingisCaring@warner.digital/bookings/)
-   Download the recurrent invite for this call
    -- <https://aka.ms/spdev-spfx-call>

## Demos

1.  **Teams Meeting Questionnaire App with SharePoint Framework** -- The
    Questionnaire Pre-meeting app allows Microsoft Teams meeting
    attendees to ask questions related to meeting before meeting
    starts.  SPFx v1.12 provides support for Microsoft Teams meeting
    apps development, this web part.   Operationally -- in calendar
    create meeting, then add Meeting Questionnaire tab to meeting.
     Questionnaire is tied to a single SharePoint list that organizes
    questions by Meeting ID.   Sample in PnP Samples repository.

2.  **Building an advanced SPFx Image Editor web part** - This solution
    contains an SPFx web part - a browser-based HTML Image Editor that
    uses canvas and Office UI Fabric.  Use File Picker component to
    select image and manipulate it -- Resize, Crop, Flip, Rotate, Scale,
    Filter (Grayscale / Sepia), Redo / Undo, History of Actions.  Web
    part created initially to pick files from a custom external data
    source.  Sample is in Sample Gallery.

3.  **Viva Connections Desktop and Extensibility** - Microsoft Viva is a
    suite of products.  Viva Connections is an integrated experience
    with Microsoft Teams and SharePoint backed by Microsoft security,
    privacy, and compliance.  Viva Connections is extensible -- use out
    of the box web parts or create custom web parts and extensions based
    on requirements.  You ultimately determine what capabilities to make
    available in the Viva Connections UX.  The journey -- a phased
    rollout of capabilities Worldwide over the next 6 months. Currently
    available Viva Connections Desktop is just a start on this journey.



**SPFx extension samples:  (<https://aka.ms/spfx-extensions>)**

</div>

-   **[Send to
    Teams](https://github.com/pnp/sp-dev-fx-extensions/tree/master/samples/react-send-to-teams)** -
    [João Mendes](https://twitter.com/joaojmendes)
    | [joaojmendes](https://github.com/joaojmendes)

**SPFx web part samples:  (<https://aka.ms/spfx-webparts>)**

-   [**Calendar**](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-calendar) -
    [Mohammad Amer ](https://twitter.com/Mohammad3mer)| @Mohammad3mer

-   **[Staff
    Directory](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-staffdirectory)** -
    [Ari Gunawan](https://twitter.com/AriGunawan) | @AriGunawan

-   **[Advanced Page
    Properties](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-advanced-page-properties)**
    -- [Mike Homol](https://twitter.com/homol) (ThreeWill) | @homol

-   **[Datatable](https://github.com/pnp/sp-dev-fx-webparts/blob/master/samples/react-datatable)** -
    [Chandani
    Prajapati](https://twitter.com/Chandani_SPD) | @Chandani_SPD

-   **[Company
    Stories](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-company-stories)** -
    [Luis Mañez](https://twitter.com/luismanez) | @luismanez

-   **[Video
    Banner](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-video-banner)** -
    [Mohamed
    Derhalli](https://twitter.com/MohamedDerhalli) | @MohamedDerhalli

-   **[Document Card
    FAQ](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-doccard-faq)** -
    [Sam
    Collins](https://twitter.com/samc148) | @SamCollins

As is the case this week, samples are often showcased in Demos.  Thank
you for your great work.

## Agenda items

-   Latest updates on SharePoint Framework - [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen --[ 5:41](https://youtu.be/PJ4aUybRrQo?t=341)
-   PnPjs Client-Side Libraries - [Julie
    Turner](https://twitter.com/jfj1997) (Sympraxis Consulting) |
    @jfj1997 -- [7:59](https://youtu.be/PJ4aUybRrQo?t=479)
-   CLI for Microsoft 365 - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [9:19](https://youtu.be/PJ4aUybRrQo?t=559)
-   PnP SPFx Controls - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [10:11](https://youtu.be/PJ4aUybRrQo?t=611)
-   PnP SPFx Generator - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [11:22](https://youtu.be/PJ4aUybRrQo?t=682)
-   PnP Modern Search - [Patrick
    Rodgers](https://twitter.com/mediocrebowler) (Microsoft) |
    @mediocrebowler -- [12:21](https://youtu.be/PJ4aUybRrQo?t=741)
-   PnP SPFx Samples - [Hugo
    Bernier](https://twitter.com/bernierh) (Tahoe Ninjas) |
    @bernierh -- [13:09](https://youtu.be/PJ4aUybRrQo?t=789)

## Demos

-   Teams Meeting Questionnaire App with SharePoint Framework --
    [Nanddeep Nachan](https://twitter.com/NanddeepNachan) |
    [nanddeepn](https://github.com/nanddeepn) --
    [17:09](https://youtu.be/PJ4aUybRrQo?t=1029)

-   Building an advanced SPFx Image Editor web part -- [Peter Paul
    Kirschner](https://twitter.com/petkir_at) (cubido) |
    @petkir\_at --
    [31:05](https://youtu.be/PJ4aUybRrQo?t=1865)

-   Viva Connections Desktop and Extensibility -- [Vesa
    Juvonen](https://twitter.com/vesajuvonen) (Microsoft) |
    @vesajuvonen -- [39:29](https://youtu.be/PJ4aUybRrQo?t=2369)


## Resources

Additional resources around the covered topics and links from the
slides.

-   [The presentation used for this community
    call](https://1drv.ms/p/s!AlposW7ozA_90j1Nf8PdUVrTlT7X?e=3Slj4d)

-   Gallery - [Microsoft 365 Extensibility look book
    gallery](https://aka.ms/m365/extensibility) 

-   Blog -  [Build Microsoft Teams meeting app with
    SPFx](https://nanddeepnachanblogs.com/posts/2021-03-22-build-ms-teams-meeting-app-with-spfx/)

-   Repo - [Questionnaire Teams Meeting
    App](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-teams-meeting-app-questionnaire)

-   Blog - [Support Microsoft Teams Themes in SharePoint Framework
    Solutions](https://blog.aterentiev.com/support-microsoft-teams-themes-in) 

-   Documentation - [Create apps for Teams
    meetings](https://docs.microsoft.com/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings)

-   Repo - [React Image
    Editor](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-image-editor) 

-   Blog Post - [Install Viva Connections
    today](https://techcommunity.microsoft.com/t5/microsoft-viva-blog/install-viva-connections-today/ba-p/2245410) 

-   Look book - [SharePoint look book](https://lookbook.microsoft.com/) 

-   Documentation - [Embedding modern SharePoint pages in Microsoft
    Teams as personal apps
    (preview)](https://docs.microsoft.com/sharepoint/dev/features/embed-pages-to-teams) 

-   PnP Weekly -- Episode 121 with guest Senior Program Manager from
    Microsoft Graph team [Nik
    Charlebois](https://twitter.com/NikCharlebois) | @NikCharlebois 
    |
    [video](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-121-6th-of-april-2021/)
    |
    [podcast](https://pnpweekly.podbean.com/e/microsoft-365-pnp-weekly-episode-119-22nd-of-march-2021/)

-   Viva Connections <https://aka.ms/VivaConnections> 

## General resources

-   [CLI for Microsoft 365
    v3](https://developer.microsoft.com/office/blogs/cli-microsoft-365-3/)
-   [CodeTour](https://aka.ms/codetour)
-   [Sharing is Caring](https://aka.ms/sharing-is-caring) |
    aka.ms/sharing-is-caring
-   [PnP Modern Search](https://aka.ms/pnp-search) | aka.ms/pnp-search
-   [M365 PnP site](https://aka.ms/m365pnp) | aka.ms/m365pnp
-   [SharePoint Starter Kit
    v2](https://github.com/pnp/sp-starter-kit/tree/v2)
-   Blog: "[A Lap Around Microsoft Graph Toolkit" blog
    series](https://aka.ms/mgtLap)
-   [New Microsoft 365 Patterns and Practices (PnP) team model with new
    community
    leads](https://developer.microsoft.com/microsoft-365/blogs/new-microsoft-365-patterns-and-practices-pnp-team-model-with-new-community-leads/)
-   [Microsoft 365 Community
    Content](https://aka.ms/m365-community-docs) (non-Dev docs)
-   [PnP SPFx web part samples](https://aka.ms/spfx-webparts)
-   [PnP SPFx extension samples](https://aka.ms/spfx-extensions)
-   [GitHub PnPjs](https://github.com/pnp/pnpjs/)
-   Tutorials - [Getting started with SharePoint Framework v1.10
    Tutorials](https://www.youtube.com/playlist?list=PLR9nK3mnD-OXvSWvS2zglCzz4iplhVrKq) (12
    videos)
-   Tutorials - [Getting started with SharePoint Framework v1.10
    Extensions](https://www.youtube.com/playlist?list=PLR9nK3mnD-OXtWO5AIIr7nCR3sWutACpV) (6
    videos)
-   Docs - [Tutorials and training material for SharePoint
    Development](https://docs.microsoft.com/sharepoint/dev/training/training/?wt.mc_id=YT_CCrecording)
-   [SPFX Training Package](https://aka.ms/spfx-training)
-   [SPFx Web Parts](https://aka.ms/spfx-webparts)
-   [SPFx Extensions](https://aka.ms/spfx-extensions)
-   [SPFx Library Components](https://aka.ms/spfx-library-components)
-   Documentation - [PnPjs v2
    documentation](https://pnp.github.io/pnpjs/)
-   Link - [Microsoft 365 developer
    training](https://aka.ms/M365DevTraining)
-   Link - [Office 365 Developer Program](https://aka.ms/O365DevProgram)
-   [Latest documentation on SharePoint
    Framework](https://aka.ms/spdev-docs)
-   Found an issue with SharePoint Dev? - please let us know
    at <https://aka.ms/spdev-issues>
-   [Reusable web part property
    controls](https://sharepoint.github.io/sp-dev-fx-property-controls/)
-   [Reusable react controls for SharePoint Framework
    solutions](https://sharepoint.github.io/sp-dev-fx-controls-react/)
-   [Reusable controls
    webcast](https://devblogs.microsoft.com/microsoft365dev/webcast-reusable-controls-for-your-sharepoint-framework-solutions/)
-   [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365)
-   [PnP SPFx Yeoman Generator](https://github.com/pnp/generator-spfx) -
    Extends the out-of-the-box experience with open-source community
    capabilities
-   [SharePoint Dev UserVoice](https://aka.ms/spdev-uservoice) - for new
    feature requests

## Other topics mentioned

-   [SharePoint dev
    documentation](https://docs.microsoft.com/sharepoint/dev/)
-   [SharePoint dev issue
    list](https://github.com/SharePoint/sp-dev-docs/issues)


## Upcoming Calls | Recurrent Invites


-   **SharePoint monthly call --** April 13th at 8:00am PDT |
    <https://aka.ms/sp-call>
-   **Office add-in monthly call --** April 14th at 8:00 am PDT |
    [https://aka.ms/officeaddinscall](https://aka.ms/officeaddinscommunitycall)
-   **M365 General Dev call --** April 15th at 7:00 am PDT |
    <https://aka.ms/m365-dev-sig>
-   **Microsoft Identity Platform --** April 15th at 9:00 am PDT |
    <https://aka.ms/IDDevCommunityCalendar> 
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
-   **Adaptive Cards monthly call --** May 13th at 9:00 am PDT |
    <https://aka.ms/adaptivecardscommunitycall>
PnP SharePoint Framework Special Interest Group bi-weekly calls are
targeted at anyone who is interested in the JavaScript-based development
towards Microsoft Teams, SharePoint Online, and also on-premises. SIG
calls are used for the following objectives.

-   SharePoint Framework engineering update from Microsoft
-   Talk about PnP JavaScript Core libraries
-   CLI for Microsoft 365 Updates
-   SPFx reusable controls
-   PnP SPFx Yeoman generator
-   Share code samples and best practices
-   Possible engineering asks for the field - input, feedback, and
    suggestions
-   Cover any open questions on the client-side development
-   Demonstrate SharePoint Framework in practice in Microsoft Teams or
    SharePoint context
-   You can download a recurrent invite
    from <https://aka.ms/spdev-spfx-call>. Welcome and join the
    discussion!

*"Sharing is caring"*

