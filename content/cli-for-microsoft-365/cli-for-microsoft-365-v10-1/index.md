---
title: CLI for Microsoft 365 v10.1
date: 2024-11-29T03:00:00.000Z
author: Milan Holemans
githubname: milanholemans
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
  - Viva
  - Viva Engage
type: popular
---

We have just published a new minor version of CLI for Microsoft 365. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces several new commands that will enhance the quality of your Microsoft 365 experience.

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover various exciting features and improvements that will revolutionize your Microsoft 365 journey. 

## What's New

### SharePoint Embedded

We're introducing **two new commands** to help you manage Container types and their associated containers in SharePoint Embedded.

**List Containers of a specific Container type**

Retrieve a detailed list of containers for any specified Container Type. This command simplifies container management and is ideal for administrators managing diverse containerized resources.

```sh
m365 spe container list --containerTypeId "91710488-5756-407f-9046-fbe5f0b4de73"
```

Or use a more convenient way by targeting a Container type by name

```sh
m365 spe container list --containerTypeName "trial container"
```

**Get details of a Container type**

Easily fetch details of a specific Container type using its unique ID. This helps you identify and understand the configuration of containerized assets in your environment.

```sh
m365 spe containertype get --id '4ec4aefd-4fa3-0e4a-20c3-6e68389e7138'
```

Or use a more convenient way by targeting a Container type by name

```sh
m365 spe containertype get --name 'test container'
```

For more information check the following resources:

- [m365 spe container list](https://pnp.github.io/cli-microsoft365/cmd/spe/container/container-list)
- [m365 spe containertype get](https://pnp.github.io/cli-microsoft365/cmd/spe/containertype/containertype-get)

### SharePoint Premium

With the new `spp model remove` command, you can now delete document understanding models directly from the CLI. This addition simplifies the management of AI models in tenants that are using SharePoint Premium.

```sh
m365 spp model remove --siteUrl "https://contoso.sharepoint.com/sites/ContentCenter" --id "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc"
```

IDs are not a convenient way of specifying a model that you only know by name. Therefore you can also specify a model by title.

```sh
m365 spp model remove --siteUrl "https://contoso.sharepoint.com/sites/ContentCenter" --title "Accountant Invoice.classifier"
```

For more information check the following resources:

- [m365 spp model remove](https://pnp.github.io/cli-microsoft365/cmd/spp/model/model-remove)

### Viva Engage

Managing Viva Engage communities just got easier! With the viva engage community set command, you can now update existing communities, making it simple to keep community configurations aligned with your organizational needs.

To rename a community, you can just run the command below.

```sh
m365 viva engage community set --displayName 'Developrs' --newDisplayName 'Developers'
```

Apart from using the title of the community, you can also target a community by its ID or Microsoft Entra Group ID.

For more information check the following resources:

- [m365 viva engage community set](https://pnp.github.io/cli-microsoft365/cmd/viva/engage/engage-community-set)

## What's changed

This release includes numerous refinements and bug fixes to improve the overall CLI experience. We’ve enhanced existing SharePoint Embedded and Premium commands and made updates to improve reliability and user experience across the board. Let's highlight a few of them.

**Enhanced group management for Microsoft 365 groups**

The `entra m365group get` command has been enhanced to provide more comprehensive details about Microsoft 365 groups, enabling administrators to better manage and understand group configurations.

The following options were added:

- **allowExternalSenders**: Indicates whether external users can send emails to the group.
- **autoSubscribeNewMembers**: Specifies if new members are automatically subscribed to receive email notifications.
- **hideFromAddressLists**: Determines if the group is hidden from address lists.
- **hideFromOutlookClients**: Indicates if the group is hidden from Outlook clients.
- **isSubscribedByMail**: Indicates whether the signed-in user is subscribed to receive email conversations.

The ability to set these properties is on our roadmap for later releases.

**Extended Graph subscription command with additional options**

In our ongoing efforts to enhance the CLI for Microsoft 365, we've expanded the `graph subscription add` command to support additional options, aligning it more closely with the capabilities of the Microsoft Graph API.

New options Introduced:

- **lifecycleNotificationUrl**: The URL of the endpoint that will receive the lifecycle notifications.
- **notificationUrlAppId**: The app ID that the subscription service can use to generate the validation token. The value allows the client to validate the authenticity of the notification received.
- **latestTLSVersion**: The latest version of TLS that the notification endpoint supports. Allowed values are `v1_0`, `v1_1`, `v1_2`, `v1_3`. Default is `v1_2`.
- **includeResourceData**: When set, the change notifications will include the changed resource data.
- **encryptionCertificate**: A base64-encoded representation of a certificate with a public key used to encrypt resource data in change notifications. Required when using `includeResourceData`.
- **encryptionCertificateId**: A custom app-provided identifier to help identify the certificate needed to decrypt resource data. Required when using `includeResourceData`.

These enhancements offer greater flexibility and security when managing Microsoft Graph subscriptions, allowing for more tailored and secure notification handling.

**SharePoint content type hierarchy**

In this release, we've improved the content type commands by incorporating the `Parent` property into their outputs. This improvement allows users to better understand the inheritance hierarchy of content types, making it easier to manage and organize your SharePoint content structure.

The following commands have the new `Parent` property in their output:

- [spo list contenttype list](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-contenttype-list)
- [spo contenttype list](https://pnp.github.io/cli-microsoft365/cmd/spo/contenttype/contenttype-list)
- [spo contenttype get](https://pnp.github.io/cli-microsoft365/cmd/spo/contenttype/contenttype-get)

**Retrieve custom directory extension attributes**

In this update, we’ve enhanced the CLI for Microsoft 365 by introducing the `properties` option to several commands, enabling you to retrieve custom directory extension attributes for Entra objects.

Previously available only for user-related commands, this functionality now extends to:

- [entra administrativeunit get](https://pnp.github.io/cli-microsoft365/cmd/entra/administrativeunit/administrativeunit-get)
- [entra administrativeunit list](https://pnp.github.io/cli-microsoft365/cmd/entra/administrativeunit/administrativeunit-list)
- [entra app get](https://pnp.github.io/cli-microsoft365/cmd/entra/app/app-get)
- [entra app list](https://pnp.github.io/cli-microsoft365/cmd/entra/app/app-list)
- [entra group get](https://pnp.github.io/cli-microsoft365/cmd/entra/group/group-get)
- [entra group list](https://pnp.github.io/cli-microsoft365/cmd/entra/group/group-list)

By specifying the `properties` option, you can access custom data added to Entra objects, such as users, groups, administrative units, and applications.

For example:

```sh
m365 entra group get --displayName Finance --properties "mail,displayName"
```

For more information check the following resources:

- [entra administrativeunit get](https://pnp.github.io/cli-microsoft365/cmd/entra/administrativeunit/administrativeunit-get)
- [entra administrativeunit list](https://pnp.github.io/cli-microsoft365/cmd/entra/administrativeunit/administrativeunit-list)
- [entra app get](https://pnp.github.io/cli-microsoft365/cmd/entra/app/app-get)
- [entra app list](https://pnp.github.io/cli-microsoft365/cmd/entra/app/app-list)
- [entra group get](https://pnp.github.io/cli-microsoft365/cmd/entra/group/group-get)
- [entra group list](https://pnp.github.io/cli-microsoft365/cmd/entra/group/group-list)
- [entra m365group get](https://pnp.github.io/cli-microsoft365/cmd/entra/m365group/m365group-get)
- [graph subscription add](https://pnp.github.io/cli-microsoft365/cmd/graph/subscription/subscription-add)
- [spo list contenttype list](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-contenttype-list)
- [spo contenttype list](https://pnp.github.io/cli-microsoft365/cmd/spo/contenttype/contenttype-list)
- [spo contenttype get](https://pnp.github.io/cli-microsoft365/cmd/spo/contenttype/contenttype-get)

If you are eager to go over all of the details and improvements added to this release, do not hesitate to check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v1010) to learn more.

## Testimonials

We’re thrilled to unveil our new community testimonials page! This page highlights the experiences and stories shared by users from around the world, showcasing the impact of CLI for Microsoft 365 in real-life scenarios. From solving challenges to streamlining workflows, these testimonials reflect the value the CLI brings to professionals and organizations alike.

Check out the page [here](https://pnp.github.io/cli-microsoft365/about/testimonials-quotes) to see how others are using CLI for Microsoft 365 and get inspired to share your own experience with us!

## Upcoming Changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 100 issues that are actively being developed and 88 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release.

## CLI for Microsoft 365: 7 years and 100 releases strong

This release marks a special milestone for CLI for Microsoft 365. Not only are we celebrating **7 years** of empowering developers and IT professionals around the globe, but this is also the **100th release** of CLI! Over the years, we've continually worked to enhance your experience, expand our capabilities, and keep pace with the evolving Microsoft 365 ecosystem.

Reaching this milestone is a testament to the amazing contributions of our community, the dedication of our team, and the ongoing support of our users. Thank you for being part of this journey—we’re excited to continue building a brighter future together!

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Herco van Brug](https://github.com/brugh)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Reshmee Auckloo](https://github.com/reshmee011)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Shantha Kumar T](https://github.com/ktskumar)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to provide us with their insights:

- [apc005](https://github.com/apc005)

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
