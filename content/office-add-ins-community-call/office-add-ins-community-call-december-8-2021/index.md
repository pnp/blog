---
title: "Office Add-ins community call -- December 8, 2021"
date: 2021-12-16T03:51:00-05:00
author: "David Chesnut"
githubname: davidchesnut

categories: ["Office add-in developer community call"]
images:
- images/office-add-ins-Thumb Dec 2021.png
tags: []
type: "regular"
---

## ![office-add-ins-Thumb Dec 2021.png](images/office-add-ins-Thumb Dec 2021.png)


## Call summary



This month's community call features an Outlook: Ignite recap from
[Juan
Balmori](https://twitter.com/juaneloBalmori) (Microsoft) highlighting the
release of Mailbox 1.11 GA and demos for Event-based add-ins and Smart
Alerts for Outlook. Then appreciate an Outlook sample: Use event-based
activation to encrypt attachments delivered by [Eric
Legault](https://twitter.com/elegault) (Eric Legault Consulting), with 3
scenarios demonstrating automated task execution, messages displayed in
information bar and related code step-through. This month's Community
spotlight recognizes Michał Królewicz, Maarten van Stam, and Eric
Legault for their continued contributions to this community. Please
complete the [Office add-in developing experience
survey](https://forms.office.com/r/wmzCgccbPa) and register for the [PnP
Recognition Program](https://aka.ms/m365pnp-recognition). Q&A both in
chat throughout call and at end of call. The call was hosted by [David
Chesnut](https://twitter.com/davidchesnut) (Microsoft) Recorded December
8, 2021.

## Presenters

-   [David Chesnut](https://twitter.com/davidchesnut), Senior Dev Writer
    (Microsoft) | @davidchesnut

-   [Juan Balmori Labra](https://twitter.com/juaneloBalmori)[, Principal
    Program Manager (Microsoft) |
    @juaneloBalmori]

-   [Eric Legault](https://twitter.com/elegault), Principal (Eric Legault
    Consulting) | @elegault


## Agenda

-   **D1:  Outlook: Ignite recap **-- [Juan
    Balmori](https://twitter.com/juaneloBalmori) (Microsoft) |
    @juaneloBalmori -- [1:10](https://youtu.be/Yx2oCeEtbQQ?t=70)
-   **D2:  Outlook sample: Use event-based activation to encrypt
    attachments** -- [Eric Legault](https://twitter.com/elegault), (Eric
    Legault Consulting) |
    @elegault -- [22:41](https://youtu.be/Yx2oCeEtbQQ?t=1361)
-   **Community spotlight:** Michał Królewicz, Maarten van Stam, and
    Eric Legault -- [37:47](https://youtu.be/Yx2oCeEtbQQ?t=2267)
-   **Q&A** -- [39:02](https://youtu.be/Yx2oCeEtbQQ?t=2342)

## Topics

-   **D1:  Outlook:  Ignite recap** -- new features to create Outlook
    add-ins that improve collaboration in a hybrid world. Mailbox 1.11
    with [more]{.underline} Events is GA and Smart Alerts preview is now
    available.  Event-based add-ins + Smart Alerts for Outlook = better
    emails. Demo of Event-based add-ins for new events including
    handling email signatures for external and internal recipients. A
    second demo shows why Smart Alerts help users send better emails.  

-   **D2:  Outlook sample: Use event-based activation to encrypt
    attachments **-- event-based activations from an Outlook add-in when
    user initiates email, appointment, or meeting request. Run tasks and
    create notification messages in information bar each time an
    attachment, recipient, meeting attendee, or meeting times are
    updated. UI and code scenarios shown: Encryption based on attachment
    change events, Notifications based on recipient changes, and
    Notifications based on date/time changes.** **Good-to-knows,
    pre-demo jingle, and samples in repo. ** **

## Actions

-   Please complete the [Office Add-in developing experience
    survey](https://forms.office.com/r/wmzCgccbPa)
-   Register for the [Microsoft 365 Developer
    Program](https://aka.ms/m365/devprogram) and get a free E5 developer
    tenant with instant availability and other assets  
-   Earn contributor badges, sign up for the [PnP Recognition
    program](https://pnp.github.io/recognitionprogram/) 
-   Save the date. The next Office Add-ins community call is January
    12th at 08:00am PST - <https://aka.ms/officeaddinscommunitycall>


## Q&A (Question & Answers)


**When the Outlook REST API is decommissioned in October 2022, what API
should add-ins deployed to customer-hosted Exchange Servers (2016/2019)
use for mobile support? Will the Outlook REST API remain active for
Exchange Server and just be decommissioned for O365 accounts?**

**The Outlook REST API is set to be decommissioned in October 2022, but
mobile add-ins do not support the necessary requirement set to get
access tokens for the suggested alternative of the MS Graph API. Does
this mean the Outlook add-ins on mobile will have no way to make Graph
API calls without forcing user interaction? Does this mean there is no
migration path to keep the existing functionality we have with the REST
API implementation on mobile add-ins?**

Thanks for these questions. We understand there are many add-ins that
rely on the Outlook REST APIs. The team is working on guidance that we
hope to provide soon. The Outlook REST API is not supported in Exchange
on-premise (2016/2019), with the exception of hybrid environments. A
hybrid environment does support Microsoft Graph so we still encourage
looking into the Microsoft Graph APIs for new solutions. For access
tokens we recommend looking to the [SSO
documentation](https://learn.microsoft.com/office/dev/add-ins/develop/authorize-to-microsoft-graph) on
how to access Microsoft Graph.

**The Microsoft Graph SSO documentation focuses on calling Graph from
server-side once an access token is obtained using a bootstrap token.
For our add-in, we would prefer to pass that token back to the client
and have the add-in initiate the MS Graph calls using the obtained
token. Is this not recommended, and if so, why not?**

Passing a token to the client increases the risk of it getting leaked
through browser history, caching, or other mechanisms. Keeping tokens on
the server is a more secure way of managing them. For more guidance we
recommend reaching out to the Microsoft identity platform team at
<https://learn.microsoft.com/azure/active-directory/develop/developer-support-help-options>.

**I have a question on unit testing. I created my office.js add-in for
Word, that is working with existing documents, and it is
blocking/unblocking sections inside the document. As I understand, unit
tests that are written in examples are working on the blank document. Is
it possible to run unit tests on a custom document, and how can we
accomplish that?**


Unit tests don't run against an actual document. This sounds more like
an end-to-end test, or UI testing. Unfortunately, there isn't a good
way to load a custom document and test against it. Many customers use
manual testing for these types of scenarios. We're hoping to improve
this story down the road.


**Our Word add-in loads on Microsoft 365 Word on desktop and Microsoft
365 Word on the browser. But the add-in fails to load on the Office
Online Server 2019 version of the Word Web App. We get an error message
saying that it is unable to load the add-in, and that we should use Word
on desktop instead.**


Unfortunately, Word add-ins are not supported on Office Online Server.
For these scenarios, we recommend that you check that Office is properly
initialized as described in
<https://learn.microsoft.com/office/dev/add-ins/develop/initialize-add-in>.


**Can the Outlook event-based add-in be triggered by a user typing a
certain word (similar to spell-check)?**

No, we don't have a specific event for this. It would be expensive to
handle an event on every keypress. We recommend using another event such
as OnMessageSend to trigger a check.

**Is there an Outlook event planned for when the Sender (From) changes?
In desktop, if you have multiple mailboxes, you can select the sender.
It would be useful to know when signatures might be different from
senders.**

This is on our backlog, but we don't yet have an ETA for when this will
be available.
**Which email signature system did you use in the demo?**

The demo used a simple signature built by the engineering team. But we
have awesome partners like CodeTwo, LetSignIt, and Exclaimer who provide
solutions in this market.
**Can the email signature pull information from Active Directory
attributes?**

Yes
**Do smart alerts work on Outlook on the web?**

The preview is only on Outlook on Windows. We are planning to add
support for Outlook on the web next, and eventually all platforms.
**\`onSend\` add-ins can't be published to the store. Will it possible
to publish add-ins with smart alerts to the store?**

Yes, add-ins using smart alerts can be published to Microsoft AppSource.

**If session data needs to be stored centrally (so individual sessions /
all users in an org can pull current, dynamic data) I'd love to
understand where to place the centralized data repository in order to
integrate it successfully**

If you need to store settings that apply to all users of the add-in
within the organization, you need to provide a data repository for it.
You should choose a repository of your choice in the cloud. Some
customers use SharePoint, for example.

**If it's web first, then I'm guessing somewhere in SharePoint users
can fill out the form then sync that into AD (Azure AD Connect) then
save that info into the on-premise AD?**

It's really your decision on which data repository you want to store
such settings.

**Any progress on support for shared mailbox add-ins on OWA?**

This is now in preview for Outlook on Windows. The Outlook team is
looking to enable the same experience on Outlook on Windows, and we
might have more updates to share early next year.

**What about supported platforms for the smart alerts? Can we expect
mobile clients (iOS and Android) getting this feature enabled?**

Yes! We are multiplatform by nature and eventually smart alerts will be
added to all platforms. We are starting the beta with Outlook on Windows
and the next platform will be on the web.

**So, next year we may expect Win32 and Web availability of smart
alerts. Is there any estimation for the mobile?**

Our goal is to GA no later than Q2 next year. Outlook on mobile will
support event-based add-ins first, and then smart alerts. We don't have
concrete dates for the smart alerts on mobile yet.

**How is the demo obtaining the document attached? It was easy when the
document had a URL. But this is from a work machine. Do we have a sample
in script lab?**

There is an API in Office.js to get the attachments. Check out the
[Office.AttachmentContent
interface. ](https://learn.microsoft.com/javascript/api/outlook/office.attachmentcontent)In
script lab for Outlook search for "Get attachments" in the samples and
you will find a sample.

**Any news when the current PowerPoint Preview API will go live?**

We are looking at early next year.


## Resources

-   **D1:** Article - [What's new for Office Add-ins at Ignite
    2021](https://devblogs.microsoft.com/microsoft365dev/whats-new-for-office-add-ins-at-ignite-2021/) 

-   **D2:** Repo - [Use Outlook event-based activation to encrypt
    attachments, process meeting request attendees and
    rea\...](https://github.com/OfficeDev/PnP-OfficeAddins/tree/main/Samples/outlook-encrypt-attachments) 

-   **D2:** Documentation - [Configure your Outlook add-in for
    event-based
    activation](https://learn.microsoft.com/office/dev/add-ins/outlook/autolaunch) 

-   **D2:** Documentation - [Outlook add-in API requirement set
    1.11](https://learn.microsoft.com/office/dev/add-ins/reference/objectmodel/requirement-set-1.11/outlook-requirement-set-1.11) 

-   **D2:** Documentation - [Authenticate a user with a single-sign-on
    token in an Outlook
    add-in](https://learn.microsoft.com/office/dev/add-ins/outlook/authenticate-a-user-with-an-sso-token) 

-   **D2:** Song -- [Office Add-ins
    Song](https://youtu.be/YdQouPsW1qo) 

### Office Add-ins community call

-   [Upcoming agenda and previous call
    resources](https://aka.ms/officeaddinsagenda)
-   [Recurring, monthly community call calendar
    invite](https://aka.ms/officeaddinscommunitycall)
-   [Community call topic requests and
    questions](https://aka.ms/officeaddinsform)
-   Community call recordings on the [YouTube Microsoft 365 community
    channel](https://www.youtube.com/channel/UC_mKdhw-V6CeCM7gTo_Iy7w)

### Office Add-ins feedback

-   Technical questions -- Microsoft Q&A
    ([office-js-dev](https://learn.microsoft.com/answers/topics/office-js-dev.html)),
    ([office-addins-dev](https://learn.microsoft.com/answers/topics/office-addins-dev.html))
-   Issues -- [GitHub](https://github.com/OfficeDev/office-js/issues)
-   Recommendations and suggestions -- [Microsoft 365 Developer Platform
    ideas](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform)
 
