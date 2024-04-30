---
title: CLI for Microsoft 365 v7.7
date: 2024-04-30T06:00:00.000Z
author: Arjun Menon
githubname: arjunumenon
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Outlook
  - Purview
  - SharePoint
  - SharePoint Framework
type: popular
lastmod: 2024-04-29T06:01:46.698Z
---

We have just published a new minor version of CLI for Microsoft 365. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces several new commands that will enhance the quality of your Microsoft 365 experience.

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover an array of exciting features and improvements that will revolutionize your Microsoft 365 journey. 
 
## What's new

### New Microsoft Entra Privileged Identity Management commands

Microsoft Entra [Privileged Identity Management (PIM)](https://learn.microsoft.com/entra/id-governance/privileged-identity-management/pim-configure) is a service in Microsoft Entra ID that enables you to manage, control, and monitor access to important resources in your organization. These resources include resources in Microsoft Entra ID, Azure, and other Microsoft Online Services such as Microsoft 365 or Microsoft Intune.

This release of [CLI for Microsoft 365](https://aka.ms/cli-m365) includes the introduction of the Privileged Identity Management (PIM) commands that allow you to manage the PIM settings for users and groups in your Microsoft Entra tenant.

For requesting activation of an Entra role assignment for a **user** or **group**, run:

```sh
m365 entra pim role assignment add --roleDefinitionName 'SharePoint Administrator'
```

For retrieving list of Entra role assignments for a **user** or **group**, run:

```sh
m365 entra pim role assignment list
```

For more information check the following resources:
- [m365 entra pim role assignment add](https://pnp.github.io/cli-microsoft365/cmd/entra/pim/pim-role-assignment-add)
- [m365 entra pim role assignment list](https://pnp.github.io/cli-microsoft365/cmd/entra/pim/pim-role-assignment-list)

### New SharePoint Embedded Container Commands

[Microsoft SharePoint Embedded](https://learn.microsoft.com/en-us/sharepoint/dev/embedded/overview) is a cloud-based file and document management system suitable for use in any application. SharePoint Embedded is a new API-only solution that enables app developers to harness the power of the Microsoft 365 file and document storage platform for any app, and is suitable for enterprises building line-of-business applications and ISVs building multitenant applications.

This release of [CLI for Microsoft 365](https://aka.ms/cli-m365) includes introduction of SharePoint Embedded (SPE) container commands which will have various commands which will help you to manage your containers.

To create a new Container Type for your app, run:

```sh
m365 spe containertype add --name 'trial container' --applicationId '1b3b8660-9a44-4a7c-9c02-657f3ff5d5ac' --trial
```

For more information check the following resources:
- [m365 spe containertype add](https://pnp.github.io/cli-microsoft365/cmd/spe/containertype/containertype-add/)

### SharePoint Commands

#### ContentType Sync Commands

We have added a new command that adds a published content type from the content type hub to a site or syncs its latest changes. This command will be useful if you want to push the changes that you have done in the Content type hub to the sites where the content type is being used.

For publishing the content type or syncing the changes, run:

```sh
m365 spo contenttype sync —webUrl https://contoso.sharepoint.com/sites/sales --id 0x01007926A45D687BA842B947286090B8F67D
```

For more information, refer the documentation for [m365 spo contenttype sync](https://pnp.github.io/cli-microsoft365/cmd/spo/contenttype/contenttype-sync/)

## What's changed

Besides all these new commands, we've also made some changes to the existing commands. A few bugs have been fixed and the codebase has been polished. Changes includes the enhancement in [SharePoint Framework commands](#sharepoint-framework-commands), [SharePoint Online commands](#sharepoint-online-commands) and [many other commands](#entra-app-and-user-commands).

### SharePoint Framework Commands

We have extended the SharePoint Framework commands so that it supports the latest beta version of the SharePoint Framework which is `v1.19.0-beta.0`. For more information on the commands, refer to the documentation,

- [m365 spfx project upgrade](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade)
- [m365 spfx doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor)
- [m365 spfx project doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-doctor)

### SharePoint Online Commands

We have also fixed a few bugs for the SharePoint Online commands and added new features to the existing commands. Some of the commands which we have modified include `m365 spo page set`, `m365 spo site hubsite connect`, and `spo site hubsite disconnect`. For more information on the commands, refer to the documentation,

- [m365 spo page set](https://pnp.github.io/cli-microsoft365/cmd/spo/page/page-set)
- [m365 spo site hubsite connect](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-hubsite-connect)
- [m365 spo site hubsite disconnect](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-hubsite-disconnect)

### Entra App and User Commands

We have extended `m365 entra app add` and `m365 entra app set` so that it will also accept *allowPublicClientFlow* as an option. We have extended Entra User List command `m365 entra user list` with *type* option.

For more information on the commands, refer the documentation,

- [m365 entra app add](https://pnp.github.io/cli-microsoft365/cmd/entra/app/app-add)
- [m365 entra app set](https://pnp.github.io/cli-microsoft365/cmd/entra/app/app-set)
- [m365 entra user list](https://pnp.github.io/cli-microsoft365/cmd/entra/user/user-list)


Apart from the above changes, we have also optimized the command code base and fixed some bugs. If you are eager to go over all of the details and improvements added in this release, do not hesitate to check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v770) to find out more.

## Upcoming changes

Curious about what lies ahead? We are excited to share some of our ongoing projects and initiatives. We have some commands pertaining to [Microsoft Entra Privileged Identity Management (PIM)](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-configure) and [SharePoint Embedded (SPE)](https://learn.microsoft.com/en-us/sharepoint/dev/embedded/overview) which are in the pipeline and will be released in the upcoming versions.

Right now, there are over 49 opened PRs with new awesome features that will soon be added to CLI for Microsoft 365, and [58 issues that are up for grabs](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22). We're working hard to bring you even more exciting features and improvements in the next release. 

But we don't stop there. We value your input and ideas. If you have any suggestions for new commands, don't hesitate to share them with us. Create a [new issue](https://github.com/pnp/cli-microsoft365/issues/new/choose) on our GitHub Issues list or join our vibrant [community Discord server](https://aka.ms/cli-m365/discord) to engage in discussions.

Sharing is Caring!

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shoutout and high fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to provide us with their insights:

- [b-a0](https://github.com/b-a0)
- [Lou-i3](https://github.com/Lou-i3)
- [murati](https://github.com/murati)
- [Ofer Gal](https://github.com/Ofer-Gal)

## Get Started Today!

Experience the power of the CLI for Microsoft 365 by getting the latest release from npm:

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

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord), or [X](https://x.com/climicrosoft365). Don't hesitate to connect with us. Your input plays a vital role in shaping the future of CLI for Microsoft 365.
