---
title: CLI for Microsoft 365 v11.2
date: 2025-11-30T01:00:00.000Z
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
type: regular
---

CLI for Microsoft 365 v11.2 is a lean release that sharpens SharePoint governance workflows while polishing documentation and permissions guidance. [CLI for Microsoft 365](https://aka.ms/cli-m365) stays the cross-platform tool you rely on to manage your tenant and SharePoint Framework projects, and this drop adds a handy site version policy command plus a set of pragmatic quality fixes.

> Explore the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v1120) to see every detail that landed in v11.2.

## What's New

## SharePoint site version policies

SharePoint site owners can now inspect version policy settings without leaving the terminal thanks to the new `spo site versionpolicy get` command. Whether you are verifying how many major versions a collaboration site keeps or ensuring auto-approval is configured correctly before enabling records management, this command surfaces the information you need in seconds.

To review the current version policy for a specific site, run:

```sh
m365 spo site versionpolicy get --siteUrl https://contoso.sharepoint.com/sites/ProjectCenter
```

Prefer to plug the details straight into automation or monitoring dashboards? Output the command as JSON and apply your favorite JMESPath query:

```sh
m365 spo site versionpolicy get --siteUrl https://contoso.sharepoint.com/sites/Marketing --output json --query "{site: siteUrl, major: majorVersionLimit, warning: majorWithMinorVersionsLimit}"
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-versionpolicy-get/).

## What's changed

### Added support for SPFx v1.22.0-rc.0
To help you keep up to date with the latest improvements in SharePoint Framework, we added support for the first release candidate version of SPFx v1.22.0 to all our SPFx commands. Now you create upgrade guidance for your SPFx project to align with what was changed in the latest version of SharePoint Framework, as well as validate the dependencies of your project. Last but not least, you may validate your local environment setup to make sure you have everything ready for the latest SPFx beta.

### Documentation & validation now Zod-first
The documentation stack continues its transition to Zod schemas, bringing more predictable validation experiences for readers. Alongside the broad doc migration, the `entra multitenant add` command now benefits from the same Zod-backed consistency, making option validation clearer for contributors and automation pipelines alike.

## Keep the momentum going

Even with a lighter release, the community's fingerprints are everywhere—from code review on Zod migrations to documenting the latest permission sets. If you're looking for a quick win, browse the open ["help wanted" issues](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22) or extend the new sample script to suit your governance needs.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Fahad](https://github.com/codevfahad)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Milan Holemans](https://github.com/milanholemans)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [John Dziurlaj](https://github.com/JDziurlaj)

Thank you for making CLI for Microsoft 365 better for everyone!

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

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord) or [Bluesky](https://bsky.app/profile/climicrosoft365.bsky.social). Don't hesitate to connect with us. Your input plays a vital role in shaping the future of CLI for Microsoft 365.