---
title: "Office Add-ins community call -- November 10, 2021"
date: 2021-12-01T11:40:00-05:00
author: "David Chesnut"
githubname: davidchesnut

categories: ["Office add-in developer community call"]
images:
- images/office-add-ins-Thumb-Nov.png
tags: []
type: "regular"
---

## ![office-add-ins-Thumb-Nov.png](images/office-add-ins-Thumb-Nov.png)


## Call summary




This month's community call features a customer presentation -
**CodeTwo Outlook Add-in for email signature management** - (email
signature manager designed for Microsoft 365) Michał Królewicz -
Technical Marketing Manager (CodeTwo), **Microsoft 365 instant sandbox**
(turnkey E5 developer sandbox all M365 workloads and Sample Data
Packs) - Michael Aldridge -- Principal Program Manager (Microsoft), and
a demo - **Unit testing Office JavaScript with Office-Addin-Mock
library** (an NPM library to facilitate unit testing) - Igor Ribeiro --
Software Engineer (Microsoft) 

 This month's Community spotlight
recognizes MVP Maarten van Stam and Eric Legault for their continued
contributions to this community.  Greatly appreciated!  Register for the
[PnP Recognition Program](https://aka.ms/m365pnp-recognition).  Q&A live
and in chat throughout call.  The call was hosted by David Chesnut
(Microsoft) | @davidchesnut. Recorded November 10, 2021.

## Presenters 

-   Michał Królewicz - Technical Marketing Manager​ at CodeTwo
-   Michael Aldridge - Principal Content Program Manager
-   Igor Ribeiro - Software Engineer


## Topics 

-   **CodeTwo Outlook Add-in for email signature management --**
    Microsoft Gold Partner CodeTwo demonstrates their email signature
    manager Outlook Web add-in product that leverages Microsoft Event
    based add-in capabilities recently released at Microsoft
    Ignite 2021. Their product allows Admins to centrally manage email
    signatures and legal disclaimers on mails sent to internal and
    external recipients. Client-side and server-side (Cloud)
    capabilities including preview are available on all Office 365
    devices.  Code sample in GitHub.     
-   **Microsoft 365 instant sandbox --** turnkey prototype environment. 
    Join the Microsoft 365 Developer program and get a pre-provisioned
    E5 tenant with Teams Developer Portal, all M365 workloads and Sample
    Data Packs.  Teams sideloading pre-installed, App Studio
    pre-installed, Full Sample Teams environment with 16 fictitious
    users, chats, channels and teams pre-installed.  Existing developer
    program members can create a 2nd Microsoft 365 Instant Sandbox E5
    developer subscription at end of November.    
-   **Unit testing Office JavaScript with Office-Addin-Mock library -**
    a new NPM library to facilitate unit testing.  Provides a way to
    unit test the Office JavaScript API and Does not depend on Office. 
    Compatible with major unit testing JavaScript frameworks, such as
    Mocha or Jest.  Supports all Office hosts.  Works for JavaScript and
    TypeScript.   Office Addin Mock along with test examples are
    available now. Future work items called out.    

## Agenda 

-   **T1:  Customer presentation:** CodeTwo Outlook Add-in for email
    signature management - Michał Królewicz (CodeTwo) --
    [1:21](https://youtu.be/7hGsmgNHqow?t=81)
-   **T2:  Tools:**  Microsoft 365 instant sandbox - Michael Aldridge
    (Microsoft) -- [15:39](https://youtu.be/7hGsmgNHqow?t=939)
-   **T3:  Demo:** Unit testing Office JavaScript with Office-Addin-Mock
    library - Igor Ribeiro (Microsoft) --
    [25:46](https://youtu.be/7hGsmgNHqow?t=1546)
-   **Community spotlight:** Maarten van Stam and Eric Legault --
    [35:00](https://youtu.be/7hGsmgNHqow?t=2100)
-   **Q&A** -- [35:44](https://youtu.be/7hGsmgNHqow?t=2144)

## Actions 

-   Provide input on Mocking Office.js for unit tests -- [Standard way
    to unit test and mock office-js
    API](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/standard-way-to-unit-test-and-mock-office-js-api/idi-p/2718673) 
-   Earn contributor badges - sign up for the PnP Recognition
    program: <https://pnp.github.io/recognitionprogram/> 
-   Follow channels in twitter -- for call agendas and summaries,
    release announcements,...
    -   <https://twitter.com/microsoft365dev>
    -   <https://twitter.com/m365pnp>
-   Next community call -- December 8th at 08:00am PST -
    <https://aka.ms/officeaddinscommunitycall>


## Q&A (Question & Answers) 


### **Microsoft 365 developer program and instant sandbox** 

**Is the developer subscription as persistent as a paid subscription? To
mimic a real environment I also attached my custom domain. Is that still
possible?**\
It is a durable subscription. If you're coming from Visual Studio, this
subscription will automatically update as part of the Visual Studio
subscription. Otherwise, you need to show developer activity within 90
days to be renewed. You don't control the domain name in the sandbox.
To configure the domain name, you'll need the customizable sandbox (the
previous sandbox experience).
**So now we can get two sandboxes using one dev account?**\
Yes.
**When you enroll in the Microsoft 365 developer program, can you choose
an instant or a provisioned account?**\
Yes, you choose when you sign up.
**How do we reset a sandbox?**
Today we don't have the ability to reset. However your old tenant will
expire naturally if you don't use it.
**Is Visio included in the Microsoft 365 developer program?**
Visio is not included in the Microsoft 365 developer program E5
subscription today.

### Unit testing with the Office JS Office-Addin-Mock library** 

**How do we unit test or integrate Cypress into an Outlook plugin?**\
It doesn't seem likely this would work as Cypress is more focused on
end-to-end testing, while the unit testing library we provide is
designed for unit testing frameworks.
**How do we unit test if we are using Excel.run?**\
Yes, there's a sample demonstrating this:
<https://github.com/OfficeDev/Office-Addin-TaskPane/tree/master/test/unit> 

### Miscellaneous 

-   **With the Outlook REST API being decommissioned in November 2022 in
    favor of Graph API, what happens to on-premise Exchange REST API
    support at that time? We have add-ins that use the REST API for
    mobile. Will the REST API still be usable at that time and does the
    decommissioning just apply to Office 365?**
-   **Are there any plans to publish a migration guide or best practices
    to Microsoft Graph from the Outlook REST API, which will be
    decommissioned in November 2022?**
-   **The Outlook REST API is being decommissioned next year. Can you
    outline what exactly the impact of this will be? For example, will
    the service be turned off for Office 365 causing mobile add-ins that
    were using the add-in to stop working? Will Exchange 2016
    environments continue to work, or will an update be pushed out to
    turn off the API on those?**

Thanks for the inquiries about the Outlook REST API! We understand there
are many add-ins that rely on the Outlook REST APIs. The team is working
on guidance that we hope to provide soon. In the meantime, we still
encourage you to look into the Microsoft Graph APIs for new solutions.

\
**What is the best approach to follow to distribute an Office-Add-in in
a single tenant scenario? Since every customer has a different URL,
every manifest should be customized to communicate with the customer's
web app instance.**\
For a single tenant, the best approach is typically to have the admin
distribute your add-in by using centralized deployment. For more
information, see [Deploy add-ins in the admin
center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).
If you are planning to use a separate manifest for each customer, then
you will still want to use centralized deployment and provide the
correct version of the manifest to each customer. If you want to support
multiple customers with one manifest, then we recommend to [Publish your
add-in on Microsoft
AppSource](https://docs.microsoft.com/office/dev/store/submit-to-appsource-via-partner-center).
**I am an Office Add-in developer, eager to work with the new PowerPoint
Shape API since the August 2021 community call. When I run the "Insert
shape, line and text box" sample code on Script Lab, unlike what
happens with all other samples there, I get an error. Could it be
because I am not in the Office Insider Program?**\
Yes, these are preview APIs right now, so most likely, you'll need to
use the insider version of Office to work with them. You can sign up for
Office Insider at <https://insider.office.com/>.
**Is there an API we can use for previewing files in Office on the
web?**\
If you intend to render something such as a thumbnail preview, then no,
we don't have any APIs around this today. However, it would be great to
learn more about your scenario. Please consider submitting a feature
request for this at <https://aka.ms/m365dev-suggestions>. If you intend
to read a file then this is possible. Please refer to the [OneDrive file
storage API overview - Microsoft Graph | Microsoft
Docs](https://docs.microsoft.com/graph/onedrive-concept-overview).

**Any news when the current PowerPoint Preview API will go live?**

We are looking to release the tags API set to general availability (GA)
by end of month. The rest of the API's will GA tentatively sometime
early next year.


## Resources 

-   **T1:**  Website - [www.codetwo.com](http://www.codetwo.com) 
-   **T1:**  Blog - [What's new for Office Add-ins at Ignite
    2021](https://devblogs.microsoft.com/microsoft365dev/whats-new-for-office-add-ins-at-ignite-2021/) 
-   **T1:**  Blog - [CodeTwo Squad
    Blog](https://www.codetwo.com/blog/outlook-add-in-new-features-ignite-2021/) 
-   **T1:**  Sample -- [Sample signatures
    add-in](https://github.com/CodeTwoDev/sample-signatures-addin) 
-   **T2:**  Blog post - [Microsoft 365 Developer Program launches new
    instant sandbox with Teams sample data
    pack](https://devblogs.microsoft.com/microsoft365dev/microsoft-365-developer-program-launches-new-instant-sandbox-with-teams-sample-data-pack/) 
-   **T2:**  Program -- [Microsoft 365 Developer
    Program](https://developer.microsoft.com/microsoft-365/dev-program) 
-   **T3:**  NPM -
    [Office-Addin-Mock](https://www.npmjs.com/package/office-addin-mock) 
-   **T3:**  Repo - [Test
    Examples](https://github.com/OfficeDev/Office-Addin-TaskPane/tree/master/test/unit) 
-   **T3:**  Issues -- [GitHub
    Issues](https://github.com/OfficeDev/Office-Addin-Scripts/issues) 

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
    ([office-js-dev](https://docs.microsoft.com/answers/topics/office-js-dev.html)),
    ([office-addins-dev](https://docs.microsoft.com/answers/topics/office-addins-dev.html))
-   Issues -- [GitHub](https://github.com/OfficeDev/office-js/issues)
-   Recommendations and suggestions -- [Microsoft 365 Developer Platform
    ideas](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform)
 