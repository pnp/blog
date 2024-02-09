---
title: CLI for Microsoft 365 v5.4
date: 2022-06-22T22:22:22.222Z
author: Adam Wójcik
githubname: adam-it
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - SharePoint
  - SharePoint Framework (SPFx)
type: regular
---

We've just published a new major version of the CLI for Microsoft 365 with new commands for working with and managing Microsoft 365 and SharePoint Framework projects on any platform.

## Manage Microsoft 365 and SharePoint Framework projects on any platform

CLI for Microsoft 365 is a cross-platform CLI that allows you to manage various configuration settings of Microsoft 365 and SharePoint Framework projects no matter which operating system or shell you use.

While building solutions for Microsoft 365 expands beyond the Windows operating system, managing many platform settings is possible only through PowerShell on Windows. As more and more users work on non-Windows machines, it's inconvenient for them to use a Windows virtual machine to configure their tenants. With the CLI for Microsoft 365, you can configure your tenant no matter which operating system you use. Additionally, using CLI for Microsoft 365, you can manage your SharePoint Framework projects.

## New version of CLI for Microsoft 365 – v5.4

Following our monthly release cadence, we've released a new version of the CLI for Microsoft 365 with some new capabilities. Here are a few of the most noteworthy additions.

> For the complete list of what's new and changed, see the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v540).

### Upgrade SharePoint Framework projects to v1.15

On June 21 2022, Microsoft released a new version of SharePoint Framework. The most noteworthy features are the introduction Form Customizer Extension, which allows developers to customize new, edit and display forms of lists and document libraries, and support for TypeScript v4.5 and Node.js v16. To help you upgrade your projects we've updated CLI for Microsoft 365 with the support for this new version.

To upgrade your SPFx project to this version, change the working directory to your project and execute:

```bash
m365 spfx project upgrade --output md > report.md
```

We'd also recommend that you try a richer upgrade report based on the Visual Studio Code CodeTour extension:

```bash
m365 spfx project upgrade --preview --output tour
```

For more information about upgrading SharePoint Framework projects, see the [CLI documentation](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade/).

### Manage Planner tasks

We added 5 new commands to manage Microsoft Planner tasks with our CLI. With this new addition you are now able to list, add and remove tasks checklist items and also now we may remove task reference.

To create a checklist item for a specified task you can use:

```sh
m365 planner task checklistitem add --taskId 2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2 --title "My checklist item"
```

You can list all checklist items for task with the new list command:

```sh
m365 planner task checklistitem list --taskId "vzCcZoOv-U27PwydxHB8opcADJo-"
```

Removing checklist item from task is possible with:

```sh
m365 planner task checklistitem remove --id "40012" --taskId "2Vf8JHgsBUiIf-nuvBtv-ZgAAYw2"
```

### Permanently remove Office 365 groups

Office 365 groups are a fundamental building block on Microsoft 365 that supports collaboration. As time passes by, you'll likely want to clean up groups that are no longer used. Previously, we added support for retrieving and removing Office 365 groups. In this release, we extended it with the ability to permanently delete removed Office 365 groups.

To remove an Office 365 group from the recycle bin, execute:

```sh
m365 aad o365group recyclebinitem remove --displayName "My Group"
```

For more information about managing Office 365 groups using CLI for Microsoft 365 see the [documentation](https://pnp.github.io/cli-microsoft365/cmd/entra/m365group/m365group-recyclebinitem-remove).

### Manage SharePoint Online event receivers

New command was added in order to help you manage event receivers on SharePoint online, which allows you to retrieve event receivers for the specified web, site or list.

In order to retrieve event receivers in web simply:

```sh
m365 spo eventreceiver list --webUrl https://contoso.sharepoint.com/sites/contoso-sales
```

You can also list all event receivers from specified list:

```sh
m365 spo eventreceiver list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listUrl '/sites/contoso-sales/lists/Events'
```

For more information about listing event receivers, see the [CLI documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/eventreceiver/eventreceiver-list/).

### What else

These features are just the tip of the ice berg of what we've shipped in this version. Check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v540) for the complete list of what's new and improved.

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Akash Karda](https://github.com/akashkarda)
- [Albert-Jan Schot](https://github.com/appieschot)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Patrick Lamber](https://github.com/plamber)
- [Vipul Kelkar](https://github.com/vipulkelkar)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

Thank you all for the time you chose to spend on CLI for Microsoft 365 and for your help to advance it!

## Work in progress

Here are some things that we're currently working on.

### `@me` user tokens to simplify working with the current user

We're constantly seeking for ways to let you work with CLI for Microsoft 365 more efficiently. In the past, we've shipped support for [passing contents from files into options using the `@` token](https://pnp.github.io/cli-microsoft365/user-guide/using-cli/#passing-complex-content-into-cli-options) and [using server-relative URLs with SharePoint commands](https://pnp.github.io/cli-microsoft365/user-guide/using-cli/#working-with-sharepoint-urls-in-spo-commands). We're continuing the improvement by introducing [`@me` tokens](https://github.com/pnp/cli-microsoft365/issues/3056) to let you pass information about the current user into options.

### Managing Planner plans

Many organizations use Microsoft Planner to keep track of their work. As you start working with Planner at scale, you'll be likely to need to automate managing plans, buckets and tasks. In the previous versions of CLI for Microsoft 365 we introduced the base functionality for managing objects in Planner and we'll keep extending it with additional features so that you have everything you need.

### Microsoft 365 app commands

When building apps for Microsoft 365, next to your code, you also need to manage how your app is exposed to Microsoft 365. You need to register your application in Azure Active Directory, and depending what type of app you build, you might need to deploy it to an app catalog as well. All these properties are managed in different locations and we're thinking of ways that we could simplify it for you.

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

If you need more help getting started or want more details about the commands, architecture, or project, go to [aka.ms/cli-m365](https://aka.ms/cli-m365). And if you see any room for improvement, please, don't hesitate to reach out to us either on [GitHub](https://github.com/pnp/cli-microsoft365/discussions) or [Twitter](https://twitter.com/climicrosoft365).
