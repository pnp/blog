---
title: CLI for Microsoft 365 v10.4
date: 2025-02-28T01:00:00.000Z
author: Martin Lingstuyl
githubname: martinlingstuyl
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Entra ID
  - SharePoint
  - Outlook
type: regular
---

It's that time of the month again! We've just published a new minor version of the CLI for Microsoft 365. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces new commands that will enhance the quality of your Microsoft 365 experience.

> Explore the [release notes](https://aka.ms/cli-m365/notes) for a neat overview of all the exciting features and improvements. 

## What's New

### Microsoft Entra ID

In this release, we added two new commands for working with Microsoft Entra ID. You can now revoke sign-in sessions for a given user. Something that may be necessary when certain security events take place where resetting a user's password may not be enough. 
We've also added an additional command for working with custom role definitions. When creating custom role definitions you'll need to know what resources actions are available. These resource actions, also called role permissions, are categorized in namespaces. We've added a command to list these namespaces, making it easier to find the correct resource actions.

To get a list of resource namespaces, run:

```sh
m365 entra resourcenamespace list
```

To revoke sign-in sessions for a given user, run:

```sh
m365 entra user session revoke --userName john.doe@contoso.onmicrosoft.com
```

For more information, check the following resources:

- [m365 entra resourcenamespace list](https://pnp.github.io/cli-microsoft365/cmd/entra/resourcenamespace/resourcenamespace-list/)
- [m365 entra user session revoke](https://pnp.github.io/cli-microsoft365/cmd/entra/user/user-session-revoke/)

### Outlook

In the previous release, we added a command to update Outlook mailbox settings. In this release, we're adding the command to retrieve these settings for a mailbox.

To get the mailbox settings of the signed-in user, run:

```sh
m365 outlook mailbox settings get
```

To get the mailbox settings of a given user, run:

```sh
m365 outlook mailbox settings get --userName john.doe@contoso.onmicrosoft.com
```

For more information, check the following resources:

- [m365 outlook mailbox settings get](https://pnp.github.io/cli-microsoft365/cmd/outlook/mailbox/mailbox-settings-get)

### Tenant report settings

We also added a new command that allows you to retrieve report settings for an organization.

To get the tenant-level settings for Microsoft 365 reports, use:

```sh
m365 tenant report settings get
```

For more information check the following resources:

- [m365 tenant report settings get](https://pnp.github.io/cli-microsoft365/cmd/tenant/report/report-settings-get/)

## What's changed

This release also brings several enhancements and bug fixes to elevate the overall CLI experience. For instance we've aligned some option names and did a lot of other housekeeping.

### New sample script - Finding obsolete Microsoft 365 groups with PowerShell

We've also added a sample about getting a report of possibly unused Microsoft 365 groups. The sample script uses the CLI for Microsoft 365 to gather insights about SharePoint file activity within the SharePoint site connected to the Microsoft 365 group. It also checks the age of email conversations in the group mailbox. And lastly it checks the amount of people (group owners, members and guests) in the group. The script generates a report based on these statistics that can help us understand what groups are possibly obsolete.

For more information check the following resource:

[Finding obsolete Microsoft 365 groups with PowerShell](https://pnp.github.io/cli-microsoft365/sample-scripts/entra/find-obsolete-m365-groups/)

## Upcoming Changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 70 issues that are actively being developed and 103 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Shantha Kumar T](https://github.com/ktskumar)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [Christian Walling](https://github.com/cwdata)
- [Francesco Belacca](https://github.com/macel94)
- [Garry Trinder](https://github.com/garrytrinder)

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
