---
title: CLI for Microsoft 365 v6.3
date: 2023-02-28T06:00:00.000Z
author: Martin Lingstuyl
githubname: martinlingstuyl
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

We've just published a new minor version of the CLI for Microsoft 365 with new commands for working with and managing Microsoft 365 and SharePoint Framework projects on any platform.

## Manage Microsoft 365 and SharePoint Framework projects on any platform

CLI for Microsoft 365 is a cross-platform CLI that allows you to manage various configuration settings of Microsoft 365 and SharePoint Framework projects no matter which operating system or shell you use.

While building solutions for Microsoft 365 expands beyond the Windows operating system, managing many platform settings is possible only through PowerShell on Windows. As more and more users work on non-Windows machines, it's inconvenient for them to use a Windows virtual machine to configure their tenants. With the CLI for Microsoft 365, you can configure your tenant no matter which operating system you use. Additionally, using CLI for Microsoft 365, you can manage your SharePoint Framework projects.

## New version of CLI for Microsoft 365 – v6.3

Following our monthly release cadence, we've released a new version of the CLI for Microsoft 365 with some new capabilities. February was no exception. We had a ton of improvements and no fewer than 33 new commands. Here are a few of the most noteworthy additions.

> For the complete list of what's new and changed, see the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v630).

## Added new Azure AD commands

Working with Azure AD is one of the things for which the CLI for Microsoft 365 is often used. In this release we've introduced a series of new commands for managing users.

To create a new user, run:

```sh
m365 aad user add --displayName "John Doe" --userName "john.doe@contoso.com" --password "SomePassw0rd" --forceChangePasswordNextSignIn
```

To delete a user, run:

```sh
m365 aad user remove --name john.doe@contoso.com
```

To list license details of a specific user, run:

```sh
m365 aad user license list --userName john.doe@contoso.com
```

Here's a list of all new Azure AD commands for this release:

- [aad license list](https://pnp.github.io/cli-microsoft365/cmd/aad/license-list)
- [aad user add](https://pnp.github.io/cli-microsoft365/cmd/aad/user/user-add)
- [aad user remove](https://pnp.github.io/cli-microsoft365/cmd/aad/user/user-remove)
- [aad user license list](https://pnp.github.io/cli-microsoft365/cmd/aad/user/user-license-list)
- [aad user license add](https://pnp.github.io/cli-microsoft365/cmd/aad/user/user-license-add)
- [aad user license remove](https://pnp.github.io/cli-microsoft365/cmd/aad/user/user-license-remove)
- [aad user recyclebinitem clear](https://pnp.github.io/cli-microsoft365/cmd/aad/user/user-recyclebinitem-clear)
- [aad user recyclebinitem list](https://pnp.github.io/cli-microsoft365/cmd/aad/user/user-recyclebinitem-list)
- [aad user recyclebinitem remove](https://pnp.github.io/cli-microsoft365/cmd/aad/user/user-recyclebinitem-remove)
- [aad user recyclebinitem restore](https://pnp.github.io/cli-microsoft365/cmd/aad/user/user-recyclebinitem-restore)

## Added new Planner Commands

In this release, another series of Microsoft Planner commands are introduced. With these commands you can manage Planner Roster. Rosters are a new type of container that you can use to manage access to planner plans without the need for a Microsoft 365 group.

To create a new Microsoft Planner Roster, run: 

```sh
m365 planner roster add
```

To give a user access to a Microsoft Planner Roster, run: 

```sh
m365 planner roster member add --rosterId tYqYlNd6eECmsNhN_fcq85cAGAnd --userName john.doe@contoso.com
```

To list all users having access to a Microsoft Planner Roster, run: 

```sh
m365 planner roster member list --rosterId tYqYlNd6eECmsNhN_fcq85cAGAnd
```

Here's a list of all new Planner commands for this release:

- [planner roster add](https://pnp.github.io/cli-microsoft365/cmd/planner/roster/roster-add)
- [planner roster get](https://pnp.github.io/cli-microsoft365/cmd/planner/roster/roster-get)
- [planner roster remove](https://pnp.github.io/cli-microsoft365/cmd/planner/roster/roster-remove)
- [planner roster member add](https://pnp.github.io/cli-microsoft365/cmd/planner/roster/roster-member-add)
- [planner roster member list](https://pnp.github.io/cli-microsoft365/cmd/planner/roster/roster-member-list)
- [planner roster member remove](https://pnp.github.io/cli-microsoft365/cmd/planner/roster/roster-member-remove)


## Added new Compliance Commands

The last few releases we introduced a lot of new commands around managing and applying Microsoft 365 Purview retention labels. This release we're expanding on that. We've introduced new commands for managing event-based retention labels and for accessing the audit log within your tenant.

To list all SharePoint audit logs for the past 24 hours, run:

```sh
m365 purview auditlog list --contentType SharePoint
```

To create a retention event type, run:

```sh
m365 purview retentioneventtype add --displayName 'Contract Expiry' --description 'A retention event type to start a retention period based on the date that a contract expired.'
```

To list all retention event types, run:

```sh
m365 purview retentioneventtype list
```

To list all retention events, run:

```sh
m365 purview retentionevent list
```

Here's a list of all new Compliance commands for this release:

- [purview auditlog list](https://pnp.github.io/cli-microsoft365/cmd/purview/auditlog/auditlog-list)
- [purview retentionevent get](https://pnp.github.io/cli-microsoft365/cmd/purview/retentionevent/retentionevent-get)
- [purview retentionevent list](https://pnp.github.io/cli-microsoft365/cmd/purview/retentionevent/retentionevent-list)
- [purview retentionevent remove](https://pnp.github.io/cli-microsoft365/cmd/purview/retentionevent/retentionevent-remove)
- [purview retentioneventtype add](https://pnp.github.io/cli-microsoft365/cmd/purview/retentioneventtype/retentioneventtype-add)
- [purview retentioneventtype get](https://pnp.github.io/cli-microsoft365/cmd/purview/retentioneventtype/retentioneventtype-get)
- [purview retentioneventtype list](https://pnp.github.io/cli-microsoft365/cmd/purview/retentioneventtype/retentioneventtype-list)
- [purview retentioneventtype remove](https://pnp.github.io/cli-microsoft365/cmd/purview/retentioneventtype/retentioneventtype-remove)
- [purview retentioneventtype set](https://pnp.github.io/cli-microsoft365/cmd/purview/retentioneventtype/retentioneventtype-set)

## Added new SharePoint commands

The CLI for Microsoft 365 has a lot of commands for managing and accessing SharePoint. In this release, more commands were introduced that make managing SharePoint easier. The main subjects are Application Customizers, Sharing Links and Navigation:

To add an application customizer to a SharePoint site, run:

```sh
m365 spo applicationcustomizer add --title 'Some customizer' --clientSideComponentId 799883f5-7962-4384-a10a-105adaec6ffc --webUrl https://contoso.sharepoint.com/sites/sales
```

To remove all sharing links from a file, run:

```sh
m365 spo file sharinglink clear --webUrl https://contoso.sharepoint.com/sites/demo --fileUrl '/sites/demo/Shared Documents/document.docx'
```

To update the title and intended audience of a navigation node, run:

```sh
m365 spo navigation node set --webUrl https://contoso.sharepoint.com/sites/marketing --id 2209 --title "Pictures" --audienceIds "61f78c73-f71a-471e-a3b9-15daa936e200,9524e6b4-e663-44fe-b179-210c963e37e7,c42b8756-494d-4141-a575-45f01320e26a"
```

Here's a list of all new SharePoint commands for this release:

- [spo tenant applicationcustomizer add](https://pnp.github.io/cli-microsoft365/cmd/spo/tenant/tenant-applicationcustomizer-add)
- [spo applicationcustomizer add](https://pnp.github.io/cli-microsoft365/cmd/spo/applicationcustomizer/applicationcustomizer-add)
- [spo file sharinglink clear](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-sharinglink-clear)
- [spo file sharinglink set](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-sharinglink-set)
- [spo navigation node get](https://pnp.github.io/cli-microsoft365/cmd/spo/navigation/navigation-node-get)
- [spo navigation node set](https://pnp.github.io/cli-microsoft365/cmd/spo/navigation/navigation-node-set)

## Making SharePoint Framework Development easier

Granting permissions in SharePoint Framework projects can be a bother. Developers need to deploy the package before the permissions are visible on the API access page of the SharePoint admin dashboard. This process takes a lot of small steps. In this release we introduce a new command to make this process easier. You can now grant consent to all API permissions that are included in your SPFx project. No need to execute multiple gulp commands. No need to leave VS Code. 

You can now simply run:

```sh 
m365 spfx project permissions grant
```

## Another step in implementing CLI for Microsoft 365 context

In our previous releases, we have taken the first steps to creating a CLI context. This allows you to save time by storing default values for options that you often use. For example, if you're working with a specific site collection, you can save the URL of the site collection in the context, and CLI for Microsoft 365 will automatically use it when you run a command that requires the URL of the site collection. This way, you don't have to specify the URL of the site collection every time you run a command. In this release, we created an extra command to work with the CLI context. Note this is still a work in progress. We allow managing context settings but don't apply them to commands just yet.

To list all options added to the context, run:

```sh
m365 context option list
```

## Listing Power Automate flow runs

Aside from new commands, we implemented a ton of enhancements and bugfixes. One we want to call out here is the command to list flow runs. It's now possible to list flow runs by status and within a time range.

To get a list of all currently running instances of a Power Automate flow, run:

```sh
m365 flow run list --environmentName Default-d87a7535-dd31-4437-bfe1-95340acd55c5 --flowName 5923cb07-ce1a-4a5c-ab81-257ce820109a --status Running
```    

To list runs of the specified Microsoft Flow between a specific time range, run:

```sh
m365 flow run list --environmentName Default-d87a7535-dd31-4437-bfe1-95340acd55c5 --flowName 5923cb07-ce1a-4a5c-ab81-257ce820109a --triggerStartTime 2023-01-21T18:19:00Z --triggerEndTime 2023-01-22T00:00:00Z
```    

## What's next

Here are some things that we are currently working on.

### Power Platform 

We're currently busy implementing a new commands for managing the owners of a Power Automate flow. Things like listing, adding and removing owners.

### Microsoft 365 Purview

We're currently busy implementing the last of a series of commands around retention labels. Aside from that, work is also being done to build new commands to manage threat assessments and sensitivity labels. 

### Manage SPFx extensions

In the upcoming weeks, we'll keep working to create more commands to add, set, list, and remove SPFx extensions such as ListView Command Sets or Application Customizers.

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Patrick Lamber](https://github.com/plamber)
- [Rabia Williams](https://github.com/rabwill)
- [Reshmee Auckloo](https://github.com/reshmee011)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

Thank you all for the time you chose to spend on CLI for Microsoft 365 and for your help to advance it!

### High fives

CLI for Microsoft 365 wouldn't be where it is today if it weren't for our users who provide us with feedback. High fives to the following people who took the time to share their feedback and ideas for improvement with us (in alphabetical order):

- [Carl Henrik Lunde](https://github.com/chlunde)
- [hsicilia](https://github.com/hsicilia)
- [Pol Van Dingenen](https://github.com/Cyhexy)
- [Trygvi Zachariassen Laksafoss](https://github.com/TrygviZL)

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
