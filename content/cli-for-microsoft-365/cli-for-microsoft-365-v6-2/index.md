---
title: CLI for Microsoft 365 v6.2
date: 2023-01-31T06:00:00.000Z
author: Milan Holemans
githubname: milanholemans
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - SharePoint
  - SharePoint Framework (SPFx)
type: popular
---

We've just published a new minor version of the CLI for Microsoft 365 with new commands for working with and managing Microsoft 365 and SharePoint Framework projects on any platform.

## Manage Microsoft 365 and SharePoint Framework projects on any platform

CLI for Microsoft 365 is a cross-platform CLI that allows you to manage various configuration settings of Microsoft 365 and SharePoint Framework projects no matter which operating system or shell you use.

While building solutions for Microsoft 365 expands beyond the Windows operating system, managing many platform settings is possible only through PowerShell on Windows. As more and more users work on non-Windows machines, it's inconvenient for them to use a Windows virtual machine to configure their tenants. With the CLI for Microsoft 365, you can configure your tenant no matter which operating system you use. Additionally, using CLI for Microsoft 365, you can manage your SharePoint Framework projects.

## New version of CLI for Microsoft 365 – v6.2

Following our monthly release cadence, we've released a new version of the CLI for Microsoft 365 with some new capabilities. The month of January was no exception. We had a ton of improvements and new commands. Here are a few of the most noteworthy additions.

> For the complete list of what's new and changed, see the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v620).

## Added support to share files

SharePoint is all about collaborating with people on documents. Previously we introduced some commands to manage permissions on documents. With our new commands, you can share your SharePoint files with anyone you like. In this release, we are introducing commands to manage sharing links on documents.

To create an anonymous sharing link for a file, run:

```sh
m365 spo file sharinglink add --webUrl https://contoso.sharepoint.com --fileUrl "/sites/demo/Shared Documents/Test1.docx" --type edit --scope anonymous --expirationDateTime "2023-01-09T16:20:00Z"
```

To list all anonymous sharing links of a file, run:

```sh
m365 spo file sharinglink list --webUrl https://contoso.sharepoint.com/sites/demo --fileUrl "/sites/demo/shared documents/document.docx" --scope anonymous
```

To remove a sharing link of a file, run:

```sh
m365 spo file sharinglink remove --webUrl https://contoso.sharepoint.com/sites/demo --fileUrl '/sites/demo/Shared Documents/document.docx' --id c391b57d-5783-4c53-9236-cefb5c6ef323
```

More sharing link commands coming soon!

## Application permissions for Planner

Eureka! Finally, we can use application permissions for Planner commands. This much-requested feature is currently rolling out in preview. Previously we showed a friendly error that told us that application permissions don't work for Planner commands, this check has now been removed. You are now free to experiment with our Planner commands with application permissions! You can do this quickly and easily by just creating a new application registration in Azure AD with Planner application permissions, logging in to the CLI with a [certificate](https://pnp.github.io/cli-microsoft365/user-guide/connecting-office-365/#log-in-using-a-certificate) or [secret](https://pnp.github.io/cli-microsoft365/user-guide/connecting-office-365/#log-in-using-a-secret), and you are good to go!

## More compliance commands

In our previous release, we introduced commands to manage compliance within your tenant. This was just the beginning, our v6.2 release contains even more compliance commands.

To create a new retention label, run:

```sh
m365 purview retentionlabel add --displayName 'some label' --behaviorDuringRetentionPeriod retain --actionAfterRetentionPeriod delete --retentionDuration 365
```

To apply a retention label on a file, run:

```sh
m365 spo file retentionlabel ensure --webUrl https://contoso.sharepoint.com/sites/project-x --fileUrl '/Shared Documents/Document.docx' --name 'Some label'
```

To clear a retention label from a folder, run:

```sh
m365 spo folder retentionlabel remove --webUrl https://contoso.sharepoint.com/sites/project-x --folderId 0cd891ef-afce-4e55-b836-fce03286cccf
```

To lock a list item record, run:

```sh
m365 spo listitem record lock --webUrl https://contoso.sharepoint.com/sites/project-x --listId 0cd891ef-afce-4e55-b836-fce03286cccf --listItemId 1
```

Here's a list of all new compliance commands for this release:

- [purview retentionlabel get](https://pnp.github.io/cli-microsoft365/cmd/purview/retentionlabel/retentionlabel-get)
- [purview retentionlabel add](https://pnp.github.io/cli-microsoft365/cmd/purview/retentionlabel/retentionlabel-add)
- [spo file retentionlabel ensure](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-retentionlabel-ensure)
- [spo file retentionlabel remove](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-retentionlabel-remove)
- [spo folder retentionlabel ensure](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-retentionlabel-ensure)
- [spo folder retentionlabel remove](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-retentionlabel-remove)
- [spo listitem record lock](https://pnp.github.io/cli-microsoft365/cmd/spo/listitem/listitem-record-lock)
- [spo listitem record unlock](https://pnp.github.io/cli-microsoft365/cmd/spo/listitem/listitem-record-unlock)
- [spo listitem retentionlabel ensure](https://pnp.github.io/cli-microsoft365/cmd/spo/listitem/listitem-retentionlabel-ensure)
- [spo list retentionlabel remove](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-retentionlabel-remove)

## Further steps in implementing CLI for Microsoft 365 context

In our previous release, we have taken the first steps to create a CLI context. This allows you to save time by storing default values for options that you often use. For example, if you're working with a specific site collection, you can save the URL of the site collection in the context, and CLI for Microsoft 365 will automatically use it when you run a command that requires the URL of the site collection. This way, you don't have to specify the URL of the site collection every time you run a command. In this release, we created extra commands to work with the CLI context. Note this is still a work in progress. We allow managing context settings but don't apply them to commands just yet.

To add/set a context value for a certain option, run:

```sh
m365 context option set --name 'listName' --value 'testList'
```

To remove a context value, run:

```sh
m365 context option remove --name "listName"
```

## Extended Power Platform commands

In the past releases, we gave more focus to our Power Platform commands. This month is no different. Also, in this release, we have new Power Platform commands, especially about AI Builder Models.

To list all AI Builder Models in a specific environment, run:

```sh
m365 pp aibuildermodel list --environment "Default-d87a7535-dd31-4437-bfe1-95340acd55c5"
```

To remove an AI Builder Model, run:

```sh
m365 pp aibuildermodel remove --environment Default-d87a7535-dd31-4437-bfe1-95340acd55c5 --name "AI Builder Model Name"
```

## What's next

Here are some things that we are currently working on.

### Planner Rosters

Rosters are a new type of container for Microsoft Planner plans. This enables users to create a Planner plan without the need to create a new Microsoft 365 group (with a mailbox, SharePoint site, ...). Access to Roster-contained plans is controlled by the members of the Roster. Even though Planner Rosters are still in preview, we are already working on providing the necessary commands for this.

### Sharing link commands

With this release, you are able to easily manage sharing links for SharePoint files. We don't stop here, we have more commands on our roadmap to manage sharing links. We are planning to create more commands to manage sharing links for SharePoint folders, SharePoint list items, OneDrive files, ...

### Manage SPFx extensions

Currently, CLI for Microsoft 365 supports a few commands for SPFx solutions. In the upcoming weeks, we are planning to create more SPFx commands with a focus on SPFx extensions. Planning to add, set, list, and remove SPFx extensions such as ListView Command Sets or Application Customizers? We provide everything to make your life easier.

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Arjun Menon](https://github.com/arjunumenon)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Michael Maillot](https://github.com/michaelmaillot)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Patrick Lamber](https://github.com/plamber)
- [Smita Nachan](https://github.com/SmitaNachan)

### New contributors

A warm welcome to this month's new contributors! (in alphabetical order):

- [Tim Van de Voorde](https://github.com/timdelavoorde)

Thank you all for the time you chose to spend on CLI for Microsoft 365 and for your help to advance it!

### High fives

CLI for Microsoft 365 wouldn't be where it is today if it weren't for our users who provide us with feedback. High fives to the following people who took the time to share their feedback and ideas for improvement with us (in alphabetical order):

- [FinderFees](https://github.com/FinderFees)
- [hcsmith](https://github.com/hcsmith)

### Discussions

CLI for Microsoft 365 is constantly growing and evolving. We're always looking for ways to improve. There are still many areas not covered by the CLI as well as many amazing ideas for unique features the tool might provide. Your feedback will help us make the right decisions in which areas we should focus on. If you want to help out please do join the currently open [discussions](https://github.com/pnp/cli-microsoft365/discussions)

What else could we simplify? Let us know what you think by helping out with one of our [open issues](https://github.com/pnp/cli-microsoft365/issues) or chime in on our [discussions](https://github.com/pnp/cli-microsoft365/discussions)!

## Try it today

Get the latest release of CLI for Microsoft 365 from npm by executing:

```bash
npm i -g @pnp/cli-microsoft365
```

Alternatively, you can get the latest release from Docker by executing:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

If you need more help getting started or want more details about the commands, architecture, or project, go to [aka.ms/cli-m365](https://aka.ms/cli-m365). If you see any room for improvement, please, don't hesitate to reach out to us either on [GitHub](https://github.com/pnp/cli-microsoft365/discussions), [Discord](https://discord.com/invite/7rfW4kg6B5), or [Twitter](https://twitter.com/climicrosoft365).
