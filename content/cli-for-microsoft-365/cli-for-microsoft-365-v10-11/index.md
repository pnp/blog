---
title: CLI for Microsoft 365 v10.11
date: 2025-08-31T01:00:00.000Z
author: Adam Wójcik
githubname: adam-it
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - SharePoint
  - SharePoint Embedded
  - Microsoft Teams
  - Viva Engage
type: popular
---

The CLI for Microsoft 365 is back with a fresh minor release! We’ve just launched a new version of [CLI for Microsoft 365](https://aka.ms/cli-m365), a versatile cross-platform command-line tool for managing your Microsoft 365 tenant and SharePoint Framework projects.

> Explore the [release notes](https://aka.ms/cli-m365/notes) for a neat overview of all the exciting features and improvements. 

## What's New

### SharePoint Embedded

We are continuously building and improving SharePoint Embedded management commands in CLI for Microsoft 365. This time, we managed to add a new command that will allow you to restore a deleted container.

You may restore a container by ID:

```sh
m365 spe container recyclebinitem restore --id "b!ISJs1WRro0y0EWgkUYcktDa0mE8zSlFEqFzqRn70Zwp1CEtDEBZgQICPkRbil_5Z"
```

Or using something more 'human'-friendly, using its name and container type name.

```sh
m365 spe container recyclebinitem restore --containerTypeName "My container type name" --name "Invoices"
```

For more information, check the following resource:

- [spe container recyclebinitem restore](https://pnp.github.io/cli-microsoft365/cmd/spe/container/container-recyclebinitem-restore/)

### Viva Engage

This release also brings two new commands to the Viva Engage area. Now you may list all Viva Engage roles as well as list all users assigned to a specific role.

To list all Viva Engage roles, run:

```sh
m365 viva engage role list
```

And to get all users assigned to a Viva Engage role specified by name, run the following:

```sh
m365 viva engage role member list --roleName 'Verified Admin'
```

For more information, check the following resources:

- [viva engage role member list](https://pnp.github.io/cli-microsoft365/cmd/viva/engage/engage-role-list/)
- [viva engage role list](https://pnp.github.io/cli-microsoft365/cmd/viva/engage/engage-role-list/)

### Microsoft Teams

This release brings a fresh new command allowing you to list all Teams calls within your tenant. Retrieving call records has never been easier.

To get all call records from the past 30 days, simply run:

```sh
m365 teams callrecord list
```

Or to get all call records where a specific user participated, run:

```sh
m365 teams callrecord list --userName "john.doe@contoso.com"
```

It is also possible to get all call records within a specific timeframe.

```sh
m365 teams callrecord list --startDateTime "2025-05-01T00:00:00Z" --endDateTime "2025-05-14T00:00:00Z"
```

For more information, check the following resource:

- [teams callrecord list](https://pnp.github.io/cli-microsoft365/cmd/teams/callrecord/callrecord-list/)

### CLI

In this release, we also added a new command allowing you to create a new app registration to use for the CLI for Microsoft 365. This may become super handy if you want to quickly create different app registrations that may be used by CLI for Microsoft 365 to connect to your Microsoft 365 tenant. The command allows you to decide if you want to create an app reg with a `minimal` set of scopes or `all` scopes, allowing you to use every CLI for Microsoft 365 command. It is also possible to pass your own list of scopes, which will be applied to the newly created app reg.

To create a new app registration to use for CLI for Microsoft 365, run:

```sh
m365 cli app add
```

In order to create a new app registration with all permission scopes and a custom name, run the following:

```sh
m365 cli app add --name "Contoso CLI app" --scopes all
```

Lastly, if you want to create a new app registration with self-defined scopes, just execute:

```sh
m365 cli app add --scopes "https://graph.microsoft.com/User.Read,https://graph.microsoft.com/Group.Read.All"
```

For more information, check the following resource:

- [cli app add](https://pnp.github.io/cli-microsoft365/cmd/cli/app/app-add/)

## What's changed

This release also brings some other great changes. Aside from many improvements in the codebase and bug fixes to elevate the overall CLI experience, there are several important updates we'd like to highlight.

### Added support for SPFx v1.22.0-beta.1 

To help you keep up to date with the latest improvements in SharePoint Framework, we added support for the first beta version of SPFx v1.22.0 to all our SPFx commands. Now you create upgrade guidance for your SPFx project to align with what was changed in the latest version of SharePoint Framework, as well as validate the dependencies of your project. Last but not least, you may validate your local environment setup to make sure you have everything ready for the latest SPFx beta.

### Nesting Entra ID groups

In this release, it's also worth mentioning that we updated the [entra group member add](https://pnp.github.io/cli-microsoft365/cmd/entra/group/group-member-add/), allowing you to add subgroups as members of an Entra group.

For example, you may now add multiple subgroups specified by name as members of a group specified by ID, by running:

```sh
m365 entra group member add --groupId a03c0c35-ef9a-419b-8cab-f89e0a8d2d2a --subgroupNames "Developers,Human Resources" --role Member
```

### New guidance - Automate your CI/CD workflow using CLI for Microsoft 365 in Azure DevOps Pipelines

In this release, we also improved our docs by adding new guidance showing how you may use CLI for Microsoft 365 in Azure DevOps Pipelines. Interested? Check out the [guide](https://pnp.github.io/cli-microsoft365/user-guide/azuredevops-pipeline) for more details.

### Minimal-permissions documentation

We're introducing a "Permissions" section on each command's documentation page. This section outlines the minimum required permissions an account or app needs to run the command with full functionality. Currently, all `planner` command docs are updated with this new section. Updating all pages will take some time, so feel free to contribute if you'd like to help!

## Upcoming Changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 56 issues that are actively being developed and 113 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Arjun Menon](https://github.com/arjunumenon)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)
- [Nirav Raval](https://github.com/nirav-raval)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
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
