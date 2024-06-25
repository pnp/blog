---
title: "Transforming SharePoint add-ins to SPFx solutions"
date: 2023-01-16T04:00:00.000Z
author: Vesa Juvonen
githubname: VesaJuvonen
categories:
  - SPFx
images:
  - images/11-sharepoint-add-ins-to-spfx-solutions.png
tags:
  - Microsoft Teams
  - Microsoft Viva
  - SharePoint Framework (SPFx)
type: regular
videos:
draft: false
---

[SharePoint Framework](https://aka.ms/spfx) (SPFx) is an extensibility model for Microsoft 365 enabling developers to build different kinds of extensibility for Microsoft Viva, Microsoft Teams, Outlook, Microsoft 365 app (Office), and SharePoint. SPFx has multiple benefits like automatic Single Sign On, automatic hosting in the customer tenant, reuse same code across the service and industry standard web stack tooling.

-	*We still have SharePoint add-ins in use, should we move them to SPFx model?*
-	That is a great question. You should absolutely look for options to transform any SharePoint add-in apps to the SPFx solution or to any other suitable model.

{{< notice note>}}
This blog post is part of a month long SPFx series for January 2023. Each business day we'll publish a new blog post covering different aspects of the SPFx.

* Previous blog post in this series - [Creating single part app page for SharePoint Online with SPFx](https://pnp.github.io/blog/post/spfx-10-single-part-app-pages/)
* Next blog post in this series - [Publishing SPFx solution offerings to app source and SharePoint store](https://pnp.github.io/blog/post/spfx-12-publishing-spfx-solutions-store/)
{{< /notice >}}


## Transforming and modernizing SharePoint add-ins

Microsoft initially released the [SharePoint add-in model](https://learn.microsoft.com/sharepoint/dev/sp-add-ins/sharepoint-add-ins) (and Office add-in model) back in 2012 with the SharePoint 2013 release. This technique was designed to be the cloud first extensibility model with an option to use it in Microsoft 365 (Office 365 at the time). Previously SharePoint extensibility was based on the server-side extensibility which was deployed to the specific servers or with the Sandbox solution model, which never really took off.

This means that the add-in model is already more than 10 years old, and Microsoft has not really invested in this model since the introduction of SPFx development pattern. SharePoint add-ins are still fully supported in SharePoint Online or in the on-premises, but it's expected that the support will be removed at some point, and we do not recommend investing in this model for any new features or capabilities.

Depending on the add-in implementation details, you should be looking at following options:

* SharePoint hosted add-ins - These are UX level extensibility in site level which is exactly the model which SPFx supports
* SharePoint provider hosted add-is - This depends a bit on the implementation details, but you would be looking to use SPFx and Azure AD registered apps

Documentation and references

- [Migrating JSLink customizations to SharePoint Framework Field Customizers](https://learn.microsoft.com/sharepoint/dev/spfx/extensions/guidance/migrate-jslink-to-spfx-extensions)
- [Migrating user custom actions and ECB menu items to SharePoint Framework Extensions](https://learn.microsoft.com/sharepoint/dev/spfx/extensions/guidance/migrate-user-customactions-to-spfx-extensions)
- [Migrate Edit Control Block (ECB) menu items to SharePoint Framework extensions](https://learn.microsoft.com/sharepoint/dev/spfx/extensions/guidance/migrate-from-ecb-to-spfx-extensions)
- [Migrating from JSLink to SharePoint Framework extensions](https://learn.microsoft.com/sharepoint/dev/spfx/extensions/guidance/migrate-from-jslink-to-spfx-extensions)
- [Migrating from UserCustomAction to SharePoint Framework extensions](https://learn.microsoft.com/sharepoint/dev/spfx/extensions/guidance/migrate-from-usercustomactions-to-spfx-extensions)
- [Migrate existing Script Editor web part customizations to the SharePoint Framework](https://learn.microsoft.com/sharepoint/dev/spfx/web-parts/guidance/migrate-script-editor-web-part-customizations)

## Frequent questions around single part app pages


**Are SharePoint add-ins officially deprecated?**

No. SharePoint add-ins are still fully supported for SharePoint Online and for SharePoint on-premises. We have not announced official deprecation for them. Deprecation means that we are announcing officially that there are no longer investments in the feature and as part of the deprecation announcement, we might provide specific end of lifes schedule for the feature. This has not happened for SharePoint add-ins.

**Will you keep on supporting SharePoint add-ins also in future?**

For now, yes. Every technology has, however, a lifecycle and sooner or later SharePoint add-ins will no longer be supported.

**We have plenty of add-ins, you are not planning to simply drop it - right?**

We would never simply drop the support without proper communications. Whenever the depreciation and end-of-life timeline is provided, we will provide enough time for the customers to transform to other techniques. This is absolutely needed to avoid any business-critical impact when the feature is removed. Any specific timeline will be shared with the deprecation statement and can be anything from 6-12-18-24 months.


**Why are you writing about SharePoint add-ins, they are no longer used**

SharePoint add-ins are still widely used, and we even still see new submissions to the app source around partner offerings which are based on the add-in model. We do not recommend using SharePoint add-ins anymore unless it's for legacy reasons. You should not create any new add-ins anymore.

**Why doesn’t the modern SharePoint contain script editor web part?**

This often comes as a question related to this discussion. Challenge with the classic script editor web part is that it opens direct security issue as it enables site owners to embed any script code on the page when it's being accessed without centralized approval and coordination by administrators. Security is critical for our customers in the cloud, and we do not want to promote options which could compromise our customers. This is exactly why the SPFx solutions will need to be deployed and approved by administrators, so that there's centralized control and approval on what's being used.


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
