---
title: "Office Add-ins developer platform community call – November 8, 2023"
summary: "Topics include: Microsoft Teams Apps for Word, Excel, and PowerPoint presented by Luyi Han, Senior Product Manager at Microsoft and Improvements to the undo behavior in Excel custom functions presented by Dongqi Lv, Senior Software Engineer and Miaofei Wang, Senior Software Engineer at Microsoft. Call hosted by Sam Ramon, Technical Writer at Microsoft. Recorded on November 8, 2023."
date: 2023-11-08T08:01:00-05:00
author: "Sam Ramon"
githubname: samantharamon
categories: ["Office add in developer community call"]
images:
- images/office-add-ins-community-call-2023-11-08.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/2LeK8X9RElU
draft: true
---

# Office Add-ins developer platform community call - November 8, 2023

## This month's agenda and presenters

The call was hosted by [Sam Ramon](https://github.com/samantharamon), Technical Writer, Microsoft.

* **Microsoft Teams apps for Word, Excel, and PowerPoint.** [Luyi Han](https://www.linkedin.com/in/luyihan/), Senior Product Manager, Microsoft.

* **Improvements to the undo behavior in Excel custom functions.** Dongqi Lv, Senior Software Engineer, Microsoft | [Miaofei Wang](https://www.linkedin.com/in/miaofei-wang), Senior Software Engineer, Microsoft.

* **Q&A.** [Sam Ramon](https://github.com/samantharamon), Technical Writer, Microsoft.

{{< youtube 2LeK8X9RElU >}}

## View video segments

* Introduction [00:00](https://youtu.be/2LeK8X9RElU?t=0)
* Microsoft Teams apps for Word, Excel, and PowerPoint [2:01](https://youtu.be/2LeK8X9RElU?t=121)
* Improvements to the undo behavior in Excel custom functions [7:55](https://youtu.be/2LeK8X9RElU?t=475)
* Q&A [12:13](https://youtu.be/2LeK8X9RElU?t=733)
* Resources [16:04](https://youtu.be/2LeK8X9RElU?t=964)
* Closing [18:13](https://youtu.be/2LeK8X9RElU?t=1093)

## Call to action

* Complete the [Teams apps for Word, Excel, and PowerPoint survey](https://forms.office.com/r/JVeLPSPgtW).
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
* Join the [next community call](https://aka.ms/officeaddinscommunitycall) on December 13th at 8:00 AM Pacific Time.

## Q&A (Question & Answers)

**We currently have a functioning VSTO add-in installed on users' machines. We've also created a new web add-in. How can we transition seamlessly from the VSTO add-in to the web add-in? Is there a method to detect if the web add-in is installed locally on a user's machine from the VSTO add-in? Is there a means to initiate or open the web add-in from within the VSTO add-in?**

To learn about how to transition from a VSTO add-in to an Office web add-in, see [Make your Office Add-in compatible with an existing COM add-in](https://learn.microsoft.com/office/dev/add-ins/develop/make-office-add-in-compatible-with-existing-com-add-in).

**Is it a good idea to host an add-in within an existing public web application (Next.js)? For example, adding a dedicated route https://.../excel to host the add-in pages.**

You should be able to host an add-in within an existing public web application. One of the purposes of add-ins is to surface existing web apps in an Office task pane. If you need additional help to develop your add-in, we encourage you to post a question to the [Microsoft Q&A](https://aka.ms/office-addins-dev-questions) or [Stack Overflow](https://stackoverflow.com) forums.

**We are distributing an admin-managed Office Add-in to users within our organization via the Integrated Apps feature in the Office 365 admin center. What's the best way to monitor the number of users who have successfully installed it?**

Unfortunately, there currently isn't a way to monitor how many users have successfully installed an add-in that was distributed through the Integrated Apps feature in the Microsoft 365 admin center. If this is a feature you’d like to see in the product, please submit a feature request to <https://aka.ms/ms365dev-suggestions>. 

**Was that change in GitHub issue <https://github.com/OfficeDev/office-js/issues/3745#issuecomment-1761194542> announced within the community call? Since July, there has been a slowdown in the release of videos on YouTube (<https://www.youtube.com/playlist?list=PLR9nK3mnD-OVExAWBr2QtS_5UmqUr7HL4>) and also no updates to the blog. At this time, the September video from last month has not been published and there has been no updates to the blog about September call.**

The removal of the URL sideloading option in Outlook wasn’t announced in a previous community call. We’ve reached out to the team who manages this feature to discuss this in a future call.

We apologize for the inconvenience with the delay in posting community call recordings and blog posts. The most recent recordings are now available in the [Microsoft 365 Platform Community YouTube channel](https://aka.ms/community/videos). We’re working to get the blog posts published as soon as possible.

**Is Win64 in scope for improvements to the undo behavior in Excel custom functions?**

Yes, Win64 is in scope.

**When it comes to Outlook add-ins, is "Centralized Deployment" still supported, or should we move to "Integrated Apps"? We're seeing massive issues with our Outlook add-in after the new OWA layout with "Apps" instead of "Get Add-ins".**

Centralized Deployment is still supported in Outlook, but must meet some Microsoft 365 requirements (see the "Microsoft 365 Requirements" section of [Determine if Centralized Deployment of add-ins works for your organization](https://learn.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins#microsoft-365-requirements)). However, we recommend the use of Integrated Apps to deploy add-ins as it provides more features to help you manage your add-ins. To learn more, see [Deploy and manage Office Add-ins](https://learn.microsoft.com/microsoft-365/admin/manage/office-addins).

If you haven't already, please open a [GitHub issue](https://github.com/OfficeDev/office-js/issues), so that the team can help investigate the issues you're experiencing.

**Can it be answered as to whether the dev of COM add-ins is going to be deprecated in the near future? (I sure hope not!)**

We have no plans to deprecate COM add-ins in the near future. However, we encourage developers to invest in JavaScript-based Office web add-ins to take advantage of cross-platform support, centralized deployment and distribution, and other advanced features.

## Resources related to this blog's content

* Survey: [Teams apps for Word, Excel, and PowerPoint survey](https://forms.office.com/r/JVeLPSPgtW)
* Documentation: [Limitations of calling Excel JavaScript APIs through a custom function](https://learn.microsoft.com/office/dev/add-ins/excel/call-excel-apis-from-custom-function#limitations-of-calling-excel-javascript-apis-through-a-custom-function)

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
* [Next community call – December 13th at 08:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}
