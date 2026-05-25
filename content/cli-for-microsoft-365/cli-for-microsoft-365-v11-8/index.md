---
title: CLI for Microsoft 365 v11.8
date: 2026-05-21T01:00:00.000Z
author: Adam Wójcik
githubname: adam-it
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Outlook
  - SPFx
type: popular
---

CLI for Microsoft 365 v11.8 is a focused release that rounds out Outlook calendar group management with a new remove command, and brings important SPFx improvements including support for the latest SPFx version. [CLI for Microsoft 365](https://aka.ms/cli-m365) remains the cross-platform tool you rely on to manage your Microsoft 365 tenant and SharePoint Framework projects, and this drop continues to expand coverage across the platform.

> Explore the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v1180) to see every detail that landed in v11.8.

## What's new

### Outlook calendar group remove

Building on the calendar group commands introduced in previous releases, this release adds the missing piece for full lifecycle management of calendar groups.

The new `outlook calendargroup remove` command removes a calendar group from a user's mailbox. This is useful when you need to clean up unused calendar groups as part of mailbox housekeeping or automated provisioning workflows.

To remove a calendar group by ID for the signed-in user, run:

```sh
m365 outlook calendargroup remove --id "AAMkAGE0MGM1Y2M5LWEzMmUtNGVlNy05MjRlLTk0YmYyY2I5NTM3ZAAuAAAAAAC_0WfqSjt_SqLtNkuO-bj1AQAbfYq5lmBxQ6a4t1fGbeYAAAAAAEOAAA="
```

To remove a calendar group by name for a specific user, run:

```sh
m365 outlook calendargroup remove --name "Personal Events" --userId "44288f7d-7710-4293-8c8e-36f310ed2e6a"
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/outlook/calendargroup/calendargroup-remove/).

## What's changed

### Added support for SPFx v1.23.0

Keeping your SharePoint Framework projects current is important, and this release adds full support for SPFx v1.23.0 across all SPFx commands. You can now generate accurate upgrade guidance, validate project dependencies, and verify your local environment against the latest SPFx version. 

### Updated `spfx project github workflow add` sppkg path resolution

The `spfx project github workflow add` command now resolves the sppkg path more reliably when generating GitHub Actions workflows. This ensures that the generated workflow correctly locates the solution package across different project configurations, removing the need for manual tweaks after generation. 

## Keep the momentum going

Every improvement in this release is driven by real-world usage and community input. If you want to help shape the next version, browse the open ["help wanted" issues](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22) or share your ideas on Discord.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)

## Get started today!

Experience the power of CLI for Microsoft 365 by getting the latest release from npm:

```bash
npm i -g @pnp/cli-microsoft365
```

Alternatively, you can access the latest release from Docker:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

## Need more information?

For additional guidance on getting started or to explore detailed information about commands, architecture, or the project itself, visit [aka.ms/cli-m365](https://aka.ms/cli-m365).

## Stay connected!

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord) or [Bluesky](https://bsky.app/profile/climicrosoft365.bsky.social). Your input plays a vital role in shaping the future of CLI for Microsoft 365.
