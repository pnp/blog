---
title: CLI for Microsoft 365 v6.7
date: 2023-05-02T17:00:00.000Z
author: Martin Lingstuyl
githubname: martinlingstuyl
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - SharePoint
  - SharePoint Framework (SPFx)
type: popular
---

We've published a new minor version of CLI for Microsoft 365. 

[CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool. It helps you manage your Microsoft 365 tenant and SharePoint Framework projects. No matter which operating system or shell you use.

> Read the [release notes](https://aka.ms/cli-m365/notes) in full for all new features and improvements.
 
## What's new

### Retrieving Application Customizers

Our work on simplifying working with SharePoint Framework extensions, like Application Customizers, is steadily moving forward. Today we're launching the ability to retrieve a specific Application Customizer, regardless of where they are registered in a SharePoint site: 

Retrieve an application customizer by title:

```sh
m365 spo applicationcustomizer get --title "Some customizer" --webUrl https://contoso.sharepoint.com/sites/sales
```


Retrieve an application customizer, registered on site-level, by clientSideComponentId:

```sh
m365 spo applicationcustomizer get --clientSideComponentId 7096cded-b83d-4eab-96f0-df477ed7c0bc --webUrl https://contoso.sharepoint.com/sites/sales --scope site
```

- [spo applicationcustomizer get](https://pnp.github.io/cli-microsoft365/cmd/spo/applicationcustomizer/applicationcustomizer-get/)

### Clearing the SharePoint site recycle bin

Working with the recycle bin programmatically has become easier as well. You can now clear a site recycle bin with a simple one-liner.

Clear all items from the first-stage recycle bin:

```sh
m365 spo site recyclebinitem clear --siteUrl https://contoso.sharepoint.com/sites/sales
```

Clear all items from the second-stage recycle bin:

```sh
m365 spo site recyclebinitem clear --siteUrl https://contoso.sharepoint.com/sites/sales --secondary
```

- [spo site recyclebinitem clear](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-recyclebinitem-clear/)

## What's changed

### Retrieving items from SharePoint lists and libraries

We've shipped several enhancements that are very useful when working with lists and libraries on SharePoint. Instead of a limited set, you can now get all list items from large lists. We also implemented extra options to retrieve specific file and folder fields, and the ability to filter files and folders in a given library.

Get all items in a list, regardless of the list size:

```sh
m365 spo listitem list --listTitle "Demo List" --webUrl https://contoso.sharepoint.com/sites/project-x
```

Only get the first 100 items in a list:

```sh
m365 spo listitem list --listTitle "Demo List" --webUrl https://contoso.sharepoint.com/sites/project-x --pageSize 100
```

Retrieve all files from a folder for which the filename starts with the word 'Demo':

```sh
m365 spo file list --webUrl https://contoso.sharepoint.com/sites/project-x --folder 'Shared Documents' --filter "startswith(Name, 'Demo')" --recursive
```

Retrieve all files from a folder and retrieve the list item Id as well as the filename:

```sh
m365 spo file list --webUrl https://contoso.sharepoint.com/sites/project-x --folder 'Shared Documents' --fields "ListItemAllFields/Id,Name" --recursive
```

The same works when retrieving folders:

Retrieve all folders for which the folder name starts with the word 'Demo':

```sh
m365 spo folder list --webUrl https://contoso.sharepoint.com/sites/project-x --parentFolderUrl 'Shared Documents' --filter "startswith(Name, 'Demo')" --recursive
```

- [spo listitem list](https://pnp.github.io/cli-microsoft365/cmd/spo/listitem/listitem-list/)
- [spo file list](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-list/)
- [spo folder list](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-list/)

### Updating Azure AD Users

You could already update user information for Azure AD users. We've made managing users even easier, by adding a lot of new options. You can now update the user company name, preferred language, usage location, job title and office location and more. 

Update multiple properties of a user:

```sh
m365 aad user set --userPrincipalName steve@contoso.onmicrosoft.com --firstName John --lastName Doe --jobTitle "Sales Manager" --companyName Contoso --department Sales --officeLocation "New York"
```

- [aad user set](https://pnp.github.io/cli-microsoft365/cmd/aad/user/user-set/)
### And there's more

We've been working tirelessly to enhance our capabilities. How about support for non-public clouds? We've now got it! How about getting extra information when listing flow runs? It's now included.

Take a look at our release notes below for the full rundown of everything we've done. Check it out! We're very curious to hear your experiences.

- [Changelog v6.7.0](https://pnp.github.io/cli-microsoft365/about/release-notes/#v670)

## What's next

Here are some things that we are currently working on.

### More commands and enhancements

We are always looking to add more commands to CLI for Microsoft 365. 

We are busy implementing commands across several Microsoft 365 services, such as Power Platform, SharePoint Online, and Microsoft Purview.

If you have any ideas or suggestions for new commands, please let us know by creating a [new issue](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=new-command.yml&title=New+command%3A+%3Cshort+description%3E) in the GitHub Issues list, or reaching out to us on our [community Discord server](https://aka.ms/cli-m365/discord) to discuss.

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Ganesh Sanap](https://github.com/ganesh-sanap)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Saurabh K. Tripathi](https://github.com/Saurabh7019)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

Thank you all for the time you chose to spend on CLI for Microsoft 365 and for your help to advance it!

### High fives

CLI for Microsoft 365 wouldn't be where it is today if it weren't for our users who provide us with feedback. High fives to the following people who took the time to share their feedback and ideas for improvement with us (in alphabetical order):

- [Dakota Wray](https://github.com/DakotaWray2)
- [doronyaary](https://github.com/doronyaary)
- [Joshua Probst](https://github.com/joshua-probst)
- [Siddharth Vaghasia](https://github.com/siddharth-vaghasia)

## Try it today!

Get the latest release of CLI for Microsoft 365 from npm by executing:

```bash
npm i -g @pnp/cli-microsoft365
```

Or, you can get the latest release from Docker by executing:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

## Need more info?

If you need more help getting started or want more details about the commands, architecture, or project, go to [aka.ms/cli-m365](https://aka.ms/cli-m365).

## Get in touch!

If you see any room for improvement, please, don't hesitate to reach out to us either on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord), or [Twitter](https://twitter.com/climicrosoft365).
