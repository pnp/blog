---
title: CLI for Microsoft 365 v7.5
date: 2024-02-29T08:00:00.000Z
author: Jasey Waegebaert
githubname: Jwaegebaert
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Entra ID
  - Microsoft Graph
  - Viva Engage
type: regular
---

Introducing the latest release of CLI for Microsoft 365. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces several new commands that will enhance the quality of your Microsoft 365 experience.

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover an array of exciting features and improvements that will revolutionize your Microsoft 365 journey.

## What's new

### Support for using multiple accounts

The release includes a major quality-of-life improvement for users who manage multiple tenants. Now you can manage multiple connections to different tenants. This feature allows you to switch between tenants without having to log out and log back in.

We introduce a whole new group of commands to manage connections. You can now list, remove, set and use different connections. With this new feature we also added the ability to provide a custom name for each connection. If this is not provided, the local account id will be used as the connection name.

With this major new feature, you'll be able to execute the following commands:

Use the device code flow to connect to a Microsoft 365 tenant and provide a custom name for the connection:

```sh
m365 login --connectionName "Customer A"
```

List all available connections:

```sh
m365 connection list
```

Remove a connection:

```sh
m365 connection remove --name "Customer A"
```

Rename an existing connection:

```sh
m365 connection set --connectionName "Customer A" --newName "Contoso"
```

And finally, you can change the active connection:

```sh
m365 connection use --name "Customer B"
```

For more information check the following resources:
- [m365 connection list](https://pnp.github.io/cli-microsoft365/cmd/connection/connection-list/)
- [m365 connection remove](https://pnp.github.io/cli-microsoft365/cmd/connection/connection-remove/)
- [m365 connection set](https://pnp.github.io/cli-microsoft365/cmd/connection/connection-set/)
- [m365 connection use](https://pnp.github.io/cli-microsoft365/cmd/connection/connection-use/)

### Microsoft Entra ID

We also introduce several new commands to manage Microsoft Entra ID. These commands allow you to manage administrative units, app permisions, groups and user registration details.

#### Administrative units

You can now remove a member from an administrative unit using the following command:

```sh
m365 entra administrativeunit member remove --userName john.doe@contoso.com --administrativeUnitName 'Marketing Division'
```

For more information check the documentation here: [m365 entra administrativeunit member remove](https://pnp.github.io/cli-microsoft365/cmd/entra/administrativeunit/administrativeunit-member-remove/)

#### App permissions

With this new command you can easily list all the application or delegated permissions for a specific app:

```sh
m365 entra app permission list --appId 'f1417aa3-bf0b-4cc5-a845-a0b2cf11f690' --type delegated
```

For more information check the documentation here: [m365 entra app permission list](https://pnp.github.io/cli-microsoft365/cmd/entra/app/app-permission-list/)

#### Groups

There are two new commands available to manage groups. With the first one, you can add a user to a Microsoft Entra ID group:

```sh
m365 entra group user add --groupDisplayName Developers --ids 098b9f52-f48c-4401-819f-29c33794c3f5 --role Member
```

And with the second one, you can create a new Microsoft Entra ID group:

```sh
m365 entra group add --displayName Developers --type microsoft365 --mailNickname devs --ownerUserNames john.doe@contoso.com --memberUserNames "john.doe@contoso.com,adele.vance@contoso.com" --visibility Private
```

For more information check the following resources:
- [m365 entra group add](https://pnp.github.io/cli-microsoft365/cmd/entra/group/group-add/)
- [m365 entra group user add](https://pnp.github.io/cli-microsoft365/cmd/entra/group/group-user-add/)

#### User registration details

Last but not least, you can easily retrieve a list of the authentication methods registered for users with the following command:

```sh
m365 entra user registrationdetails list --userPreferredMethodForSecondaryAuthentication 'sms,push'
```

For more information check the documentation here: [m365 entra user registrationdetails list](https://pnp.github.io/cli-microsoft365/cmd/entra/user/user-registrationdetails-list/)

### Copy file

We've added a new command to copy a file to a different location. Here you'll be able to copy a file from one location to another within the same site or to a different site. This command is especially useful for users who need to move files around within their SharePoint environment. Here a different approach is used than the existing `m365 spo file copy` command, which uses the SharePoint REST API to copy files. The new `m365 file copy` command uses the Microsoft Graph API to copy files.

You can use the following command to copy a file to a different location:

```sh
m365 file copy --webUrl https://contoso.sharepoint.com/sites/project --sourceUrl "/sites/project/Shared Documents/Document.pdf" --targetUrl "/sites/IT/Shared Documents"
```

For more information check the documentation here: [m365 file copy](https://pnp.github.io/cli-microsoft365/cmd/file/file-copy/)

## What's changed

Besides all these new commands, we've also made some changes to the existing commands. A lot of bugs have been fixed and the codebase has been polished. A major change that has been made is the renaming of the `yammer` command group to `viva engage`. This is to better reflect the change Microsoft has made to the name of the service.

Also, a lot of improvements have been made to the documentation. We've added more examples, improved the readability of the documentation, and we introduced a new article. This article explains how to use Use CLI for Microsoft 365 VS Code extension. You can find this article [here](https://pnp.github.io/cli-microsoft365/user-guide/using-cli-vs-code-extension/).

If you are eager to go over all of the details and improvements added in this release, do not hesitate to check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v750) to find out more.

## Upcoming changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 91 issues that are actively being developed and 63 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release.

But we don't stop there. We value your input and ideas. If you have any suggestions for new commands, don't hesitate to share them with us. Create a [new issue](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=new-command.yml&title=New+command%3A+%3Cshort+description%3E) on our GitHub Issues list or join our vibrant [community Discord server](https://aka.ms/cli-m365/discord) to engage in discussions.

Together, let's shape the future of CLI for Microsoft 365 and unlock even greater possibilities.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Arjun Menon](https://github.com/arjunumenon)
- [János Dojcsák](https://github.com/dojcsakj)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Vedant Lakshminarayanan](https://github.com/Vedu1996)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shoutout and high fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to provide us with their insights:

- [Alex Al-Saffar](https://github.com/thisismygitrepo)
- [brugh](https://github.com/brugh)
- [dontforgeturmail](https://github.com/dontforgeturmail)

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

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord), or [X](https://x.com/climicrosoft365). Don't hesitate to connect with us. Your input plays a vital role in shaping the future of CLI for Microsoft 365.
