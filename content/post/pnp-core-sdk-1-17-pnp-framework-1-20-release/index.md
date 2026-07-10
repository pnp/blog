---
title: "PnP Core SDK v1.17.0 and PnP Framework 1.20.0 release"
date: 2026-07-08T01:00:00.000Z
author: "Adam Wójcik"
githubname: adam-it
categories: ["Community post"]
images:
- images/main.png
tags: [".Net", "SDK", "PnP Core SDK", "PnP Framework", "SharePoint"]
type: "regular"
summary: "PnP Core SDK v1.17.0 and PnP Framework 1.20.0 are out — bringing new features, improvements, and community-driven enhancements."
description: "PnP Core SDK v1.17.0 and PnP Framework 1.20.0 are out — bringing new features, improvements, and community-driven enhancements."
---

## 🗒️ Quick intro

[PnP Core SDK](https://github.com/pnp/pnpcore) is a modern .NET SDK designed to work for Microsoft 365. It provides a unified object model for working with SharePoint Online and Teams which is agnostic to the underlying APIs being called.

[PnP Framework](https://github.com/pnp/pnpframework) is a .NET library targeting Microsoft 365 containing the PnP Provisioning engine and a ton of other useful extensions.

Both libraries received a fresh release, so let's bundle them together and walk through what's new 👇

## 🌍 Better support for sovereign clouds

The headline theme for this release is **sovereign cloud support**. Both libraries got improvements here so that more customers running in specialized cloud environments can rely on PnP tooling.

- **PnP Core SDK** added support for new sovereign cloud environments [#1727](https://github.com/pnp/pnpcore/pull/1727) and the environments were renamed in `CloudManager` and `Microsoft365Environment` for clarity and consistency [#1787](https://github.com/pnp/pnpcore/pull/1787).
- **PnP Framework** added support for the **DelosCloud**, **BleuCloud** and **GovSGCloud** environments [#1245](https://github.com/pnp/pnpframework/pull/1245).

Big thanks to [Gautam Sheth](https://github.com/gautamdsheth) for driving these across both repos.

## 🔥 What's new in PnP Core SDK v1.17.0

Here are the more interesting items from this release:

- **Fixed vertical section type detection** and added a regression test for save/reload [#1772](https://github.com/pnp/pnpcore/pull/1772) [Rene Nicolao]
- **Fixed a folder race condition** for more reliable folder operations [#1770](https://github.com/pnp/pnpcore/pull/1770) [Aram B]
- **Fixed news page thumbnails** that did not appear in the news web parts [#1782](https://github.com/pnp/pnpcore/pull/1782) [Pedro Monte]
- **Separated the `QuickLaunchEnabled` call** from the batch in the branding manager. This was a critical fix for the problem with provisioning headers using PnP Provisioning engine [#1789](https://github.com/pnp/pnpcore/pull/1789) [Patrik Hellgren]
- **Added support for new sovereign cloud environments** [#1727](https://github.com/pnp/pnpcore/pull/1727) and **renamed** them in `CloudManager` and `Microsoft365Environment` [#1787](https://github.com/pnp/pnpcore/pull/1787) [Gautam Sheth]
- **Updated to the modern DocFx theme** with dark mode support for the docs [#1773](https://github.com/pnp/pnpcore/pull/1773) [Paul Bullock]
- **Improved repo security** [#1785](https://github.com/pnp/pnpcore/pull/1785) and **updated the setup test env script** [#1769](https://github.com/pnp/pnpcore/pull/1769) [Adam Wójcik]

For the full list of changes, check the [PnP Core SDK release notes](https://github.com/pnp/pnpcore/releases/tag/1.17.0).

## 🔥 What's new in PnP Framework v1.20.0

And here is what landed in PnP Framework:

- **Bumped MSAL.NET to 4.85.2** to stay current with the latest identity library [#1245](https://github.com/pnp/pnpframework/pull/1245)
- **Added support for DelosCloud, BleuCloud and GovSGCloud** sovereign cloud environments [#1245](https://github.com/pnp/pnpframework/pull/1245) [Gautam Sheth]
- **Fixed an empty section issue** deployed from an XML template [#1179](https://github.com/pnp/pnpframework/pull/1179) [Christian Zuellig]
- **Fixed an Owner/Member add and delete issue** [#1247](https://github.com/pnp/pnpframework/pull/1247) [Per Jakobsen]

For the full list of changes, check the [PnP Framework release notes](https://github.com/pnp/pnpframework/releases/tag/1.20.0).

## 🙌 Community and contributors

These releases would not have been possible without the help of some really awesome folks who stepped in and kept things moving. We would like to express our huge gratitude and shout out to (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Aram B](https://github.com/aramB)
- [Christian Zuellig](https://github.com/czullu)
- [Gautam Sheth](https://github.com/gautamdsheth)
- [Patrik Hellgren](https://github.com/patrikhellgren)
- [Paul Bullock](https://github.com/pkbullock)
- [Pedro Monte](https://github.com/PedroMordeP)
- [Per Jakobsen](https://github.com/singingknight)
- [Rene Nicolao](https://github.com/nicolaor)

And to everyone in the wider **PnP community** who raised issues, shared feedback, contributed code, and kept the momentum going — that feedback mattered. A lot.

> PnP is not just a set of libraries — it's a **community-driven effort**.

## 🐞 Found something?

If you run into issues or have suggestions, please open an issue on the repos:

👉 [PnP Core SDK issues](https://github.com/pnp/pnpcore/issues)

👉 [PnP Framework issues](https://github.com/pnp/pnpframework/issues)

You can also contribute with a PR — we'd love to see it!

## 📥 Get the package

👉 [PnP.Core 1.17.0 on NuGet](https://www.nuget.org/packages/PnP.Core/1.17.0)

👉 [PnP.Framework 1.20.0 on NuGet](https://www.nuget.org/packages/PnP.Framework/1.20.0)
