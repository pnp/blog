---
title: "PnP Framework roadmap update"
date: 2026-06-07T01:00:00.000Z
author: "Adam Wójcik"
githubname: "Adam-it"
categories: ["Community post"]
images:
- images/main.png // TODO: use my paint or AI skills to generate some relevant pic
tags: [".Net", "SDK", "PnP Core SDK", "PnP Framework"]
type: "regular"
summary: "The PnP Framework has served the community incredibly well, but the time has come to look ahead. We are sharing a transparent, two-phase roadmap: first migrating the Provisioning and Modernization engines to PnP Core SDK, then eventually archiving PnP Framework. Read on to understand the timeline, the reasoning, and what you should do to prepare."
description: "The PnP Framework has served the community incredibly well, but the time has come to look ahead. We are sharing a transparent, two-phase roadmap: first migrating the Provisioning and Modernization engines to PnP Core SDK, then eventually archiving PnP Framework. Read on to understand the timeline, the reasoning, and what you should do to prepare."
---

## Where we are coming from

[PnP Framework](https://github.com/pnp/pnpframework) has been a cornerstone of the SharePoint and Microsoft 365 developer community for years. Born as the successor to the much-loved PnP-Sites-Core library, it brought the community a rich set of tools including the **Provisioning Engine** - a declarative, XML-based way to apply site templates - and the **Modernization Engine**, which helped organisations transform classic SharePoint sites into modern experiences.

The library has seen thousands of downloads, contributions from dozens of community members, and has powered a huge variety of solutions out in the wild. We are incredibly proud of what has been built here, together, as a community.

But the .NET and SharePoint Online ecosystem has evolved. [PnP Core SDK](https://github.com/pnp/pnpcore) was created from scratch to be the modern, cross-platform foundation for the next generation of PnP tooling. It targets modern .NET, runs anywhere .NET runs - Windows, Linux, macOS, containers - and is built with a clean, testable architecture. Maintaining two overlapping libraries side-by-side is increasingly difficult to sustain, and the community is better served by focusing energy on one well-maintained SDK.

With that context in mind, we want to share a **transparent, two-phase roadmap** for the future of PnP Framework. We are giving as much lead time as possible, and we are committed to making this transition well-supported every step of the way.

## Phase 1 - Migrating the Provisioning and Modernization Engines to PnP Core SDK

> 🗓️ **Target: Q4 2026**

The first phase focuses on moving the most widely used parts of PnP Framework into PnP Core SDK.

### What is planned

The **Provisioning Engine** and the **Modernization Engine** will be copied into PnP Core SDK as new, dedicated projects within that repository. The goal is feature parity so that existing workflows can be moved across without losing functionality.

Once that work is complete:

- The Provisioning and Modernization parts of PnP Framework will be **marked as deprecated**.
- Developers using those features will receive **deprecation warnings** in their build output pointing them to the equivalent APIs in PnP Core SDK.
- **No new pull requests or features** will be accepted for those parts of PnP Framework.
- Everything else in PnP Framework remains unchanged at this stage.

### Why consolidate into PnP Core SDK?

PnP Core SDK was built for modern .NET development from day one. Bringing the Provisioning and Modernization engines across means:

- **A single, actively maintained SDK** for all your SharePoint Online development needs.
- **New features and improvements land in one place**, making it easier to keep up with changes in Microsoft 365.
- **A healthier, more sustainable codebase** that the community can continue to grow for years to come.

### What should you do now?

- If your code depends on the **Provisioning Engine** or the **Modernization Engine** in PnP Framework, this is a great time to start **evaluating PnP Core SDK** and understanding the new APIs.
- Watch both the [PnP Framework repo](https://github.com/pnp/pnpframework) and the [PnP Core SDK repo](https://github.com/pnp/pnpcore) for updates as the migration work progresses.
- Come to community calls and [GitHub Discussions](https://github.com/pnp/pnpframework/discussions) - the team is happy to help you plan your migration path.

## Phase 2 - Full Deprecation and Archival of PnP Framework

> 🗓️ **Target: Q2 2027**

Once Phase 1 is complete and the community has had time to migrate the most critical pieces, the second phase will bring the full lifecycle of PnP Framework to a close.

### What will happen

In the second quarter of 2027, the **PnP Framework repository will be set to public archive status**. From that point:

- No further maintenance will be performed.
- No pull requests will be accepted.
- No new releases will be published.

### What does "archived" mean in practice?

Archiving does **not** mean the code disappears. The repository will remain fully accessible and readable on GitHub. All existing NuGet packages will remain available on NuGet.org. **Your existing code will not stop working overnight.**

Archiving simply means that active development has moved on - to PnP Core SDK - and PnP Framework enters a read-only, as-is state.

### Why are we doing this?

This decision is not made lightly. It is the result of extensive community discussion and a long, careful look at what is best for the ecosystem as a whole. PnP Framework has served its purpose extraordinarily well. PnP Core SDK is its natural, modern successor. Maintaining two overlapping libraries is not sustainable, and consolidating everything into PnP Core SDK means a better, more focused experience for everyone going forward.

We are announcing this more than a year in advance precisely because we respect the community and the real-world production code that depends on PnP Framework.

### What should you do?

- **Start planning your migration now**, even if the work itself happens later.
- Review the [PnP Core SDK documentation](https://pnp.github.io/pnpcore/) to understand the new APIs and patterns.
- Follow the phased approach: migrate Provisioning and Modernization functionality first, then look at any remaining PnP Framework usage in your solutions.
- **Engage with the community** - migration guidance, documentation, and support will be provided throughout this process.

## Summary timeline

| Milestone | Target |
|---|---|
| Phase 1: Provisioning & Modernization Engines available in PnP Core SDK and deprecated in PnP Framework | Q4 2026 |
| Phase 2: PnP Framework repository archived | Q2 2027 |

## Closing thoughts

This is a significant moment for the community, and we want to be clear: **we are fully committed to making this an easy, well-supported transition**. The PnP ecosystem is not going away - it is growing up and moving forward.

Thank you for everything you have contributed to PnP Framework over the years. Every issue filed, every PR submitted, every question asked and answered in community calls has made it what it is today. We look forward to continuing that journey together in PnP Core SDK.

- [Phase 1 roadmap issue on GitHub](https://github.com/pnp/pnpframework/issues/1237)
- [Phase 2 roadmap issue on GitHub](https://github.com/pnp/pnpframework/issues/1238)
- [PnP Core SDK repository](https://github.com/pnp/pnpcore)
- [PnP Framework repository](https://github.com/pnp/pnpframework)

