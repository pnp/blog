---
title: "Office Add-ins community call – March 9, 2022"
date: 2022-03-16T08:01:00-05:00
author: "David Chesnut"
githubname: davidchesnut
categories: ["Office add-in developer community call"]
images:
- images/office-add-ins-Thumb Mar 2022.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
---

## Call Summary

This month's community call features an update on **Excel API 1.15 preview** (accessing and using Chart Series Dimension and Pivot Table Data Source APIs) – Sirui Sun, Software Engineer (Microsoft) and **Q&A** both at end of call and in chat throughout call. Don’t forget to register for the [PnP Recognition Program](https://aka.ms/m365pnp-recognition). The call was hosted by Alex Jerabek (Microsoft). Recorded March 9, 2022.

## Microsoft Presenters

*   Sirui Sun – Software Engineer (Microsoft)
*   Alex Jerabek - Dev Writer (Microsoft)

## Agenda

*   **Excel API 1.15 preview** – Sirui Sun, Software Engineer (Microsoft) – [00:31](https://youtu.be/eC94i0ZJkao?t=31)
*   **Q&A** – [05:10](https://youtu.be/eC94i0ZJkao?t=310)

> Last updated: July 7. The presentation **Consuming Graph Services using SSO and CORS from event–based Outlook add–ins** was removed from this call. Upon further research, it came to our attention that this approach has a potential security risk. Once the Microsoft Graph token is obtained by the middle-tier, it sends the token to the add-in's client code running in Outlook. The Microsoft Graph access token created by the Microsoft identity platform as part of the on-behalf-of flow is only intended to be used by the middle-tier. Find more details about this security risk at [Middle-tier access token request](https://learn.microsoft.com/azure/active-directory/develop/v2-oauth2-on-behalf-of-flow#middle-tier-access-token-request).
> We are working on creating a sample with prescriptive guidance on how to implement event-based add-ins in Outlook using SSO with the guidance documented at [Microsoft identity platform and OAuth 2.0 On-Behalf-Of flow](https://learn.microsoft.com/azure/active-directory/develop/v2-oauth2-on-behalf-of-flow).

## Actions

*   Earn contributor badges – sign up for the PnP Recognition program at [https://pnp.github.io/recognitionprogram/](https://pnp.github.io/recognitionprogram/)
*   Follow channels in twitter – for call agendas, summaries, and release announcements
    *   [https://twitter.com/microsoft365dev](https://twitter.com/microsoft365dev)
    *   [https://twitter.com/m365pnp](https://twitter.com/m365pnp)
*   Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free E5 developer tenant with instant availability and other assets
*   Next community call – April 13th at 08:00am PST – [https://aka.ms/officeaddinscommunitycall](https://aka.ms/officeaddinscommunitycall)
*   Please complete the [Office add-in developing experience survey](https://forms.office.com/r/wmzCgccbPa)

## Q&A (Question & Answers)


### When can we expect the getSelectedDataAsync functionality to be able to get the selected shapes in a PowerPoint presentation?

Currently, there is no near-term plan to enable **getSelectedDataAsync** to support selected shapes in PowerPoint. Please let us know more about this scenario on the [Microsoft 365 Developer Platform ideas site](https://aka.ms/m365dev-suggestions).

### Our Outlook integration sometimes breaks because changes are made to the API and we only find out about them when our integration goes down. Is there any way we could get advance notice of breaking changes so we can update and avoid the friction caused by the downtime?

We’re sorry to hear you’ve been experiencing issues with your add-in. Unless there is a really important reason, we rarely make breaking changes to an API after it has been released in a requirement set. Can you please let us know more about this by creating an issue at [https://github.com/officedev/office-js](https://github.com/officedev/office-js)?

We strive to update our documentation to reflect upcoming changes, but we recognize that these may not be immediately visible to our developer community. We are currently working on posting changes and new features to the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap) to better communicate these to the community. In addition to updating our documentation, we also highlight upcoming changes and features in our monthly community call. Again, if you run into a particular issue during development, we encourage you to report the issue at [https://github.com/officedev/office-js](https://github.com/officedev/office-js), so that we can provide you with further assistance.


### Is the ability to call the Microsoft Graph API for various customer tenants via JS runtime available for add-ins in Excel and Word? What about shared runtime?

It is available for Excel, but not available in Word yet. If you use shared runtime for Excel, CORS is already supported prior to this. For Excel custom functions that do not use shared runtime, CORS was recently enabled.

### Can we use the Fetch API in the Outlook JS runtime?

You can use Fetch, but it is a polyfill over XHR, not a full fetch implementation. The Outlook demo uses Fetch.

### Will event-based add-ins support a mail received event rather than compose event?

Support for a read event in event-based add-ins is on our backlog. We're working to get to it as soon as we can.

### Does Office.js in Outlook still work with IE? I created a vanilla task pane add-in using yeoman, and it fails in Exchange on-premises 2016 with IE11.

This should work. We'll check into the \`yo office\` templates to be sure there isn't an error.

### Something that would be very useful is visibility into host application (Word, Excel, etc.) API feature development and deployment roadmaps. I would be able better plan a functionality roadmap for our internal Enterprise Office plugins.

We plan announce changes and features via the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap). This should help everyone keep track of upcoming features and APIs. We are open to your suggestions for how to better communicate upcoming feature development.

### For Excel add-ins with a task pane, can we use Next.JS along with React? if so, are there any examples?

Office Add-ins run in an iframe in a browser, or webview on desktop, and therefore support most HTML/JS frameworks and libraries. We don’t have any samples of using Next.JS, although it looks like it would work. You’ll want to be sure the resources that Office expects when loading are configured correctly. For example, you need to be sure the routing is set up to provide the correct URLs for all the images, HTML, and JS pages referenced in the manifest.

### Any update on [https://github.com/OfficeDev/office-js/issues/1108](https://github.com/OfficeDev/office-js/issues/1108)? The issue with the cursor placement in web Outlook?

We see this issue is affecting multiple customers and we’ve moved this up in priority on the backlog. We’re working to get this resolved as soon as we can. We’ll keep you updated on progress at the original GitHub issue. Thanks!

### Should we post in the Microsoft Q&A forum or StackOverflow or GitHub?

The team monitors all of these locations. For development assistance, particularly with coding, please post your questions to [Microsoft Q&A](https://learn.microsoft.com/answers/products/m365) or [Stack Overflow](https://stackoverflow.com). To report bugs, please open an issue in [GitHub](https://github.com/OfficeDev/office-js).

### Is there a documented or known issue that anyone is aware of with the Word API and supporting older versions of Word documents?

Office Add-ins only work with .docx files. They do not work with the older .doc file extensions. You would need to convert older doc files to the newer format to work with Office Add-ins.

### When will current APIs be available across all platforms? For example, OneNote APIs are only available from Office on the web. PowerPoint on an iPad only supports PowerPoint API 1.1, which can only create a new presentation. The main appeal of Office Add-ins is cross platform code, but only seems available for Excel.

Enabling the APIs available across all endpoints is our strategy. However, due to the different technology for the client of different endpoints, sometimes we have to start with one first then expand to others when it’s ready. We don’t have any ETA at this moment and the situation varies for different APIs. If there are specific APIs you need to see implemented across more platforms, please let us know more details at the [Microsoft 365 ideas site](https://aka.ms/m365dev-suggestions%20). We use the feedback there to help with planning.

## Resources

*   Microsoft Tech Community – Submit Feature Requests | [https://aka.ms/m365dev-suggestions](https://aka.ms/m365dev-suggestions)
*   Office Developer Community help | [https://developer.microsoft.com/office](https://developer.microsoft.com/office) (**Office–js–docs–pr, PnP–OfficeAddins**)
*   Office Add–ins documentation | [https://aka.ms/office-add-ins-docs](https://aka.ms/office-add-ins-docs)
*   Office Scripts | [https://aka.ms/office-scripts-docs](https://aka.ms/office-scripts-docs)
*   Microsoft 365 Developer Program | [https://aka.ms/M365devprogram](https://aka.ms/M365devprogram)
*   Script Lab | [https://aka.ms/getscriptlab](https://aka.ms/getscriptlab)
*   Office Add–ins documentation | [https://aka.ms/office-add-ins-docs](https://aka.ms/office-add-ins-docs)
*   Twitter | [https://twitter.com/microsoft365dev](https://twitter.com/microsoft365dev)
*   YouTube | [https://aka.ms/m365pnp/videos](https://aka.ms/m365pnp/videos)
*   Link to all Microsoft Developer Community calls | [https://aka.ms/M365DevCalls](https://aka.ms/M365DevCalls)

### Office Add-ins community call

*   [Upcoming agenda and previous call resources](https://aka.ms/officeaddinsagenda)
*   [Recurring, monthly community call calendar invite](https://aka.ms/officeaddinscommunitycall)
*   [Community call topic requests and questions](https://aka.ms/officeaddinsform)
*   Community call recordings on the [YouTube Microsoft 365 community channel](https://www.youtube.com/channel/UC_mKdhw-V6CeCM7gTo_Iy7w)

### Office Add-ins feedback

*   Technical questions – Microsoft Q&A ([office-js-dev](https://learn.microsoft.com/answers/topics/office-js-dev.html)), ([office-addins-dev](https://learn.microsoft.com/answers/topics/office-addins-dev.html))
*   ​Questions for the developer community – [Stack Overflow](https://stackoverflow.com) (**office-js,​ outlook-web-addins​, office-scripts**)
*   Issues – [GitHub](https://github.com/OfficeDev/office-js/issues)
*   Recommendations and suggestions – [Microsoft 365 Developer Platform ideas](https://aka.ms/m365dev-suggestions)
