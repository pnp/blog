---
title: CLI for Microsoft 365 v10.8
date: 2025-05-31T01:00:00.000Z
author: Jasey Waegebaert
githubname: jwaegebaert
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
  - Microsoft Graph
type: regular
---

The CLI for Microsoft 365 strikes again! We've just published a new minor version of the CLI for Microsoft 365. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces new commands that will enhance the quality of your Microsoft 365 experience.

> Explore the [release notes](https://aka.ms/cli-m365/notes) for a neat overview of all the exciting features and improvements. 

## What's New

### Microsoft Graph

In this release, we’ve added new commands to improve how you interact with Microsoft Graph and Entra ID. You now have more flexibility when working with directory and open extensions, which allow you to store custom data for various resources like users and groups. This will help you manage and enrich your environment in a more streamlined way.

To get all directory extensions registered for an application specified by name, run:

```sh
m365 graph directoryextension list --appName ContosoApp
```

To update an open extension for a user specified by UPN, run:

```sh
m365 graph openextension set --userName john.doe@contoso.com --name 'com.contoso.roamingSettings' --resourceType user --theme dark --color red --language English
```

For more information, check the following resources:

- [graph directoryextension list](https://pnp.github.io/cli-microsoft365/cmd/graph/directoryextension/directoryextension-list/)
- [graph openextension set](https://pnp.github.io/cli-microsoft365/cmd/graph/openextension/openextension-set/)


### Microsoft Entra ID

A feature has been added to retrieve and manage a list of organizations within your Entra ID environment, simplifying administrative tasks.

To retrieve all your organizations, simply run:

```sh
m365 entra organization list
```

For more information check the following resources:
- [m365 entra organization list](https://pnp.github.io/cli-microsoft365/cmd/entra/organization/organization-list/)

### SharePoint Embedded

New features for SharePoint Embedded enhance container management. You can now create and remove containers, view and manage permissions, and retrieve lists of deleted containers. These improvements offer more control over your SharePoint Embedded environments, making it easier to organize, maintain, and recover containers, ultimately improving your administrative workflows and efficiency.

To create a new container, run:

```sh
m365 spe container add --name Invoices --containerTypeName "Invoice app container type"
```

To remove a container, run:

```sh
m365 spe container remove --name "My Application Storage Container" --containerTypeName "My Application Container Type"
```

To list all permissions for a specific container, run:

```sh
m365 spe container permission list --containerId "b!ISJs1WRro0y0EWgkUYcktDa0mE8zSlFEqFzqRn70Zwp1CEtDEBZgQICPkRbil_5Z"
```

To list all deleted containers in a specific type, run:

```sh
m365 spe container recyclebinitem list --containerTypeName "My container type name"
```

To remove a container type, run:

```sh
m365 spe containertype remove --name 'My container type'
```

For more information, check the following resources:
- [spe container add](https://pnp.github.io/cli-microsoft365/cmd/spe/container/container-add/)
- [spe container remove](https://pnp.github.io/cli-microsoft365/cmd/spe/container/container-remove/)
- [spe container permission list](https://pnp.github.io/cli-microsoft365/cmd/spe/container/permission-list/)
- [spe container recyclebinitem list](https://pnp.github.io/cli-microsoft365/cmd/spe/container/recyclebinitem-list/)
- [spe containertype remove](https://pnp.github.io/cli-microsoft365/cmd/spe/containertype/containertype-remove/)

### SharePoint Premium

We’ve introduced a new command to manage SharePoint Premium features, allowing you to easily apply trained document understanding models to document libraries. This feature is particularly useful for organizations looking to enhance their document processing capabilities by leveraging AI-driven insights.

To apply a trained model to a document library, run:

```sh
m365 spp model apply --webUrl "https://contoso.sharepoint.com" --contentCenterUrl "https://contoso.sharepoint.com/sites/ContentCenter" --title "ModelExample" --listTitle "Shared Documents"
```

For more information, check the following resource:
- [spp model apply](https://pnp.github.io/cli-microsoft365/cmd/spp/model/model-apply/)

## What's changed

This release also brings some other great changes. Aside from many improvements in the codebase and bug fixes to elevate the overall CLI experience, there are a couple of things we'd like to highlight.

### Support for SharePoint Framework v1.21.1

Support for SPFx 1.21.1 has been added, ensuring compatibility with the latest version of the SharePoint Framework. This update allows you to take full advantage of the new features and improvements in SPFx 1.21.1, enhancing your development experience and enabling you to build more efficient and modern SharePoint solutions.

### Federated Identity Login for Azure DevOps

A new feature has been added to support federated identity login when running in Azure DevOps, allowing you to deploy apps without the need for certificates in your CI/CD pipeline. This provides a more streamlined and secure authentication process, enabling easier integration and automation of your Microsoft 365 workflows directly within Azure DevOps. Whether you're using a service connection or not, you can now authenticate with federated identity, simplifying the overall deployment process and enhancing security across your workflows.

### Refactorings & improvements

We’ve made several refactorings and improvements to enhance the performance and usability of existing commands, ensuring a smoother experience when managing teams, sites, and Viva Connections. Additionally, as part of our ongoing effort to improve reliability, we’ve migrated several commands to Zod, a powerful data validation library. This migration enhances the accuracy, stability, and overall performance of the CLI, making it easier to accomplish tasks with greater ease.

## Upcoming Changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 50 issues that are actively being developed and 107 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release.

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
- [Smita Nachan](https://github.com/SmitaNachan)
- [Tobias Maestrini](https://github.com/tmaestrini)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [Hanne Lauritzen](https://github.com/MissHerku)
- [JustinCLyon](https://github.com/JustinCLyon)
- [strln0750](https://github.com/strln0750)
- [webmastergott](https://github.com/webmastergott)

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
