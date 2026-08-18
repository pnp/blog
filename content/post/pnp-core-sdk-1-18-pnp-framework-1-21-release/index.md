---
title: "PnP Core SDK v1.18.0 and PnP Framework 1.21.0 release"
date: 2026-08-18T01:00:00.000Z
author: "Adam Wójcik"
githubname: adam-it
categories: ["Community post"]
images:
- images/main.png
tags: [".Net", "SDK", "PnP Core SDK", "PnP Framework", "SharePoint"]
type: "regular"
summary: "PnP Core SDK v1.18.0 and PnP Framework 1.21.0 are out — bringing new features, improvements, and community-driven enhancements."
description: "PnP Core SDK v1.18.0 and PnP Framework 1.21.0 are out — bringing new features, improvements, and community-driven enhancements."
---

## 🗒️ Quick intro

[PnP Core SDK](https://github.com/pnp/pnpcore) is a modern .NET SDK designed to work for Microsoft 365. It provides a unified object model for working with SharePoint Online and Teams which is agnostic to the underlying APIs being called.

[PnP Framework](https://github.com/pnp/pnpframework) is a .NET library targeting Microsoft 365 containing the PnP Provisioning engine and a ton of other useful extensions.

Both libraries received a fresh release, so let's bundle them together and walk through what's new 👇

## 🔥 What's new in PnP Core SDK v1.18.0

### Added

- **CSOM-based `GetItems` support** [#1802](https://github.com/pnp/pnpcore/pull/1802) [Jeppe Mastrup Spanggaard] — list items can now be retrieved through CSOM, which unlocks scenarios that the REST/Graph based retrieval could not cover and brings the behaviour closer to what people were used to from CSOM based tooling.

### Changed

- **Fixed negative currency values returned by `LoadListDataAsStreamAsync`** [#1818](https://github.com/pnp/pnpcore/pull/1818) [mateusz-sintel] — negative amounts in currency columns were not being parsed back correctly, so values could come out wrong. They are now returned as expected.
- **Fixed the MC791596 banner migration** incorrectly adding a banner header on pages that have no header [#1758](https://github.com/pnp/pnpcore/pull/1758) [Rene Nicolao] — pages explicitly configured without a header were getting one added during the migration. Headerless pages now stay headerless.
- **Updated the `Demo.WPF` sample** [#1829](https://github.com/pnp/pnpcore/pull/1829) [gszdev] — the WPF demo has been refreshed so it builds and runs against the current SDK, which makes it a much better starting point again for anyone exploring the SDK from a desktop app.
- **Updated AngleSharp to 1.5.2** [Adam Wójcik] - Updated that addresses a vulnerability issue

For the full list of changes, check the [PnP Core SDK release notes](https://github.com/pnp/pnpcore/releases/tag/1.18.0).

## 🔥 What's new in PnP Framework v1.21.0

### Changed

- **Fixed `ListUserDelta` throwing on a null delta token and never returning one** [svermaak] — the delta call blew up when no token was present and, worse, never handed a token back, so consumers could not continue the delta chain. Both sides of that are now handled.
- **Made the provisioning field XML cache thread safe** [#1257](https://github.com/pnp/pnpframework/pull/1257) [svermaak] — the cache used while resolving field XML during provisioning could be hit from multiple threads, leading to intermittent and hard to reproduce failures. Access is now properly synchronised.
- **Stopped forcing a legacy TLS preference on `net10.0`** [svermaak] — the library used to pin a TLS setting that made sense on older targets but is unnecessary (and undesirable) on .NET 10. On `net10.0` the platform default is now respected.
- **Kept `ListInstance` `DataSource` across a template round trip** [#1261](https://github.com/pnp/pnpframework/pull/1261) [svermaak] — the `DataSource` information on a list instance was lost when a template was saved and read back in. It now survives the round trip intact.
- **Updated AngleSharp to 1.5.2 and AngleSharp.Css to 1.0.0** [Adam Wójcik] — keeping the HTML/CSS parsing dependencies current, which also pulls in upstream fixes and keeps the dependency tree clean.

For the full list of changes, check the [PnP Framework release notes](https://github.com/pnp/pnpframework/releases/tag/1.21.0).

## 🛣️ First steps of migrating the PnP Provisioning engine to PnP Core SDK

In this release we have officially started walking the path we announced a while ago.

As described in [🛣️ Roadmap phase 1: Migrating Provisioning and Modernization Engines to PnP Core SDK](https://github.com/pnp/pnpframework/issues/1237), the plan is to bring the **Provisioning Engine** and the **Modernization Engine** over to PnP Core SDK as first class citizens of that repo. This release marks the **first concrete steps** in that direction.

The work is already in flight and being tested in an open PR:

👉 [Adds PnP Provisioning engine and provisioning sample app (pnp/pnpcore#1847)](https://github.com/pnp/pnpcore/pull/1847)

That PR brings the Provisioning engine into PnP Core SDK together with a sample app so the engine can be exercised end to end against real tenants. It is intentionally still open — we want it properly reviewed and battle tested before it becomes part of a shipped release. If you rely on the Provisioning engine today, this is a great moment to have a look, try it out, and tell us what breaks or what feels off. Early feedback here is worth a lot.

### Why this matters for PnP Framework

This ties directly into the longer term plan we shared in the [PnP Framework roadmap update](https://pnp.github.io/blog/post/pnp-framework-roadmap-update-1/) blog post: **PnP Framework will eventually be deprecated and archived**, with PnP Core SDK becoming the single, actively maintained .NET SDK for Microsoft 365 development.

To be clear about what that means in practice right now:

- PnP Framework is **still maintained** and still gets fixes — as you can see from this very release.
- Nothing breaks overnight, and existing packages stay on NuGet.
- But **new energy is deliberately going into PnP Core SDK**, and that is where the Provisioning and Modernization engines will live going forward.

With that shift in focus, we also took some time to look after the **PnP Core SDK repository itself** - how we maintain it, how we handle issues and PRs. The goal is simple: make this a welcoming place to contribute and a repo that stays healthy, predictable and easy to plan for in the long run.

## 🙌 Community and contributors

These releases would not have been possible without the help of some really awesome folks who stepped in and kept things moving. We would like to express our huge gratitude and shout out to (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [gszdev](https://github.com/gszdev)
- [Jeppe Mastrup Spanggaard](https://github.com/jeppesc11)
- [mateusz-sintel](https://github.com/mateusz-sintel)
- [Rene Nicolao](https://github.com/nicolaor)
- [svermaak](https://github.com/svermaak)

And to everyone in the wider **PnP community** who raised issues, shared feedback, contributed code, and kept the momentum going — that feedback mattered. A lot.

> PnP is not just a set of libraries — it's a **community-driven effort**.

## 🐞 Found something?

If you run into issues or have suggestions, please open an issue on the repos:

👉 [PnP Core SDK issues](https://github.com/pnp/pnpcore/issues)

👉 [PnP Framework issues](https://github.com/pnp/pnpframework/issues)

You can also contribute with a PR — we'd love to see it!

## 📥 Get the package

👉 [PnP.Core 1.18.0 on NuGet](https://www.nuget.org/packages/PnP.Core/1.18.0)

👉 [PnP.Framework 1.21.0 on NuGet](https://www.nuget.org/packages/PnP.Framework/1.21.0)
