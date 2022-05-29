---
title: CLI for Microsoft 365 v5.3
date: 2022-05-31T09:22:38.096Z
author: Patrick Lamber
githubname: plamber
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

We've just published a new major version of the CLI for Microsoft 365 with new commands for working with and managing Microsoft 365 and SharePoint Framework projects on any platform.

## Manage Microsoft 365 and SharePoint Framework projects on any platform

CLI for Microsoft 365 is a cross-platform CLI that allows you to manage various configuration settings of Microsoft 365 and SharePoint Framework projects no matter which operating system or shell you use.

While building solutions for Microsoft 365 expands beyond the Windows operating system, managing many platform settings is possible only through PowerShell on Windows. As more and more users work on non-Windows machines, it's inconvenient for them to use a Windows virtual machine to configure their tenants. With the CLI for Microsoft 365, you can configure your tenant no matter which operating system you use. Additionally, using CLI for Microsoft 365, you can manage your SharePoint Framework projects.

## New version of CLI for Microsoft 365 – v5.3

Following our monthly release cadence, we've released a new version of the CLI for Microsoft 365 with some new capabilities. Here are a few of the most noteworthy additions.

> For the complete list of what's new and changed, see the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v530).

### Manage the Planner bucket life-cycle

We added 16 commands to manage Microsoft Planner with our CLI in the past couple of months. This latest beta introduces the ability to manage all aspects of managing Planner buckets.

To create a new Bucket in a Plan associated with a Group you can use:

"`bash
m365 planner bucket add --name "My Planner Bucket" --planName "My Planner Plan" --ownerGroupName "My Planner Group"
```

You can list the Buckets of a Plan by using the bucket list command:

"`bash
m365 planner bucket list --planName "My Planner Plan" --ownerGroupName "My Planner Group"
```

Some commands allow you to set and delete Planner buckets. For more information about using these commands, see [bucket set](https://pnp.github.io/cli-microsoft365/cmd/planner/bucket/bucket-set/) or [bucket remove](https://pnp.github.io/cli-microsoft365/cmd/planner/bucket/bucket-remove/).

### Manage the list and listitem role inheritance

In some situations, you must break or restore the role inheritance for SharePoint Online lists or items. With this version we introduced 4 new commands to handle these use cases.

To break the role inheritance of a list, use:

```sh
m365 spo list roleinheritance break --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList"
```

To restore it back, use:

```sh
m365 spo list roleinheritance reset --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList"
```

If you are interested in managing the role inheritance for list items, see [spo listitem role inheritance break](https://pnp.github.io/cli-microsoft365/cmd/spo/listitem/listitem-roleinheritance-break/) and [spo listitem role inheritance reset](https://pnp.github.io/cli-microsoft365/cmd/spo/listitem/listitem-roleinheritance-reset/).

### Retrieve the security alerts for a tenant

We extended the list of reporting commands in our CLI with the list of security alerts associated with a tenant:

"`sh
m365 tenant security alerts list --vendor "Azure Sentinel"
```

### What else

These features are just the tip of the ice berg of what we've shipped in this version. Check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v530) for the complete list of what's new and improved.

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Michaël Maillot](https://github.com/michaelmaillot)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Patrick Lamber](https://github.com/plamber)
- [Reshmee Auckloo](https://github.com/reshmee011)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Veronique Lengelle](https://github.com/veronicageek)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

Thank you all for the time you chose to spend on CLI for Microsoft 365 and for your help to advance it!

## Work in progress

Here are some things that we're currently working on.

### Manage Planner checklist items

You can add checklist items to a Planner task to organize your task. We are working on the commands to manage a Planner task's checklist item life cycle.

## Try it today

Get the latest release of CLI for Microsoft 365 from npm by executing:

"`bash
npm i -g @pnp/CLI-microsoft365
```

Alternatively, you can get the latest release from Docker by executing:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

If you need more help getting started or want more details about the commands, architecture, or project, go to [aka.ms/cli-m365](https://aka.ms/cli-m365). And if you see any room for improvement, please, don't hesitate to reach out to us either on [GitHub](https://github.com/pnp/cli-microsoft365/discussions) or [Twitter](https://twitter.com/climicrosoft365).
