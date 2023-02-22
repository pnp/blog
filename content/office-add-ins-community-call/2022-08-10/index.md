---
title: "Office Add-ins developer platform community call – August 10, 2022"
summary: "Topics include Excel add-in user pattern Open in Excel, Linq to XML in Office.js, Office Add-ins developer platform community update, Outlook add-in API update, REST decommission, Mailbox 1.12 scope definition."
date: 2022-08-10T08:01:00-05:00
author: "Preethika Kiruveedula"
githubname: preethikakiru
categories: ["Office Add-in developer community call"]
images:
- images/office-add-ins-call-august-2022-recording.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/KxaE0SLk-lM 
draft: false
---

# Office Add-ins developer platform community call - August 10, 2022

## This month's agenda and presenters

The call was hosted by [David Chesnut](http://twitter.com/davidchesnut), Senior Technical Writer, Microsoft Office Developer Platform
* **Excel add-in user pattern – Open in Excel.** Export data from any system to Excel. [Yawei Zhu](https://www.linkedin.com/in/yaweizhu-henson/), Senior Product Manager, Microsoft. 
* **Use Linq to XML in Office.js Add-ins.** Two TypeScript libraries for dealing with Open XML markup. [Thomas Barnekow](https://www.linkedin.com/in/thomas-barnekow-2580b11), Senior Principal Software Architect, [Analog Devices](https://www.analog.com/en/index.html).
* **Office Add-ins community engagement update.** Help us select a single destination for product ideas and suggestions. [Linda Lu Cannon](https://www.linkedin.com/in/lindalu-msft/), Senior Content Project Manager Microsoft, Microsoft.
* **Outlook add-in API update: REST decommission and Mailbox 1.12 scope.** New event-based features in Mailbox v1.12 and REST decommission update. [Juan Balmori](http://twitter.com/juaneloBalmori), Principal Product Manager, Microsoft.
* **Q&A.** See question and answers at end of call and in chat throughout call.

{{< youtube COic6ghBWsU >}}

## View Video Segments

* Excel add-in User Pattern: Open in Excel [1:12] (https://youtu.be/KxaE0SLk-lM?t=72)
* Use Linq to XML in Office.js Add-ins [9:27] (https://youtu.be/KxaE0SLk-lM?t=567)
* Office Add-ins community engagement update[31:00] (https://youtu.be/KxaE0SLk-lM?t=1860)
* Outlook add-in API update: REST decommission and Mailbox v1.12 scope [42:05] (https://youtu.be/KxaE0SLk-lM?t=2525)
* Q&A [59:17](https://youtu.be/KxaE0SLk-lM?t=3557)

## Topic summaries

* **Excel add-in user pattern – Open in Excel .** In the Open in Excel pattern, reduce steps for sourcing, installing, and using an add-in from 6 to 3. See when and how to use pattern along with benefits for users and developers. User can export data from any system to Excel.The Excel JavaScript add-in integrates your service with Excel by maintaining a connection between system data and your add-in.
* **Use Linq to XML in Office.js Add-ins.** To support Office.js Add-ins, presenter has developed two TypeScript libraries (linq-to-xml and linq-to-ooxml) to handle Open XML markup. The code enables pure functional transformations of Office Open XML documents in Office.js Add-ins. In the Linq samples shown, see how to use capabilities from the libraries to transform a Word document that contains a massive number of content controls. 
* **Office Add-ins Community engagement update** Pros/cons of locations to share your Office.js ideas, improvements, and feature suggestions. Linda had three asks: 1.) Provide feedback and other suggestions on using GitHub issues vs. discussions, 2.) Tag @lindalu-MSFT on your ideas previously submitted to [Tech Communities ideas forum](https://aka.ms/m365dev-suggestions) to ensure transfer, and 3.) Are you interested in participating in a User Research session about customer support channels? [Contact Linda](mailto:lindalu@microsoft.com)        
* **Outlook add-in API update: REST decommission and Mailbox 1.12 scope** Updates since February regarding Outlook v2.0 REST API decommission. Mailbox v1.12 adds two big event-based features: Smart Alerts (onMessageSend and onAppointmentSend) and New Compose events (onMessageCompose and onAppointmentOrganizer). The features are available in preview for Windows and Outlook on the web. Q&A at end of demo addresses when you can still use the REST API, solution for mobile, and using REST in OnPrem.
  
## Call to action

* If you are a Word developer go ahead and give us feedback on what you need from Word apis. [Word APIs Survey](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR6n1U-1y30dHploxSapt6sxUMEdRQUMyU1kzSExENUI1WTIzN1k1WlMxQy4u).
* Share your feedback on how we can provide you with a better Office Add-ins development experience. Join a community panel. 
    * [Outlook add-ins panel](https://ux.microsoft.com/Panel/OutlookAddinDeveloper)
    * [Excel add-ins panel](https://ux.microsoft.com/Panel/ExcelAddinDeveloper)
    * [Word add-ins panel](https://ux.microsoft.com/Panel/WordAddinDeveloper)
    * [PowerPoint add-ins panel](https://ux.microsoft.com/Panel/PowerPointAddinDeveloper)
    * [Samples and docs](https://ux.microsoft.com/Panel/OfficeAddinImproveSamplesDocs)
* [Sign up for the PnP Recognition Program](https://pnp.github.io/recognitionprogram/) and earn contribution badges.
* Follow us on Twitter to see call agendas, important updates, and release announcements. 
    * [@microsoft365dev](https://twitter.com/microsoft365dev)
    * [@m365pnp](https://twitter.com/m365pnp)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free E5 developer tenant with instant availability and other assets.
* [Join the next Office Add-ins community call](https://aka.ms/officeaddinscommunitycall) on September 14th at 8:00 AM Pacific Time.

## Q&A (Question & Answers)

**Is there a resource that shows speed parity issues between PC/Mac/Web? For text search and selection, we see much faster performance on PC than on Mac. It would be great to see best practices on how to keep performance consistent among platforms.**

In order to best answer your question we need further clarification. Does this performance issue occur with a particular set of Word APIs being introduced or is there a difference in performance for the host Word on PC and Mac? It would be great if you could log an issue and provide more context here on our [Office.js Github repo](https://github.com/OfficeDev/office-js). 

**Any timelines on when these Smart Alerts will be supported on Outlook Mobile?**

We currently don't have concrete plans on the roadmap. It would be great if you could create a feature request with more information at https://aka.ms/m365dev-suggestions.

**Is there a way to stop the mouse cursor icon from changing into a loading icon when calling the 'Powerpoint.run()' function?**

This behavior is by design because Office JS APIs run on PowerPoint’s UI thread. The user is unable to interact with PowerPoint until API operations are complete. If an operation takes a bit longer than usual, the cursor change informs the user they are temporarily blocked.

**Will the APIs for opening a document be extended to allow for opening POTX files? It currently only allows for PPTX I believe. (Unless I've missed something.)**

This is a great feature to request, please go to the M365 developer platform and put in a new idea request with more information at https://aka.ms/m365dev-suggestions.

**When performing a search using Microsoft Graph, preferably using the '/search(q='${searchText}' endpoint, is it possible to search SharePoint files by their 'ImageTags'?**

We recommend you follow up with the Microsoft Graph team at https://docs.microsoft.com/en-us/answers/products/graph.

**With VSTO it is possible to create PDF/A versions of Office files. In our target sector (public sector, governments) using PDF/A is important and required in most cases. How can a PDF/A representation of an office file can be created using the JS APIs?**

Unfortunately Office JS only supports the PDF format right now. This would be a great feature request. Please let us know more at https://aka.ms/m365dev-suggestions.

**Is there a way to start a web addin (open the web task pane) from a VSTO add-in? This capability would make the transition from VSTO to web much easier to implement some functionality in a web add-in and have a smooth transition from VSTO to web as if it was a single add-in. Migrating the entire add-in from VSTO to web in a big bang is not possible since the JS api is lacking some COM APIs.**

No this capability does not exist. There are resources available for this scenario though. Please see https://docs.microsoft.com/en-us/office/dev/add-ins/develop/make-office-add-in-compatible-with-existing-com-add-in and https://docs.microsoft.com/en-us/office/dev/add-ins/tutorials/migrate-vsto-to-office-add-in-shared-code-library-tutorial.

**Is this add-in installation option only available for Excel? Are there plans to allow this for Word?**

It's currently only available for Excel in the code sample. We would love to hear about your Word use case and scenarios. Please complete the feedback form.

**Does clicking on Open in Excel install the add-in in Excel?**

Yes, it installs the add-in in Excel if the user hasn't already done so.

**Can Open in Excel be restricted by enterprise admins?**

If the store is enabled for the tenant users, the feature should work.

**What happens in case a vendor has multiple add-ins for Excel? How does the system know which one of their add-ins to launch?**

Excel supports multiple task panes opening at the same time. This is something we'll need to test further for the auto-launch feature.

**Can the Excel PnP sample also be modified to work with Word?**

We'll look into this further. We do want to understand the scenario for "Open in Word" integration. For Word developers interested in this, please complete the feedback form.

**I want to develop an Outlook add-ins project. What is the best tech stack? (Would prefer React Typescript.)**

The beauty of web add-ins is that you can choose the technology you know best! For further guidance, see Develop Office Add-ins and Office Add-ins platform overview.

**Is there any way to know if the Excel calculation is complete after calling calculate method on Range or Application (for both Manual and Automatic mode)? Previously tried with Worksheet and WorksheetCollection oncalculated event, but these are unreliable in case of volatile functions. Multiple events are triggered for single worksheet before entire worksheet is calculated.**

Please open an issue on GitHub so that we can assist you further.

**What is most safe way of determining if the custom functions have completed executing in Excel?
Application.CalculationState == "Done" works fine when the CalculationMode is Automatic but fails when CalculationMode is Manual.**

Please open an issue on GitHub so that we can assist you further.

**We have multiple Outlook add-ins but not everyone needs all of them. It would be great to have an on demand deployment via an email or request.**

You could develop a web service that sends out Outlook Actionable Message emails; a button within that message can auto-install an Outlook add-in that is published in AppSource.

**1) Can we get a quick status/timeline update for One Outlook? 2) Outlook Add-in on Mac Desktop still has issues writing attachments on send, which have been acknowledged by MS team in various posts. Is there any plan for resolution or any feasible workarounds?**

We'll provide an update on One Outlook regularly via the monthly community call. For a recent update on the timeline, see the Office Add-ins June community call blog post.

We are working on fixing this bug. Stay tuned!

**If a feature exists in the VSTO API and I need it in the JS API, is that an "idea"? I am looking to re-build my VSTO for Word in JS. The API is woefully lacking though. Specifically, I am missing key features with content control fields and events.**

Yes! Please complete the Word add-ins survey at aka.ms/wordAPI.

**Is the "the feedback portal" where I should be submitting things?**

Tech Communities is where we currently ask customers to submit their ideas and requests. The Feedback Portal is a new platform option we're weighing against GitHub for issue and idea submissions. We encourage you to review the new Feedback Portal versus GitHub and send your thoughts about the two by opening an issue on GitHub and mentioning @lindalu-MSFT.

**Can you check with the languages team how they do that? For them GitHub is leading I think but is rerouting feature requests to internal systems.**

Thanks, we'll take a look. There are a few sites out there that we can see if we can borrow some processes or tools to help set this up.

**Do you have data that compares the performance of Office.js vs. VSTO add-ins? For example, is the Office.js API faster than the COM API?**

For the vast majority of scenarios, the performance between the two isn't significantly different.

**It's definitely been a pain point for us to know where Microsoft engineers commune or are able to engage with the developer community. Can you clarify if there will be a paid support path for non-enterprise developers?**

No, there is no paid support for non-enterprise Office Add-ins developer customers. I do believe Graph has paid support so that's good news if you have a suggestion for a Graph service API.

**How can we move API calls to the server for a Outlook mobile add-in and obtain a token that can be used with EWS or Graph without user interaction?**

The idea is that you do expose a server service as part of your add-in. That service is the one calling Graph (on the server) and returning the needed data to your add-in JS layer.

**On Outlook mobile we won't be provided with the initial bootstrap token from the user to send to the server, so how can we go about retrieving that token in then mobile environment given all we'll have is user email address? Is the concept that the server would authenticate as a service user? Need further clarifcation on who the server is meant to authenticate with the Graph APIs. Context: Regular desktop flow: Bootstrap token generated on client by add-in getAccess, specific to user. Sent to server and on-behalf of token retrieved to issue actual Graph API calls. Mobile: what is the mobile equivalent?**

During the REST exemption period, we will be working on providing a similar API for mobile so you can implement that functionality. Until then, you can keep using REST.

**Since REST will only keep working for existing add-ins does that mean any new Office add-ins we develop after decommissioning are limited on mobile to what Office.js provides in requirement set 1.5 and EWS's GetItem/GetAttachment call?**

REST exemption will apply to existing and new add-ins. Add-ins created after the decommission date in November can continue to consume REST services until October 2025. We'll have our new auth APIs to get Graph-compatible tokens by then, which will also support mobile.

**We currently use the PowerPoint.run() on a timer to check for tag changes of the document in the background. Ideally we'd like to make it so there isn't an icon change so the user doesn't feel like they need to wait for something to load.**

Try creating a web worker that runs the timer. This would put it on a separate thread and would stop the icon from changing. For an example, see Office-Add-in-samples/Excel-custom-functions/web-worker at main · OfficeDev/Office-Add-in-samples (github.com).


## Additional Resources

* **Excel add-in user pattern: Open in Excel**
    *[Open Excel from your web page and embed your Office Add-in](https://docs.microsoft.com/office/dev/add-ins/excel/pnp-open-in-excel)
    *[Deploy add-ins in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)
    *[Configure your Office Add-in to use a shared JavaScript runtime](https://docs.microsoft.com/office/dev/add-ins/develop/configure-your-add-in-to-use-a-shared-runtime)
    * Feedback - [Open in Excel pattern proposal feedback](https://forms.office.com/r/14KL0MjPfJ)
* **Use Linq to XML in Office.js Add-ins**
    * Github Sample repo - [OpenXmlDev/linq-to-xml](https://ineleccom-my.sharepoint.com/personal/andrb_inelec_com/Documents/Desktop/Office Videos/Add In Calls/2022-08-10-OfficeAdd-ins/OpenXmlDev / linq-to-xml)
    * npm - [LINQ to XML for TypeScript](https://www.npmjs.com/package/@openxmldev/linq-to-xml)
    * Github Sample repo - [OpenXmlDev/linq-to-ooxml](https://github.com/OpenXmlDev/linq-to-ooxml)
    * npm - [OOXML Namespace-Related Classes for LINQ to XML for TypeScript](https://www.npmjs.com/package/@openxmldev/linq-to-ooxml)
    * Github sample repo- [OpenXmlDev/inq-add-in](https://github.com/OpenXmlDev/linq-add-in)
  **Outlook Add-in API update: REST decommission and Mailbox 1.12 scope **
    *[REST API Add-in verification request](https://aka.ms/RESTCheck)
    *[Add-ins for Outlook mobile](https://docs.microsoft.com/office/dev/add-ins/outlook/outlook-mobile-addins)
    *[On-Premises Architectural Requirements for the REST API](https://techcommunity.microsoft.com/t5/exchange-team-blog/on-premises-architectural-requirements-for-the-rest-api/ba-p/605609)
    

## Stay connected

* See the full blog post at [Microsoft 365 and Power Platform Community Blog](https://aka.ms/m365pnp/blog)
* [Follow @microsoft365dev on Twitter](https://twitter.com/microsoft365dev)
* [Microsoft 365 Platform Community on YouTube](https://aka.ms/m365/videos)
* Invites to all [Microsoft 365 Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions about Office Add-ins development](https://aka.ms/officeaddinsform) for our next community call
* [Join us for our next community call](https://aka.ms/officeaddinscommunitycall) on August 10th at 8:00 AM PT

{{< attachments >}}
