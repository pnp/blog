---
title: CLI for Microsoft 365 v11.5
date: 2026-02-28T01:00:00.000Z
author: Jasey Waegebaert
githubname: jwaegebaert
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - SharePoint
  - SPFx
  - Microsoft Teams
type: popular
---

CLI for Microsoft 365 v11.5 is a compact release that introduces new commands for SharePoint brand management and Teams call records alongside targeted improvements and fixes. [CLI for Microsoft 365](https://aka.ms/cli-m365) remains the cross-platform tool you rely on to manage your Microsoft 365 tenant and SharePoint Framework projects, and this drop continues to expand coverage across the platform.

> Explore the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v1150) to see every detail that landed in v11.5.

## What's new

### SharePoint brand center settings

The new `spo brandcenter settings list` command lets you view the brand center configuration for your SharePoint tenant. This is helpful for admins who want to verify branding policies such as custom fonts, color palettes, and logo settings without navigating the admin center.

To list the brand center settings, run:

```sh
m365 spo brandcenter settings list
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/brandcenter/brandcenter-settings-list/).

### Teams call record

The new `teams callrecord get` command retrieves a specific Teams call record, making it easier to audit call activity, troubleshoot quality issues, or feed call metadata into reporting pipelines.

To get a specific call record by its ID, run:

```sh
m365 teams callrecord get --id "2f09c851-72d1-4c56-afe4-9a5407be5e33"
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/teams/callrecord/callrecord-get/).

## What's changed

### Added support for SPFx v1.22.2

Keeping your SharePoint Framework projects current is important, and this release adds full support for SPFx v1.22.2 across all SPFx commands. You can now generate accurate upgrade guidance, validate project dependencies, and verify your local environment against the latest SPFx version.

## Keep the momentum going

Even in a focused release like this, every improvement is driven by real-world usage and community input. If you want to help shape the next version, browse the open ["help wanted" issues](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22) or share your ideas on Discord.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Martin Machacek](https://github.com/MartinM85)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nirav Raval](https://github.com/nirav-raval)
- [Saurabh Tripathi](https://github.com/Saurabh7019)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [Adam Lonsdale](https://github.com/adamlonsdale)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Paul Schaeflein](https://github.com/pschaeflein)
- [zwiles-bw](https://github.com/zwiles-bw)

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
