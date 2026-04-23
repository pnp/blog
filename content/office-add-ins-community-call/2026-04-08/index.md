---
title: "Office Add-ins developer platform community call – April 2026"
summary: "Topics include: Blazor-based Office add-ins demo (Leon Gorbaty, CTO Standards Core LLC), Office servicing simplified (Chris Hopkins, Senior Product Manager), Add-in quality and deployment updates (Sean Laberee, Principal Group Product Manager). Call hosted by Mansi Agarwal, Product Manager. Recorded on April 2026."
date: 2026-04-08T07:00:00-05:00
author: "David Chesnut"
githubname: davidchesnut
categories: ["Office add in developer community call"]
images:
- images/office-add-ins-community-call-2026-01-14.png
tags: ["Office Add-ins","Microsoft 365"]
type: "regular"
videos:
- https://youtu.be/EM_r3HlPkHM
draft: true
---

# Office Add-ins developer platform community call - April 2026

{{< youtube EM_r3HlPkHM >}}

## This month's agenda and presenters

- **Blazor-based Office add-ins demo – Leon Gorbaty (CTO Standards Core LLC)**  
  Leon demonstrated how to build Office add-ins for Word and Excel using Blazor, highlighting reusable components, integration with existing .NET libraries, and use of the Fluent UI component library to modernize UI and simplify styling. Check out more at [https://standards-core.ai](https://standards-core.ai) and [https://launchpadcommons.com](https://launchpadcommons.com) 

- **Office servicing simplified – Chris Hopkins (Senior Product Manager)**  
  Chris announced upcoming changes to Office servicing, including the unification of enterprise update channels. The first phase will begin in July, with both Monthly Enterprise and Semi-Annual channels receiving the same builds to reduce fragmentation.

- **Add-in quality and deployment updates – Sean (Principal Group Product Manager)**  
  Sean shared updates on improving add-in deployment reliability, including work to address centralized deployment issues, increased investment in telemetry and diagnostics, and continued progress toward adoption of the unified manifest.

---

## View video segments

- Introduction and announcements [00:04](https://youtu.be/EM_r3HlPkHM?t=5)
- Blazor-based Office add-ins demo [01:24]( https://youtu.be/EM_r3HlPkHM?t=84)
- Office servicing simplified announcement[25:00](https://youtu.be/EM_r3HlPkHM?t=1500)
- Add-in quality and deployment updates[27:12](https://youtu.be/EM_r3HlPkHM?t=1632)
- Q&A and closing remarks[36:28](https://youtu.be/EM_r3HlPkHM?t=2188)

---

## Resources related to this blog's content

**Blazor:**

- [https://dotnet.microsoft.com/en-us/apps/aspnet/web-apps/blazor](https://dotnet.microsoft.com/en-us/apps/aspnet/web-apps/blazor)
- Component Libraries: [https://blazor.radzen.com](https://blazor.radzen.com), [https://www.telerik.com/blazor-ui](https://www.telerik.com/blazor-ui), [https://www.infragistics.com/blogs/blazor-component-libraries](https://www.infragistics.com/blogs/blazor-component-libraries), [https://www.fluentui-blazor.net/](https://www.fluentui-blazor.net/)
    
---

## Q&A (Question & Answers)

**Could we get "referred in" or "used in" documentation in classes? Now, if a developer seeks out a desired object from the API, there is no way to find the objects that has an access to that object type. E.g. "OLEFormat is referred in Word.Field"**

Currently the tooling we use doesn't generate reference documentation in a way you can discover which classes use a specific type. We're working to add relevant samples that clearly show the object model. If you find a type that needs better documentation or samples, please let us know at [Issues · OfficeDev/office-js-docs-reference](https://github.com/OfficeDev/office-js-docs-reference/issues).

**Why doesn't .exportAsBase64 keep embedded fonts when exporting the slide?**

We have shared the query with the respective team. Please follow the GitHub issue for the updates - [PowerPoint.Slide.exportAsBase64 does not preserve embedded fonts in exported .pptx · Issue #6613 · OfficeDev/office-js](https://github.com/OfficeDev/office-js/issues/6613)

## Documentation updates and highlights

| Category | Article | Description |
| --------- | --------- | ------------- |
| **General** | [Office Add-ins glossary](https://learn.microsoft.com/office/dev/add-ins/resources/resources-glossary) | Familiarize yourself with commonly used terms in the Office Add-ins development space. |
| **Developer Experience** | [Office Add-ins with the unified manifest for Microsoft 365](https://learn.microsoft.com/office/dev/add-ins/develop/unified-manifest-overview) | Learn how to create an Excel, Outlook, PowerPoint, or Word add-in that uses a unified manifest for Microsoft 365. |
| **Developer Experience** | [Usability testing for Office Add-ins](https://learn.microsoft.com/office/dev/add-ins/develop/usability-testing) | Learn how to run usability test for your Office Add-in. |
| **Outlook** | [Changes to attachment IDs for inline images in Outlook on the web and the new Outlook on Windows](https://devblogs.microsoft.com/microsoft365dev/changes-to-attachment-ids-for-inline-images-in-outlook-add-ins/) | Learn how a recent update to the way inline attachments are handled when programmatically added to a mail item could impact your add-in. |
| **UI** | [Dialog: Don't use window.open](https://learn.microsoft.com/office/dev/add-ins/develop/dialog-api-in-office-add-ins#dont-use-windowopen) | Familiarize yourself with the guidelines for implementing dialogs in your Office Add-in, including avoiding window.open() in your code. |
| **PowerPoint** | [Script Lab sample: Get shape from selected shapes by ID](https://github.com/OfficeDev/office-js-snippets/blob/prod/samples/powerpoint/shapes/get-shape-by-id.yaml) | Run the sample in [Script Lab](https://learn.microsoft.com/office/dev/add-ins/overview/explore-with-script-lab) to learn how to get and use shape IDs with selected shapes. |
| **PowerPoint** | [Script Lab sample: Get selected slides](https://github.com/OfficeDev/office-js-snippets/blob/prod/samples/powerpoint/slide-management/get-slide-by-id.yaml) | Run the sample in Script Lab to learn how to get the IDs of selected slides and to get one of the currently selected slides by its ID. |
| **PowerPoint** | [Script Lab sample: Get and set theme color scheme](https://github.com/OfficeDev/office-js-snippets/blob/prod/samples/powerpoint/slide-management/get-set-theme-color-scheme.yaml) | Run the sample in Script Lab to learn how to get and set the theme colors of a selected slide. |
| **PowerPoint** | [Script Lab sample: Get and set slide background fill](https://github.com/OfficeDev/office-js-snippets/blob/prod/samples/powerpoint/slide-management/get-set-background-fill.yaml) | Run the sample in Script Lab to learn how to get and set the background fill of a slide using solid, gradient, pattern, and picture fill types. |
| **Word** | [Script Lab sample: Table formatting](https://github.com/OfficeDev/office-js-snippets/blob/prod/samples/word/40-tables/manage-formatting.yaml) | Run the sample in Script Lab to learn how to get and set formatting details of a table, table row, and table column, including borders, alignment, and cell padding. |
| **Word** | [Script Lab sample: Get file as PDF in slices](https://github.com/OfficeDev/office-js-snippets/blob/prod/samples/word/50-document/get-file-as-pdf.yaml) | Run the sample in Script Lab to learn how to get the current document as a PDF in slices and save it locally. |
| **Word** | [Script Lab sample: Insert symbol](https://github.com/OfficeDev/office-js-snippets/blob/prod/samples/word/55-selection/insert-symbol.yaml) | Run the sample in Script Lab to learn how to insert a Unicode or ANSI symbol at the selection. |

---

## Call to action

- Join the [next community call](https://aka.ms/officeaddinscommunitycall) on May 13, 2026 at 7:00 AM Pacific Time

---

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
- [Next community call – December 11th at 07:00am PT](https://aka.ms/officeaddinscommunitycall)

{{< attachments >}}{{< /attachments >}}
