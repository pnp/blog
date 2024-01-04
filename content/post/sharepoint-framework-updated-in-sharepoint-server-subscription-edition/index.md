---
title: SharePoint Framework Updated in SharePoint Server Subscription Edition

# Add a summary to convince readers to read your article (recommended). It will display on the homepage.
summary: For the first time in 7 years, Microsoft has updated the installed version of the SharePoint Framework in an on-premises SharePoint Server deployment!
date: 2023-04-05T05:50:37-04:00

# Author. Your own name
author: "Andrew Connell"

# GitHub username.
githubname: "andrewconnell"

# Featured image
# To use, add an image named `thumbnail.jpg/png` to your page's images folder. Make sure to replace the placeholder image
images:
- images/feature.png

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
# Community posts should always use "Community post" as the categories
tags: ["SharePoint Framework (SPFx)"]
categories: ["Community post"]
canonicalURL: https://www.voitanos.io/blog/sharepoint-framework-updated-in-sharepoint-server-subscription-edition/
---
> This article originally appeared on Andrew Connell's site, **[SharePoint Framework Updated in SharePoint Server Subscription Edition](https://www.voitanos.io/blog/sharepoint-framework-updated-in-sharepoint-server-subscription-edition/?utm_medium=website&utm_source=pnpblog&utm_campaign=blog&utm_content=SharePoint%20Framework%20Updated%20in%20SharePoint%20Server%20Subscription%20Edition)**, where it's [also available as a video](https://youtu.be/sQhUTQkgL4s) and podcast episode.

Microsoft released the SharePoint Framework (SPFx) in early 2017 & followed up later that year with a Feature Pack for SharePoint Server 2016. Since then, the latest version of SPFx has been available exclusively on SharePoint Online, but the version included in the on-premises deployments of SharePoint Server was stuck to that version.

This meant that SharePoint Server 2016 (with Feature Pack 2) is stuck on [SPFx v1.1.0](https://learn.microsoft.com/sharepoint/dev/spfx/release-1.1?MT.wc_id=M365-MVP-21083), SharePoint Server 2019 is stuck on [SPFx v1.4.1](https://learn.microsoft.com/sharepoint/dev/spfx/release-1.4.1?MT.wc_id=M365-MVP-21083), and SharePoint Server Subscription Edition (SE) is stuck on SPFx v1.4.1.

> **Working with SPFx in SharePoint On-Premises?**
>
> Check out my series **[Definitive guides for developers to SharePoint Framework for SharePoint Server on-premises](https://www.voitanos.io/series/definitive-guide-sharepoint-framework-sharepoint-server?dst=pnpblog&utm_medium=website&utm_source=pnpblog&utm_campaign=blog&utm_content=SharePoint+Framework+Updated+in+SharePoint+Server+Subscription+Edition)** for detailed steps on setting up your SPFx developer environment for all three (3) SharePoint Server on-premises deployments. All include workarounds & accompanying video demos!

Until now 😳

Microsoft recently released the a new 23H1 feature release for SharePoint Server SE, the second such feature pack (following 22H1), and as part of this release they’ve bumped the SPFx version for the first time in an on-premises deployment! 😱

Don’t get too excited… the installed version of SPFx was only bumped up to [SPFx v1.5.1](https://learn.microsoft.com/sharepoint/dev/spfx/release-1.5.1?MT.wc_id=M365-MVP-21083)… that version was released just 4 months after SPFx v1.4.1 was released in 2018, *four years ago*.

The only changes we saw in the SPFx v1.5.1 release were minor from my perspective:

- Support for additional package managers, not just NPM, such as Yarn & PNPM
- TSLint was bumped from v5.6 to v5.9.1 - *I’ve already discussed the TSLint vs. ESLint [at great length](https://www.voitanos.io/search?q=tslint+eslint&dst=pnpblog&utm_medium=website&utm_source=pnpblog&utm_campaign=blog&utm_content=SharePoint+Framework+Updated+in+SharePoint+Server+Subscription+Edition)*

## What’s the point of such a minor update?

I asked the same question when I learned this was coming. If you’re going to upgrade the version of SPFx, why not make more of an impact?

Apparently Microsoft wants to take small steps to show their commitment to upgrading SPFx for on-premises SharePoint deployments… like **really small steps**.

In [their blog post](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/what-s-new-for-sharepoint-server-subscription-edition-march-2023/ba-p/3768752?MT.wc_id=M365-MVP-21083), Bill Baer said: *"This is the first step on a long-term journey to continue investing in SharePoint Framework for SharePoint Server Subscription Edition."*

For now, **I don’t see any reason why you should rush to get this feature pack installed if your goal is to upgrade your SPFx version**. Nothing compelling was added to SPFx in the 4 months between the v1.4.1 & v1.5.1 releases in 2018.

Will they hold to this commitment to upgrade the SPFx in future feature packs? We’ll see… with the current release cadence, apparently we should set our calendars to next spring. 🤷‍♂️

## What about SharePoint 2016 & 2019

Sorry, but there’s no change in the plans or stance for these versions. This update exclusively applies to SharePoint Server SE. I don’t expect we’ll ever see updates to SharePoint Server 2016 or 2019 with respect to SPFx.

If you’re stuck with an on-premises deployment, SharePoint Server SE is your only hope to get an updated version of SPFx.
