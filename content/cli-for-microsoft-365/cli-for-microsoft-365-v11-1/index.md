---
title: CLI for Microsoft 365 v11.1
date: 2025-10-31T01:00:00.000Z
author: Adam Wójcik
githubname: Adam-it
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - SharePoint
type: popular
---

We're thrilled to introduce a new minor release of CLI for Microsoft 365 v11.1, bringing new commands and improvements that enhance your Microsoft 365 workflow. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release builds upon the foundation of v11.0, introducing several new commands and improvements designed to enhance functionality and align with the latest Microsoft 365 innovations.

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover all the new features and improvements in this release. 
 
## CLI for Microsoft 365 v11.1 – Minor release overview

CLI for Microsoft 365 v11.1 continues our commitment to providing powerful, reliable automation tools for Microsoft 365. This minor release introduces new commands for managing SharePoint web alerts. Additionally, we're thrilled to share the incredible contributions our community made during Hacktoberfest 2025, significantly improving our codebase by refactoring command options validation to use ZOD and documentation.

## New commands

### SharePoint list alerts

In this release, we added two new commands that allow you to list all SharePoint list alerts and remove an existing alert. Let's go over a few examples of how to use these new commands:

In order to list all SharePoint list alerts in a specific site, run:

```sh
m365 spo web alert list --webUrl https://contoso.sharepoint.com/sites/Marketing
```

To list alerts for a SharePoint list by listUrl:

```sh
m365 spo web alert list --webUrl https://contoso.sharepoint.com/sites/Marketing --listUrl /sites/Marketing/lists/Tasks
```

To list alerts for a specific list by title and user by username, execute the following:

```sh
m365 spo web alert list --webUrl https://contoso.sharepoint.com/sites/Marketing --listTitle "Tasks" --userName jane.doe@contoso.com
```

It is possible to remove an alert by its ID using the following command:

```sh
m365 spo web alert remove --webUrl https://contoso.sharepoint.com/sites/Marketing --id 7cbb4c8d-8e4d-4d2e-9c6f-3f1d8b2e6a0e
```

For more information, check the following resources:

- [spo web alert list](https://pnp.github.io/cli-microsoft365/cmd/spo/web/web-alert-list)
- [spo web alert remove](https://pnp.github.io/cli-microsoft365/cmd/spo/web/web-alert-remove/)

## Additional improvements

Beyond the new commands, we've made several important improvements to existing functionality:

### Refactored command options validation to use ZOD

To enhance the maintainability of our codebase, we managed to refactor 16 commands validation mechanisms to utilize ZOD, a TypeScript-first schema declaration and validation library. This change improves type safety, reduces boilerplate code, and streamlines the validation process across various commands in CLI for Microsoft 365.

### Permissions management

To help users better understand the permissions required to execute specific commands, we have added detailed permission information to the documentation of over 100 commands. This enhancement aims to improve user experience by providing clarity on the necessary minimal permissions that are required for effective command execution.

## Upcoming changes

We continue to work on exciting new features and improvements for future releases.

**In development:**
- Over 30 pull requests in progress with new features and updates
- [115 issues available for grabs](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22)

### Hacktoberfest 2025

During Hacktoberfest 2025, our community came together to make remarkable contributions to the CLI for Microsoft 365 project. We are incredibly grateful for the outstanding work done by all participants who dedicated their time and expertise to improve the project.

The community's efforts this Hacktoberfest were particularly impactful in two key areas:

**Command options validation refactoring**: Contributors successfully refactored 16 commands to use Zod for validation.

**Documentation enhancement**: The community added minimal required permissions documentation to over 100 commands, making it much easier for users to understand exactly what permissions are needed to execute each command. This enhancement is invaluable for security planning, implementing least-privilege access, and helping users work more confidently with the CLI.

These contributions demonstrate the power of open-source collaboration. Thank you for making such a meaningful impact on the project!

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Ayush Jain](https://github.com/URAYUSHJAIN)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Malay Kumar](https://github.com/Malay-dev)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nirav Raval](https://github.com/nirav-raval)
- [Nishkalank Bezawada](https://github.com/NishkalankBezawada)
- [Reshmee Auckloo](https://github.com/reshmee011)
- [Sanket Mundra](https://github.com/sanket-mundra)
- [santhosh teja piridi](https://github.com/santhosh-7777)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Siddheya Kulkarni](https://github.com/Asymtode712)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Tobias Maestrini](https://github.com/tmaestrini)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [Mark van Dijk](https://github.com/MarksPoint)
- [Michał Kornet](https://github.com/mkm17)

Thank you for making CLI for Microsoft 365 better for everyone!

## Get started today!

Experience the power of CLI for Microsoft 365 by getting the latest release from npm:

```bash
npm i -g @pnp/cli-microsoft365
```

Alternatively, you can access the latest release from Docker:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

## Need more information?

For additional guidance on getting started or to explore detailed information about commands, architecture, or the project itself, visit [aka.ms/cli-m365](https://aka.ms/cli-m365).

## Stay connected!

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord) or [Bluesky](https://bsky.app/profile/climicrosoft365.bsky.social). Don't hesitate to connect with us. Your input plays a vital role in shaping the future of CLI for Microsoft 365.
