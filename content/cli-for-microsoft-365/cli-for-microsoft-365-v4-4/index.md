---
title: "CLI for Microsoft 365 v4.4"
summary: "CLI for Microsoft 365 is a cross-platform CLI that allows you to manage various configuration settings of Microsoft 365 and SharePoint Framework projects no matter which operating system or shell you use"
date: 2022-01-28T12:17:00-05:00
author: "Arjun Menon"
githubname: "arjunumenon"
categories: []
images:
- images/banner-cli-m365.png
tags: ["Azure AD","CLI for Microsoft 365","SharePoint Framework (SPFx)"]
type: "regular"
---

## Manage Microsoft 365 and SharePoint Framework projects on any platform

CLI for Microsoft 365 is a cross-platform CLI that allows you to manage various configuration settings of Microsoft 365 and SharePoint Framework projects no matter which operating system or shell you use.

While building solutions for Microsoft 365 expands beyond the Windows operating system, managing many of the platform settings is possible only through PowerShell on Windows. As more and more users work on non-Windows machines, it’s inconvenient for them to have to use a Windows virtual machine to configure their tenants. With the CLI for Microsoft 365, you can configure your tenant no matter which operating system you use. Additionally, using CLI for Microsoft 365, you can manage your SharePoint Framework projects.

## New version of CLI for Microsoft 365 – v4.4

Following our monthly release cadence, we’ve released a new version of the CLI for Microsoft 365 with some new capabilities. Here are a few of the most noteworthy additions.

### Upgrade SharePoint Framework projects to SPFx v1.14.0 Public Preview

With the announcement of the availability of public preview of the SharePoint Framework (SPFx) 1.14 – with updates for Viva Connections, Microsoft Teams and SharePoint Online experiences, we have added support for upgrading your SPFx projects to the latest preview version, v1.14.0-beta.5.

To upgrade your SPFx project to this version, change the working directory to your project and execute:

```bash
m365 spfx project upgrade --preview --output md > report.md
```

We'd also recommend that you try a richer upgrade report based on the Visual Studio Code CodeTour extension:

```bash
m365 spfx project upgrade --preview --output tour
```

For more information about upgrading SharePoint Framework projects, see the [CLI documentation](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade/).

### List all messages from Microsoft Teams Chat Conversation

Imagine a case where you want to list the messages in a chat conversation. A conversation could be a one-on-one conversation or a meeting conversation or even a group chat. You can use this command if you want to export the conversations easily.

To list the Microsoft Teams chat conversation, execute:

```bash
m365 teams chat message list --chatId 19:2da4c29f6d7041eca70b638b43d45437@thread.v2
```

For more information about listing a particular chat conversation, see the [documentation](https://pnp.github.io/cli-microsoft365/cmd/teams/chat/chat-message-list/).

### List members  from a Microsoft Teams Chat Conversation

If you want to list the members of a chat conversation which you are part of, we have released a new command just for you.  A conversation could be a one-on-one conversation or a meeting conversation or even a group chat. You can use this command if you want to export the conversations easily.

Lists all members from a Microsoft Teams chat conversation, execute:

```bash
m365 teams chat member list --chatId 19:8b081ef6-4792-4def-b2c9-c363a1bf41d5_5031bb31-22c0-4f6f-9f73-91d34ab2b32d@unq.gbl.spaces
```

For more information about listing the members of a chat conversation, see the [documentation](https://pnp.github.io/cli-microsoft365/cmd/teams/chat/chat-member-list/).

### List all Microsoft Teams Chat Conversation for the current user

List of chat conversations which you are part of can become overwhelming when time goes on. With this new command, you can list all the chat conversation which the current logged in user is part. This will be beneficial if you want to report or see the list of conversation of the currently logged in user. You can even filter only One-on-One conversations if needed.

Lists all Microsoft Teams chat conversations for the current user, execute:

```bash
m365 teams chat list
```

For more information about getting the list of conversation of the currently logged in user, see the [documentation](https://pnp.github.io/cli-microsoft365/cmd/teams/chat/chat-list/).

### List all Azure AD groups from a tenant

IT pros may constantly need the inventory of users, groups etc. which are there in a tenant. In this version  we have released a new command which you can use to get the complete list of AD groups which are part of the tenant.

To retrieve the list of AD groups, execute :

```bash
m365 aad group list
```

For more information about getting the list of AD groups in your tenant, see the [documentation](https://pnp.github.io/cli-microsoft365/cmd/aad/group/group-list/).

### Get the list of  “pwned” users of a particular Username

Security breach of users of the organization is a nightmare to any Admins. Imagine if user accounts which are part of your organization has been compromised via a data leak affected to any other organizations where users of your organization has used his / her username. This may lead the user data to be available in the web. We released a new command where you can run against the username of your organization to identify whether users have been pwned.

If you want to check whether a username is in a data breach,  execute :

```bash
m365 aad user hibp --userName account-exists@hibp-integration-tests.com --apiKey _YOUR-API-KEY_
```

For more information about getting the details about pwned users of your organization, see the [documentation](https://pnp.github.io/cli-microsoft365/cmd/aad/user/user-hibp/)

### Set a planner task

Usage of Microsoft Planner becomes inevitable for any organization where tasks are being assigned and managed. With this version of CLI for Microsoft 365., we have released a new command where you can update any planner tasks with the needed properties / attributes. If you want to update any planner task, execute :

```bash
m365 planner task set --id "Z-RLQGfppU6H3663DBzfs5gAMD3o" --title "My Planner Task"
```

For more information about setting the planner tasks, see the [documentation](https://pnp.github.io/cli-microsoft365/cmd/planner/task/task-set/)

### List the items of SharePoint recycle bin

IT pros often gets requests from the users to know about the items which had been deleted by the users. In this version, we have released a new command which will give you the list of items from SharePoint Recycle bin. This command also gives you the flexibility to filter only files from the list.

For getting list if all items from Recycle bin, execute :

```bash
m365 spo site recyclebinitem list --siteUrl https://contoso.sharepoint.com/site
```

For more information about getting the items from recyclebin, see the [documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-recyclebinitem-list/)

### Extended CLI configuration with CSV Output

In our [last release](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/cli-for-microsoft-365-v4-3/ba-p/3051947), we had extended our output to support results in CSV format. Now we have extended our commands so that users can set the configuration if you want to have the output always in CSV format.

For setting the output to CSV in the configuration, execute :

```bash
m365 cli config set --key output --value csv
```

For more information about setting configuration for CLI, see the [documentation](https://pnp.github.io/cli-microsoft365/cmd/cli/config/config-set/)

### More options to add users to a SharePoint group

In this new release, we have added the ability to add users to SharePoint group with SharePoint group name as well using email of the user. With this update, users can easily add users to SharePoint group without the need for them to know the if of the SharePoint group.

For adding users to SharePoint group using Group name, execute :

```bash
m365 spo group user add --webUrl https://contoso.sharepoint.com/sites/SiteA --groupName "Contoso Site Owners" --email "Alex.Wilber@contoso.com, Adele.Vance@contoso.com"
```

For more information about adding users to SharePoint group, see the [documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/group/group-member-add)

### Enhanced Documentation for managing Microsoft 365 Apps

We had enhanced our command for adding Azure AD apps by adding the `--save`  option which would be beneficial for creating Microsoft 365 apps easily from your project. We now have extended out documentation on how to use the command while you develop Microsoft 365 Apps.

For knowing more details on managing Microsoft 365 Apps, see the [documentation](https://pnp.github.io/cli-microsoft365/user-guide/manage-microsoft-365-apps/)

## New script samples

CLI for Microsoft 365 is a great tool both for quick adjustments to the configuration of your Microsoft 365 tenant as well as automating more complex tasks. Because CLI for Microsoft 365 is cross-platform you can use it on any OS and in any shell. To help you get started using the CLI for Microsoft 365 for automation scenarios, we started gathering some [sample scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/introduction).

### List all large files in a SharePoint site

This script will help you [find files in a specific SharePoint Online site that are over a certain size](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/list-large-files-within-a-site/). It iterates through all libraries and identifies all files larger than the set threshold.

If you have any scripts that you use frequently, please [share](https://github.com/pnp/cli-microsoft365/discussions) them with us so that we can learn more about the common automation scenarios.

## Contributors

This release wouldn’t be possible without the help of (in alphabetical order):

*   [Adam Wójcik](https://github.com/Adam-it)
*   [Albert-Jan Schot](https://github.com/appieschot)
*   [Christian Bewernitz](https://github.com/karfau)
*   [Jasey Waegebaert](https://github.com/Jwaegebaert)
*   [Martin Lingstuyl](https://github.com/martinlingstuyl)
*   [Nanddeep Nachan](https://github.com/nanddeepn)
*   [Robert Dyjas](https://github.com/robdy)
*   [Veronique Lengelle](https://github.com/veronicageek)
*   [Vipul Kelkar](https://github.com/vipulkelkar)
*   [Waldek Mastykarz](https://github.com/waldekmastykarz)

## Work in Progress

Here are some things that we’re currently working on.

### CLI for Microsoft 365 v5

For the last few months we've been working on a new major version of CLI for Microsoft 365 – v5. While typically we release a major version once a year, we sped up releasing v5 to migrate commands using the Azure AD Graph to use Microsoft Graph instead. Azure AD Graph will be deprecated later this year and we wanted to be ahead of the deprecation to ensure that CLI for Microsoft 365 keeps working uninterrupted.

We are expecting to release CLI for Microsoft 365 v5 by the end of February 2022. Once the release of v5 is complete, we'll publish an upgrade guidance to help you determine the impact of the upgrade on your work.

### CLI for Microsoft 365 Themes

Following our latest major release, we have started thinking about themes for the coming year but we would love to know what you think we should concentrate on next. We are of course looking at topics as Microsoft Viva and the Power Platform but if you have any suggestions, please let us know by adding your suggestion to our [open discussion](https://github.com/pnp/cli-microsoft365/discussions/2708) on GitHub.

### Tenant Status Commands to handle the deprecated Endpoints

Some of the endpoints which our command is using for getting the Tenant status is getting deprecated. We are updating our commands to ensure that deprecation does not affect our commands.

### Extending AD user commands for getting the deleted users

We are updating some Azure AD commands so that you can even get the users which are deleted from Azure AD

### Microsoft 365 app commands

When building apps for Microsoft 365, next to your code, you also need to manage how your app is exposed to Microsoft 365. You need to register your application in Azure Active Directory, and depending what type of app you build, you might need to deploy it to an app catalog as well. All these properties are managed in different locations and we're thinking of ways that we could simplify it for you.

What else could we simplify? Let us know what you think by helping out with one of our [open issues](https://github.com/pnp/cli-microsoft365/issues) or chime in on our [open discussion](https://github.com/pnp/cli-microsoft365/discussions)!

## Try it today

Get the latest release of the CLI for Microsoft 365 from npm by executing:

```bash
npm i -g @pnp/cli-microsoft365
```


Alternatively, you can get the latest release from Docker by executing:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

If you need more help getting started or want more details about the commands, the architecture or the project, go to [aka.ms/cli-m365](https://aka.ms/cli-m365).

If you see any room for improvement, please, don’t hesitate to reach out to us either on [GitHub](https://github.com/pnp/cli-microsoft365/issues) or [twitter](https://twitter.com/climicrosoft365).
