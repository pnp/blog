---
title: CLI for Microsoft 365 v7.3
date: 2023-12-29T08:00:00.000Z
author: Martin Lingstuyl
githubname: martinlingstuyl
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Azure Active Directory
  - SharePoint
type: popular
---

Introducing the latest release of CLI for Microsoft 365

[CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces a number of new administrative commands as well as a ton of awesome improvements.

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover an array of exciting features and improvements that will revolutionize your Microsoft 365 journey.

## What's new

### Microsoft Entra ID

In the last release, we introduced a series of commands that allow you to manage administrative units. An administrative unit is a Microsoft Entra resource that can be a container for other Microsoft Entra resources. It may contain users, groups and devices. In this new release, we're adding new commands to manage the members of these administrative units.

To retrieve a list of all members of a specified administrative unit

```sh
m365 aad administrativeunit member list --administrativeUnitName 'Marketing Division'
```

To retrieve a list of users that are part of a specified administrative unit

```sh
m365 aad administrativeunit member list --administrativeUnitName 'Marketing Division' --type user
```

To add a user to an administrative unit

```sh
m365 aad administrativeunit member add --administrativeUnitName 'Marketing Division' --userName john.doe@contoso.com
```

To add an Entra Group to an administrative unit

```sh
m365 aad administrativeunit member add --administrativeUnitName 'Marketing Division' --groupName 'Marketing Group'
```

To get information about a single user that's a member of an administrative unit

```sh
m365 aad administrativeunit member get --id 64131a70-beb9-4ccb-b590-4401e58446ec --administrativeUnitName 'Marketing Division'
```

We've also added a new command around permission management. An area that the CLI for Microsoft 365 shines in. While we already supported managing delegated and application permissions on enterprise applications, managing permissions of App Registrations was not fully covered. This release brings a new command to achieve that purpose.

Grant multiple delegated API permissions to an Entra ID (Azure AD) app specified by client id

```sh
m365 aad app permission add --appId 'f1417aa3-bf0b-4cc5-a845-a0b2cf11f690' --delegatedPermissions 'https://management.azure.com/user_impersonation https://service.flow.microsoft.com/Flows.Read.All https://graph.microsoft.com/Agreement.Read.All'
```

For more information check the following resources:
- [m365 aad administrativeunit member add](https://pnp.github.io/cli-microsoft365/cmd/aad/administrativeunit/administrativeunit-member-add)
- [m365 aad administrativeunit member list](https://pnp.github.io/cli-microsoft365/cmd/aad/administrativeunit/administrativeunit-member-list)
- [m365 aad administrativeunit member get](https://pnp.github.io/cli-microsoft365/cmd/aad/administrativeunit/administrativeunit-member-get)
- [m365 aad app permission add](https://pnp.github.io/cli-microsoft365/cmd/aad/app/app-permission-add)

### External content

The release of Microsoft Copilot for Microsoft 365 brings new challenges and possibilities in surfacing your data to your users. As an aid in this field, Graph connectors can be a significant asset to get line of business data into Microsoft 365 and allow Copilot to work with it. The CLI for Microsoft 365 has a growing group of commands that allow you to work with Graph connectors.
This release brings a new command to add new items to a connector and a new doctor command to verify if your external connection is correctly configured.

To add a new item to an external connection, with simple properties that everyone is allowed to access

```sh
m365 external item add --id "pnp-ensure-siteassets-library" --connectionId "samplesolutiongallery" --content "Ensure that the Site Assets library is created." --title "Ensure the Site Assets Library is created" --description "Ensure that the Site Assets library is created." --authors "Phil Harding" --acls "grant,everyone,everyone"
```

To check if an external connection is correctly configured for use with Microsoft Copilot for Microsoft 365

```sh
m365 external connection doctor --id contosoproducts --ux copilot
```

For more information check the following resources:
- [m365 external connection doctor](https://pnp.github.io/cli-microsoft365/cmd/external/connection/connection-doctor)
- [m365 external item add](https://pnp.github.io/cli-microsoft365/cmd/external/item/item-add)

### Microsoft Teams

This release also brings a new command to create new meetings in Microsoft Teams. This can be useful in automation scenarios where creating meetings on the fly brings an advantage. But it can also be used from the terminal interactively by those who love the speed of terminal interactions and often have one available.

To create a new online meeting for the currently logged-in user, starting immediately and ending after one hour, run

```sh
m365 teams meeting add
```

To create a new online meeting for the currently logged-in user, with a specified subject and a list of participants, run

```sh
m365 teams meeting add --subject "Test Subject" --participantUserNames "john.doe@contoso.com,olga.manager@contoso.com"
```

To create a new online meeting from an automated app-only process, using a selected organizer and have Microsoft Teams record the meeting automatically

```sh
m365 teams meeting add --organizerEmail "john.doe@contoso.com" --subject "Test Subject" --participantUserNames "olga.manager@contoso.com" --recordAutomatically
```

For more information check the following resources:
- [m365 teams meeting add](https://pnp.github.io/cli-microsoft365/cmd/teams/meeting/meeting-add)

## What's changed

As an important part of our work, we squashed some major bugs and polished the codebase some more. We also added some additional options. You can now list specific entra groups by type, and we added name options to a couple of commands for working with Microsoft Teams apps.

### And more...

If you are eager to go over all of the details and improvements added in this release, do not hesitate to check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v730) to find out more.

## Upcoming changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 80 issues that are actively being developed and 66 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release.

But we don't stop there. We value your input and ideas. If you have any suggestions for new commands, don't hesitate to share them with us. Create a [new issue](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=new-command.yml&title=New+command%3A+%3Cshort+description%3E) on our GitHub Issues list or join our vibrant [community Discord server](https://aka.ms/cli-m365/discord) to engage in discussions.

Together, let's shape the future of CLI for Microsoft 365 and unlock even greater possibilities.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Gustavo Velez](https://github.com/gavdgavd)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Reshmee Auckloo](https://github.com/reshmee011)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

We express our deepest gratitude for the time and effort you have invested in CLI for Microsoft 365, improving its progress and enriching its capabilities. Your contributions have played a significant role in advancing this project and empowering users worldwide. Thank you for your commitment and valuable assistance!

### High fives

We would like to give a big shoutout and high fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to provide us with their insights:

- [brugh](https://github.com/brugh)
- [Andy Kipp](https://github.com/anki-code)
- [Garry Trinder](https://github.com/garrytrinder)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Milan Holemans](https://github.com/milanholemans)
- [Steve Johnson](https://github.com/StevieBleeds)
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

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord), or [X](https://twitter.com/climicrosoft365). Don't hesitate to connect with us. Your input plays a vital role in shaping the future of CLI for Microsoft 365.
