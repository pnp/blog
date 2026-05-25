---
title: "PnP Framework v1.19.0 – .NET 10 support, lighter dependencies, and steady progress"
summary: "PnP Framework v1.19.0 is out — bringing .NET 10 support, the removal of the Microsoft.Graph package dependency, flexible sections in the provisioning engine, and several community-driven fixes."
description: "PnP Framework v1.19.0 is out — bringing .NET 10 support, the removal of the Microsoft.Graph package dependency, flexible sections in the provisioning engine, and several community-driven fixes."
date: 2026-05-26T01:00:00+00:00
author: "Ejaz Hussain"
githubname: ejazhussain
categories:
  - Community post
images:
  - images/cover.png
tags:
  - .Net
  - PnP
  - PnP Framework
  - PnP Provisioning
  - SharePoint
  - SharePoint Online
  - Microsoft 365
type: regular
---

## 🗒️ Quick intro

[PnP Framework](https://github.com/pnp/pnpframework) is a .NET library targeting Microsoft 365 that contains the PnP Provisioning engine and a ton of useful extension methods to make you more productive while developing for SharePoint Online.

With v1.19.0 now available on [NuGet](https://www.nuget.org/packages/PnP.Framework/1.19.0), let's walk through what's new 👇

## 🚀 Why this release matters

If you've been following the recent updates across the PnP ecosystem, you'll know that we recently shipped [PnP Core SDK v1.16.0](https://pnp.github.io/blog/post/pnp-core-sdk-1-16-release/) — which was all about unblocking the release pipeline, getting signed builds working again, and bringing in .NET 10 support.

PnP Framework v1.19.0 is the natural companion to that effort. Since PnP Framework depends on PnP Core SDK under the hood (now aligned to PnP.Core >= 1.16.0), getting that foundation right was a prerequisite for this release too.

But this release isn't just a version bump — it brings meaningful improvements of its own, including .NET 10 support, a leaner dependency footprint, and several community-contributed fixes to the provisioning engine.

## 🔥 .NET 10 support

Just like PnP Core SDK, PnP Framework now ships with **first-class .NET 10 support**. The package targets .NET 8.0, .NET 9.0, .NET 10.0, and .NET Standard 2.0 — so whether you're on the latest runtime or maintaining something on an older framework, you're covered.

## 📦 Removed Microsoft.Graph dependency

One change worth highlighting — the dependency on `Microsoft.Graph` packages has been completely removed [#1003](https://github.com/pnp/pnpframework/pull/1003). This is a significant change that makes the package lighter and avoids potential version conflicts in projects that bring in their own Microsoft Graph SDK version. If you were previously dealing with binding redirect headaches or conflicting Graph package versions, this should make your life easier.

## 📋 What's inside the changelog

For the full list of changes, check the [release notes](https://github.com/pnp/pnpframework/releases/tag/1.19.0). Here are the highlights:

- **Support for .NET 10.0** — first-class target alongside .NET 8.0, .NET 9.0, and .NET Standard 2.0
- **Provisioning engine: flexible sections on pages** — the provisioning engine now supports flexible sections on modern pages [#1159](https://github.com/pnp/pnpframework/pull/1159)
- **System.Text.Json updated to 9.0.0** — for the .NET Standard build, keeping things aligned with current ecosystem standards
- **Removed Microsoft.Graph package dependency** — leaner footprint, fewer version conflicts [#1003](https://github.com/pnp/pnpframework/pull/1003)
- **Fixed exception in page transformation error handling** — resolved an issue when throwing error messages during page transformation [#1158](https://github.com/pnp/pnpframework/pull/1158)
- **Null footer DisplayName handling** — safely handles null footer DisplayName in ProvisionObjects to avoid REST API failures [#1161](https://github.com/pnp/pnpframework/pull/1161)
- **Fixed vertical section control export** — corrected an issue where vertical section controls were being exported with the wrong Column [#1232](https://github.com/pnp/pnpframework/pull/1232)

## 🙌 Community and contributors

This release would not have been possible without contributions from the community. We would like to express our huge gratitude and shout out to (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Bert Jansen](https://github.com/jansenbe)
- [Christian Zuellig](https://github.com/czullu)
- [quails4Eva](https://github.com/quails4Eva)
- [Rene Nicolao](https://github.com/nicolaor)
- [Vasco Azevedo](https://github.com/vascoazevedo08)
- [Yihua Jin](https://github.com/AlanJinTS)

And to everyone in the wider **PnP community** who raised issues, shared feedback, and stayed engaged — thank you 🙏

> PnP is not just a set of libraries — it's a **community-driven effort**.

## 🐞 Found something?

If you run into issues or have suggestions, please open an issue on the repo:

👉 <https://github.com/pnp/pnpframework/issues>

You can also contribute with a PR — we'd love to see it!

## 📥 Get the package

👉 [PnP.Framework 1.19.0 on NuGet](https://www.nuget.org/packages/PnP.Framework/1.19.0)

Onwards and upwards 🚀