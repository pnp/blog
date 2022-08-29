---
title: CLI for Microsoft 365 v5.6
date: 2022-08-11T12:53:34.970Z
author: Garry Trinder
githubname: garrytrinder
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

## New version of CLI for Microsoft 365 – v5.6

Following our monthly release cadence, we've released a new version of the CLI for Microsoft 365 with some new capabilities. Here are a few of the most noteworthy additions.

> For the complete list of what's new and changed, see the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v560).

### Upgrade SharePoint Framework projects to v1.15.2

Recently Microsoft [released](https://devblogs.microsoft.com/microsoft365dev/announcing-sharepoint-framework-1-15-2-with-updates-for-viva-connections-microsoft-teams-and-sharepoint/) a new version of SharePoint Framework - the development model for extending Microsoft Viva Connections, Microsoft Teams and SharePoint.

This new version includes new capabilities to streamline multi-tenant partner solution deployment process with integrated Azure AD app consent for the API registration, the general availability of new media action type for supporting uploading media assets from the Viva Connections Adaptive Card Extensions, updates to the default ESLint rules and how you can configure them based on environment requirements, the ability to defer loading Adaptive Card Extension Quick View for optimized performance, and improvements to address issues raised by customers and partners across Microsoft Viva, Microsoft Teams and SharePoint.

To help you upgrade your projects we've updated CLI for Microsoft 365 with the support for this new version.

To upgrade your SPFx project to this version, change the working directory to your project and execute:

```bash
m365 spfx project upgrade --output md > report.md
```

We'd also recommend that you try a richer upgrade report based on the Visual Studio Code CodeTour extension:

```bash
m365 spfx project upgrade --preview --output tour
```

For more information about upgrading SharePoint Framework projects, see the [CLI documentation](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade/).

### Rename file stored in SharePoint

We have added a new command which enables you to easily rename files stored in SharePoint.

To rename a file:

```sh
m365 spo file rename --webUrl https://contoso.sharepoint.com/sites/project-x --sourceUrl '/Shared Documents/Test1.docx' --targetFileName 'Test2.docx'
```

To rename a file where the filename already exists, moving the old file into the recycle bin:

```sh
m365 spo file rename --webUrl https://contoso.sharepoint.com/sites/project-x --sourceUrl '/Shared Documents/Test1.docx' --targetFileName 'Test2.docx' --force
```

### What else

These features are just the tip of the ice berg of what we've shipped in this version. Check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v560) for the complete list of what's new and improved.

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Garry Trinder](https://github.com/garrytrinder)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Patrick Lamber](https://github.com/plamber)

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
