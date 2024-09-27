---
title: CLI for Microsoft 365 v9.1
date: 2024-09-30T08:00:00.000Z
author: Jasey Waegebaert
githubname: Jwaegebaert
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Power Automate
  - Power Platform
  - SharePoint
  - SharePoint Premium
  - Microsoft Graph
  - Microsoft Teams
  - Viva Engage
type: popular
---

We have just published a new minor version of CLI for Microsoft 365. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces several new commands that will enhance the quality of your Microsoft 365 experience.

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover various exciting features and improvements that will revolutionize your Microsoft 365 journey. 

## What's New

### File Management Enhancements

#### Move Files with Ease

We’ve introduced the `file move` command, allowing you to move files to a new location using the Microsoft Graph API. This is a powerful addition for those who frequently reorganize content within their SharePoint environments.

Here’s how you can move a file:

```sh
m365 file move --webUrl https://contoso.sharepoint.com/sites/project --sourceUrl "/sites/project/Shared Documents/Document.pdf" --targetUrl "/sites/IT/Shared Documents"
```

For more details, visit [file move](https://pnp.github.io/cli-microsoft365/cmd/file/file-move/).

### Power Automate Management

#### Manage Recycle Bin Items

Managing soft-deleted flows just got simpler! The new commands for Power Automate allow you to list and restore flows from the recycle bin.

List all soft-deleted flows:

```sh
m365 flow recyclebinitem list --environmentName Default-d87a7535-dd31-4437-bfe1-95340acd55c5
```

Restore a soft-deleted flow:

```sh
m365 flow recyclebinitem restore --environmentName Default-d87a7535-dd31-4437-bfe1-95340acd55c5 --flowName 5923cb07-ce1a-4a5c-ab81-257ce820109a
```

Explore more at [flow recyclebinitem list](https://pnp.github.io/cli-microsoft365/cmd/flow/recyclebinitem/recyclebinitem-list/) and [flow recyclebinitem restore](https://pnp.github.io/cli-microsoft365/cmd/flow/recyclebinitem/recyclebinitem-restore/).

### SharePoint Management

#### Streamlined Folder Sharing

We’ve expanded SharePoint commands to include new options for managing folder-sharing links. Now, you can easily create, remove, or clear all sharing links associated with a folder.

Create a new sharing link for a folder:

```sh
m365 spo folder sharinglink add --webUrl https://contoso.sharepoint.com/sites/demo --folderUrl /sites/demo/shared%20documents/Folder --type view --scope anonymous
```

Remove all sharing links from a folder:

```sh
m365 spo folder sharinglink clear --webUrl https://contoso.sharepoint.com/sites/demo --folderUrl '/sites/demo/Shared Documents/folder1'
```

Remove a specific sharing link from a folder:

```sh
m365 spo folder sharinglink remove --webUrl https://contoso.sharepoint.com/sites/demo --folderUrl /sites/demo/shared%20documents/Folder --id c391b57d-5783-4c53-9236-cefb5c6ef323
```

For more information check the following resources:
- [m365 spo folder sharinglink add](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-sharinglink-add/)
- [m365 spo folder sharinglink clear](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-sharinglink-clear/)
- [m365 spo folder sharinglink remove](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-sharinglink-remove/)

#### Advanced Site Administration

Adding and removing site collection administrators is now more efficient with our new commands. Plus, you can now set sharing permissions for a site collection directly from the CLI.

Add a group as a secondary site collection administrator:

```sh
m365 spo site admin add --siteUrl https://contoso.sharepoint.com --groupName SP_Administrators --asAdmin
```

Remove a user as site collection admin:

```sh
m365 spo site admin remove --siteUrl https://contoso.sharepoint.com --userId 600713c5-53c6-4f24-b454-3c35e22b2639
```

Update the sharing permissions for a site so only owners can share files and the site:

```sh
m365 spo site sharingpermission set --siteUrl https://siteaddress.com/sites/sitename --capability ownersOnly
```

For more information check the following resources:
- [m365 spo site admin add](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-admin-add/)
- [m365 spo site admin remove](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-admin-remove/)
- [m365 spo site sharingpermission set](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-sharingpermission-set/)

### SharePoint Premium

We’re excited to introduce commands to list SharePoint Premium content centers, helping you manage these advanced services more effectively.

Get information about the SharePoint Premium content centers:

```sh
m365 spp contentcenter list
```

For more details, visit [spp contentcenter list](https://pnp.github.io/cli-microsoft365/cmd/spp/contentcenter/contentcenter-list/).

### Microsoft Teams

We're not stopping there! We've also added a new command to download a transcript for a given meeting. This is a great addition for those who want to keep a record of their meeting conversations.

Save a transcript for a specific meeting:

```sh
m365 teams meeting transcript get --userName garthf@contoso.com --meetingId MSo1N2Y5ZGFjYy03MWJmLTQ3NDMtYjQxMy01M2EdFGkdRWHJlQ --id MSMjMCMjNzU3ODc2ZDYtOTcwMi00MDhkLWFkNDItOTE2ZDNmZjkwZGY4 --outputFile c:/Transcript.vtt
```

For more information, visit [teams meeting transcript get](https://pnp.github.io/cli-microsoft365/cmd/teams/meeting/meeting-transcript-get/)

### Viva Engage

Last but not least, we've added a new command to list all Viva Engage communities. This is a great addition for those who want to manage their communities more effectively.

List all Viva Engage communities:

```sh
m365 viva engage community list
```

For more information, visit [viva engage community list](https://pnp.github.io/cli-microsoft365/cmd/viva/engage/engage-community-list/)

## What's Changed

This release isn't just about new commands. We’ve also refined existing ones. Notable changes include bug fixes, enhanced functionality for SharePoint commands, and expanded support for SPFx v1.20.0-rc.1. We’ve also improved documentation to help you get the most out of these tools.

If you are eager to go over all of the details and improvements added to this release, do not hesitate to check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v910) to learn more.

## Upcoming Changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 98 issues that are actively being developed and 102 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release.

### Hacktoberfest is Here!

Hacktoberfest has started, and it's the perfect time to contribute! We've labeled issues in our repository with **hacktoberfest** to make it easier for you to find and contribute to them. Whether you're a seasoned developer or just starting, your contributions are welcome. Their are already 62 issues labeled with **hacktoberfest** and we're looking forward to seeing your pull requests. You can find a whole list of issues [here](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aopen+label%3A%22help+wanted%22+label%3A%22hacktoberfest%22).

We value your input and ideas. If you have any suggestions for new commands, don't hesitate to share them with us. Create a [new issue](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=new-command.yml&title=New+command%3A+%3Cshort+description%3E) on our GitHub Issues list or join our vibrant [community Discord server](https://aka.ms/cli-m365/discord) to engage in discussions.

Together, let's shape the future of CLI for Microsoft 365 and unlock even greater possibilities.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Albert-Jan Schot](https://github.com/appieschot)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shoutout and high fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to provide us with their insights:

- [apc005](https://github.com/apc005)
- [dshirk-uci](https://github.com/dshirk-uci)
- [dschenlin](https://github.com/dschenlin)
- [fra86435](https://github.com/fra86435)
- [mhouvenaghel](https://github.com/mhouvenaghel)
- [Nikolai Essel](https://github.com/nikolaiessel)
- [Paul](https://github.com/paul-gladoon)
- [Stefan Bauer](https://github.com/StfBauer)
- [Tobias Maestrini](https://github.com/tmaestrini)

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
