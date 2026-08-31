---
title: CLI for Microsoft 365 v11.11
date: 2026-08-31T01:00:00.000Z
author: Adam Wójcik
githubname: adam-it
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Entra
  - SharePoint Online
type: popular
---

CLI for Microsoft 365 v11.11 opens the door to the agent era with a brand new Entra command, continues the ongoing work on minimal permissions and Zod schema validation, and fixes two SharePoint issues reported by the community. [CLI for Microsoft 365](https://aka.ms/cli-m365) remains the cross-platform tool you rely on to manage your Microsoft 365 tenant and SharePoint Framework projects, and this release keeps that foundation sharp and reliable.

> Explore the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v11110) to see every detail that landed in v11.11.

## What's new

### Entra agent list

Agents are quickly becoming first-class citizens in Microsoft 365, and with the new `entra agent list` command you can now enumerate the agents in your tenant straight from the command line. This is a great starting point for auditing which agents exist, exporting an inventory, or feeding the results into your own automation.

To retrieve all agents, run:

```sh
m365 entra agent list
```

By default the command returns the `id` and `displayName` of each agent. If you need more, or want to trim the output down, use the `--properties` option to specify exactly which properties to return:

```sh
m365 entra agent list --properties 'id,displayName'
```

> This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reaches general availability.

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/entra/agent/agent-list/).

## What's changed

### Fixed retrieving a SharePoint user by ID with `spo user get`

The `spo user get` command failed with a `Specified id is not a number` error whenever you tried to retrieve a user by their ID, effectively making that option unusable. The validation has been corrected, so looking up a site user by ID works as expected again.

To get a SharePoint user by ID, run:

```sh
m365 spo user get --webUrl https://contoso.sharepoint.com/sites/Marketing --id 6
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/user/user-get/).

### Fixed apostrophes in file names with `spo file add`

Uploading a file whose name contains a single quote resulted in the apostrophe being doubled, so `my'file.pdf` ended up in the library as `my''file.pdf`. The internal escaping has been fixed, which means file names with apostrophes are now uploaded exactly as you specified them, with or without the `--fileName` option.

```sh
m365 spo file add --webUrl https://contoso.sharepoint.com/sites/Marketing --folder 'Shared Documents' --path "C:\reports\Adam's report.pdf"
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-add/).

### Tightened minimal permissions for more commands

We pushed the minimal permissions effort further so you can grant your app registrations only what they actually need. This release documents the least privilege required for the `spo folder`, `spo file version`, `spo group`, `todo task`, and `todo list` commands.

### Continued migration to Zod schema validation

The migration to Zod-based schema validation continued across the Power Platform commands. The `pp aibuildermodel`, `pp copilot`, `pp dataverse`, `pp gateway`, `pp managementapp`, `pp solution`, and `pp tenant` commands now use Zod schemas, giving them more consistent option validation and clearer error messages when something is off.

## Keep the momentum going

Every improvement in this release is driven by real-world usage and community input. If you want to help shape the next version, browse the open ["help wanted" issues](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22) or share your ideas on Discord.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Martin Machacek](https://github.com/MartinM85)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [Elliot Margot](https://github.com/OwnOptic)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [KnightyCode](https://github.com/KnightyCode)
- [Shirish Mawande](https://github.com/shirishmawande)
- [Svyatoslav Pidgorny](https://github.com/SP3269)

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
