---
title: CLI for Microsoft 365 v6.10
date: 2023-07-31T08:00:00.000Z
author: Adam Wójcik
githubname: adam-it
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - SharePoint
  - SharePoint Framework (SPFx)
  - Power Apps
  - Planner
  - Microsoft Teams
type: popular
---

Introducing the latest release of CLI for Microsoft 365

[CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command line tool based on Node.js that helps you manage many things around Microsoft 365 and your SPFx project. You may manage OneDrive, Planner, Power Apps and Automate, Teams, Yammer, SharePoint (of course), and many many more. The list keeps on growing and growing. In this minor release, we introduced new commands as well as a tonne of improvements.

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover an array of exciting features and improvements that will revolutionize your Microsoft 365 journey.

## What's new

In this minor release, we added a couple of new commands and enhancements to the existing functionality. Check out some of the awesome stuff added and be sure to try them out.

### Power Apps Management

We've introduced a new command that allows you to list all permissions of a Power App as well as an additional command to modify the app owner. Check out the details below:

To lists all permissions of a Power App, simply run:

```sh
m365 pa app permission list --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0
```

You may also filter the results to only a given role by doing:

```sh
m365 pa app permission list --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0 --roleName CanEdit
```

In order to set a new owner for a Power App and remove the previous owner, all you need to do is:

```sh
m365 pa app owner set --environmentName Default-716eb9fb-bf79-4be9-b0c7-900824fcbe25 --appName 7ab97923-4a4d-4467-b030-12071d2b810b --userName john.doe@contoso.com
```

For more information, check out:

- [m365 pa app owner set](https://pnp.github.io/cli-microsoft365/cmd/pa/app/app-owner-set/)
- [m365 pa app permission list](https://pnp.github.io/cli-microsoft365/cmd/pa/app/app-permission-list/)

### Teams Management

Microsoft Teams has become a collaboration platform of its own and for many of us, working remotely or not, it is the first start-up tool when starting your working day. With CLI for Microsoft 365 we try to extend the capabilities of what you may manage around that product. In this release, we introduce a command which allows you to add a member to a Microsoft Teams chat conversation

To add a member by UPN to a Teams chat and share chat history until a specific point in time, simply run:

```sh
m365 teams chat member add --chatId 19:8b081ef6-4792-4def-b2c9-c363a1bf41d5_5031bb31-22c0-4f6f-9f73-91d34ab2b32d@unq.gbl.spaces --userName john.doe@contoso.com --visibleHistoryStartDateTime 2023-05-03T12:00:00Z
```

For more information, check out:

- [m365 teams chat member add](https://pnp.github.io/cli-microsoft365/cmd/teams/chat/chat-member-add)

### SharePoint Framework Projects v1.18.0-beta.1 Support

If you want to keep up to date with the latest SPFx enhancements you are going to love our latest update. In this release, we added the support for SPFx `v1.18.0-beta.1` to three of our most popular commands: `spfx project upgrade`, `spfx project doctor`, and `spfx doctor`.

Here are the commands to get you started:

```sh
m365 spfx project upgrade --output md
```

```sh
m365 spfx doctor --output text
```

```sh
m365 spfx project doctor --output md
```

For more information, check out the documentation for each command:

- [spfx project upgrade](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade/)
- [spfx doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor/)
- [spfx project doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-doctor/)

### Extended Planner commands with rosters support

Not so long ago we introduced Planner Roster commands and now we refactored the already existing commands to add that support there as well. In this minor release, we modified the planner bucket commands with the ability to reference Planner Rosters. Check out the [related issue](https://github.com/pnp/cli-microsoft365/issues/4820) to find out more.

### The fun never stops, improving our Codebase

In this minor release, we continue our work on refactoring the code base to embrace the asynchronous programming model using **async/await**. All this would not have been possible without our awesome contributors and their dedication to CLI for Microsoft 365. Just have a look at the [list](https://github.com/pnp/cli-microsoft365/issues/3618) to get a feeling of the amount of work already done and what is left.

We've also taken the first steps to refactor our codebase to centralize the shared code in util functions. This refactor will bring a performance boost to the tool as well as allows easier integration and testing. Check out the [related issue](https://github.com/pnp/cli-microsoft365/issues/4531) to go over the details.

### What else

If you are eager to go over all of the details and improvements added in this release, do not hesitate to check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v6100) to find out more.

## Upcoming Changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

### Expanding Command Arsenal

Our relentless pursuit of empowering your Microsoft 365 experience continues. We're actively working on introducing more commands to CLI for Microsoft 365. From Power Platform to SharePoint Online, we're exploring various services to enhance your command-line capabilities. Additionally, we're dedicated to refactoring our codebase to embrace the power of async/await, further improving performance and readability.

But we don't stop there. We value your input and ideas. If you have any suggestions for new commands, don't hesitate to share them with us. Create a [new issue](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=new-command.yml&title=New+command%3A+%3Cshort+description%3E) on our GitHub Issues list or join our vibrant [community Discord server](https://aka.ms/cli-m365/discord) to engage in discussions.

Together, let's shape the future of CLI for Microsoft 365 and unlock even greater possibilities.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Arjun Menon](https://github.com/arjunumenon)
- [Ganesh Sanap](https://github.com/ganesh-sanap)
- [Garry Trinder](https://github.com/garrytrinder)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Matthijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Patrick Lamber](https://github.com/plamber)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

We express our deepest gratitude for the time and effort you have invested in CLI for Microsoft 365, improving its progress and enriching its capabilities. Your contributions have played a significant role in advancing this project and empowering users worldwide. Thank you for your commitment and valuable assistance!

### High fives

We would like to give a big shoutout and high fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to provide us with their insights:

- [Aadit Ambadkar](https://github.com/Aadit-Ambadkar)

Your feedback has been instrumental in shaping the direction of CLI for Microsoft 365, and we are grateful for your involvement in making our platform even better. Your active participation and valuable insights continue to drive innovation and enhance the user experience for all. Thank you for being an essential part of our community!

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

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord), or [Twitter](https://twitter.com/climicrosoft365). Don't hesitate to connect with us; your input plays a vital role in shaping the future of CLI for Microsoft 365.