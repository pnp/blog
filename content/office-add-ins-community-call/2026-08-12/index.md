---
title: "Office Add-ins developer platform community call – August 12, 2026"
summary: "Topics include: AI tool to verify if an add-in has a first-run experience by Ricky Kirkham, Unified manifest general availability by Emma Saboureau. Call hosted by Mansi Agrawal, Product Manager. Recorded on August 12, 2026."
date: 2026-08-12T14:00:00Z
author: "Sam Ramon"
githubname: samantharamon
categories: ["Office add in developer community call"]
images:
  - images/office-add-ins-community-call-2026-08-12.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
  - https://youtu.be/vl9WhxMw400
draft: true
---

# Office Add-ins developer platform community call - August 12, 2026

{{< youtube vl9WhxMw400 >}}

## This month's agenda and presenters

- **Add-in First-run Precheck tool** – Ricky Kirkham, Principal Technical Writer. Ricky demonstrated the First-run Precheck tool, an AI prompt that inspects an Office Add-in package and reports whether its startup experience meets a key Microsoft Marketplace requirement. He also introduced a repository for AI prompts, skills, agents, and other tools for Office developers.
- **Unified manifest general availability** – Emma Saboureau, Senior Product Manager. Emma announced that unified manifest support is generally available for Word, Excel, PowerPoint, and Outlook add-ins, including Excel custom functions. She demonstrated how to convert an XML manifest to JSON, package and sideload the add-in, and prepare for migration while maintaining compatibility with clients that still require the XML manifest

## View video segments

- Introduction and agenda [00:04](https://www.youtube.com/watch?v=vl9WhxMw400&t=4s)
- Add-in First-run Precheck tool [01:00](https://www.youtube.com/watch?v=vl9WhxMw400&t=60s)
- Unified manifest general availability [20:41](https://www.youtube.com/watch?v=vl9WhxMw400&t=1241s)
- Q&A [32:15](https://www.youtube.com/watch?v=vl9WhxMw400&t=1935s)

## Resources related to this blog's content

- [Office-Developer-Tools GitHub repository](https://github.com/OfficeDev/Office-Developer-Tools)
- [Build Once, Run Everywhere: Unified Manifest for Office Add-Ins now Generally Available](https://devblogs.microsoft.com/microsoft365dev/unified-manifest-for-office-add-ins-now-ga/)
- [Office Add-ins with the unified manifest for Microsoft 365](https://learn.microsoft.com/office/dev/add-ins/develop/unified-manifest-overview)
- [Convert an Office Add-in to use the unified manifest for Microsoft 365](https://learn.microsoft.com/office/dev/add-ins/develop/convert-xml-to-json-manifest)

## Q&A (question & answers)

**Is there any plan to add a way to listen to slide changes in PowerPoint? We currently have to poll the current slide every few hundred milliseconds, that's neither efficient nor convenient and is basically impossible to use for us because we have real-time websocket updates which create infinite loops on PowerPoint web, as the edited slide is still rendered in the background when starting a presentation.**

At the moment, we don't have plans to add a new API for listening to slide changes. We appreciate the feedback and will add it to our backlog. Additionally, please create a request for this feature on the [Microsoft 365 Developer Platform Ideas Forum](https://techcommunity.microsoft.com/category/microsoft365/ideas/microsoft365developerplatform).

## Documentation updates and highlights

| Category | Article | Description |
| -------- | ------- | ----------- |
| General | [Request permissions for API use in add-ins](https://learn.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins) | Learn about the different permission levels you can declare in your add-in to access the Office JavaScript APIs. |
| Copilot extensibility | [Create a Copilot skill for Excel that uses the Office JavaScript library (preview)](https://learn.microsoft.com/office/dev/add-ins/excel/excel-copilot-skill) | Preview how to create a Copilot skill for Excel that uses the Office JavaScript library. |
| Outlook | [Preview encryption add-in improvements](https://learn.microsoft.com/office/dev/add-ins/outlook/encryption-decryption) | Preview improvements for your encryption add-in. |

## Call to action

- Join the [next community call](https://aka.ms/officeaddinscommunitycall) on September 9, 2026 at 7:00 AM Pacific Time.

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

