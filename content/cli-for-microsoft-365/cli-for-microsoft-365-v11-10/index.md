---
title: CLI for Microsoft 365 v11.10
date: 2026-07-25T01:00:00.000Z
author: Milan Holemans
githubname: milanholemans
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Outlook
  - Power Platform
  - SharePoint Online
  - SPFx
type: popular
---

CLI for Microsoft 365 v11.10 expands coverage across Outlook and Power Pages with a handful of new commands, renames the SharePoint alert commands to reflect their new purpose, and keeps the codebase healthy with more Zod migrations, tighter minimal permissions, and support for the latest SPFx version. [CLI for Microsoft 365](https://aka.ms/cli-m365) remains the cross-platform tool you rely on to manage your Microsoft 365 tenant and SharePoint Framework projects, and this release continues to broaden that reach.

> Explore the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v11100) to see every detail that landed in v11.10.

## What's new

### Outlook event get

The new `outlook event get` command retrieves a single event from a specific calendar of a user. This complements the existing `outlook event list` command and is handy when you already know the event ID and want to inspect its details, such as the start and end times in a specific time zone.

To get an event for the signed-in user from a calendar specified by ID, run:

```sh
m365 outlook event get --id "AAMkAGVmMDEzMTM4L" --userId "@meId" --calendarId "AAMkAGRkZ"
```

To get an event for a specific user and return the event times in Pacific Standard Time, run:

```sh
m365 outlook event get --id "AAMkAGVmMDEzMTM4L" --userName "john.doe@contoso.com" --calendarId "AAMkAGRkZ" --timeZone 'Pacific Standard Time'
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/outlook/event/event-get/).

### Power Pages website remove

The new `pp website remove` command removes a Power Pages website from the list of active sites in an environment. You can target the site by URL, name, or ID, which makes it easy to clean up sites as part of environment housekeeping or automated lifecycle management.

To remove a Power Pages website by name, run:

```sh
m365 pp website remove --name Demo --environmentName Default-d87a7535-dd31-4437-bfe1-95340acd55c5
```

To remove a Power Pages website by ID without prompting for confirmation, run:

```sh
m365 pp website remove --id 4916bb2c-91e1-4716-91d5-b6171928fac9 --environmentName Default-d87a7535-dd31-4437-bfe1-95340acd55c5 --force
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/pp/website/website-remove/).

### Power Pages website webrole list

The new `pp website webrole list` command lists all web roles for a specified Power Pages website. Web roles drive the authorization model of a Power Pages site, so being able to enumerate them from the command line is useful when auditing access or documenting a site's configuration.

To list all web roles for a site specified by name, run:

```sh
m365 pp website webrole list --websiteName "Contoso" --environmentName "Default-2ca3eaa5-140f-4175-8261-3272edf9f339"
```

To list all web roles for a site specified by ID as admin, run:

```sh
m365 pp website webrole list --websiteId "2ca3eaa5-140f-4175-8261-3272edf9f339" --environmentName "Default-2ca3eaa5-140f-4175-8261-3272edf9f339" --asAdmin
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/pp/website/website-webrole-list/).

## What's changed

### Renamed `spo web alert` commands to `spo web rule`

Because SharePoint alerts are being deprecated, the `spo web alert list` and `spo web alert remove` commands have been renamed to `spo web rule list` and `spo web rule remove`. The original `spo web alert` names are kept as aliases, so your existing scripts continue to work while you migrate to the new naming. This also sets us up to cleanly remove the aliases in a future major version once SharePoint alerts reach end of life.

To list the rules for a SharePoint site using the new command name, run:

```sh
m365 spo web rule list --webUrl https://contoso.sharepoint.com/sites/Marketing
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/web/web-rule-list/).

### Added support for SPFx v1.23.2

Keeping your SharePoint Framework projects current is important, and this release adds full support for SPFx v1.23.2 across all SPFx commands. You can now generate accurate upgrade guidance, validate project dependencies, and verify your local environment against the latest SPFx version.

### Tightened minimal permissions for more SharePoint commands

We continued the ongoing effort to document and apply the least privilege required for each command. This release adds minimal permissions for the `spo applicationcustomizer`, `spo cdn`, `spo contenttype`, `spo homesite`, `spo field`, `spo file`, and `spo hubsite` commands, helping you grant only the permissions your automation actually needs.

### Continued migration to Zod schema validation

The migration to Zod-based schema validation continued with the `purview`, `purview retentionevent`, `purview retentioneventtype`, `planner roster`, and `planner task` commands. Zod gives these commands more consistent and robust option validation, along with clearer error messages when something is off.

## Keep the momentum going

Every improvement in this release is driven by real-world usage and community input. If you want to help shape the next version, browse the open ["help wanted" issues](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22) or share your ideas on Discord.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Antanina Druzhkina](https://github.com/Ateina)
- [Brian McCullough](https://github.com/brianpmccullough)
- [Eric Schoeller](https://github.com/eschoeller)
- [Martin Machacek](https://github.com/MartinM85)
- [Matt Van Horn](https://github.com/mvanhorn)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [Xinzhao Zhang](https://github.com/xinzhaozhang1985)
- [Fabian Hutzli](https://github.com/fabianhutzli)

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
