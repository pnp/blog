---
title: CLI for Microsoft 365 v7.10
date: 2024-06-30T05:00:00.000Z
author: Martin Lingstuyl
githubname: martinlingstuyl
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Entra ID
  - Privileged Identity Management
  - Microsoft 365 Archive
  - Teams
  - SharePoint
type: popular
---

We have just published a new minor version of CLI for Microsoft 365. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces several new commands that will enhance the quality of your Microsoft 365 experience.

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover an array of exciting features and improvements that will revolutionize your Microsoft 365 journey. 
 
## What's new

### New Microsoft Entra Privileged Identity Management commands

Microsoft Entra [Privileged Identity Management (PIM)](https://learn.microsoft.com/entra/id-governance/privileged-identity-management/pim-configure) is a service in Microsoft Entra ID that enables you to manage, control, and monitor access to important resources in your organization. These resources include resources in Microsoft Entra ID, Azure, and other Microsoft Online Services such as Microsoft 365 or Microsoft Intune.

This release of [CLI for Microsoft 365](https://aka.ms/cli-m365) includes additional commands that allow you to get a list of requests for roles and a list of eligible roles a user can be assigned to.

To get a list of PIM requests for a **user** or **group**, run:

```sh
m365 entra pim role request list
```

To get a list of PIM requests pending approval for the current user, run:

```sh
m365 entra pim role request list --userId '@meID' --status PendingApproval
```

To get a list of eligible roles for a **user** or **group**, run:

```sh
m365 entra pim role assignment eligibility list
```

To get a list of eligible roles for the current user, run:

```sh
m365 entra pim role assignment eligibility list --userId '@meID'
```

For more information check the following resources:
- [m365 entra pim role request list](https://pnp.github.io/cli-microsoft365/cmd/entra/pim/pim-role-request-list)
- [m365 entra pim role assignment eligibility list](https://pnp.github.io/cli-microsoft365/cmd/entra/pim/pim-role-assignment-eligibility-list)

### New Microsoft Entra ID commands

We've added a new command around permission management in Entra ID. An area that the CLI for Microsoft 365 shines in. While we already supported managing delegated and application permissions on enterprise applications, managing permissions of App Registrations was not fully covered. This release brings a new command to achieve that purpose.

To remove multiple delegated API permissions from an Entra ID app, run:

```sh
m365 entra app permission remove --appId 'f1417aa3-bf0b-4cc5-a845-a0b2cf11f690' --delegatedPermissions 'https://management.azure.com/user_impersonation https://service.flow.microsoft.com/Flows.Read.All https://graph.microsoft.com/Agreement.Read.All'
```

To remove multiple delegated API permissions from an Entra ID app and revoke admin consent, run:

```sh
m365 entra app permission remove --appId 'f1417aa3-bf0b-4cc5-a845-a0b2cf11f690' --applicationPermissions 'https://graph.microsoft.com/Sites.FullControl.All https://microsoft.sharepoint-df.com/Sites.FullControl.All' --revokeAdminConsent
```

For more information check the following resources:
- [m365 entra app permission remove](https://pnp.github.io/cli-microsoft365/cmd/entra/app/app-permission-remove)

### New SharePoint commands

Microsoft 365 Archive offers cost-effective storage for inactive SharePoint sites. Many organizations want to retain inactive data, but may also wrestle with rising storage costs. Microsoft 365 Archive allows you to retain this inactive data by moving it into cold storage within SharePoint. The CLI for Microsoft 365 now has new commands to archive and unarchive sites.

To archive a SharePoint site, run:

```sh
m365 spo tenant site archive --url "https://contoso.sharepoint.com/sites/Marketing"
```

To unarchive a SharePoint site, run:

```sh
m365 spo tenant site unarchive --url "https://contoso.sharepoint.com/sites/Marketing"
```

In this release we're also adding the ability to list site administrators.

To list all admins of a SharePoint site, run:

```sh
m365 spo site admin list --siteUrl https://contoso.sharepoint.com
```

To list all admins of a SharePoint site, as a SharePoint administrator without access to the site, run:

```sh
m365 spo site admin list --siteUrl https://contoso.sharepoint.com --asAdmin
```

For more information, check the following resources:
- [m365 spo tenant site archive](https://pnp.github.io/cli-microsoft365/cmd/spo/tenant/tenant-site-archive)
- [m365 spo tenant site unarchive](https://pnp.github.io/cli-microsoft365/cmd/spo/tenant/tenant-site-unarchive)
- [m365 spo site admin list](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-admin-list)

### New Microsoft Teams command

Using the CLI, it was already possible to install and uninstall apps in the personal scope of a user in Teams. We've now added a new command to upgrade such an app installation to the latest version.

To upgrade an app by name for the specified user, run:

```sh
m365 teams user app upgrade --name HelloWorld --userName admin@contoso.com
```

For more information, check the following resources:
- [m365 teams user app upgrade](https://pnp.github.io/cli-microsoft365/cmd/teams/user/user-app-upgrade)

## What's changed

Besides all these new commands, we've also made some changes to some existing commands. A few bugs have been fixed and the codebase has been polished. Changes include an enhancement when [adding folders in SharePoint](#adding-folders-in-sharepoint).

### Adding folders in SharePoint

It's now possible to ensure a create a new folder recursively. The entire folder path will be created if necessary using the new `--ensureParentFolders` option. 

To create a folder an ensure all parent folders in the path are created as well, run:

```sh
m365 spo folder add --webUrl https://contoso.sharepoint.com/sites/project-x --parentFolderUrl '/Projects/2024/Q1/Reports' --name Financial --ensureParentFolders
```

- [m365 spo folder add](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-add)

## Upcoming changes

Curious about what lies ahead? We are excited to share some of our ongoing projects and initiatives. We have some commands pertaining to [Multitenant organization capabilities in Microsoft Entra ID](https://learn.microsoft.com/entra/identity/multi-tenant-organizations/overview) which are in the pipeline and will be released in the upcoming versions.

Right now, there are over 40 opened PRs with new awesome features that will soon be added to CLI for Microsoft 365, and [54 issues that are up for grabs](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22). We're working hard to bring you even more exciting features and improvements in the next release. 

But we don't stop there. We value your input and ideas. If you have any suggestions for new commands, don't hesitate to share them with us. Create a [new issue](https://github.com/pnp/cli-microsoft365/issues/new/choose) on our GitHub Issues list or join our vibrant [community Discord server](https://aka.ms/cli-m365/discord) to engage in discussions.

Sharing is Caring!

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Arjun Menon](https://github.com/arjunumenon)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [lovyjain](https://github.com/lovyjain)
- [Martin Loitzl](https://github.com/mloitzl)
- [Martin Machacek](https://github.com/MartinM85)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shoutout and high fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to provide us with their insights:

- [Angel L. Mateo](https://github.com/amateo)
- [bubbletroubles](https://github.com/bubbletroubles)
- [dojcsakj](https://github.com/dojcsakj)
- [Ikramullah Quraishi](https://github.com/IkramullahQuraishi)
- [Martin Loitzl](https://github.com/mloitzl)
- [Michał Kornet](https://github.com/mkm17)
- [Mikey](https://github.com/BrainSlugs83)
- [Scott Berry](https://github.com/scberr)
- [ToeKneeFan](https://github.com/ToeKneeFan)

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
