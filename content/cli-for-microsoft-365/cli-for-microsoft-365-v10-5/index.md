---
title: CLI for Microsoft 365 v10.5
date: 2025-03-31T01:00:00.000Z
author: Martin Lingstuyl
githubname: martinlingstuyl
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Viva Engage
  - SharePoint
  - Microsoft Graph
type: regular
---

It's that time of the month again! We've just published a new minor version of the CLI for Microsoft 365. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces new commands that will enhance the quality of your Microsoft 365 experience.

> Explore the [release notes](https://aka.ms/cli-m365/notes) for a neat overview of all the exciting features and improvements. 

## What's New

### Microsoft Graph

In this release, we added three new commands to manage directory extensions for Entra ID through the Microsoft Graph. Directory extensions are a way to add additional properties to Entra ID resources: users, groups, administrative units, applications, devices, or organizations. They're a flexible way to enrich your company data with information that's relevant to you. Using the below new commands you can define new directory extensions, remove these definitions, and retrieve them.

To define a new directory extension for saving GitHub information for Entra users, run:

```sh
m365 graph directoryextension add --name gitHubWorkAccountName --appName ContosoApp --targetObjects User --dataType String
```

To retrieve a specific directory extension, run:

```sh
m365 graph directoryextension get --name extension_105be60b603845fea385e58772d9d630_GitHubWorkAccount --appName ContosoApp
```

To remove the directory extension, run:

```sh
m365 graph directoryextension remove --name extension_105be60b603845fea385e58772d9d630_GitHubWorkAccount --appName ContosoApp --force
```

For more information, check the following resources:

- [graph directoryextension add](https://pnp.github.io/cli-microsoft365/cmd/graph/directoryextension/directoryextension-add/)
- [graph directoryextension get](https://pnp.github.io/cli-microsoft365/cmd/graph/directoryextension/directoryextension-get/)
- [graph directoryextension remove](https://pnp.github.io/cli-microsoft365/cmd/graph/directoryextension/directoryextension-remove/)

### SharePoint

In this release, we're also adding two new commands for SharePoint. It's now possible to add new home sites, making it easier to create new Viva Connections experiences, each on a standalone home site. Or how about removing sections on a SharePoint page. It's now possible in our effort to make it easier to design SharePoint sites using scripting, for example, in a migration scenario.

To add a new home site, run:

```sh
m365 spo homesite add --url "https://contoso.sharepoint.com/sites/testcomms"
```

To remove a page section from a specified page, run:

```sh
m365 spo page section remove --webUrl https://contoso.sharepoint.com/sites/team-a --pageName home.aspx --section 1
```

For more information, check the following resources:

- [m365 spo homesite add](https://pnp.github.io/cli-microsoft365/cmd/spo/homesite/homesite-add)
- [m365 spo page section remove](https://pnp.github.io/cli-microsoft365/cmd/spo/page/page-section-remove)

### Viva Engage 

Managing Viva Engage communities has also been enhanced with two new commands. It's now possible to add and remove community users.

To add a new user as an admin to a specific community, run:

```sh
m365 viva engage community user add --communityDisplayName "Innovation" --userNames john.doe@contoso.com --role Admin
```

To remove a user from a specific community, run:

```sh
m365 viva engage community user remove --communityDisplayName "Innovation" --userName john.doe@contoso.com --force
```

For more information, check the following resources:

- [m365 viva engage community user add](https://pnp.github.io/cli-microsoft365/cmd/viva/engage/engage-community-user-add)
- [m365 viva engage community user remove](https://pnp.github.io/cli-microsoft365/cmd/viva/engage/engage-community-user-remove)

## What's changed

This release also brings some other great changes. Aside from several enhancements and bug fixes to elevate the overall CLI experience, there are a couple of things we'd like to highlight.

### New sample script - Check what users assigned to a specific role are allowed to do in a tenant

We've added a new sample to the docs site about getting a report about roles and permissions. Using role based access control (RBAC) with Microsoft Entra ID to control access to resources is a best practice that's at the foundation of good tenant management. But do you actually know what a user will be able to do with a specific role that you're about to assign them? This new sample script gives an overview of the permissions that are available on the role. This is handy for default roles that Microsoft shipped with your tenant, but even more so if you employ custom roles in your organization.

For more information check the following resource:

[Check what users assigned to a specific role are allowed to do in a tenant](https://pnp.github.io/cli-microsoft365/sample-scripts/entra/read-role-permissions/)

### New sample script - Remove SharePoint page header

We've also added a new sample regarding page management. With this sample it's easier to automatically remove the page header from a page. 

For more information check the following resource:

[Remove SharePoint page header](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/remove-page-header/)

### New guide - Using CLI in an Azure Function with PowerShell

Did you know you can run CLI for Microsoft 365 scripts in an Azure Function? It's a great way to automate your scripts with a tool that's familiar to you. You could write your script on your machine, testing it out as you go. As soon as you're ready, create a new function app in Azure and deploy your script to run every day or on whatever schedule or with whatever trigger you like. 

This guide helps to get you started! 

For more information check the following resource:

[Using CLI in an Azure Function with PowerShell](https://pnp.github.io/cli-microsoft365/user-guide/automation/azure-function-powershell/)

### Using Federated Identity in GitHub actions

Deploying apps in GitHub workflows is getting easier! Drop all your certificates and implement Federated Credentials! Federated identity is a quite recent addition to Entra ID, which means you can establish a trust relationship between a third-party service like GitHub and Entra ID. It means that you can start using credentialless authentication for the CLI for Microsoft 365! You'll be able to configure an Entra application to allow GitHub Actions to sign in. Deploying an SPFx app using GitHub Actions becomes easier like this. You won't have to keep certificate expiration dates in mind and you don't need to be afraid that your certificate is compromised... No credentials, better security!

Federated Identity for GitHub actions has currently been added to the `m365 login` command. Signing into the CLI using federated identity within a GitHub workflow can therefore be done as follows:

```yaml
- name: 'Connect using Federated Identity'
  run: "m365 login --authType federatedIdentity --appId "<some-client-id>" --tenant "<some-tenant-id>"
```

As of now, we still have to adapt the GitHub actions CLI task package to be able to work with this new `authType`. But that will probably be updated soon as well! We'll keep you posted on that!

## Upcoming Changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 70 issues that are actively being developed and 109 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release.

As written above, one of the fields in which we want to improve is Federated Identity. Not only targeting GitHub, but also Azure DevOps.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)
- [Reshmee Auckloo](https://github.com/reshmee011)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [Nanddeep Nachan](https://github.com/nanddeepn)

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
