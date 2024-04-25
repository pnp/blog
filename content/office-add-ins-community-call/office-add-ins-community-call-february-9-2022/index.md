---
title: "Office Add-ins community call – February 9, 2022"
date: 2022-02-15T02:44:00-05:00
author: "David Chesnut"
githubname: davidchesnut
categories: ["Office add-in developer community call"]
images:
- images/office-add-ins-Thumb Feb 2022.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://www.youtube.com/watch?v=O47gN9P8KAI
---

## Call summary

This month's community call features updates on **Excel data type APIs** (Review card view anatomy, data types, composable building blocks, New Values API and Data Types in Custom Functions) – Chris Gross, Senior Program Manager (Microsoft), **Word Online API updates** (Demo of In Preview capabilities – _Comment_ and _Track changes_, Coming soon – _Fields_) – Phoebe Yuan, Program Manager (Microsoft) and **Outlook add-ins and Outlook REST V2 decommission** (move to Graph or EWS before Nov 2022, APIs impacted, exceptions called out) – [Juan Balmori](https://twitter.com/juaneloBalmori), Principal Program Manager (Microsoft). This month’s Community spotlight recognizes [Maarten van Stam](https://twitter.com/aafvstam) (Deloitte) for his continued contributions to this community. Q&A both at end of call and in chat throughout call. Please register for the [PnP Recognition Program](https://aka.ms/m365pnp-recognition). The call was hosted by [David Chesnut](https://twitter.com/davidchesnut) (Microsoft) | @davidchesnut. Recorded February 9, 2022.

## Microsoft presenters

*   Chris Gross, Senior Program Manager
*   Pheobe Yuan, Program Manager
*   Juan Balmori, Principal Program Manager

{{< youtube O47gN9P8KAI >}}

## Agenda

*   Excel data type APIs – Chris Gross, Senior Program Manager (Microsoft) – [01:07](https://youtu.be/O47gN9P8KAI&t=67s)
*   Word Online API updates – Phoebe Yuan, Program Manager (Microsoft) – [16:50](https://youtu.be/O47gN9P8KAI&t=1010s)
*   Outlook add-ins and Outlook REST V2 decommission – [Juan Balmori](https://twitter.com/juaneloBalmori), Principal Program Manager (Microsoft) | @juaneloBalmori – [22:40](https://youtu.be/O47gN9P8KAI&t=1360s)
*   Community spotlight: [Maarten van Stam](https://twitter.com/aafvstam) (Deloitte) – [38:49](https://youtu.be/O47gN9P8KAI&t=2329s)
*   Q&A – [39:35](https://youtu.be/O47gN9P8KAI&t=2375s)

## Actions

*   Register for the [PnP Recognition Program](https://aka.ms/m365pnp-recognition)

## Q&A (Question & Answers)

### Excel data type APIs

**Would dot notation formula work if you name the cell? So instead of \`=B1.Address\` can you do \`=MyCell.Address\`?**

Yes! We have tried to make it as accessible as possible.

### Word online API updates

**Can we use bookmarks in content controls?**

Yes, the Word APIs support this.

**When are getting events like \`on close\` / \`on open\` / \`on share\` in Word?**

Sorry, we haven't had a plan to enable these APIs yet but would love to hear more scenarios around this at [https://aka.ms/m365dev-suggestions.](https://aka.ms/m365dev-suggestions)

**Can we also get the content of a field or only the list of fields?**

You can get the field contents as well.

**The current preview of Word APIs has been going a long time. When will this release (with version number)?**

No definitive ETA yet. As we have a bunch of new APIs in preview for Word, we're planning to have new requirement sets for these APIs.

### Outlook add-ins and Outlook REST V2 decommission

**Does the extension for add-ins apply only to add-ins deployed via the store? What about enterprise deployed add-ins?**

The extension applies to all add-ins regardless of how they are deployed. As long as the add-in runs before November 2022, it will be granted the extension. Add-ins developed after November 2022 will not be granted the extension.

**If the manifest is changed after November 2022 on an enterprise install, will this affect the extension granted to the add-in? Will the detection of pre-existing add-ins be tied to the manifest ID?**

No, the manifest is not part of how extensions are tracked for add-ins. There is a token passed on the call that we identify the add-in with.

**Could we have a demo of a basic Outlook add-in using Microsoft Graph in the future?**

Yes, please see our Outlook SSO sample at: [https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/auth/Outlook-Add-in-SSO.](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/auth/Outlook-Add-in-SSO)

**Is there a way to check if a certain add-in's ID is on your "extension" list?**

Yes, you can submit a REST API Add-in verification request here: [https://aka.ms/RESTCheck.](https://aka.ms/RESTCheck)

**I have a legacy client who is using on-premise Exchange only with Azure AD hybrid. We're having to fall back to rest.**

You want to use EWS in this case.

### Miscellaneous Q&A

**I have a question on how to manage an Office Add-in with multiple task panes. I'm creating an Excel add-in with two task panes. Can I use the same file.html and only change the content of the file, based on the URL routing (react-router-dom)?**

You could do this by passing a parameter in the URL request, such as "index.html?page1" and "index.html?page2". Then, when your page loads, you use the parameter to render the appropriate UI. You can also use the same parameter approach in the manifest file to specify which task pane to load.

**We are getting an increased number of reports from customers that our add-in sporadically disappears from the ribbon in Word. It is a problem for us, as people don't use what they can't see. Many are very un-tech savvy, and don't know how to reactivate add-ins (especially if they are used to their central admin pushing them out to them).**

**Is this a known issue? Is there any setting in the manifest file that we might have missed? We would appreciate any information that might point us in the right direction to solve this.**

Sorry to hear this is happening. We'd like to look into this more. Can you please create a GitHub issue at [https://github.com/OfficeDev/office-js/issues](https://github.com/OfficeDev/office-js/issues)? We need more information like whether its specific to a platform or happening on all platforms. Is it happening only for centrally deployed add-ins or user deployed as well? Is it specific to an app, all apps? Please use the Issues template and we'll follow up with you on the GitHub issue.

**Are there any updates on using Word JS APIs to compare two word documents programmatically? Something similar to the Document.Compare method but for the JS API. Thank you!**

We don't have anything in the works on this. Can you please submit a suggestion at [https://aka.ms/m365dev-suggestions](https://aka.ms/m365dev-suggestions)? If you can provide more details about this scenario that would be super helpful.

**Are there any updates to this feature request? [Office JS Save and Close methods for Word, Excel and PowerPoint](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/office-js-save-and-close-methods-for-word-excel-and-powerpoint/idi-p/2800214)**

We don't have plans at this time. It would be great if we could connect with you and learn more about this scenario. If you can reach out to us on a future community call chat, we can set up some more direct communication. Thanks!

**In "Office Add-ins community call – December 8, 2021", the answer was "Outlook on mobile will support event-based add-ins first, and then smart alerts." This is very good news! Our customers are asking for a mobile add-in that will confirm the content when sent. Just to confirm, do you plan to introduce only Smart Alerts in Outlook Mobile, and not the On-send feature? Also, will Smart Alerts be part of your 2022 Q2 goals? We are very excited about getting an add-in working by events in Outlook Mobile, thank you!**

Yes, this is on the backlog. The Outlook mobile team is focusing first on event-based add-ins (compose event). They're hoping to release this soon. After that, they plan to roll out smart alerts.


**Can Power automate 'Excel Run script' run macros in a .xlsm file?**

No, you can't run VBA macros using the Run Script action. However, you can run Office Scripts in a .xlsm file. See [https://learn.microsoft.com/office/dev/scripts/develop/macros-power-automate](https://learn.microsoft.com/office/dev/scripts/develop/macros-power-automate) for more information.


**Is it possible to get the w14:paraId attribute value for paragraphs using the API? When getting the Open XML, it is not included even if the paragraphs have w14:paraId attributes.**

Thanks for the question, which is super interesting! Can you please post this on Stack Overflow at [https://stackoverflow.com/questions/tagged/office-js](https://stackoverflow.com/questions/tagged/office-js) with more details so we can have a deeper look?

**Are there any plans to allow change of appointment organizer?**

This is not allowed by the Outlook user experience, so there really isn't a way to add extensibility here.

**We have a client using Outlook 2019 Volume License edition and they are stuck in using Internet Explorer as the host, is there any intention to update this to support Edge/Chromium as later e3/e5 builds do and the retail version does**

As per [Browsers used by Office Add-ins - Office Add-ins](https://learn.microsoft.com/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) | Microsoft Docs, Office 2019 uses Trident (IE), there is no plan to backport. If they want to stay in that licensing model they can upgrade to Office 2021 which uses WebView2.


**Is there a plan to support Message.Compose on native mobile add-ins?**

Yes, we are working on this.

## Resources

*   Documentation – [Call Exchange web services from an Outlook add-in](https://learn.microsoft.com/office/dev/add-ins/outlook/web-services) | [https://learn.microsoft.com/office/dev/add-ins/outlook/web-services](https://learn.microsoft.com/office/dev/add-ins/outlook/web-services)
*   REST API Add-in verification request – [https://aka.ms/RESTCheck](https://aka.ms/RESTCheck). 
*   Article – [Outlook REST API v2.0 production and beta endpoint deprecation](https://devblogs.microsoft.com/microsoft365dev/outlook-rest-api-v2-0-deprecation-notice/) | [https://devblogs.microsoft.com/microsoft365dev/outlook-rest-api-v2-0-deprecation-notice](https://devblogs.microsoft.com/microsoft365dev/outlook-rest-api-v2-0-deprecation-notice)
*   Sample – [Single Sign-on (SSO) sample Outlook add-in](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/auth/Outlook-Add-in-SSO) | [https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/auth/Outlook-Add-in-SSO](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/auth/Outlook-Add-in-SSO) 

### Office Add-ins community call

*   [Upcoming agenda and previous call resources](https://aka.ms/officeaddinsagenda)
*   [Recurring, monthly community call calendar invite](https://aka.ms/officeaddinscommunitycall)
*   [Community call topic requests and questions](https://aka.ms/officeaddinsform)
*   Community call recordings on the [YouTube Microsoft 365 community channel](https://www.youtube.com/channel/UC_mKdhw-V6CeCM7gTo_Iy7w)

### Office Add-ins feedback

*   Technical questions – Microsoft Q&A ([office-js-dev](https://learn.microsoft.com/answers/topics/office-js-dev.html)), ([office-addins-dev](https://learn.microsoft.com/answers/topics/office-addins-dev.html))
*   Issues – [GitHub](https://github.com/OfficeDev/office-js/issues)
*   Recommendations and suggestions – [Microsoft 365 Developer Platform ideas](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform)
