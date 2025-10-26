---
title: CLI for Microsoft 365 v10.9
date: 2025-06-30T01:00:00.000Z
author: Jasey Waegebaert
githubname: jwaegebaert
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Docker
  - SharePoint
  - Viva Engage
type: regular
---

The CLI for Microsoft 365 strikes again! We've just published a new minor version of the CLI for Microsoft 365. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces new commands and improvements that will enhance the quality of your Microsoft 365 experience.

> Explore the [release notes](https://aka.ms/cli-m365/notes) for a neat overview of all the exciting features and improvements. 

## What's New

### Viva Engage

In this release, we've added a new command to help you manage Viva Engage communities more effectively. You can now remove communities that are no longer needed, providing better control over your Viva Engage environment and helping you maintain a clean and organized workspace.

To remove a Viva Engage community specified by name, run:

```sh
m365 viva engage community remove --displayName 'Software Engineers'
```

For more information, check the following resource:
- [viva engage community remove](https://pnp.github.io/cli-microsoft365/cmd/viva/engage/engage-community-remove/)

## What's changed

This release also brings some other great changes. Aside from many improvements in the codebase and bug fixes to elevate the overall CLI experience, there are several important updates we'd like to highlight.

### Node.js Support Update

We've removed support for Node.js 18, which has reached its end of life, as part of our ongoing effort to maintain compatibility with the latest and most secure versions of Node.js. This change ensures that CLI for Microsoft 365 continues to leverage the latest features and security improvements available in newer Node.js versions.

### Docker Improvements

We've enhanced our Docker support with several improvements:

- **Alpine 3.20 Image**: Added support for Alpine 3.20 in our Dockerfile, providing a more up-to-date and secure base image for containerized deployments.
- **Fixed Docker Image Completion**: Resolved issues with command completion in Docker environments, ensuring a smoother experience when using the CLI in containers.

These Docker improvements make it easier to deploy and use CLI for Microsoft 365 in containerized environments, whether you're running it in development, testing, or production scenarios.

### SharePoint Online Enhancements

We've improved how SharePoint Online page commands work with different page layouts. The `spo page` commands now properly handle emphasis sections for highlighting content and vertical sections for column-based layouts. This makes it much more reliable when creating or modifying pages with complex structures through the command line interface.

## Upcoming Changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 57 issues that are actively being developed and 110 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [Bhushan Salunkhe](https://github.com/I-BhushanSalunkhe)
- [Peter](https://github.com/quantrpeter)
- [Saurabh Tripathi](https://github.com/Saurabh7019)

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
