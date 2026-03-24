---
title: Office Add-ins community call – March 11, 2026
summary: Learn about platform direction and quality investments for Office Add-ins, hybrid Blazor-based add-ins, and upcoming changes to Outlook inline image attachments. Recorded on March 11, 2026
date: 2026-03-11T07:00:00-08:00
author: "David Chesnut"
githubname: davidchesnut
categories: ["Office add in developer community call"]
images:
- images/office-add-ins-community-call-2026-03-11.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/77Op-no2wsY
draft: true
---

## Office Add-ins developer platform community call – March 2026

{{< youtube 77Op-no2wsY >}}

## Agenda and presenters

- **Open letter and Auto Open updates**
    - Sean Laberee – Principal Group Product Manager at Microsoft
    - [1:34](https://youtu.be/77Op-no2wsY?t=94)
- **Hybrid Blazor-based Office Add-ins**
    - Martin Van Stam – Microsoft MVP 
    - [33:40](https://youtu.be/77Op-no2wsY?t=2020)
- **Temporary Attachment IDs for add-in added inline images** 
    - Arpit Sangwan – Software Engineer at Microsoft 
    - [53:44](https://youtu.be/77Op-no2wsY?t=3224)
- **Q&A (Question & Answers)**
    - David Chesnut - Senior technical writer at Microsoft
    - [1:00:26](https://youtu.be/77Op-no2wsY?t=3626)

## Open letter and Auto Open updates

[1:34](https://youtu.be/77Op-no2wsY?t=94)

This month's call began with a discussion around recent developer feedback regarding Office Add-ins reliability, deployment consistency, and long-standing regressions.

The Office Add-ins team shared several ongoing initiatives aimed at improving platform quality and stability across Outlook, Word, Excel, and PowerPoint, including:

- Continued investment in the unified manifest across Office applications.
- Improvements to deployment consistency.
- Quality-focused investments across core Office.js APIs.
- Investigation into an Office.js NPM package.
- Multi-provider, cross-geo failover redundancy following recent outages.

The team also highlighted plans to introduce a recurring **Quality Corner** in future community calls to share updates on resolved bugs and quality improvements based on issues logged in the Office.js GitHub repository.

### More information

- [Increased control over Office Add-in user experiences](https://devblogs.microsoft.com/microsoft365dev/increased-control-over-office-add-in-user-experiences/)

## Task pane auto-open updates

[26:03](https://youtu.be/77Op-no2wsY?t=1563)

To address user concerns around add-ins unintentionally embedding themselves into shared documents, several changes are being introduced:

- Add-ins will no longer be able to automatically set the `AutoShowTaskpaneWithDocument` property without explicit user interaction.
- Task panes closed by users will no longer reopen automatically.
- Users will only be prompted to install add-ins when required for document functionality.

These updates are expected to begin rolling out in mid-to-late April.

## Hybrid Blazor-based Office Add-ins

[33:40](https://youtu.be/77Op-no2wsY?t=2020)

Martin Van Stam presented updated hybrid Blazor-based Office Add-in samples that enable developers to:

- Run add-in logic on both the server and client.
- Interact with Office documents using Office.js APIs.
- Register event handlers for Word content controls.
- Use Fluent UI components.
- Execute .NET logic alongside JavaScript APIs.

These hybrid templates are intended to provide a migration path for developers transitioning from COM or VSTO add-ins to Office.js-based web add-ins while continuing to leverage existing .NET development expertise.


## Outlook inline image attachment changes

[53:44](https://youtu.be/77Op-no2wsY?t=3224)

Arpit Sangwan presented an important update regarding how add-ins handle inline image attachments in Outlook on Web and the new Outlook for Windows. The Office JS API `addFileAttachmentFromBase64Async` will now return a temporary client-generated ID for inline images instead of a server-generated ID. This change means add-ins can immediately reference images without waiting for server upload, improving reliability and reducing latency.

## Q&A (Question & Answers)

[1:00:26](https://youtu.be/77Op-no2wsY?t=3626)

**Is there a known issue with an Office Add-in's buttons appearing multiple times in the ribbon? If so what is the cause and fix?**

There can be a few causes:

- The Office Add-in cache could be out of sync. You can try [clearing the cache](https://learn.microsoft.com/office/dev/add-ins/testing/clear-cache).
- There could be duplicate command definitions in the manifest.
- You could have the same add-in deployed more than once, such as from both the Microsoft Store, and from a developer sideload. 
- If it’s none of these, please create a GitHub issue on https://github.com/OfficeDev/Office-js 

**Is there an update regarding the ability to have Office.js expose the individual members of a group in Outlook? It was mentioned last month that there would be an update in the Microsoft Office Developer's blog but it doesn't seem like there was any update regarding this.**

There's an API change in our backlog to get the members of a distribution list (DL), but it has not yet been implemented. Developers may be able to use a Microsoft Graph API to retrieve group members. We're hoping to implement the DL API soon.

## Call to action

- Join the [next community call](https://aka.ms/officeaddinscommunitycall) on April 8th at 7:00 AM Pacific Time.

## General Resources

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
- [Next community call – December 11th at 07:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}