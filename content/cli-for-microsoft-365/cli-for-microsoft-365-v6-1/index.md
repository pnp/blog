---
title: CLI for Microsoft 365 v6.1
date: 2022-12-31T06:00:00.000Z
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

We've just published a new minor version of the CLI for Microsoft 365 with new commands for working with and managing Microsoft 365 and SharePoint Framework projects on any platform.

## Manage Microsoft 365 and SharePoint Framework projects on any platform

CLI for Microsoft 365 is a cross-platform CLI that allows you to manage various configuration settings of Microsoft 365 and SharePoint Framework projects no matter which operating system or shell you use.

While building solutions for Microsoft 365 expands beyond the Windows operating system, managing many platform settings is possible only through PowerShell on Windows. As more and more users work on non-Windows machines, it's inconvenient for them to use a Windows virtual machine to configure their tenants. With the CLI for Microsoft 365, you can configure your tenant no matter which operating system you use. Additionally, using CLI for Microsoft 365, you can manage your SharePoint Framework projects.

## New version of CLI for Microsoft 365 – v6.1

Following our monthly release cadence, we've released a new version of the CLI for Microsoft 365 with some new capabilities. The month of December was no exception. We had a ton of improvements and new commands. Here are a few of the most noteworthy additions.

> For the complete list of what's new and changed, see the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v610).

### Added support for upgrading SPFx projects to v1.16.1

SharePoint Framework (SPFx) allows you to build solutions for Microsoft Teams, Microsoft Viva, Outlook, the Microsoft 365 app and SharePoint. v1.16.1 of SPFx was released shortly after v1.16.0 introducing a few minor fixes and improvements around SharePoint Framework.

To benefit from these, upgrade your existing projects using the CLI for Microsoft 365.

> Important: CLI for Microsoft 365 won't upgrade your project. Instead, it will provide you with a report that you can use to upgrade your project yourself.

To upgrade your SPFx projects to v1.16.1, run the following command:

```sh
m365 spfx project upgrade --toVersion 1.16.1 --output md > report.md
```

You can also request a more interactive report built on top of the [VSCode CodeTour extension](https://marketplace.visualstudio.com/items?itemName=vsls-contrib.codetour), by running:

```sh
m365 spfx project upgrade --toVersion 1.16.1 --output tour
```

We've also updated other SPFx-related commands to support SPFx v1.16.1.

### First steps towards implementing CLI for Microsoft 365 context

CLI context allows you to save time by storing default values for options that you often use. For example, if you're working with a specific site collection, you can save the URL of the site collection in the context, and CLI for Microsoft 365 will automatically use it when you run a command that requires the URL of the site collection. This way, you don't have to specify the URL of the site collection every time you run a command. Currently, we added support that allows you to add and remove context.

To create a new context file to store properties run:

```sh
m365 context init
```

To remove the context file run: 

```sh
m365 context remove
``` 

For more information check [related issue](https://github.com/pnp/cli-microsoft365/issues/3896).

### More Power Platform commands

We continue to extend the support for managing Power Platform. In this release, we added commands for managing Power Platform Dataverse tables rows, publishers, and chatbot.

To get a chatbot with a given id in the default environment you may run:

```sh
m365 pp chatbot get --environment "Default-2ca3eaa5-140f-4175-8261-3272edf9f339" --id 9be05428-a279-4aa3-ae54-8449c2cc2722
```

To remove the chatbot with the given ID in the default environment and prompt for confirmation simply run:

```sh
m365 pp chatbot remove --environment "Default-2ca3eaa5-140f-4175-8261-3272edf9f339" --id 9be05428-a279-4aa3-ae54-8449c2cc2722
```

To list all rows for the Appointment table run:

```sh
m365 pp dataverse table row list --environment  "Default-2ca3eaa5-140f-4175-8261-3272edf9f339" --tableName "Appointment"
```

To remove a row for the Appointment table with confirmation prompt:

```sh
m365 pp dataverse table row remove --environment  "Default-2ca3eaa5-140f-4175-8261-3272edf9f339" --tableName "Appointment" --id 3
```

To add a publisher in the environment using the name and the prefix simply run:

```sh
m365 pp solution publisher add --environment Default-d87a7535-dd31-4437-bfe1-95340acd55c5 --name Contoso --displayName Contoso --prefix new --choiceValuePrefix 10000
```

To learn more about managing Power Platform see the [m365 pp chatbot get](https://pnp.github.io/cli-microsoft365/cmd/pp/chatbot/chatbot-get/).

### The work continues on retention labels

In this release, we added new commands which allow you to manage retention labels as well as possibility to list the available (published) retention labels on a specific SharePoint site and the possibility to clear the retention label on a list item.

To get a list of retention labels run: 

```sh
m365 purview retentionlabel list
```

To delete a retention label by id, execute:

```sh
m365 purview retentionlabel remove --id 'e554d69c-0992-4f9b-8a66-fca3c4d9c531'
```

To update a retention label, so that it retains documents as records and deletes them after one year, run:

```sh
m365 purview retentionlabel set --id c37d695e-d581-4ae9-82a0-9364eba4291e --behaviorDuringRetentionPeriod retainAsRecord --actionAfterRetentionPeriod delete --retentionDuration 365
```

To get a list of retention labels for the Sales site, run:

```sh
m365 spo web retentionlabel list --webUrl 'https://contoso.sharepoint.com/sites/sales'
```

To remove the retention label from a list item in a given site based on the list id, execute:

```sh
m365 spo listitem retentionlabel remove --webUrl https://contoso.sharepoint.com/sites/project-x --listId 0cd891ef-afce-4e55-b836-fce03286cccf --listItemId 1
```

To learn more about managing retention labels commands, see the [m365 purview retentionlabel list](https://pnp.github.io/cli-microsoft365/cmd/purview/retentionlabel/retentionlabel-list/).

### Introduce markdown output

We heard your feedback and we are happy to announce that we added support for markdown output for CLI commands. This functionality is perfect for documentation purposes. The Markdown output can be used with each command using `--output md` option. Try it out and let us know what you think.

### New way of handling booleans options

To simplify using commands with boolean options we refactored the way we handle them. Now you can use the following values to specify boolean options: 

For true you may use: `1`, `yes`, `true`, `on`, and for false: `0`, `no`, `false`, `off`

### Telemetry information

Telemetry in CLI for Microsoft 365 is used by default in order to track the usage within the project. It's worth noting that we don't collect any personal information. Instead, CLI for Microsoft 365 collects which command you are using and which command options, this gives us the information needed to better understand how the CLI for Microsoft 365 is being used and where we can make improvements. 

To find out more please check [Telemetry general info](https://pnp.github.io/cli-microsoft365/about/telemetry/).

### Easier way in getting your Power Platform default environment

Till now CLI for Microsoft 365 didn't provide an easy way to get your default Power Platform environment. This has changed thanks to a minor enhancement done in the `m365 pp environment get` command. If you don't specify the `name` option the command will now return the default environment.

To get the default Power Platform environment, run:

```sh
m365 pp environment get
```

To learn more about see the [m365 pp environment get](https://pnp.github.io/cli-microsoft365/cmd/pp/environment/environment-get/).

### What else

These features are just the tip of the iceberg of what we've shipped in this version. The code base of the CLI for Microsoft 365 has received a huge update as well, making it easier for maintainers and contributors to create new functionality. And so many other fixes.
Check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v610) for the complete list of what's new and improved.

### What's next

Here are some things that we are currently working on.

#### Manage application customizers and command set extensions

To some extent, CLI for Microsoft 365 already supports managing application customizers and command set extensions. To make this even easier we are currently working on ways to improve the experience with additional commands and adding support to manage tenant-wide extensions. If you are interested to read more about what we are planning, see the [related issue](https://github.com/pnp/cli-microsoft365/issues/4219).

#### Manage retention labels

An important part of content management is applying retention labels to your content. Retention labels define how content should be managed and which policies apply to it.

To help you automate working with retention labels, we're working on adding a set of [related commands](https://github.com/pnp/cli-microsoft365/issues/4145). We'd appreciate your feedback if this is an area you're working with.

#### Use context information to simplify using CLI's commands

If you use the CLI a lot, you might find it tedious to have to repeat some options like the URL of the site or a list you want to work with.

To help you save time, we're working on adding the concept of context to CLI for Microsoft 365. Using the context, you will be able to store in a file default values for specific options. When you run a command that has a context value defined, and you haven't specified the option explicitly yourself, CLI for Microsoft 365 will automatically use the value from the context saving you some work and typing! For more information about what we've got planned, see the [related issue](https://github.com/pnp/cli-microsoft365/issues/3896).

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Chinu Anand](https://github.com/chinu-anand)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Patrick Lamber](https://github.com/plamber)
- [Rabia Williams](https://github.com/rabwill)
- [Stijn Haerkens](https://github.com/stijnhaerkenss)
- [Taaqif Peck](https://github.com/Taaqif)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### New contributors

A warm welcome to this month's new contributors! (in alphabetical order):

- [Chinu Anand](https://github.com/chinu-anand)

Thank you all for the time you chose to spend on CLI for Microsoft 365 and for your help to advance it!

### High fives

CLI for Microsoft 365 wouldn't be where it is today if it weren't for our users who provide us with feedback. High fives to the following people who took the time to share their feedback and ideas for improvement with us (in alphabetical order):

- [dojcsakj](https://github.com/dojcsakj)
- [JJFranko](https://github.com/JJFranko)
- [Jussi Palo](https://github.com/jpalo)

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
