---
title: CLI for Microsoft 365 v10.2
date: 2024-12-31T03:00:00.000Z
author: Adam Wójcik
githubname: adam-it
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

We have just published a new minor version of CLI for Microsoft 365. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces several new commands that will enhance the quality of your Microsoft 365 experience.

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover various exciting features and improvements that will revolutionize your Microsoft 365 journey. 

## What's New

### SharePoint Embedded

In this release, we've added yet another command in SharePoint Embedded area that allows you to get the details of a specific Container. 

To get a container of a specific type run:

```sh
m365 spe container get --id "b!ISJs1WRro0y0EWgkUYcktDa0mE8zSlFEqFzqRn70Zwp1CEtDEBZgQICPkRbil_5Z"
```

For more information, check the following resources:

- [m365 spe container get](https://pnp.github.io/cli-microsoft365/cmd/spe/container/container-get/)

### SharePoint Premium

This time we added a new command that will help you retrieve information about a document understanding model.

In order to get information about a SharePoint Premium document understanding model by title, simply use:

```sh
m365 spp model get --siteUrl "https://contoso.sharepoint.com/sites/ContentCenter" --title "climicrosoft365Model"
```

For more information, check the following resources:

- [m365 spp model get](https://pnp.github.io/cli-microsoft365/cmd/spp/model/model-get/)

### SharePoint

In this release we added a new command to one of our biggest areas: SharePoint. The new command allows you to list all home sites.

In order to do that simply run:

```sh
m365 spo tenant homesite list
```

For more information, check the following resources:

- [m365 spo tenant homesite list](https://pnp.github.io/cli-microsoft365/cmd/spo/tenant/tenant-homesite-list/)

### Microsoft Entra ID

In this release we added three new commands that increase the management capabilities of Microsoft Entra ID role definitions. You can now list, get and remove role definitions.

To retrieve all Microsoft Entra ID role definitions, run:

```sh
m365 entra roledefinition list
```

To get limited info about a role specified by the display name:

```sh
m365 entra roledefinition get --displayName 'Custom SharePoint Role' --properties 'description,isEnabled'
```

And to remove a role definition specified by name and prompt for confirmation you may use the following:

```sh
m365 entra roledefinition remove --displayName 'Custom Role'
```

For more information, check the following resources:

- [m365 entra roledefinition get](https://pnp.github.io/cli-microsoft365/cmd/entra/roledefinition/roledefinition-get/)
- [m365 entra roledefinition list](https://pnp.github.io/cli-microsoft365/cmd/entra/roledefinition/roledefinition-list/)
- [m365 entra roledefinition remove](https://pnp.github.io/cli-microsoft365/cmd/entra/roledefinition/roledefinition-remove/)

### Manage pronouns settings for an organization

In this release we added a new command that allows you to retrieve information about pronouns settings for an organization.

To retrieve information about pronouns settings for your organization, use:

```sh
m365 tenant people pronouns get
```

For more information check the following resources:

- [m365 tenant people pronouns get](https://pnp.github.io/cli-microsoft365/cmd/tenant/people/people-pronouns-get/)

## What's changed

This release includes numerous refinements and bug fixes to improve the overall CLI experience. As an example, we updated the `spo user ensure` and `spo page section add` commands with additional options that will increase their functionality and usability.

## Testimonials

We’re thrilled to unveil our new community testimonials page! This page highlights the experiences and stories shared by users from around the world, showcasing the impact of CLI for Microsoft 365 in real-life scenarios. From solving challenges to streamlining workflows, these testimonials reflect the value the CLI brings to professionals and organizations alike.

Check out the page [here](https://pnp.github.io/cli-microsoft365/about/testimonials-quotes) to see how others are using CLI for Microsoft 365 and get inspired to share your own experience with us!

## Upcoming Changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 100 issues that are actively being developed and 94 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Reshmee Auckloo](https://github.com/reshmee011)
- [Saurabh Tripathi](https://github.com/Saurabh7019)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [Daniel Laskewitz](https://github.com/Laskewitz)
- [piniontech777](https://github.com/piniontech777)
- [Rabia Williams](https://github.com/rabwill)
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

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord), [Bluesky](https://bsky.app/profile/climicrosoft365.bsky.social), or [X](https://x.com/climicrosoft365). Don't hesitate to connect with us. Your input plays a vital role in shaping the future of CLI for Microsoft 365.
