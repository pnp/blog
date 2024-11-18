---
title: CLI for Microsoft 365 v7.1
date: 2023-10-31T08:00:00.000Z
author: Jasey Waegebaert
githubname: jwaegebaert
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Azure AD
  - SharePoint
type: regular
---

Introducing the latest release of CLI for Microsoft 365

[CLI for Microsoft 365](https://aka.ms/cli-m365): a cross-platform command-line tool that empowers you to manage your Microsoft 365 tenant and SharePoint Framework projects. This release comes packed with a brand new command, along with a bunch of interesting enhancements to existing commands.

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover an array of exciting features and improvements that will revolutionize your Microsoft 365 journey.

## What's new

### Azure Active Directory

With this release, we've introduced a new command that allows you to list users of a specific Azure AD group. This command is a great addition to your arsenal, as it provides you with greater control and flexibility when managing your Azure AD groups.

List all group users from a group specified by ID.

```sh
m365 aad group user list --groupId 03cba9da-3974-46c1-afaf-79caa2e45bbe
```

List all group users from a group specified by name. For each one return the display name, e-mail address, and manager display name.

```sh
m365 aad group user list --groupDisplayName Developers --properties "displayName,mail,manager/displayName"
```

List all group members that are guest users.

```sh
m365 aad group user list --groupDisplayName Developers --filter "userType eq 'Guest'"
```

- [m365 aad group user list](https://pnp.github.io/cli-microsoft365/cmd/aad/group/group-user-list)

## What's changed

### Improved documentation

We're committed to providing you with the best possible experience when using CLI for Microsoft 365. That's why we've made some improvements to our documentation to help you get started and find the information you need.

The outputs of several commands have been added or adjusted to provide you with more detailed information. Additionally, we've updated the documentation of several commands to include more information and cross-references.

### SharePoint command improvements

We've made some improvements to our SharePoint commands to enhance your experience and provide you with greater control over your SharePoint environment.

You can now get the currently logged-in user using the `spo user get` command.

```sh
m365 spo user get --webUrl https://contoso.sharepoint.com/sites/project-x
```

Besides this, there have been some minor improvements to other commands to provide you with a more clear error message.

- [m365 spo user get](https://pnp.github.io/cli-microsoft365/cmd/spo/user/user-get)

### And more...

If you are eager to go over all of the details and improvements added in this release, do not hesitate to check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v710) to find out more.

## Upcoming changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 90 issues that are actively being developed and 66 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release.

But we don't stop there. We value your input and ideas. If you have any suggestions for new commands, don't hesitate to share them with us. Create a [new issue](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=new-command.yml&title=New+command%3A+%3Cshort+description%3E) on our GitHub Issues list or join our vibrant [community Discord server](https://aka.ms/cli-m365/discord) to engage in discussions.

Together, let's shape the future of CLI for Microsoft 365 and unlock even greater possibilities.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [David Jackowiak](https://github.com/unkn0wn-root)
- [Ganesh Sanap](https://github.com/ganesh-sanap)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [János Dojcsák](https://github.com/dojcsakj)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Vedant L Iyangar](https://github.com/vlakshminarayanan)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

We express our deepest gratitude for the time and effort you have invested in CLI for Microsoft 365, improving its progress and enriching its capabilities. Your contributions have played a significant role in advancing this project and empowering users worldwide. Thank you for your commitment and valuable assistance!

### High fives

We would like to give a big shoutout and high fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to provide us with their insights:

- [Aaron Junker](https://github.com/Aaron-Junker)
- [Brugh](https://github.com/brugh)
- [Carsten Behring](https://github.com/behrica)
- [Martin Machacek](https://github.com/MartinM85)

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
