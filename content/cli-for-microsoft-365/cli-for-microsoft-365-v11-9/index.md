---
title: CLI for Microsoft 365 v11.9
date: 2026-06-30T01:00:00.000Z
author: Adam Wójcik
githubname: adam-it
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Outlook
  - SharePoint Online
  - SharePoint Embedded
  - Viva
  - SPFx
type: regular
---

CLI for Microsoft 365 v11.9 rounds out several command families across Outlook, SharePoint, SharePoint Embedded, and Viva Engage, while sharpening existing SharePoint Embedded commands and fixing the ability to update text web parts. [CLI for Microsoft 365](https://aka.ms/cli-m365) remains the cross-platform tool you rely on to manage your Microsoft 365 tenant and SharePoint Framework projects, and this release continues to expand coverage across the platform.

> Explore the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v1190) to see every detail that landed in v11.9.

## What's new

### Outlook calendar list

The new `outlook calendar list` command retrieves all calendars of a user or a group. This complements the calendar management commands introduced in earlier releases and is handy when you need to enumerate calendars before working with a specific one, or when auditing mailbox configurations.

To list all calendars for the signed-in user, run:

```sh
m365 outlook calendar list --userId "@meId"
```

To list all calendars in a specific calendar group for a specific user, run:

```sh
m365 outlook calendar list --userName "john.doe@contoso.com" --calendarGroupName "Colleague calendars"
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/outlook/calendar/calendar-list/).

### SharePoint file unarchive

The new `spo file unarchive` command unarchives a file in SharePoint, bringing back files that were previously archived. This pairs with the `spo file archive` command from v11.7 to give you full control over the file archival lifecycle from the command line.

To unarchive a file by its ID without prompting for confirmation, run:

```sh
m365 spo file unarchive --webUrl https://contoso.sharepoint.com/sites/Marketing --id 7a8c9207-7745-4cda-b0e2-be2618ee3030 --force
```

To unarchive a file by its server-relative URL, run:

```sh
m365 spo file unarchive --webUrl https://contoso.sharepoint.com/sites/Marketing --url '/sites/Marketing/shared documents/document.docx'
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-unarchive/).

### SharePoint folder archive

The new `spo folder archive` command archives a folder in SharePoint. This is useful for storage management scenarios where you want to move an entire folder to an archived state without permanently deleting it.

To archive a folder by its ID without prompting for confirmation, run:

```sh
m365 spo folder archive --webUrl https://contoso.sharepoint.com/sites/Marketing --id 7a8c9207-7745-4cda-b0e2-be2618ee3030 --force
```

To archive a folder by its server-relative URL, run:

```sh
m365 spo folder archive --webUrl https://contoso.sharepoint.com/sites/Marketing --url '/sites/Marketing/shared documents/folder'
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-archive/).

### SharePoint list sensitivity label removal

The new `spo list sensitivitylabel remove` command clears a default sensitivity label from a document library. This is helpful for admins who need to reset or remove the default labeling policy applied to a library as part of governance and compliance workflows.

To remove the sensitivity label from a library by its title, run:

```sh
m365 spo list sensitivitylabel remove --webUrl 'https://contoso.sharepoint.com' --listTitle 'Shared Documents'
```

To remove the sensitivity label from a library by its ID without prompting for confirmation, run:

```sh
m365 spo list sensitivitylabel remove --webUrl 'https://contoso.sharepoint.com' --listId 'b4cfa0d9-b3d7-49ae-a0f0-f14ffdd005f7' --force
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-sensitivitylabel-remove/).

### SharePoint Embedded container set

The new `spe container set` command updates a SharePoint Embedded container. You can rename the container, change its description, and configure settings such as OCR, item versioning, and the major version limit—all without leaving your terminal.

To update the container display name by ID, run:

```sh
m365 spe container set --id "b!ISJs1WRro0y0EWgkUYcktDa0mE8zSlFEqFzqRn70Zwp1CEtDEBZgQICPkRbil_5Z" --newName "Contoso Project A"
```

To enable versioning and set the major version limit, run:

```sh
m365 spe container set --id "b!ISJs1WRro0y0EWgkUYcktDa0mE8zSlFEqFzqRn70Zwp1CEtDEBZgQICPkRbil_5Z" --isItemVersioningEnabled true --itemMajorVersionLimit 100
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spe/container/container-set/).

### Viva Engage role member add

The new `viva engage role member add` command assigns a Viva Engage role to a user. This complements the `viva engage role member remove` command from v11.6, giving you full control over role-based access in Viva Engage when onboarding admins or rotating responsibilities.

To assign a user specified by ID to a role specified by name, run:

```sh
m365 viva engage role member add --userId 7a2ca997-9461-402e-9882-58088a370889 --roleName 'Verified Admin'
```

To assign a user specified by UPN to a role specified by ID, run:

```sh
m365 viva engage role member add --userName john.doe@contoso.com --roleId 77aa47ad-96fe-4ecc-8024-fd1ac5e28f17
```

> This command is based on a Microsoft Graph API that is currently in preview and is subject to change once the API reaches general availability.

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/viva/engage/engage-role-member-add/).

## What's changed

### Update text web parts with `spo page control set`

The `spo page control set` command can now update text web parts on a modern page. Previously, attempting to update a text web part resulted in an error. With this fix you can reliably update the content of text web parts as part of your page automation scenarios.

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/page/page-control-set/).

### Enhanced `spe container get` with name support

The `spe container get` command now supports retrieving a container by its display name. By combining `--name` with either `--containerTypeId` or `--containerTypeName`, you can look up a container without needing to know its ID first.

To get a container by display name and container type name, run:

```sh
m365 spe container get --name "Invoices" --containerTypeName "My container type name"
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spe/container/container-get/).

### Enhanced `spe container permission list` with a containerName option

The `spe container permission list` command now accepts a `containerName` option, letting you list a container's permissions by its display name instead of its ID. As with `spe container get`, you pair the name with a container type ID or name to resolve the container.

To list container permissions by display name and container type name, run:

```sh
m365 spe container permission list --containerName "My Application Storage Container" --containerTypeName "My container type name"
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spe/container/container-permission-list/).

## Keep the momentum going

Every improvement in this release is driven by real-world usage and community input. If you want to help shape the next version, browse the open ["help wanted" issues](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22) or share your ideas on Discord.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Asish Kumar](https://github.com/officialasishkumar)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Machacek](https://github.com/MartinM85)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [arthur-bamboo](https://github.com/arthur-bamboo)
- [brianpmccullough](https://github.com/brianpmccullough)
- [isaac-ja](https://github.com/isaac-ja)
- [KaKi87](https://github.com/KaKi87)

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
