---
title: CLI for Microsoft 365 v5.2
date: 2022-04-29T09:22:38.096Z
author: Waldek Mastykarz
githubname: waldekmastykarz
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

While building solutions for Microsoft 365 expands beyond the Windows operating system, managing many of the platform settings is possible only through PowerShell on Windows. As more and more users work on non-Windows machines, it’s inconvenient for them to have to use a Windows virtual machine to configure their tenants. With the CLI for Microsoft 365, you can configure your tenant no matter which operating system you use. Additionally, using CLI for Microsoft 365, you can manage your SharePoint Framework projects.

## New version of CLI for Microsoft 365 – v5.2

Following our monthly release cadence, we've released a new version of the CLI for Microsoft 365 with some new capabilities. Here are a few of the most noteworthy additions.

> For the full list of what's new and changed, see the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v520).

### Upgrade SharePoint Framework projects to v1.15.0-beta.6

Recently, Microsoft released a new preview version of SharePoint Framework - the development model for extending Microsoft Viva Connections, Microsoft Teams and SharePoint. This latest beta, introduces a new ability to customize list forms. It also allows you to seamlessly [use the Microsoft Graph JS SDK v3](https://learn.microsoft.com/sharepoint/dev/spfx/release-1.15#microsoft-graph-javascript-sdk-v3-support) which offers a more robust way to connect to Microsoft Graph. To help you upgrade your projects we've updated CLI for Microsoft 365 with the support for this new version.

To upgrade your SPFx project to this version, change the working directory to your project and execute:

```bash
m365 spfx project upgrade --preview --output md > report.md
```

We'd also recommend that you try a richer upgrade report based on the Visual Studio Code CodeTour extension:

```bash
m365 spfx project upgrade --preview --preview --output tour
```

For more information about upgrading SharePoint Framework projects, see the [CLI documentation](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade/).

### Automatically open links in the browser

Before you can start using CLI for Microsoft 365 to manage your tenant, you need to sign in with your account. And typically, you'll do it using the device code flow. After running the `m365 login` command, you'll get the device code to copy and a URL to open.

To make it easier, previously we introduced the `copyDeviceCodeToClipboard` setting. By setting it to `true`, we'll automatically copy the device code to clipboard for you. That's not all. To simplify the login experience further, we introduced a new setting named `autoOpenLinksInBrowser`. When you set it to `true`, we'll automatically open the default browser window with the login URL and all you'll have to do, is to paste the device code.

To enable automatically opening links in browser, run:

```sh
m365 cli config set --key autoOpenLinksInBrowser --value true
```

For more information about configuring CLI for Microsoft 365 see the [documentation](https://pnp.github.io/cli-microsoft365/user-guide/configuring-cli/).

### Manage Power Platform solutions

More and more organizations use Power Platform to automate their business processes and work. To help you manage applications built using Power Platform at scale, we've extended the functionality with CLI for Microsoft 365 with two new commands.

Before you can call Power Platform API from a custom application, you need to register it with Power Platform as a management app. We already offered support for registering custom apps as Power Platform management apps and in this version extended it with support for listing registered management apps, which you can do by running:

```sh
m365 pp managementapp list
```

Managing Power Platform applications starts with environments. Previously, we offered the ability to retrieve Power Automate and Power Apps environments separately, which is odd given they're the same. To make it easier for you, we extended it with the ability to retrieve Power Platform environments:

```sh
m365 pp environment list
```

### Manage private Microsoft Teams channels

One of the recent additions to Microsoft Teams are private channels that offer teams "a focused place to collaborate". We've extended CLI for Microsoft 365 with functionality to manage private chats.

First, we introduced the ability to add private channels:

```sh
m365 teams channel add --teamId 6703ac8a-c49b-4fd4-8223-28f0ac3a6402 --name climicrosoft365 --type private --owner john.doe@contoso.com
```

We've also added a way to manage private chats' members. You can add them:

```sh
m365 teams channel member add --teamName "Human Resources" --channelName "Private Channel" --userDisplayName "Anne Matthews,John Doe" --owner
```

Update their membership by for example changing their role from owner to member:

```sh
m365 teams channel member set --teamName "Team Name" --channelName "Channel Name" --userName johndoe@example.com --role member
```

Or remove them from the chat altogether:

```sh
m365 teams channel member remove --teamName "Team Name" --channelName "Channel Name" --userName johndoe@example.com
```

To see, who's member of a chat, run:

```sh
m365 teams channel member list --teamName "Team Name" --channelName "Channel Name"
```

For more information about managing Teams chats, see the [documentation](https://pnp.github.io/cli-microsoft365/cmd/teams/channel/channel-member-list/).

### Manage Planner buckets

As you start using Microsoft Planner, you might need to update the structure of your plans. If you've been using Planner extensively, you'll need to update the information at scale. To support you in this process, we're continuing extending support for Planner. In this version we introduced the ability to update buckets.

To rename a bucket, run:

```sh
m365 planner bucket set --name "My Bucket" --planName "My Plan" --ownerGroupName "My Group" --newName "New bucket name"
```

For more information about managing Microsoft Planner using CLI for Microsoft 365, see the [documentation](https://pnp.github.io/cli-microsoft365/cmd/planner/plan/plan-list/).

### What else

These features are just the tip of the ice berg of what we've shipped in this version. Check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v520) for the full list of what's new and improved.

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Abhishek K M](https://github.com/Sync271)
- [Reshmee Auckloo](https://github.com/reshmee011)
- [Milan Holemans](https://github.com/milanholemans)
- [Nicholas Honen](https://github.com/nickhonen)
- [Akash Karda](https://github.com/akashkarda)
- [Patrick Lamber](https://github.com/plamber)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)
- [Albert-Jan Schot](https://github.com/appieschot)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)

Thank you all for the time you chose to spend on CLI for Microsoft 365 and your help to advance it!

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

If you need more help getting started or want more details about the commands or the architecture or the project, go to [aka.ms/cli-m365](https://aka.ms/cli-m365). And if you see any room for improvement, please, don't hesitate to reach out to us either on [GitHub](https://github.com/pnp/cli-microsoft365/discussions) or [twitter](https://twitter.com/climicrosoft365).
