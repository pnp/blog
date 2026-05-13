---
title: PnP PowerShell v3.2 released!
summary: PnP PowerShell is a cross-platform PowerShell module providing 815 (and counting) cmdlets that work with Microsoft 365 environments and more specifically SharePoint Online, Microsoft Teams, Microsoft Planner, and Power Automate.
date: 2026-05-13T01:00:00.000Z
author: Gautam Sheth
githubname: gautamdsheth
categories:
  - PnP PowerShell
images:
  - images/PnP-PS-RELEASE-32.png

tags:
  - .NET
  - Microsoft Entra ID
  - PnP PowerShell
  - Microsoft Teams
  - SharePoint
  - Microsoft Graph
type: trending
---

## 🚀 PnP PowerShell 3.2.0 Released!

After quite some time, we are excited to finally announce the release of **PnP PowerShell 3.2.0** 🎉

First things first — **thank you for your patience**.

It has been over a year since our last release, and we know many of you have been waiting for updates, fixes, and new capabilities. **We sincerely apologize for the delay**. The gap was not intentional. We ran into some **technical challenges around our signing process**, which blocked us from shipping a new release.

The good news? Those challenges are now behind us.

## 🤝 Now part of the .NET Foundation

One of the biggest milestones for this release is that **PnP PowerShell is now part of the .NET Foundation**. You might notice that PnP PowerShell DLLs are now signed by the .NET Foundation.

This is a huge step forward for the project.

Through this partnership, we now have access to proper **code-signing infrastructure**, which was the key blocker preventing us from shipping new releases. This ensures:

* Secure and trusted distribution of the module
* Compliance with stricter execution policies (like `AllSigned`)
* A sustainable path for future releases

This also means that **PnP PowerShell is unblocked again**, and we can return to a more regular release cadence going forward. We are also now signing nightly builds, so if your organization previously blocked unsigned binaries, this should help.

## 🔍 What's new in 3.2.0 – Key highlights

A lot has happened since the last release. While the full list is extensive, here are **three of the most impactful changes** in this version.

### ⚡ 1. Minimum PowerShell version

We heard from Azure Automation users who were blocked from using PnP PowerShell 3.1.0 because it required PowerShell **7.4.6**. After revisiting that requirement and confirming the related security issues have been resolved, PnP PowerShell now supports PowerShell **7.4.0** and later. This does not change much for most users, but it unblocks Azure Automation scenarios.

### 🛡️ 2. Federated Identity support

We are now pleased to announce support for federated identity using GitHub Actions and Azure DevOps. This was also a long-pending feature request. If you have set up federated identity in GitHub or Azure DevOps, you can now use the `-FederatedIdentity` parameter with `Connect-PnPOnline`.

### 🤖 3. SSO in Linux/WSL

As part of ongoing security improvements, we now support SSO login in Linux and WSL. When using `Connect-PnPOnline`, you can specify the `-OSLogin` parameter, which supports Conditional Access, FIDO keys, and other native OS authentication integrations. This already worked on Windows. Please check the documentation before using it, as it requires some changes to your Entra ID app registration.

## Changelog

These are just the top three highlights of the 3.2.0 release. You can find the full changelog [here](https://github.com/pnp/powershell/releases/tag/v3.2.0).

## 👥 Welcoming new maintainers

We are also excited to welcome **two new maintainers** to the PnP PowerShell project! 🎉

### 🧑‍💻 Nishkalank Bezawada

Nish works as a Lead Developer and Microsoft 365 Solutions Architect with a deep passion for SharePoint and Microsoft 365. He has always felt that the community has given so much to developers like him, and now it's his time to give back by making meaningful contributions.

You can connect with him on [LinkedIn](https://www.linkedin.com/in/nishkalankbezawada) or [GitHub](https://github.com/NishkalankBezawada) here.

### 🧑‍💻 Reshmee Auckloo

Reshmee Auckloo is a Modern Workplace Consultant at Avanade, a Microsoft MVP, and an active contributor to the Microsoft 365 & Power Platform community. As a Core PnP Team Member, Reshmee is passionate about community-driven innovation and sharing knowledge through open source and technical advocacy.

You can connect with her on [LinkedIn](https://www.linkedin.com/in/reshmee-auckloo-98a23619) or [GitHub](https://github.com/reshmee011) here.

Their involvement strengthens the project and ensures we continue to grow, improve, and support the community effectively. They have already helped us a lot with the issues list and features. We are thrilled to have them.

## 🙌 Contributors

This release would not have been possible without the amazing contributions from the community members listed below (in random order) ❤️

- [James May](https://github.com/fowl2)
- [Kinga](https://github.com/kkazala)
- [Noel Tautges](https://github.com/NoelTautges)
- [Nishkalank Bezawada](https://github.com/NishkalankBezawada)
- [Irving](https://github.com/irvcov)
- [Koen Zomers](https://github.com/koenzomers)
- [Janne Holm](https://github.com/jhholm)
- [Marc D Anderson](https://github.com/sympmarc)
- [abwlodar](https://github.com/abwlodar)
- [Reshmee Auckloo](https://github.com/reshmee011)
- [wuxiaojun514](https://github.com/wuxiaojun514)
- [pajeffery](https://github.com/pajeffery)
- [Giacomo Pozzoni](https://github.com/jackpoz)
- [sofbkeller](https://github.com/sofbkeller)
- [Ali Robertson](https://github.com/alirobe)
- [Christian Veenhuis](https://github.com/ChVeen)
- [James Epp](https://github.com/jamesaepp)
- [Sven Boll](https://github.com/svenboll)
- [Joshua Henderson](https://github.com/JoshuaSHenderson)
- [Siddharth Vaghasia](https://github.com/siddharth-vaghasia)
- [David Schenk](https://github.com/davidschenkUPG)
- [reusto](https://github.com/reusto)
- [gaiking-uk](https://github.com/gaiking-uk)

We deeply appreciate every issue reported, PR submitted, and discussion started.

## 📦 Getting started

You can install or update to the latest version using:

```powershell
Install-Module PnP.PowerShell
# or
Update-Module PnP.PowerShell
```

PnP PowerShell continues to be a **cross-platform module with 800+ cmdlets** supporting Microsoft 365 workloads, including SharePoint, Teams, and more.

## 💬 Try it out, share feedback and stay connected

We encourage you to:

* Try out the new version
* Explore the new capabilities
* Update your scripts

And most importantly:

* 👉 **Report any issues or bugs you encounter**
* 👉 **Share feedback and suggestions**
* 👉 **Raise feature requests**

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/powershell/issues). Your input directly shapes the future of this project.

## 🚀 What's next

With the release pipeline unblocked, we're excited to:

* Return to **more frequent releases**
* Continue improving performance and reliability
* Add more capabilities based on your needs

We will also help the PnP Framework and PnP Core projects publish newer versions in the coming days.

## Need more information?

For additional guidance on getting started or to explore detailed information about commands, architecture, or the project itself, visit [aka.ms/pnppowershell](https://aka.ms/pnppowershell).

Thank you again for your patience, support, and contributions 🙏

Happy scripting! 💙
