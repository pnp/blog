---
title: "PnP Core SDK v1.16.0 – Back on track with .NET 10 and a new release foundation"
date: 2026-05-20T01:00:00.000Z
author: "Ejaz Hussain"
githubname: ejazhussain
categories: ["Community post"]
images:
- images/cover.png
tags: [".Net", "SDK", "PnP Core SDK", "SharePoint"]
type: "regular"
summary: "PnP Core SDK v1.16.0 is out — the first stable, signed release with .NET 10 support, a rebuilt release pipeline, and a new active maintainers team."
description: "PnP Core SDK v1.16.0 is out — the first stable, signed release with .NET 10 support, a rebuilt release pipeline, and a new active maintainers team."
---

## 🗒️ Quick intro

[PnP Core SDK](https://github.com/pnp/pnpcore) is a modern .NET SDK for working with Microsoft 365, providing a unified object model across SharePoint Online and Microsoft Teams.

With the latest release now available on [NuGet](https://www.nuget.org/packages/PnP.Core/1.16.0), let's walk through what's new 👇

## 🚀 Why this release matters

If you've been following the PnP Core SDK journey, you'll know this wasn't just another release cycle. For quite some time, progress was blocked by challenges that were outside of pure coding — signing pipeline issues, release process complexity, and dependencies between repositories.

To be honest — for a while, it felt like we were unblocking the process more than building new features.

Instead of rushing a quick fix, the team stepped back and rebuilt the foundation properly. The result is **v1.16.0** — the first stable, signed release in a while, and a signal that things are moving again.

## 🔥 First stable release with .NET 10 support

This is the **first non-beta release** that fully supports **.NET 10**. No hacks, no workarounds — just a clean, supported, forward-looking base for your projects.

## 🔐 Signed builds and a new release flow

We now have a proper, working signing flow. Builds are signed through the **PnP PowerShell pipeline**, which acts as the trusted environment for signing and packaging. It might not sound exciting at first glance — but this was the main blocker for a long time. Without a reliable way to sign and publish packages, nothing else could move forward. Solving it unlocks the ability to release consistently again.

On top of that, the entire release process has been completely overhauled. We now have automated build and signing, GitHub workflows handling packaging and publishing, and clear, maintainer-friendly guidance that any team member can follow. The goal was to remove single points of failure — no more "only one person knows how this works" situations. Going forward, any maintainer should be able to trigger a release with confidence 😄

## 📋 What's inside the changelog

For the full list of changes, check the [release notes](https://github.com/pnp/pnpcore/releases/tag/1.16.0). Here are some of the more interesting items:

- **Support for .NET 10.0** — a first-class, non-beta target
- **Support for reading Alerts** — you can now work with SharePoint Alerts through the SDK [#1688](https://github.com/pnp/pnpcore/pull/1688)
- **Configurable REST and Graph clients** — allow optional configuration of the used `SharePointRestClient` and `MicrosoftGraphClient` [#1659](https://github.com/pnp/pnpcore/pull/1659)
- **Page API: collapsible section header sizes** — support for setting the header size of collapsible sections [#1687](https://github.com/pnp/pnpcore/pull/1687)
- **DisableCommenting on lists** — support for setting and getting the `DisableCommenting` property of a list [#1695](https://github.com/pnp/pnpcore/pull/1695)
- **Improved page parsing robustness** — better handling of undefined control index values and wrongly decoded quotes
- **Dublin timezone mapping fix** — correctly maps the Dublin timezone [#1665](https://github.com/pnp/pnpcore/pull/1665)
- Stability improvements, dependency updates, and internal clean-ups

## 👥 New maintainers team

Another big step forward — we now have an **active maintainers team**. The team is still ramping up and getting familiar with the full codebase and processes, but the overall goal is clear: faster PR reviews, better issue handling, and more predictable progress. It's early days, but having a dedicated group in place is a key step towards making the project truly community-driven again.

## 📚 What's next

Now that the heavy lifting is done:

- Documentation and guidance will be refreshed to reflect the new packages
- Regular PR reviews and merges are back on track
- New features and improvements can move forward again

We're finally in a place where we can **build instead of unblock**.

## 🙌 Community and contributors

This release would not have been possible without the help of some really awesome folks who stepped in and kept things moving. We would like to express our huge gratitude and shout out to (in alphabetical order):

- [Adam Murchison](https://github.com/A-Murchison)
- [Adam Wójcik](https://github.com/Adam-it)
- [Bert Jansen](https://github.com/jansenbe)
- [Christian Zuellig](https://github.com/czullu)
- [Ejaz Hussain](https://github.com/ejazhussain)
- [Gautam Sheth](https://github.com/gautamdsheth)
- [Kinga](https://github.com/kkazala)
- [kola-tm](https://github.com/kola-tm)
- [Luc Mo Costabella](https://github.com/lucmoco)
- [Oliver Fast](https://github.com/tikki100)
- [Pedro Monte](https://github.com/PedroMordeP)
- [Per Jakobsen](https://github.com/singingknight)
- [Rafal Urbanski](https://github.com/RafalUrbanski)
- [Shayne Hunsaker](https://github.com/shunsaker)

And to everyone in the wider **PnP community** who raised issues, shared feedback, contributed code, and stayed patient while things were not moving as fast as we all wanted — that feedback mattered. A lot.

> PnP is not just a set of libraries — it's a **community-driven effort**.

## 🐞 Found something?

If you run into issues or have suggestions, please open an issue on the repo:

👉 [https://github.com/pnp/pnpcore/issues](https://github.com/pnp/pnpcore/issues)

You can also contribute with a PR — we'd love to see it!

## 📥 Get the package

👉 [PnP.Core 1.16.0 on NuGet](https://www.nuget.org/packages/PnP.Core/1.16.0)

And honestly — it just feels good to finally ship this 🚀
