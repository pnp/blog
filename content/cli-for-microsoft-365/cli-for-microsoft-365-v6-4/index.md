---
title: CLI for Microsoft 365 v6.4
date: 2023-03-31T06:00:00.000Z
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

We've published a new minor version of CLI for Microsoft 365. 

[CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform tool. It helps you manage your Microsoft 365 tenant and SharePoint Framework projects. No matter which operating system or shell you use.

> Read the [release notes](https://aka.ms/cli-m365/notes) in full for all new features and improvements.
 
## What's new

We've added new commands in this release. This section gives an overview of the new functionality.

### Retrieve a member from Microsoft Planner Roster

Rosters are a new type of container that you can use to manage access to Planner plans without the need for a Microsoft 365 group.

To retrieve a specific user by their user name from a given roster, use:

```sh
m365 planner roster member get --rosterId tYqYlNd6eECmsNhN_fcq85cAGAnd --userName john.doe@contoso.com
```

### Manage Power Automate Flow ownership

Flows in Power Automate let you share your flows with others as owners or users. Owners can change flows, whereas users can run or execute flows.

We've released three new commands in this release to manage the ownership of Power Automate Flows.

To list the owners of a Power Automate Flow created by another user in by it's name, use:

```sh
m365 flow owner list --environmentName Default-c5a5d746-3520-453f-8a69-780f8e44917e --flowName 72f2be4a-78c1-4220-a048-dbf557296a72 --asAdmin
```

To add a new user as an owner of a Power Automate Flow by their username, use: 

```sh
m365 flow owner ensure --userName "john.doe@contoso.com" --environmentName Default-c5a5d746-3520-453f-8a69-780f8e44917e --flowName 72f2be4a-78c1-4220-a048-dbf557296a72 --roleName CanEdit
```

To remove a user as an owner of a Power Automate Flow by their username, use:

```sh
m365 flow owner remove --userName john.doe@contoso.com --environmentName Default-c5a5d746-3520-453f-8a69-780f8e44917e --flowName 72f2be4a-78c1-4220-a048-dbf557296a72
```

Also to adding specific users, we've also included support for adding a group as an owner.

To add a group as an owner of a Power Automate Flow by its id, use:

```sh
m365 flow owner ensure --groupId 8d4d9f32-1ab0-4f81-9054-efbb1759e8e6 --environmentName Default-c5a5d746-3520-453f-8a69-780f8e44917e --flowName 72f2be4a-78c1-4220-a048-dbf557296a72 --roleName CanEdit
```

To remove a group as an owner of a Power Automate Flow by its id, use:

```sh
m365 flow owner remove --groupId "5c241023-2ba5-4ea8-a516-a2481a3e6c51" --environmentName Default-c5a5d746-3520-453f-8a69-780f8e44917e --name 72f2be4a-78c1-4220-a048-dbf557296a72
```

### Create Microsoft Purview retention events

When you keep content, the retention period is often based on the age of the content. For example, you might keep documents for seven years after they're created and then delete them.  when you configure retention labels, you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period. All content with a retention label applied for that type of event get the label's retention actions enforced on them.

We've added a new command in this release to create new retention events to trigger the start of a retention period.

To create a retention event to start retention at the end of 2022 for all employee documents that have a label and have the Asset ID `EmployeeNr1234`, use:

```sh
m365 purview retentionevent add --displayName 'Employee information expiration' --description 'Employee documents expired due to offboarding' --eventType 'CustomRetentionTime' --triggerDateTime '2022-12-31' --assetIds 'ComplianceAssetId:EmployeeNr1234'
```

### Retrieve tenant scoped SharePoint Online Application Customizers

SharePoint Online Tenant Application Customizers are a type of SharePoint Framework (SPFx) extension. They allow developers to adding custom scripts or HTML to the header or footer of every page in a SharePoint site collection. A tenant scoped customization applies to all sites and subsites within the tenant.

To retrieve a tenant scoped Application Customizer by its title, use:

```sh
m365 spo tenant applicationcustomizer get --title 'Some customizer'
```

### Ensure a user on a SharePoint Online site

When attempting to add a user to a SharePoint Online site that is already a member you will recieve an error.

We've added a new command in this release to check whether the specified user name is a member of the site. If the user is not a member of the site, it adds it as a member.

To ensure a user on a site, use:

```sh
m365 spo user ensure --webUrl https://contoso.sharepoint.com/sites/project --userName john.doe@contoso.com
```

### Manage SharePoint Online ListView Command Sets

ListView Command Sets are a feature in SharePoint Online that allow you to add custom actions to the command bar in a list or library.

We've added four new commands to this release to manage ListView Command Sets on SharePoint Online sites.

To remove a ListView Command Set by its title on a specified SharePoint Onlin site, use:

```sh
m365 spo commandset remove --title 'Some customizer' --webUrl https://contoso.sharepoint.com/sites/sales
```

To update the title and location of a ListView Command Set
Updates the title and location of a ListView Command Set on the sales site.

```sh
m365 spo commandset set --clientSideComponentId 799883f5-7962-4384-a10a-105adaec6ffc --newTitle 'Some new title' --location Both --webUrl https://contoso.sharepoint.com/sites/sales --scope Site
```

To retrieve a ListView Command Set by it's title from a SharePoint Online site, use:

```sh
m365 spo commandset get --title "Some customizer" --webUrl https://contoso.sharepoint.com/sites/sales
```

To retrieve a list of ListView Command Sets from a SharePoint Online site, use:

```sh
m365 spo commandset list --webUrl https://contoso.sharepoint.com/sites/sales
```

To add a ListView Command Set to a list on a SharePoint Online site, use: 

```sh
m365 spo commandset add --title 'Some customizer' --clientSideComponentId 799883f5-7962-4384-a10a-105adaec6ffc --listType List --webUrl https://contoso.sharepoint.com/sites/sales
```

## What's changed

We've updated some existing commands with new functionality. Here is an overview of the new functionality.

### Improvements to Power Platform commands

In this release we've made an internal change to our existing Power Platform commands.

The change does not change any of the command options, however it does introduce an additional permission that you may need to consent to.

If you have scripts that are using Power Platform commands and they stop working, it is highly likely that it will be due to this change. 

To resolve the issue, you need to consent to the additional permission,PowerApps Service, that have been added to the PnP Management Shell Azure AD application.

To review and re-consent CLI for Microsoft 365 permissions, use:

```sh
m365 cli reconsent
```

> Read the [pull request](https://github.com/pnp/cli-microsoft365/pull/4460) for more details on this change.

### Add link-less navigation nodes to SharePoint Online navigation

SharePoint Online supports the ability to create navigation nodes called Labels that don't need you to provide a URL.

We've updated the `spo navigation node add` command to support the creation of Label navigation nodes. 

To create a label (or linkless navigation node), use:

```sh
m365 spo navigation node add --webUrl https://contoso.sharepoint.com/sites/team-a --location TopNavigationBar --title About
```

### List Power Automate Flow runs for a flow created by another user

Before the `flow run list` command only returned runs for Flows that were create by the logged in user. 

In this release, we've extended the command to support returning runs for Flows created by other users with an `--asAdmin` option.

To list Power Automate Flow runs for a flow created by another user, use:

```sh
m365 flow run list --environmentName Default-d87a7535-dd31-4437-bfe1-95340acd55c5 --flowName 5923cb07-ce1a-4a5c-ab81-257ce820109a --asAdmin
```

### Create tasks with more detail in Microsoft To Do 

The Microsoft Graph endpoint that we use for creating tasks has been updated with new properties.

In this release we have extended the `todo task add` command with new options:

- Status
- Categories
- Start Date Time
- Completed Date Time

To create a new task, setting categories, a completed date and time, a start date and Time and a task status, use:

```sh
m365 todo task add --title "New task" --listName "My task list" --categories "Red category,Important" --completedDateTime 2023-12-01 --startDateTime 2023-12-01 --status "notStarted"
```

### Turn on or off the Viva Connections start experience on a SharePoint Online Home Site

In this release we have extended the `spo homeset set` command to now give the ability to turn on or off the Viva Connections start experience.

To turn on the Viva Connections start experience on a SharePoint Online Home Site, use:

```sh
m365 spo homesite set --siteUrl https://contoso.sharepoint.com/sites/comms --vivaConnectionsDefaultStart $true
```

### Upgrade SharePoint Framework projects to v1.17.0-beta.3

In this release we've updated the `spfx project upgrade` command to provide support for upgrading your projects to the latest preview version of SharePoint Framework.

To upgrade your project to the latest preview version, use:

```sh
m365 spfx project upgrade --preview
```

## What's next

Here are some things that we are currently working on.

### More commands

We are always looking to add more commands to CLI for Microsoft 365. 

We are busy implementing commands across several Microsoft 365 services, such as Power Platform, SharePoint Online and Microsoft Purview.

If you have any ideas or suggestions for new commands, please let us know by creating a [new issue](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=new-command.yml&title=New+command%3A+%3Cshort+description%3E) in the GitHub Issues list, or reaching out to us on our [community Discord server](https://aka.ms/cli-m365/discord) to discuss.

### Improvements to our community Discord server

We recently launched a community Discord server for CLI for Microsoft 365. 

We've seen a huge amount of engagement and activity on the server. So much so, that we've decided to make it is where we want to focus and grow the CLI for Microsoft 365 community.

We've made it easier for you to get help, share and find content related to CLI for Microsoft 365.

- Have a question about CLI for Microsoft 365? Create a thread in the `#ask-for-help` channel.
- Have you seen or created an article related to CLI for Microsoft 365? Share it in the `#articles` channel.
- Have you seen or created a video related to CLI for Microsoft 365? Share it in the `#videos` channel.
- Want to have chat about CLI for Microsoft 365? Use the `#chat` channel.

We are looking at other ways in which we can use Discord. So expect to see a lot more changes and activity over the coming months.

If you aren't already a member, join today: [aka.ms/cli-m365/discord](https://aka.ms/cli-m365/discord)

If you are, thank you for being an amazing part of this community.

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [alanc-msft](https://github.com/alanc-msft)
- [Garry Trinder](https://github.com/garrytrinder)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Reshmee Auckloo](https://github.com/reshmee011)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Valeras Narbutas](https://github.com/ValerasNarbutas)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

Thank you all for the time you chose to spend on CLI for Microsoft 365 and for your help to advance it!

## Try it today!

Get the latest release of CLI for Microsoft 365 from npm by executing:

```bash
npm i -g @pnp/cli-microsoft365
```

Or, you can get the latest release from Docker by executing:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

## Need more info?

If you need more help getting started or want more details about the commands, architecture, or project, go to [aka.ms/cli-m365](https://aka.ms/cli-m365).

## Get in touch!

If you see any room for improvement, please, don't hesitate to reach out to us either on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://discord.com/invite/7rfW4kg6B5), or [Twitter](https://twitter.com/climicrosoft365).
