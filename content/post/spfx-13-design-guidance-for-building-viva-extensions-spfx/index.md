---
title: "Design guidance and assets on building Microsoft Viva extensions with SPFx"
date: 2023-01-18T04:00:00.000Z
author: Vesa Juvonen
githubname: VesaJuvonen
categories:
  - SPFx
images:
  - images/13-design-guidance-assets-viva-spfx.png
tags:
  - Microsoft Teams
  - Microsoft Viva
  - SharePoint Framework (SPFx)
type: regular
videos:
- https://www.youtube.com/watch?v=zcCNaQya1BA
- https://www.youtube.com/watch?v=ouKq4i9RjbY
draft: false
---

[SharePoint Framework](https://aka.ms/spfx) (SPFx) is an extensibility model for Microsoft 365 enabling developers to build different kinds of extensibility for Microsoft Viva, Microsoft Teams, Outlook, Microsoft 365 app (Office), and SharePoint. SPFx has multiple benefits like automatic Single Sign On, automatic hosting in the customer tenant, reuse same code across the service and industry standard web stack tooling.

-	*We are curious on the art of possible with SPFx for Microsoft Viva. Would you have any design assets supporting on how to get started?*
-	That is a great question. We absolutely have design guidance and assets available which are showcasing the art of possible. There are also countless of Microsoft and community provided samples for the Microsoft Viva, which are great resources to see what's possible.

{{< notice note>}}
This blog post is part of a month long SPFx series for January 2023. Each business day we'll publish a new blog post covering different aspects of the SPFx.

* Previous blog post in this series - [Publishing SPFx solution offerings to app source and SharePoint store](https://pnp.github.io/blog/post/spfx-12-publishing-spfx-solutions-store/)
* Next blog post in this series - [Getting Started with using PnPjs in your SPFx solutions](https://pnp.github.io/blog/post/spfx-14-getting-started-with-pnpjs-spfx/)
{{< /notice >}}


## Design guidance and assets for Viva Home and Viva Connections solutions

As the Viva Home and Viva Connections experiences are a new extensibility option for customers and aprtners, we have worked on providing speficic guidance for these areas to provide you inspiration and also a starting point as you start designing experiences for the Viva Home and for Viva Connections.

Key design guidance for the Viva Card experiences:

- [Designing Viva Connections custom cards for your dashboard](https://learn.microsoft.com/sharepoint/dev/spfx/viva/design/designing-card)
- [Designing Viva Connections Quick Views](https://learn.microsoft.com/sharepoint/dev/spfx/viva/design/designing-quick-view)

Here's a video showcasing the different adaptive card designs Microsoft has provided for inspirational purposes around Microsoft Viva. These assets are availble for reuse anyway you need from [GitHub](https://github.com/pnp/adaptivecards-templates).

{{< youtube zcCNaQya1BA >}}

To also showcase how the adaptive cards designs can be made dynamic with SPFx solutions, we have partnered with Sympraxis Consulting to provide you fully [open-source reference solutions](https://github.com/pnp/spfx-reference-scenarios/tree/main/samples/ace-designtemplate-gallery) which is also available from the [app source / SharePoint store](https://appsource.microsoft.com/en-US/product/office/WA200003929?exp=ubp8). This solution is showcasing the Microsoft provided designs as real SPFx ACEs and also includes guidance with the integration to the Microsoft Teams apps - like with deep linking and with other scenarios. This solution is a great solution to be installed from the app source / SharePoint store to showcase the art of possible with the Microsoft Viva dashboard for Viva Home or Viva COnnections.

{{< youtube ouKq4i9RjbY >}}


## Frequent questions around Viva Home and Viva Connections design guidance

**When will the Adaptive Cards in ACEs be supporting a newer version?**

At time of writing this article, you can only use Adaptive Cards v1.3 when you design your ACE experiences. We are looking to support v1.5 starting from the SPFx v1.17 release currently planned for the first quarter of 2023.

**What's the role of SPFx in the Viva components, wouldn't adaptive cards be enough?**

Adaptive Cards are used as the static presentation layer, but if you’d like to show dynamic data or behaviours, you’d use SPFx as the orchestrator for accessing the data using APIs and for reacting to the user actions.

## References

Here are some initial references to get started with the SPFx in your development. Please do provide us with feedback and suggestions on what is needed to help you to get started with the SPFx development for Microsoft 365.

-	SPFx documentation – https://aka.ms/spfx
-	Issues and feedback around SPFx - https://aka.ms/spfx/issues
-	Microsoft 365 Platform Community – https://aka.ms/m365/community
-	Public SPFx and other community calls – https://aka.ms/m365/calls
    - These calls are for everyone to take advantage to stay up to date on the art of possible within Microsoft 365 and to provide guidance for beginners and more advance users
-	SPFx samples in the Microsoft 365 Unified Sample gallery – https://aka.ms/m365/samples

- - -

We will provide more details on the different options and future direction of the SPFx in upcoming blog posts. This post focused on the getting started steps with SPFx - more details coming up with this series with one post within each business day of January 2023.
