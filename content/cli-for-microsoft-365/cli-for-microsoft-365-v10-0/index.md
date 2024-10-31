---
title: CLI for Microsoft 365 v10
date: 2024-10-31T01:00:00.000Z
author: Adam Wójcik
githubname: Adam-it
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Entra ID
  - Viva
  - Viva Engage
  - SharePoint
  - SharePoint Premium
type: popular
---

We have just published a new major version of CLI for Microsoft 365 v10. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This major release introduces several new commands that will enhance the quality of your Microsoft 365 experience as well as numerous breaking changes.

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover an array of exciting features and improvements that will revolutionize your Microsoft 365 journey. 
 
## The new major version of CLI for Microsoft 365 – v10

We know, another major release! But this one is not an ASAP reaction to a breaking change we needed to adapt to. This one is is the longly awaited and planned release that will introduce a lot of helpful improvements to our product. The [list of breaking changes](https://pnp.github.io/cli-microsoft365/about/release-notes#%EF%B8%8F-breaking-changes) is quite long but it introduces a lot of helpful and necessary improvements to CLI for Microsoft 365 and also aligns it with the the latest changes and naming updates of Microsoft 365 products and apps. 

A good example of necessary changes that were done in order to align with Microsoft 365 were 
- [removal of the `AAD` alias](https://pnp.github.io/cli-microsoft365/v10-upgrade-guidance#removed-aad-options-and-aliasses-to-aad-commands), which means from now on we will be using only the `Entra` word when referring to Entra ID
- We also [removed aliases to good old Yammer and therefore leaving only Viva Engage](https://pnp.github.io/cli-microsoft365/v10-upgrade-guidance#removed-aad-options-and-aliasses-to-aad-commands) to align all our commands with the current state of Microsoft 365

We also introduced breaking changes that will greatly improve some functionalities of our product. For example, we updated the API endpoints that were used in [spo folder move](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-move/) and [spo folder copy](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-copy/) commands so that now it will be possible to manage large folders between site collections. As now we use different APIs we also need to adapt our command options to what is supported in the new endpoints. You may read more details about this change here: 

- [Updated command spo folder move and spo folder copy](https://pnp.github.io/cli-microsoft365/v10-upgrade-guidance#updated-command-spo-folder-move-and-spo-folder-copy)

Similar improvements we introduced to [spo file copy](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-copy/) and [spo file move](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-move/) commands. We also updated those commands to new endpoints to ensure the command's functionality and reliability. You may find more details about those changes here: 

- [Updated command spo file copy](https://pnp.github.io/cli-microsoft365/v10-upgrade-guidance#updated-command-spo-file-copy)
- [Updated command spo file move](https://pnp.github.io/cli-microsoft365/v10-upgrade-guidance#updated-command-spo-file-move)

Other breaking changes were introduced to align some of our commands with our conventions so that we are consistent and follow similar approaches in all places. For example we: 
- added `--force` option to [spo site appcatalog remove](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-appcatalog-remove)
- or we updated the purpose of option `displayName` for [entra m365group set command](https://pnp.github.io/cli-microsoft365/cmd/entra/m365group/m365group-set) 

This is just the tip of the iceberg of the necessary and longly awaited updates we introduced to CLI for Microsoft 365 that will greatly improve its usage and align it with Microsoft 365!

> To help you go over all the changes and upgrade to v10, we prepared a summary of the breaking changes and the recommended actions. For more information see the [v10 Upgrade Guidance](https://pnp.github.io/cli-microsoft365/v10-upgrade-guidance) on our docs.

> For the complete list of what's new and changed, see the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v1000).

## What else is new

### New SharePoint Premium commands

This major release also introduces a brand new [spp model list](https://pnp.github.io/cli-microsoft365/cmd/spp/model/model-list/) command which will allow you to retrieve the list of unstructured document processing models.

The usage is as always very easy and in order to retrieve a list of SharePoint Premium unstructured document processing models on the content center site, just run:

```sh
m365 spp model list --siteUrl https://contoso.sharepoint.com/sites/ContentCenter
```

For more information check the following resources:
- [m365 spp model list](https://pnp.github.io/cli-microsoft365/cmd/spp/model/model-list/)

### New Viva engage command

We don't stop enhancing the Viva Engage area with new commands that will help you automate and manage this part of Microsoft 365. In this release, we added a command that will allow you to get all users within a specified Microsoft 365 Viva Engage community.

To list all admins from a community specified by display name run:

```sh
m365 viva engage community user list --communityDisplayName "All company" --role Admin
```

Or you may get the list of members by specifying the group ID by running:

```sh
m365 viva engage community user list --entraGroupId b6c35b51-ebca-445c-885a-63a67d24cb53 --role Member
```

For more information check the following resources:
- [m365 viva engage community user list](https://pnp.github.io/cli-microsoft365/cmd/viva/engage/engage-community-user-list/)

### Publish your SharePoint Online Modern page

This is a straightforward and simple thing that is missing in CLI for Microsoft 365, I mean, was missing till now. 

Now you may publish a modern page by running: 

```sh
m365 spo page publish --webUrl https://contoso.sharepoint.com/sites/Marketing --name "Style guide.aspx"
```

For more information check the following resources:
- [m365 spo page publish](https://pnp.github.io/cli-microsoft365/cmd/spo/page/page-publish/)

### Update your SharePoint folder sharing link

We already have a lot of commands that allow you to automate and manage SharePoint Online folder-sharing links and in this release we added another one that will now allow you to update a sharing link of a folder.

For example to update the expiration date-time of an anonymous sharing link for a folder specific by folder ID, simply run:

```sh
m365 spo folder sharinglink set --webUrl https://contoso.sharepoint.com/sites/demo --folderId daebb04b-a773-4baa-b1d1-3625418e3234 --id 7c9f97c9-1bda-433c-9364-bb83e81771ee --expirationDateTime '2022-11-30T00:00:00Z'
```

Or to update the expiration date-time of an anonymous sharing link for a folder specific by folder URL, run: 

```sh
m365 spo folder sharinglink set --webUrl https://contoso.sharepoint.com/sites/demo --folderUrl /sites/demo/shared%20documents/Folder --id 7c9f97c9-1bda-433c-9364-bb83e81771ee --expirationDateTime '2022-11-30T00:00:00Z'
```

For more information check the following resources:
- [m365 spo folder sharinglink set](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-sharinglink-set/)

### New SharePoint admin management command

In this release, we also introduced a new command that allows you to retrieve the information about default site group membership.

It is as easy as:

```sh
m365 spo tenant site membership list --siteUrl https://contoso.sharepoint.com
```

For more information check the following resources:
- [m365 spo tenant site membership list](https://pnp.github.io/cli-microsoft365/cmd/spo/tenant/tenant-site-membership-list/)

## What's changed

Besides all these new commands, we've also made some changes to some existing commands. A few bugs have been fixed and the codebase has been polished. Let's have a closer look at some of the updates that stand out the most.

### Extended `login` command with `--ensure` option

We updated our `login` command adding a new option that ensures that the user is signed in. If the user isn't signed in, it initiates the login flow. This option will allow you to update and simplify your scripts as now you will no longer need to run the `m365 status` command first to ensure that you are logged in and if not run the `login` command which is typically the first thing we do in almost every script. Now you may do all that by simply running `m365 login --ensure`.

- [m365 login](https://pnp.github.io/cli-microsoft365/cmd/login/)

### Enhanced the `spo list remove` command with `--recycle` option

We improved the [spo list remove](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-remove) with a new `--recycle` option that when used will send the list to the recycle bin instead of permanently deleting it.

### Renamed the default CLI for Microsoft 365 app registration created during `m365 setup`

Not so long ago we updated the default behavior of the login command which now requires you to provide an app registration which will allow CLI for Microsoft 365 to sign in to your tenant. You may read more details about this change in [previous major release blog post](https://pnp.github.io/blog/cli-for-microsoft-365/cli-for-microsoft-365-v9-0/#the-new-major-version-of-cli-for-microsoft-365--v9). Along with this change we updated the `m365 setup` command so that it now also allows you to create the required app registration on your tenant along with all required settings and selected set of permissions. In this release we updated the default name of this app to 'CLI for M365', previously it was 'CLI for Microsoft 365'. Unfortunately, it turned out that the word 'Microsoft' in your app registration name blocks it from becoming multitenant. That is why in order to avoid this unnecessary problem we updated the name.

## Upcoming changes

Curious about what lies ahead? We are excited to share some of our ongoing projects and initiatives.

Right now, there are over 50 opened PRs with new awesome features that will soon be added to CLI for Microsoft 365, and [89 issues that are up for grabs](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22). We're working hard to bring you even more exciting features and improvements in the next release. 

But we don't stop there. We value your input and ideas. If you have any suggestions for new commands, don't hesitate to share them with us. Create a [new issue](https://github.com/pnp/cli-microsoft365/issues/new/choose) on our GitHub Issues list or join our vibrant [community Discord server](https://aka.ms/cli-m365/discord) to engage in discussions.

Sharing is Caring!

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Can Arslan](https://github.com/mc2rcanarslan)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Michał Kornet](https://github.com/mkm17)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Shantha Kumar T](https://github.com/ktskumar)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shoutout and high fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to provide us with their insights:

- [David Wales](https://github.com/daviewales)

## Get started today!

Experience the power of the CLI for Microsoft 365 by getting the latest release from npm:

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

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord), or [X](https://x.com/climicrosoft365), or [LinkedIn](https://www.linkedin.com/company/m365pnp). Don't hesitate to connect with us. Your input plays a vital role in shaping the future of CLI for Microsoft 365.
