---
title: "Office Add-ins developer platform community call – July 8, 2026"
summary: "Topics include: Office.js API delivery updates by Jonah Karpman, Building Copilot skills for Excel by Sankalp Madaan and Merry Zebro, Office.js quality updates by Akshay Dixit. Call hosted by Mansi Agrawal, Product Manager. Recorded on July 8, 2026."
date: 2026-07-08T14:00:00Z
author: "Alex Jerabek"
githubname: AlexJerabek
categories: ["Office add in developer community call"]
images:
  - images/office-add-ins-community-call-2026-07-08.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
  - https://youtu.be/QMImYn14FIM
draft: false
---

# Office Add-ins developer platform community call - July 8, 2026

{{< youtube QMImYn14FIM >}}

## This month's agenda and presenters

- **Office.js API delivery updates** — Jonah Karpman, Product Manager, Office.js API deployment pipeline. Jonah shared reliability improvements to the Office.js delivery infrastructure, including multi-provider CDN failover for Office.js endpoints. He also discussed ongoing work on an npm package for Office.js and a future unified domain for the Office.js API reference.
- **Building Copilot skills for Excel** — Sankalp Madaan, Product Manager for Office.js in Excel, and Merry Zebro, Software Engineer for Office.js in Excel. Sankalp introduced Copilot skills in Excel as reusable packages of instructions, artifacts, workflow steps, resources, scripts, and guardrails. Merry demonstrated how a skill package works using the user's Markdown file, resources, and Office.js scripts.
- **Office.js quality updates** — Akshay Dixit, Product Manager, Office Extensibility quality. Akshay shared the team's progress on triaging and resolving Office.js issues, focusing on Word and Excel issues raised since the open letter. He described the triage approach, recent fixes, issue-age insights, and the areas where the team is actively investing next.

## View video segments

- Introduction and agenda [0:00](https://youtu.be/QMImYn14FIM?t=0)
- Office.js API delivery updates [01:12](https://youtu.be/QMImYn14FIM?t=72)
- Building Copilot skills for Excel [3:52](https://youtu.be/QMImYn14FIM?t=232)
- Copilot skills for Excel demo: Zava Finance earnings quality dashboard [7:31](https://youtu.be/QMImYn14FIM?t=451)
- Copilot skills for Excel demo: player impact spotlight [8:00](https://youtu.be/QMImYn14FIM?t=480)
- Copilot skills package walkthrough [12:52](https://youtu.be/QMImYn14FIM?t=772)
- Office.js quality updates [20:44](https://youtu.be/QMImYn14FIM?t=1244)
- Q&A [27:51](https://youtu.be/QMImYn14FIM?t=1671)
- Documentation updates and highlights [30:02](https://youtu.be/QMImYn14FIM?t=1802)
- General resources and next call details [30:28](https://youtu.be/QMImYn14FIM?t=1828)

## Resources related to this blog's content

- [Office Add-ins documentation](https://aka.ms/office-add-ins-docs)
- [Office Add-ins developer questions](https://aka.ms/office-addins-dev-questions)
- [GitHub office-js issues](https://github.com/OfficeDev/office-js/issues)
- [Microsoft Tech Community – Submit feature requests](https://aka.ms/m365dev-suggestions)
- [Office Add-ins community call](https://aka.ms/officeaddinscommunitycall)
- [Submit questions for next community call](https://aka.ms/officeaddinsform)

## Q&A (questions and answers)

**Is there a plan to build an endpoint for extracting a user's full HTML email signature?**

Currently, there's no plan to develop this feature. If you'd like to request it, please submit your idea on [the Microsoft 365 Developer Platform ideas forum](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform).

**When will Mailbox API 1.15 support be available for the new macOS client?**

Mailbox API 1.15 support in macOS will be generally available by mid-August.

**We're interested in building Declarative Agents for the Microsoft 365 Copilot Agent Store, but our use case requires direct PowerPoint slide editing. Today, custom agents appear limited to chat interactions and can't participate in Copilot's PowerPoint authoring ("allow editing") experience. What's driving this limitation, and is support for third-party ISV agents in the editing experience on the roadmap, under consideration, or out of scope?**

The team demonstrated in Excel a preview of how skills are enabling similar capabilities. They're hoping to learn more about how people use these capabilities in Excel to inform the roadmap for bringing similar capabilities to other apps. Please try the Excel preview and share feedback, even if your ultimate use case is in PowerPoint.

**Our team is looking at extending our add-in to work with Copilot. Is there a supported way to display an image in the Copilot chat pane as part of an agent function response?**

While there's nothing specific to announce today, the product team is continuing to evaluate the best ways to connect add-in capabilities with Copilot. Please continue to monitor this forum for the latest developments.

**In one of the previous community calls, you mentioned you were working on support for offline Outlook web add-ins (no cloud-hosted JavaScript), especially for the OnMessageSend flow. Is there an update on that? Also, is there progress on exposing the user's final decision (Send/Don't Send) in OnMessageSend, similar to the legacy ItemSend API?**

The product team is still working on the offline support piece. It's technically complex, so they don't expect a meaningful update for a couple of months.

**Does the unified manifest currently work with custom functions, and is this feature still in beta?**

The product team shared that the unified manifest should work with custom functions and asked developers to raise a GitHub issue if they encounter problems. They also confirmed support is still in beta and continuing to roll out.

## Documentation updates and highlights

| Category | Article | Description |
|---|---|---|
| Developer experience | [Learn how to use the office-addin-cache tool](https://learn.microsoft.com/office/dev/add-ins/testing/clear-cache#use-the-office-addin-cache-tool) | Learn how to use the office-addin-cache tool to programmatically clear your cache. |
| Excel | [Try out Excel JavaScript API 1.21](https://learn.microsoft.com/javascript/api/requirement-sets/excel/excel-api-1-21-requirement-set) | Try out the new APIs introduced in Excel JavaScript API 1.21, including how to programmatically load linked entity cell values. |
| Excel | [Create custom functions in Excel](https://learn.microsoft.com/office/dev/add-ins/excel/custom-functions-overview?tabs=jsonmanifest) | Preview how to use the unified manifest with custom function add-ins. |
| Outlook | [Try out Outlook add-in API requirement set 1.16](https://learn.microsoft.com/javascript/api/requirement-sets/outlook/outlook-requirement-set-1-16) | Try the new Mailbox requirement set 1.16 features, including how to create an encryption add-in that handles the `OnMessageDecrypt` event. See the [announcement blog post](https://devblogs.microsoft.com/microsoft365dev/mailbox-requirement-set-1-16-now-available-for-outlook-add-ins/) for more details. |
| Outlook | [Updated blog post: Prepare your add-in for Outlook ribbon improvements](https://devblogs.microsoft.com/microsoft365dev/prepare-your-addin-for-outlook-ribbon-improvements/) | Review updated naming changes for add-in buttons on the ribbon in Outlook on the web and the new Outlook on Windows. |
| Outlook | [Sample: Invoke an Outlook add-in from an actionable message](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/outlook-actionable-message) | Run the sample to learn how to activate an Outlook add-in from an actionable message. |
| PowerPoint | [Create custom keyboard shortcuts](https://learn.microsoft.com/office/dev/add-ins/design/keyboard-shortcuts) | Implement custom keyboard shortcuts for your PowerPoint add-ins. |
| PowerPoint | [Sample: Use keyboard shortcuts for Office Add-in actions](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/office-keyboard-shortcuts) | Run the sample to test custom keyboard shortcuts for Office Add-ins. |

## Call to action

- Join the [next community call](https://aka.ms/officeaddinscommunitycall) on August 12, 2026 at 7:00 AM Pacific Time.

## General resources

- [Documentation](https://aka.ms/office-add-ins-docs)
- Quick Starts:
    - [Outlook](https://learn.microsoft.com/office/dev/add-ins/quickstarts/outlook-quickstart)
    - [Excel](https://learn.microsoft.com/office/dev/add-ins/quickstarts/excel-quickstart-jquery)
    - [Word](https://learn.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart)
    - [PowerPoint](https://learn.microsoft.com/office/dev/add-ins/quickstarts/powerpoint-quickstart)
- [Script Lab](https://aka.ms/getscriptlab)
- [Samples](https://aka.ms/officeaddinsamples)
- [Microsoft 365 Developer Program](https://aka.ms/M365devprogram)
- [Office Scripts](aka.ms/office-scripts-docs)
- [Technical questions about Office add-ins](https://aka.ms/office-addins-dev-questions)
- [Stack Overflow questions](https://stackoverflow.com). Use keywords **office-js**, **outlook-web-addins**, or **office-scripts**.
- [Github office-js issues](https://github.com/OfficeDev/office-js/issues)
- [Microsoft Tech Community – Submit feature requests](https://aka.ms/m365dev-suggestions)
- [Microsoft 365 Developer Program](https://aka.ms/M365devprogram)

## Stay connected

- See the full blog post for this call in the [Microsoft 365 platform community blog](https://aka.ms/m365pnp/blog)
- [X (formerly Twitter)](https://twitter.com/microsoft365dev)
- [Microsoft 365 Unified Sample gallery](https://aka.ms/community/samples)
- [Microsoft 365 Platform Community on YouTube](https://aka.ms/community/videos)
- [Microsoft 365 Platform Community](https://aka.ms/community/home)
- [Link to all Microsoft Developer Community calls](https://aka.ms/M365DevCalls)
- [Submit questions for next community call](https://aka.ms/officeaddinsform)

{{< attachments >}}{{< /attachments >}}
