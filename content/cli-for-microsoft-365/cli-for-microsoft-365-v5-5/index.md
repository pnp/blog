---
title: CLI for Microsoft 365 v5.5
date: 2022-07-27T22:22:22.222Z
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

## New version of CLI for Microsoft 365 – v5.5

Following our monthly release cadence, we've released a new version of the CLI for Microsoft 365 with some new capabilities. Here are a few of the most noteworthy additions.

> For the complete list of what's new and changed, see the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v550).

### Manage Planner

Many organizations use Microsoft Planner to keep track of their work. As you start working with Planner at scale, you'll be likely to need to automate managing plans, buckets and tasks. In this release we introduce commands which allow you to remove a specified plan and manage planner tenant settings.

Removes the Microsoft Planner plan with title My Plan in group with name My Planner Group without confirmation prompt

```sh
m365 planner plan remove --title "My Plan" --ownerGroupName "My Planner Group" --confirm
```

Disable Microsoft Planner in the tenant

```sh
m365 planner tenant settings set --isPlannerAllowed false
```

Disable Outlook calendar sync and mobile push notifications

```sh
m365 planner tenant settings set --allowCalendarSharing false --allowPlannerMobilePushNotifications false
```

For more information see the [planner plan remove](https://pnp.github.io/cli-microsoft365/cmd/planner/plan/plan-remove/) and [planner tenant settings set](https://pnp.github.io/cli-microsoft365/cmd/planner/tenant/tenant-settings-set/)

### Get external connection in Microsoft Search

There is no better place to find what you are looking for than Microsoft Search. Now we allow the administrator to get a specific external connection.

Get the External Connection by its name

```sh
m365 search externalconnection get --name "Test"
```

For more information see the [search externalconnection get](https://pnp.github.io/cli-microsoft365/cmd/search/externalconnection/externalconnection-get/)

### Manage SharePoint Online roles and groups

Using permission roles and groups in SharePoint gives possibility to make your solution more secure and available only to specified group of users. In this release we added couple of commands which help with group and role management.

Retrieve the role definition for site https://contoso.sharepoint.com/sites/project-x with id 1

```sh
m365 spo roledefinition get --webUrl https://contoso.sharepoint.com/sites/project-x --id 1
```

Update group with membership requests

```sh
m365 spo group set --webUrl https://contoso.sharepoint.com/sites/project-x --title "Project leaders" --allowRequestToJoinLeave true --requestToJoinLeaveEmailSetting john.doe@contoso.com
```

Sets a specified user as group owner

```sh
m365 spo group set --webUrl https://contoso.sharepoint.com/sites/project-x --id 18 --ownerEmail john.doe@contoso.com
```

Create group with title and description

```sh
m365 spo group add --webUrl https://contoso.sharepoint.com/sites/project-x --name "Project leaders" --description "This group contains all project leaders"
```

For more information see the [spo roledefinition get](https://pnp.github.io/cli-microsoft365/cmd/spo/roledefinition/roledefinition-get/), [spo group set](https://pnp.github.io/cli-microsoft365/cmd/spo/group/group-set/) and [spo group add](https://pnp.github.io/cli-microsoft365/cmd/spo/group/group-add/) command documentation.

### Remove Microsoft Teams client cache

Microsoft Teams has become a collaboration platform of its own and for many of us, working remotely or not, it is the first start up tool when starting your working day. With CLI for Microsoft 365 we try to extend the capabilities of what you may manage around that product. In this release we introduce a command which allows you to remove the Microsoft Teams client cache

Removes the Microsoft Teams client cache

```sh
m365 teams cache remove
```

For more information see the [teams cache remove](https://pnp.github.io/cli-microsoft365/cmd/teams/cache/cache-remove/)

### Introduce @meId and @meUsername user tokens to simplify working with the current user

We're constantly seeking for ways to let you work with CLI for Microsoft 365 more efficiently. In this release we introduce the @meId and @meUsername which we may use to easily specify information about the current user in a command. This is a huge improvement as now we no longer need to retrieve current user name from the `status` command or use `aad user get` to get the current user id.

Get information about the currently logged in user using the Id token

```sh
m365 aad user get --id "@meId"
```

Get information about the currently logged in user using the UserName token

```sh
m365 aad user get --userName "@meUsername"
```

For more information see the [@meId and @meUserName tokens](https://pnp.github.io/cli-microsoft365/user-guide/using-cli/#meid-and-meusername-tokens)

## New script samples

CLI for Microsoft 365 is a great tool both for quick adjustments to the configuration of your Microsoft 365 tenant as well as automating more complex tasks. Because CLI for Microsoft 365 is cross-platform you can use it on any OS and in any shell. To help you get started using the CLI for Microsoft 365 for automation scenarios, we started gathering some [sample scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/).

If you have any scripts that you use frequently, please [share](https://github.com/pnp/cli-microsoft365/discussions) them with us so that we can learn more about the common automation scenarios.

### List all external users in site groups across all site collections

Martin Lingstuyl contributed a sample that shows external users in site groups across all site collections [List all external users in site groups across all site collections](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/list-externalusers-in-sitegroups/).

### What else

These features are just the tip of the ice berg of what we've shipped in this version. Check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v550) for the complete list of what's new and improved.

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Albert-Jan Schot](https://github.com/appieschot)
- [Garry Trinder](https://github.com/garrytrinder)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Kevin McDonnell](https://github.com/kevmcdonk)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Patrick Lamber](https://github.com/plamber)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

Thank you all for the time you chose to spend on CLI for Microsoft 365 and for your help to advance it!

## Work in progress

Here are some things that we're currently working on.

### Extend Outlook mail send command with support for attachments

We are constantly improving where possible. Currently we are working on improving the command which allows to send mail with possiblity to add attachements to it.

### SharePoint event receiver commands

We are extending our commands with adding more functionality which will allow to manage SharePoint event receivers.

### Managing SharePoint files

CLI for Microsoft 365 already has a lot of commands which allow to do various operations on files but we are adding yet another one to the collection which will allow to do a file rename.

### Microsoft Graph insights

We are adding a new command which will allow to get an overview of specific API-level changes in Microsoft Graph v1.0 and beta.

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
