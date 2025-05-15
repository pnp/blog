---
title: CLI for Microsoft 365 v10.3
date: 2025-01-31T01:00:00.000Z
author: Martin Lingstuyl
githubname: martinlingstuyl
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Entra ID
  - SharePoint
  - SharePoint Embedded
  - SharePoint Premium
type: regular
---

🎺 Shout it from the rooftops! We've just published the first minor version in 2025 of the CLI for Microsoft 365. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces 14 (!!) new commands that will enhance the quality of your Microsoft 365 experience.

> Explore the [release notes](https://aka.ms/cli-m365/notes) for a neat overview of all the exciting features and improvements. 

## What's New

The year got off to a good start with a whopping 14 new commands in this release!

### SharePoint Embedded

We've added yet another command to manage SharePoint Embedded containers. 

To activate a specific container run:

```sh
m365 spe container activate --id "b!ISJs1WRro0y0EWgkUYcktDa0mE8zSlFEqFzqRn70Zwp1CEtDEBZgQICPkRbil_5Z"
```

For more information, check the following resources:

- [m365 spe container activate](https://pnp.github.io/cli-microsoft365/cmd/spe/container/container-activate/)

### SharePoint

In this release, we've added four new commands to manage default column values for a specific document library or a folder within that library. This feature of SharePoint has been around for quite a while, and our contributors finally found time (and reason) to add it to the CLI!

To update the default value of a field in a library, run:

```sh
m365 spo list defaultvalue set --webUrl https://contoso.sharepoint.com/sites/Marketing --listTitle Logos --fieldName Company --fieldValue Contoso
```

To get a list of the default values in a library, run:

```sh
m365 spo list defaultvalue list --webUrl https://contoso.sharepoint.com/sites/marketing --listTitle "Project Documents"
```

To remove a default column value in a library, run:

```sh
m365 spo list defaultvalue remove --webUrl https://contoso.sharepoint.com/sites/Marketing --listTitle Logos --fieldName Company
```

To clear default column values in a library, run:

```sh
m365 spo list defaultvalue clear --webUrl https://contoso.sharepoint.com/sites/Marketing --listTitle Logos
```

For more information, check the following resources:

- [m365 spo list defaultvalue clear](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-defaultvalue-clear)
- [m365 spo list defaultvalue list](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-defaultvalue-list)
- [m365 spo list defaultvalue remove](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-defaultvalue-remove)
- [m365 spo list defaultvalue set](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-defaultvalue-set)

### Microsoft Entra ID

In this release, we added four new commands for working with Microsoft Entra ID roles. You can now add and update custom role definitions. For working with custom role definitions you'll need to know what resources actions are available. Retrieving these resource actions, also called role permissions, can be done by using the new command to list role permissions. And lastly, we've added a new command to be able to deactivate role assignments in Privileged Identity Management (PIM).

To get a list of role permissions or resource actions in the Microsoft directory, run:

```sh
m365 entra rolepermission list --resourceNamespace microsoft.directory
```

To create a custom Microsoft Entra ID role definition, run:

```sh
m365 entra roledefinition add --displayName 'Application Remover' --description 'Allows to remove any Entra ID application' --allowedResourceActions 'microsoft.directory/applications/delete'
```

To update an existing role definition:

```sh
m365 entra roledefinition set --id fadbc488-151d-4431-9143-6abbffae759f --newDisplayName 'Application Remover' --description 'Allows to remove any Entra ID application' --allowedResourceActions 'microsoft.directory/applications/delete'
```

To deactivate a PIM role assignment for the current user, run:

```sh
m365 entra pim role assignment remove --roleDefinitionName 'SharePoint Administrator'
```

For more information, check the following resources:

- [m365 entra pim role assignment remove](https://pnp.github.io/cli-microsoft365/cmd/entra/pim/pim-role-assignment-remove/)
- [m365 entra roledefinition add](https://pnp.github.io/cli-microsoft365/cmd/entra/roledefinition/roledefinition-add/)
- [m365 entra roledefinition set](https://pnp.github.io/cli-microsoft365/cmd/entra/roledefinition/roledefinition-set/)
- [m365 entra rolepermission list](https://pnp.github.io/cli-microsoft365/cmd/entra/rolepermission/rolepermission-list/)

### Outlook

We've also added a new command to update Outlook mailbox settings.

To update the date, time format and time zone of the signed-in user, run:

```sh
m365 outlook mailbox settings set --dateFormat 'dd.MM.yyyy' --timeFormat 'H:mm' --timeZone 'Central Europe Standard Time' --language 'en-US'
```

For more information, check the following resources:

- [m365 outlook mailbox settings set](https://pnp.github.io/cli-microsoft365/cmd/outlook/mailbox/mailbox-settings-set)

### Exchange

In this release, we've added a command that allows you to grant granular Exchange permissions to applications that need to access data in Exchange Online. 

The following command will add 'Application Contacts.ReadWrite' permissions to the Marketing group for the ContactsSyncApp:

```sh
m365 exo approleassignment add --roleDefinitionName 'Application Contacts.ReadWrite' --principalName 'ContactsSyncApp' --scope group --groupName 'Marketing'
```

For more information, check the following resources:

- [m365 exo approleassignment add](https://pnp.github.io/cli-microsoft365/cmd/exo/approleassignment/approleassignment-add/)

### Power Platform

Retrieving the details for a power pages website can now be done using our brand new command!

To get the Demo Power Pages website by name in the given environment, run:

```sh
m365 pp website get --name Demo --environmentName Default-d87a7535-dd31-4437-bfe1-95340acd55c5 
```

For more information, check the following resources:

- [m365 pp website get](https://pnp.github.io/cli-microsoft365/cmd/pp/website/website-get/)

### Manage pronouns settings for an organization

We also added a new command that allows you to update pronouns settings for an organization.

To enable pronouns settings for your organization, use:

```sh
m365 tenant people pronouns set --enabled true
```

For more information check the following resources:

- [m365 tenant people pronouns set](https://pnp.github.io/cli-microsoft365/cmd/tenant/people/people-pronouns-set/)

## What's changed

This release also brings several enhancements and bug fixes to elevate the overall CLI experience. For instance, we've enhanced some SharePoint role assignment commands with new options to support Microsoft Entra Groups.

## Upcoming Changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 80 issues that are actively being developed and 103 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Nishkalank Bezawada](https://github.com/NishkalankBezawada)
- [Reshmee Auckloo](https://github.com/reshmee011)
- [Shantha Kumar T](https://github.com/ktskumar)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Stefan Bauer](https://github.com/StfBauer)
- [Tobias Maestrini](https://github.com/tmaestrini)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

## Get Started Today!

Experience the power of CLI for Microsoft 365 by getting the latest release from npm:

```bash
npm i -g @pnp/cli-microsoft365
```

Alternatively, you can access the latest release from Docker:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

## Need More Information?

For additional guidance on getting started or to explore detailed information about commands, architecture, or the project itself, visit [aka.ms/cli-m365](https://aka.ms/cli-m365).

## Stay Connected!

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord) or [Bluesky](https://bsky.app/profile/climicrosoft365.bsky.social). Don't hesitate to connect with us. Your input plays a vital role in shaping the future of CLI for Microsoft 365.
