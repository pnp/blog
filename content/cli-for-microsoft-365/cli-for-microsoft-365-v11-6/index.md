---
title: CLI for Microsoft 365 v11.6
date: 2026-03-31T01:00:00.000Z
author: Adam Wójcik
githubname: Adam-it
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - SharePoint
  - SPFx
  - Microsoft Teams
type: regular
---

CLI for Microsoft 365 v11.6 brings new commands spanning Outlook, SharePoint, and Viva Engage, along with meaningful enhancements to existing SharePoint commands. [CLI for Microsoft 365](https://aka.ms/cli-m365) remains the cross-platform tool you rely on to manage your Microsoft 365 tenant and SharePoint Framework projects, and this release continues to expand coverage across the platform.

> Explore the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v1160) to see every detail that landed in v11.6.

## What's new

### Outlook calendar groups

The new `outlook calendargroup list` command retrieves calendar groups for a user. This is useful for automation scenarios where you need to enumerate calendar groups before working with individual calendars, or when auditing mailbox configurations.

To list all calendar groups for the signed-in user, run:

```sh
m365 outlook calendargroup list
```

To retrieve calendar groups for a specific user by their email, run:

```sh
m365 outlook calendargroup list --userName "john.doe@contoso.com"
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/outlook/calendargroup/calendargroup-list/).

### SharePoint agents

The new `spo agent add` command lets you create a SharePoint agent directly from the command line. SharePoint agents are AI-powered assistants grounded in your SharePoint content. You can define the agent's name, instructions, welcome message, and the content sources it should use—all without leaving your terminal.

To add a SharePoint agent with site and library sources, run:

```sh
m365 spo agent add --webUrl https://contoso.sharepoint.com/sites/projectSite --name "Project Assistant" --agentInstructions "You are a helpful assistant for project management tasks. Be professional and concise." --welcomeMessage "Hello! I'm here to help you with project management tasks." --sourceUrls "https://contoso.sharepoint.com/sites/projectSite,https://contoso.sharepoint.com/sites/projectSite/Shared Documents/Forms/AllItems.aspx" --description "A helpful agent for project management assistance"
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/agent/agent-add/).

### SharePoint tenant site information

The new `spo tenant site get` command retrieves detailed tenant-level information for a specific site collection. This is helpful for admins who need to inspect site properties, verify configurations, or feed site metadata into governance reports.

To retrieve info about a site using its URL, run:

```sh
m365 spo tenant site get --url "https://contoso.sharepoint.com/sites/Marketing"
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/tenant/tenant-site-get/).

### SharePoint site access request settings

The new `spo site accessrequest setting set` command allows you to configure access request settings for a specific site collection. You can disable access requests, route them to the site owner group, or send them to a specific email address—all with an optional custom message.

To disable access requests for a specific site, run:

```sh
m365 spo site accessrequest setting set --siteUrl https://contoso.sharepoint.com/sites/Management --disabled
```

To send access requests to a specific email address with a custom message, run:

```sh
m365 spo site accessrequest setting set --siteUrl https://contoso.sharepoint.com/sites/Management --email john.doe@contoso.com --message "Motivate why you need access."
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-accessrequest-setting-set/).

### Viva Engage role member removal

The new `viva engage role member remove` command removes a user from a Viva Engage role. This is useful for managing role-based access in Viva Engage, for example when offboarding an admin or rotating responsibilities.

To revoke a user from a Viva Engage role by name, run:

```sh
m365 viva engage role member remove --userName john.doe@contoso.com --roleName 'Verified Admin'
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/viva/engage/engage-role-member-remove/).

## What's changed

### Enhanced `spo site add` with Brand Center site support

The `spo site add` command now supports creating a Brand Center site. By specifying `--type BrandCenter`, you can provision a dedicated branding hub for your organization directly from the command line.

To create a brand center site, run:

```sh
m365 spo site add --type BrandCenter --url https://contoso.sharepoint.com/sites/brandcenter --title Branding
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-add/).

### Enhanced `spo list set` with extra versioning settings

The `spo list set` command has been extended with additional versioning options. You can now configure `versionAutoExpireTrim` to enable automatic version trimming, and `versionExpireAfterDays` to set a version retention period. These options give admins finer-grained control over version storage on document libraries and lists.

To enable automatic version trimming on a list, run:

```sh
m365 spo list set --webUrl https://contoso.sharepoint.com/sites/project-x --id 3EA5A977-315E-4E25-8B0F-E4F949BF6B8F --versionAutoExpireTrim true
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-set/).

## Keep the momentum going

Every improvement in this release is driven by real-world usage and community input. If you want to help shape the next version, browse the open ["help wanted" issues](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22) or share your ideas on Discord.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Alejandro Gispert](https://github.com/AlejandroGispert)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Machacek](https://github.com/MartinM85)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [Eric Schoeller](https://github.com/eschoeller)
- [Ken Jenney](https://github.com/kjenney)
- [Zekai (Kai) Zhao](https://github.com/Zekai-Zhao-321)

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
