---
title: CLI for Microsoft 365 v10.10
date: 2025-07-31T01:00:00.000Z
author: Milan Holemans
githubname: milanholemans
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Docker
  - SharePoint
  - Microsoft Entra ID
type: regular
---

The CLI for Microsoft 365 strikes again! We've just published a new minor version of the CLI for Microsoft 365. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces new commands and improvements that will enhance the quality of your Microsoft 365 experience.

> Explore the [release notes](https://aka.ms/cli-m365/notes) for a neat overview of all the exciting features and improvements. 

## What's New

### Microsoft Entra ID

Need to change your company’s display name, privacy-statement link or the addresses that receive Microsoft service notifications? The brand-new `m365 entra organization set` command lets you do exactly that, without touching the portal.

Updates properties of an organization specified by displayName

```sh
m365 entra organization set --displayName Contoso --marketingNotificationEmails 'marketing@contoso.com'
```

For more information, check the following resource:

- [entra organization set](https://pnp.github.io/cli-microsoft365/cmd/entra/organization/organization-set)

### SharePoint Online

Cleaning up pages just got easier: `m365 spo page control remove` deletes any control by its GUID—no page design manager required.

Remove a control from a SharePoint page, with confirmation

```sh
m365 spo page control remove --webUrl https://contoso.sharepoint.com/sites/Marketing --pageName home.aspx --id b3d6ebc9-6c7b-4e1e-99c1-4c08b682e8c1
```

For more information, check the following resource:

- [spo page control remove](https://pnp.github.io/cli-microsoft365/cmd/spo/page/page-control-remove)

## What's changed

This release also brings some other great changes. Aside from many improvements in the codebase and bug fixes to elevate the overall CLI experience, there are several important updates we'd like to highlight.

### Minimal-permissions documentation

We're introducing a "Permissions" section on each command's documentation page. This section outlines the minimum required permissions an account or app needs to run the command with full functionality. Currently, all `planner` command docs are updated with this new section. Updating all pages will take some time, so feel free to contribute if you'd like to help!

### SharePoint Online Enhancements

Building modern SharePoint experiences is now a lot easier. You can add Calendar, Gallery, and Kanban views straight from the CLI with [spo list view add](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-view-add), giving lists the visual flair and task-board functionality they deserve. At the same time, [spo page section add](https://pnp.github.io/cli-microsoft365/cmd/spo/page/page-section-add) introduces support for Flexible sections. Web parts can be moved anywhere on the two-dimensional grid within flexible sections. Together, these enhancements make it simple to craft information-rich layouts and views without leaving your terminal.

## Upcoming Changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 62 issues that are actively being developed and 117 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [Mauricio Sougarret](https://github.com/msouga)

## Get Started Today!

Experience the power of CLI for Microsoft 365 by getting the latest release from npm:

```bash
npm i -g @pnp/cli-microsoft365
```

Alternatively, you can access the latest release from Docker:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

## Need More Information?

For additional guidance on getting started or to explore detailed information about commands, architecture, or the project itself, visit [aka.ms/cli-m365](https://aka.ms/cli-m365).

## Stay Connected!

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord) or [Bluesky](https://bsky.app/profile/climicrosoft365.bsky.social). Don't hesitate to connect with us. Your input plays a vital role in shaping the future of CLI for Microsoft 365.
