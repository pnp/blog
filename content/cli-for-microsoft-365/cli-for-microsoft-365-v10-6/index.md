---
title: CLI for Microsoft 365 v10.6
date: 2025-04-30T01:00:00.000Z
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
  - Microsoft Graph
type: popular
---

The CLI for Microsoft 365 strikes again! We've just published a new minor version of the CLI for Microsoft 365. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces new commands that will enhance the quality of your Microsoft 365 experience.

> Explore the [release notes](https://aka.ms/cli-m365/notes) for a neat overview of all the exciting features and improvements. 

## What's New

### Microsoft Graph

In this release, we added four new commands to manage open extensions for Entra ID through the Microsoft Graph. Open extensions are similar to directory extensions and schema extensions: they are a way to add additional properties to resources in Microsoft 365. There's a quite broad array of resources you can enrich with properties using open extensions. The CLI for Microsoft 365 currently supports the following: users, groups, devices, and organizations. Open extensions are very flexible and support saving untyped data. Whether you use directory extensions, open extensions, or schema extensions depends on the use case and the features Microsoft made available. [You can read more here.](https://learn.microsoft.com/graph/extensibility-overview) Whatever you'll be using, the CLI for Microsoft 365 supports you either way, managing extensions on data in Microsoft 365. 

To add some data to a specific Entra user using open extensions, run:

```sh
m365 graph openextension add --resourceId adelev@contoso.com --resourceType user --name 'com.contoso.roamingSettings' --theme dark --color red --language English
```

To retrieve a specific open extension for a user, run:

```sh
m365 graph openextension get --resourceId john.doe@contoso.com --name 'com.contoso.roamingSettings' --resourceType user
```

To list all open extensions for a specific user, run:

```sh
m365 graph openextension list --resourceId john.doe@contoso.com --resourceType user
```

To remove the open extension, run:

```sh
m365 graph openextension remove --resourceId john.doe@contoso.com --name 'com.contoso.roamingSettings' --resourceType user --force
```

For more information, check the following resources:

- [graph openextension add](https://pnp.github.io/cli-microsoft365/cmd/graph/openextension/openextension-add/)
- [graph openextension get](https://pnp.github.io/cli-microsoft365/cmd/graph/openextension/openextension-get/)
- [graph openextension list](https://pnp.github.io/cli-microsoft365/cmd/graph/openextension/openextension-list/)
- [graph openextension remove](https://pnp.github.io/cli-microsoft365/cmd/graph/openextension/openextension-remove/)


### Microsoft Entra ID

In this release, we introduced a new Entra ID command that allows you to remove a group member.

To remove a single group member from a specific group specified by user ID, simply run:

```sh
m365 entra group member remove --groupName Developers --userIds 098b9f52-f48c-4401-819f-29c33794c3f5 --role Member
```

For more information check the following resources:
- [m365 entra group member remove](https://pnp.github.io/cli-microsoft365/cmd/entra/group/group-member-remove/)

## What's changed

This release also brings some other great changes. Aside from many improvements in the codebase and bug fixes to elevate the overall CLI experience, there are a couple of things we'd like to highlight.

### SharePoint Framework commands

We have extended the SharePoint Framework commands so that it supports the latest version of the SharePoint Framework which is `v1.21.0`. For more information on the commands, refer to the documentation:

- [m365 spfx project upgrade](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade)
- [m365 spfx doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor)
- [m365 spfx project doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-doctor)

### Allow unknown options on additional commands in Entra ID

We have configured group, app and administrative unit commands to allow unknown options. The major benefit of this change is that it allows you to update non-default properties. Examples of that are Directory Extensions, which make it possible to extend Microsoft 365 resources with custom data. The CLI for Microsoft 365 already allows you to add and remove definitions for these directory extensions, using the `m365 graph directoryextension <verb>` commands. But now, you can also use these definitions by assigning the directory extension with values for specific Entra ID resources. It was already possible to do this for users. We've now added it for the other resources as well.   

### New sample script - Create a report on parent Power Automate flows

We've also added a new sample regarding reporting on Power Automate flows. In the low code world, executing child flows is a common practice that makes it easier to reuse functionality. However, it can also become a bit unclear what flows are tied together is this way. With this new sample it's easier to distinguish what flows are calling a specific flow using the 'Run a Child Flow' action. 

For more information check the following resource:

[Find all parent flows that invoke the specified child flow](https://pnp.github.io/cli-microsoft365/sample-scripts/flow/search-parent-flows/)

## Upcoming Changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 60 issues that are actively being developed and 104 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release.

As written earlier, one of the fields in which we want to improve is Federated Identity. Not only targeting GitHub, but also Azure DevOps. The next release will contain this feature, making it easier for people working with Azure DevOps to deploy apps and solutions to microsoft 365 without having to use certificates or secrets! We'll keep you posted.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Luiza de Melo](https://github.com/luizademelo)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [Janne Holm](https://github.com/jhholm)

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
