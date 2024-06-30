---
title: CLI for Microsoft 365 v7.9
date: 2024-05-31T02:00:00.000Z
author: Adam Wójcik
githubname: Adam-it
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Microsoft Entra ID
  - Search
  - Viva Engage
  - SharePoint Framework
  - SharePoint
type: regular
---

We have just published a new minor version of CLI for Microsoft 365. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces several new commands that will enhance the quality of your Microsoft 365 experience.

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover an array of exciting features and improvements that will revolutionize your Microsoft 365 journey.

## What's new

### New search command

Nowadays searching for the right information is a fundamental action that many times is an initial point to flows, scripts, or our day-to-day tasks. That is why we introduced a new `m365 search` command that is at the very root of our command hierarchy. It leverages Mircosoft Graph search capabilities to retrieve information about almost any Microsoft 365 area.

To search for all sites you may simply run:

```sh
m365 search --scopes 'site' --queryText 'site:\"https://contoso-my.sharepoint.com/personal/*\"'
```

To query list items and sites that contain the string "accountt" and request a spelling modification for the query, just use:

```sh
m365 search --scopes 'listItem, site' --queryText 'accountt' --enableSpellingSuggestion --enableSpellingModification
```

To search for file report.xlsl in a specific folder of user's personal OneDrive you may run the following:

```sh
m365 search --scopes 'driveItem' --queryText 'filename:report.xlsl AND path:\"https://contoso-my.sharepoint.com/personal/john.doe_contoso_com/Documents/Reports/2024\"'
```

For more information, check the following resources:
- [m365 search](https://pnp.github.io/cli-microsoft365/cmd/search/)

### New Viva Engage command

We took the first steps in introducing commands that will allow you to manage your Viva Engage communities. We added a `get` command to retrieve details about a specific community.

To get a specific community by ID, simply run:

```sh
m365 viva engage community get --id eyJfdHlwZSI6Ikdyb3VwIiwiaWQiOiI0Mjg1NzkwNjE3NyJ9
```

For more information, check the following resources:
- [m365 viva engage community get](https://pnp.github.io/cli-microsoft365/cmd/viva/engage/engage-community-get/)

### New SharePoint command

Do you know what's better than removing list items from a SharePoint list? Removing them in a batch! In this release, we added a command that will help you be more effective in exactly that.

To remove a list of IDs from a list with a csv run:

```sh
m365 spo listitem batch remove --filePath ./IDlist.csv --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List"
```

For more information, check the following resources:
- [m365 spo listitem batch remove](https://pnp.github.io/cli-microsoft365/cmd/spo/listitem/listitem-batch-remove/)

### New Microsoft Entra ID group commands

In this release, we introduced new Entra ID commands that allow you to update the roles of single or multiple users and a new command that retrieves all groups of which the user is a member of. Let's check them out in action.

To update a single user specified by UPN to an owner of a group, simply run:

```sh
m365 entra group user set --groupDisplayName Developers --userNames john.doe@contoso.com --role Owner
```

To update multiple users specified by UPN to owners of a group, you may run the following:

```sh
m365 entra group user set --groupId a03c0c35-ef9a-419b-8cab-f89e0a8d2d2a --userNames "john.doe@contoso.com,adele.vance@contoso.com" --role Owner
```

To retrieve groups where the currently logged-in user is a member of, just run the following:

```sh
m365 entra user groupmembership list --userName '@meUserName'
```

For more information check the following resources:
- [m365 entra group user set](https://pnp.github.io/cli-microsoft365/cmd/entra/group/group-user-set/)
- [m365 entra user groupmembership list](https://pnp.github.io/cli-microsoft365/cmd/entra/user/user-groupmembership-list/)

## What's changed

Besides all these new commands, we've also made some changes to some existing commands. A few bugs have been fixed and the codebase has been polished. Changes includes the enhancement in [SharePoint Framework commands](#sharepoint-framework-commands), [Outlook commands](#outlook-commands) and [Power Automate commands](#power-automate-commands)

### SharePoint Framework commands

We have extended the SharePoint Framework commands so that it supports the latest version of the SharePoint Framework which is `v1.19.0`. We've also updated the `spfx doctor` command to validate and suggest the latest version of gulp-cli. For more information on the commands, refer to the documentation:

- [m365 spfx project upgrade](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade)
- [m365 spfx doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor)
- [m365 spfx project doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-doctor)

### Outlook commands

Thanks to the latest update done to the `outlook message list` command, you may now retrieve messages within a specific time frame.
Check out the documentation to find out more:

- [m365 outlook message list](https://pnp.github.io/cli-microsoft365/cmd/outlook/message/message-list)

### Power Automate commands

We have extended the `flow run list` command with an additional option that now allows you to retrieve details about the flow trigger.
Review the command documentation for more details:

- [m365 flow run list](https://pnp.github.io/cli-microsoft365/cmd/flow/run/run-list/)

## Upcoming changes

Curious about what lies ahead? We are excited to share some of our ongoing projects and initiatives. We have some commands pertaining to [Microsoft Entra Privileged Identity Management (PIM)](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-configure) which are in the pipeline and will be released in the upcoming versions.

Right now, there are over 50 opened PRs with new awesome features that will soon be added to CLI for Microsoft 365, and [58 issues that are up for grabs](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22). We're working hard to bring you even more exciting features and improvements in the next release.

But we don't stop there. We value your input and ideas. If you have any suggestions for new commands, don't hesitate to share them with us. Create a [new issue](https://github.com/pnp/cli-microsoft365/issues/new/choose) on our GitHub Issues list or join our vibrant [community Discord server](https://aka.ms/cli-m365/discord) to engage in discussions.

Sharing is Caring!

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Reshmee Auckloo](https://github.com/reshmee011)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Smita Nachan](https://github.com/SmitaNachan)

### High fives

We would like to give a big shoutout and high fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to provide us with their insights:

- [Alexander Kislukhin](https://github.com/liquidcarbon)
- [Luiz (Rick) Costa](https://github.com/lhdeveloper)
- [Martin Löper](https://github.com/MartinLoeper)
- [maheshpalle](https://github.com/maheshpalle)

## Get started today!

Experience the power of the CLI for Microsoft 365 by getting the latest release from npm:

```bash
npm i -g @pnp/cli-microsoft365
```

Alternatively, you can access the latest release from Docker:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

## Need more information?

For additional guidance on getting started or to explore detailed information about commands, architecture, or the project itself, visit [aka.ms/cli-m365](https://aka.ms/cli-m365).

## Stay connected!

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord), or [X](https://x.com/climicrosoft365). Don't hesitate to connect with us. Your input plays a vital role in shaping the future of CLI for Microsoft 365.
