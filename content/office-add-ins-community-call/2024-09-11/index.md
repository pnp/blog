---
title: "Office Add-ins developer platform community call – September 11, 2024"
summary: "Topics include: PowerPoint Preview APIs and Ribbon 1.1 API Updates​ by Ester Bergen​, Senior Product Manager at Microsoft, Word API Update​ by Yun Wang, Principal Product Manager​ at Microsoft and Steve Jin, Senior Product Manager at Microsoft, A new NAA sample for Outlook event-based add-ins​ by David Chesnut, Senior Technical Writer at Microsoft, Visual Studio Code extension for Office Add-ins Public Preview by Mingjia Liu, Product Manager2 at Microsoft.  Call hosted by Mingjia Liu, Product Manager2 at Microsoft. WXP Add-ins with the Unified manifest for Microsoft 365 Public Preview by Luyi Han​, Senior Product Manager​ at Microsoft.Recorded on September 11, 2024."
date: 2024-09-11T07:00:00-05:00
author: "Mingjia Liu"
githubname: MingjiaLiu1995
categories: ["Office add in developer community call"]
images:
- images/office-add-ins-community-call-2024-09-11.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/cJK9rvCTeAY
draft: true
---

# Office Add-ins developer platform community call - September 11

## This month's agenda and presenters

The call was hosted by [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager, Microsoft.

* **PowerPoint Preview APIs and Ribbon 1.1 API Updates** [Ester Bergen](https://www.linkedin.com/in/esterbergen/), Senior Product Manager at Microsoft.
* **Word API Update** [Yun Wang](https://www.linkedin.com/in/airwangyun/), Principal Product Manager at Microsoft and [Steve Jin](https://www.linkedin.com/in/steve-jin-61b08011), Senior Product Manager at Microsoft.
* **A new NAA sample for Outlook event-based add-ins** [David Chesnut](https://www.linkedin.com/in/davidpchesnut), Senior Technical Writer at Microsoft.
* **Visual Studio Code extension for Office Add-ins Public Preview** [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager2 at Microsoft.
* **WXP Add-ins with the Unified manifest for Microsoft 365 Public Preview** [Luyi Han](https://www.linkedin.com/in/luyihan/), Senior Product Manager at Microsoft.

* **Q&A.** [Mingjia Liu](https://www.linkedin.com/in/mingjia-liu-90a69a24a/), Product Manager, Microsoft.

{{< youtube cJK9rvCTeAY >}}

## View video segments

* Introduction [00:00](https://youtu.be/cJK9rvCTeAY?t=0)
* PowerPoint Preview APIs and Ribbon 1.1 API Updates [01:27](https://youtu.be/cJK9rvCTeAY?t=87)
* Word API Update [04:56](https://youtu.be/cJK9rvCTeAY?t=296)
* A new NAA sample for Outlook event-based add-ins [12:20](https://youtu.be/cJK9rvCTeAY?t=740)
* Visual Studio Code extension for Office Add-ins Public Preview [25:05](https://youtu.be/cJK9rvCTeAY?t=1505)
* WXP Add-ins with the Unified manifest for Microsoft 365 Public Preview [27:02](https://youtu.be/cJK9rvCTeAY?t=1622)
* Q&A [33:16](https://youtu.be/cJK9rvCTeAY?t=1996)
* Resources [39:10](https://youtu.be/cJK9rvCTeAY?t=2350)

## Resources related to this blog's content
PowerPoint Preview APIs and Ribbon 1.1 API Updates
* [PowerPoint JavaScript preview APIs](https://learn.microsoft.com/javascript/api/requirement-sets/powerpoint/powerpoint-preview-apis?view=common-js-preview)
* [Ribbon API requirement sets](https://learn.microsoft.com/javascript/api/requirement-sets/common/ribbon-api-requirement-sets?view=common-js-preview#ribbon-api-11)
* [Enable and Disable Add-in Commands](https://learn.microsoft.com/office/dev/add-ins/design/disable-add-in-commands)

WXP Add-ins with the Unified manifest for Microsoft 365 Public Preview
* [Install the Office Add-ins Development Kit](https://marketplace.visualstudio.com/items?itemName=msoffice.microsoft-office-add-in-debugger)
* [M365 blog annoucement](https://devblogs.microsoft.com/microsoft365dev/announcing-the-office-add-ins-development-kit-for-visual-studio-code-public-preview/)
* [Create Office Add-in projects using Office Add-ins Development Kit for Visual Studio Code (preview)](https://learn.microsoft.com/office/dev/add-ins/develop/development-kit-overview?tabs=vscode)

## Q&A (Question & Answers)

**The OnMessageReadWithCustomHeader and OnMessageReadWithCustomAttachment Events are currently in preview on Classic Outlook (only). Is there a timeline when these Events will be in preview on other platforms? Is the expectation these will be in Requirements Set 1.15, and is that planned for release at this time?**

These events on other platforms are already in our backlog and are coming soon. Please stay tuned for the updates.

**There's a common ask from Microsoft on these calls for functionality gaps between Outlook COM add-ins and Office.js. One such gap is that Office.js add-ins don't support being used from the context-menu but COM add-ins do. I can find prior reference online to this being a requested feature from 2018. Can we get some insight onto if the Office.js team would offer support for making add-ins available in the context menu e.g. when right-clicking an email show configured MessageRead add-ins in the menu.**

We don’t have any plans to allow web add-ins to be accessible via a context menu currently but would like to learn more about your scenario. Please leave a message in chat or submit a feature request [here](https://aka.ms/m365dev-suggestions).

**I'm going to submit my Excel add-in on Partner Center Microsoft 365 and Copilot. I've created a related Partner Center SaaS transactable offer under the Commerical Marketplace. The SaaS offer setup has a section that asks do you have published Teams apps, Office Add-ins etc. and if you select the Yes radio button, it asks you to fill in your AppSource link. [This page](https://learn.microsoft.com/partner-center/marketplace-offers/plan-saas-offer) says: "For linked products, search on AppSource will return with one result that includes both SaaS and all linked add-ins. Customer can navigate between the product detail pages of the SaaS offer and linked add-ins. IT admins can review and deploy both the SaaS and linked add-ins within the same process through an integrated and connected experience within the Microsoft 365 admin center." So my understanding is that as soon as I publish my Excel add-in and its up on AppSource, I just copy that link and put it in my SaaS offer setup and publish it. Then there will be a single AppSource offer for my add-in that will be transactable. Is my understanding correct?**

AFor submission process, please check the related document [here](https://learn.microsoft.com/partner-center/marketplace-offers/plan-saas-offer), where it shows you how to plan a SaaS offer for the Microsoft commercial marketplace. If you have additional questions about Publish Center, you can post them in our [Microsoft Partner Community​](https://techcommunity.microsoft.com/category/PartnerCommunity).

**I've implemented the Microsoft SaaS Accelerator my SaaS transactable offer (which I will link to my Excel Partner Center Add-In offer). This creates a webhook, landing page and admin portal for my SaaS offer, which I have been testing. The admin portal shows me the Purchaser Email and Marketplace Subscription ID. I've been working on getting SSO working for my add-in (just starting to test it) which I think is referred to as Authentication. I think I will still need to figure out how to get Authorization working, so only those folks who have purchased the transactable app on AppSource can use it. Can you provide some guidance on how to implement this?**

Single Sign-On (SSO) Authentication: Since you're already working on SSO, you're setting up a way to authenticate users based on their existing Microsoft identity. This part of the setup confirms the identity of the users. The official documentation on implementing SSO for Office Add-ins can be found [here](https://learn.microsoft.com/office/dev/add-ins/develop/sso-in-office-add-ins?tabs=jsonmanifest).​

Authorization via SaaS Fulfillment APIs: For authorization, you'll need to check if the user has an active subscription for your SaaS offer after they are authenticated. This involves using the Microsoft SaaS Fulfillment APIs, which allow you to verify subscription status. Here’s the documentation on [SaaS Fulfillment API](https://learn.microsoft.com/partner-center/marketplace-offers/partner-center-portal/pc-saas-fulfillment-life-cycle).​

**When I submit my Excel add-in to the Partner Center it says "Provide any critical testing instructions, including test accounts, license keys and test credentials. Failure to do so results in an automatic rejection ." Once I get Authorization working for my transactable app, is there some sort of a way to provide a back-door so that I can give that info to the Partner Center Certification team?**

You can set up a test account and add the necessary information to your critical test instructions. Please check [here](https://learn.microsoft.com/partner-center/marketplace-offers/add-in-submission-guide). 

**I have uploaded all of my Excel Add-in dist folder files to my Azure subscription Storage account Blob Container $web folder, which my Manifest points to. Is this the appropriate place to put these files? Should it only contain a subset of the dist folder files? This location does work, but I'm not sure how to secure this location so that someone can't find this location and take all these files.**

Yes, uploading your Excel Add-in distribution files to your Azure subscription's Storage account Blob Container in the $web folder is an appropriate and common practice. However, there's no way to prevent from other people getting as the locations of these manifests are public, so they can be accessed by others.

## Call to action

* Join a community panel – product focused add-in discussion groups.
    * [Outlook add-ins panel](https://ux.microsoft.com/Panel/OutlookAddinDeveloper)
    * [Excel add-ins panel](https://ux.microsoft.com/Panel/ExcelAddinDeveloper)
    * [Word add-ins panel](https://ux.microsoft.com/Panel/WordAddinDeveloper)
    * [PowerPoint add-ins panel](https://ux.microsoft.com/Panel/PowerPointAddinDeveloper)
    * [Samples and docs](https://ux.microsoft.com/Panel/OfficeAddinImproveSamplesDocs)
* [Register for the PnP Recognition Program](https://pnp.github.io/recognitionprogram/) and earn contributor badges.
* Follow channels on X (formerly Twitter) to see call agendas, important updates, and release announcements.
    * [@microsoft365dev](https://twitter.com/microsoft365dev)
    * [@m365pnp](https://twitter.com/m365pnp)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free E5 developer tenant with instant availability and other assets.
* Join the [next community call](https://aka.ms/officeaddinscommunitycall) on October 9 at 7:00 AM Pacific Time.

## General Resources

* [Documentation](https://aka.ms/office-add-ins-docs)
* Quick Starts:
    * [Outlook](https://learn.microsoft.com/office/dev/add-ins/quickstarts/outlook-quickstart)
    * [Excel](https://learn.microsoft.com/office/dev/add-ins/quickstarts/excel-quickstart-jquery)
    * [Word](https://learn.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart)
    * [PowerPoint](https://learn.microsoft.com/office/dev/add-ins/quickstarts/powerpoint-quickstart)
* [Script Lab](https://aka.ms/getscriptlab)
* [Samples](https://aka.ms/officeaddinsamples)
* [Microsoft 365 Developer Program](https://aka.ms/M365devprogram)
* [Office Scripts](aka.ms/office-scripts-docs)
* [Technical questions about Office add-ins](https://aka.ms/office-addins-dev-questions)
* [Stack Overflow questions](https://stackoverflow.com). Use keywords **office-js**, **outlook-web-addins**, or **office-scripts**.
* [Github office-js issues](https://github.com/OfficeDev/office-js/issues)
* [Microsoft Tech Community – Submit feature requests](https://aka.ms/m365dev-suggestions)
* [Microsoft 365 Developer Program](https://aka.ms/M365devprogram)

## Stay connected

* See the full blog post for this call in the [Microsoft 365 platform community blog](https://aka.ms/m365pnp/blog)
* [X (formerly Twitter)](https://twitter.com/microsoft365dev)
* [Microsoft 365 Unified Sample gallery](https://aka.ms/community/samples)
* [Microsoft 365 Platform Community in YouTube](https://aka.ms/community/videos)
* [Microsoft 365 Platform Community](https://aka.ms/community/home)
* [Link to all Microsoft Developer Community calls](https://aka.ms/M365DevCalls)
* [Submit questions for next community call](https://aka.ms/officeaddinsform)
* [Next community call – October 9 at 07:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}
