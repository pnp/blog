---
title: CLI for Microsoft 365 v7.4
date: 2024-01-31T08:00:00.000Z
author: Jasey Waegebaert
githubname: Jwaegebaert
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Entra ID
  - Copilot
type: regular
---

Introducing the latest release of CLI for Microsoft 365

[CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces a few new commands as well as a ton of awesome improvements.

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover an array of exciting features and improvements that will revolutionize your Microsoft 365 journey. 
 
## What's new

### External content

The release of Microsoft Copilot for Microsoft 365 brings new challenges and possibilities in surfacing your data to your users. As an aid in this field, Graph connectors can be a significant asset to get line of business data into Microsoft 365 and allow Copilot to work with it. The CLI for Microsoft 365 has a growing group of commands that allow you to work with Graph connectors. 

This release brings a new command to add a URL to the item resolver for an existing connection. This allows you to add a URL pattern to an existing connection that will be used to resolve URLs to items in your external content.

Adds a URL to the item resolver to an existing connection.

```sh
m365 external connection urltoitemresolver add --externalConnectionId "samplesolutiongallery" --baseUrls "https://adoption.microsoft.com" --urlPattern "/sample-solution-gallery/sample/(?<sampleId>[^/]+)" --itemId "{sampleId}" --priority 1
```

For more information check the following resources:   
- [m365 external connection urltoitemresolver add](https://pnp.github.io/cli-microsoft365/cmd/external/connection/connection-urltoitemresolver-add/)

### Microsoft Entra ID

With this release, we're introducing a new command to manage Microsoft Entra ID. With this new command, you'll be able to assign a role with administrative privileges to a user or group for a specific administrative unit.

To assign a role definition specified by name to a user-specified by name for an administrative unit specified by name, run:

```sh
m365 entra administrativeunit roleassignment add --administrativeUnitName 'Marketing Division' --roleDefinitionName 'License Administrator' --userName 'john.doe@contoso.com'
```

For more information check the following resources:
- [m365 entra administrativeunit roleassignment add [options]](https://pnp.github.io/cli-microsoft365/cmd/entra/administrativeunit/administrativeunit-roleassignment-add/)

## What's changed

As an important part of our work, we squashed some major bugs and polished the codebase some more. We also added some additional options. A major change that has been made is the renaming of the `aad` command group to `entra`. This is to better reflect the change Microsoft has made to the name of the service.

### Renamed `aad` to `entra`

The command group `aad` has undergone a name change and is now known as `entra`, mirroring the rebranding to Microsoft Entra ID. This modification has been implemented to align with Microsoft's recent renaming of the service. While the previous command group will remain accessible for some time, it is slated for removal in an upcoming release. We encourage users to familiarize themselves with the `entra` command group to ensure a smooth transition when the `aad` command group is eventually phased out.

### Proxy support

The CLI for Microsoft 365 now supports proxy configuration. This feature allows you to configure the CLI to use a proxy server to connect to the internet. This is especially useful for users who are behind a corporate firewall. We now support the use of environment variables HTTP_PROXY or HTTPS_PROXY.

More information on how to configure the CLI for Microsoft 365 to use a proxy server can be found [here](https://pnp.github.io/cli-microsoft365/user-guide/using-proxy-url).

### And more...

If you are eager to go over all of the details and improvements added in this release, do not hesitate to check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v740) to find out more.

## Upcoming changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 86 issues that are actively being developed and 71 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release. 

But we don't stop there. We value your input and ideas. If you have any suggestions for new commands, don't hesitate to share them with us. Create a [new issue](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=new-command.yml&title=New+command%3A+%3Cshort+description%3E) on our GitHub Issues list or join our vibrant [community Discord server](https://aka.ms/cli-m365/discord) to engage in discussions.

Together, let's shape the future of CLI for Microsoft 365 and unlock even greater possibilities.

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
- [Paolo Pialorsi](https://github.com/PaoloPia)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shoutout and high fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to provide us with their insights:

- [Andrew Carvalho](https://github.com/AndrewCarvalho)
- [Anouck Fierens](https://github.com/AnouckF)
- [dontforgeturmail](https://github.com/dontforgeturmail)
- [greczimarton](https://github.com/greczimarton)
- [Jorge Castro](https://github.com/jorgecc)

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
