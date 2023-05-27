---
title: CLI for Microsoft 365 v6.8
date: 2023-05-31T08:00:00.000Z
author: Martin Lingstuyl
githubname: martinlingstuyl
categories:
  - CLI for Microsoft 365
images:
  - images/blog/cli-for-microsoft365/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - SharePoint
  - SharePoint Framework (SPFx)
type: popular
---

We've published a new minor version of CLI for Microsoft 365. 

[CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool. It helps you manage your Microsoft 365 tenant and SharePoint Framework projects. No matter which operating system or shell you use. This release is again brimming with new features and enhancements. We've added no less than **18 new commands** for managing multiple Microsoft 365 services. We've also added **40+ enhancements** to existing commands. This is also the release in which we added 🌶️ chili, our AI-based docs assistant. Besides that, we built an entirely new documentation site for the CLI for Microsoft 365. Interested? Read on for more details.

> Read the [release notes](https://aka.ms/cli-m365/notes) in full for all new features and improvements.
 
## What's new

### 🌶️ Chili, our AI-based docs assistant

Context-switching is sometimes called one of the big productivity killers. And yet, working with a command line interface will often make us want to open the project website or search the web in order to find out how something works. We recently added an AI-based search engine to our documentation site to make searching our site more convenient. This AI assistant is powered by Mendable. In this release, we bring the AI-based search engine to the CLI. You can now get answers to specific questions without leaving your terminal.

Ask Chili a question by running:

```sh
m365? "how can I upgrade my SPFx project?"
```

Or just type `m365?` and hit enter.

![cli-assistant](./images/cli-assistant.gif)

- [CLI assistant (chili)](https://pnp.github.io/cli-microsoft365/user-guide/chili/)
- [Check out **Mendable**](https://www.mendable.ai/)
 
### Setting up the CLI

Some people use the CLI for Microsoft 365 interactively. Other people use it to build scripts that can run autonomously. The new `m365 setup` command is a wizard-style command that helps you configure the CLI for Microsoft 365 for your needs. It will ask you a series of questions and based on your answers, it will configure the CLI for Microsoft 365 for you. It also has a few flags to quickly configure the CLI according to some presets based on best practices.

To configure the CLI using the setup wizard, run:

```sh
m365 setup
```

To configure the CLI with specific scripting presets, run:

```sh
m365 setup --scripting
```

- [m365 setup](https://pnp.github.io/cli-microsoft365/cmd/setup/)

### Working with Azure AD permissions

We've implemented a new command for working with permissions of Azure AD App Registrations. This command can be used within the context of working with an App Registration that is included in your project folder.

To add delegated and app-only scopes to your App Registration and grant admin consent, run:

```sh
m365 app permission add --applicationPermission 'https://graph.microsoft.com/User.ReadWrite.All' --delegatedPermission 'https://graph.microsoft.com/offline_access' --grantAdminConsent
```

- [app permission add](https://pnp.github.io/cli-microsoft365/cmd/app/permission/permission-add/)
- [Read more about working with Azure AD apps in your project](https://pnp.github.io/cli-microsoft365/user-guide/manage-microsoft-365-apps/)

### Listing plans in Planner Rosters

A new command has been added with which you can manage Planner Rosters. Rosters are a new type of container that you can use to manage access to Planner plans without the need for a Microsoft 365 group. You can now list plans that are contained in Microsoft Planner Rosters.

To list all Planner plans contained in a Roster where the currently logged-in user is a member, run:

```sh
m365 planner roster plan list
```

- [planner roster plan list](https://pnp.github.io/cli-microsoft365/cmd/planner/roster/roster-plan-list/)

### Bypassing the consent screen of a Power App

When a new Power App has been distributed in an organization, it's not unusual to get questions from users about the consent screen that's shown when first starting the app. You can now configure the Power App to bypass this consent screen when starting up.

To enable the bypass for a specific canvas app, run the following:

```sh
m365 pa app consent set --environment '4be50206-9576-4237-8b17-38d8aadfaa36' --name '3989cb59-ce1a-4a5c-bb78-257c5c39381d' --bypass true
```

- [pa app consent set](https://pnp.github.io/cli-microsoft365/cmd/pa/app/app-consent-set/)

### Working with Purview Information Protection

In this release, we started implementing some commands for working with sensitivity labels in Microsoft Purview. 

To get a list of sensitivity labels, execute:

```sh
m365 purview sensitivitylabel list
```

To get the details of a specific sensitivity label, run:

```sh
m365 purview sensitivitylabel get --id 6f4fb2db-ecf4-4279-94ba-23d059bf157e
```

To retrieve policy settings for sensitivity labels, run:

```sh
m365 purview sensitivitylabel policysettings list
```

- [purview sensitivitylabel list](https://pnp.github.io/cli-microsoft365/cmd/purview/sensitivitylabel/sensitivitylabel-list/)
- [purview sensitivitylabel get](https://pnp.github.io/cli-microsoft365/cmd/purview/sensitivitylabel/sensitivitylabel-get/)
- [purview sensitivitylabel policysettings list](https://pnp.github.io/cli-microsoft365/cmd/purview/sensitivitylabel/sensitivitylabel-policysettings-list//)

### Managing SharePoint

We've added more commands for working with SharePoint. We've made it easier to manage Application Customizers, ListView Command Sets and items in the recycle bin. You can also update large amounts of list items.

To remove an Application Customizer from a site, execute:

```sh
m365 spo applicationcustomizer remove --title "Some customizer" --webUrl https://contoso.sharepoint.com/sites/sales
```

To get a list of Application Customizers that are deployed tenant-wide, run:

```sh
m365 spo tenant applicationcustomizer list
```

To remove an Application Customizer that is deployed tenant-wide, run:

```sh
m365 spo tenant applicationcustomizer remove --title "Some customizer"
```

To remove a ListView Command Set that is deployed tenant-wide, run:

```sh
m365 spo tenant commandset remove --title "Some command set"
```

To update the properties of a ListView Command Set that is deployed tenant-wide, run:

```sh
m365 spo tenant commandset  set --id 3  --clientSideComponentProperties '{ "someProperty": "Some value" }'
```

To update a lot of items as quick as possible, run:

```sh
m365 spo listitem batch set --filePath "C:\Path\To\Csv\CsvFile.csv" --webUrl https://contoso.sharepoint.com/sites/project-x --listTitle "Demo List"
```

Remove an item from the first-stage recycle bin:

```sh
m365 spo site recyclebinitem remove --siteUrl https://contoso.sharepoint.com/sites/sales --ids "06ca4fe4-3048-4b76-bd41-296fed4c9881"
```

Move an item to the second-stage recycle bin:

```sh
m365 spo site recyclebinitem move --siteUrl https://contoso.sharepoint.com/sites/sales --ids "06ca4fe4-3048-4b76-bd41-296fed4c9881"
```

- [spo applicationcustomizer remove](https://pnp.github.io/cli-microsoft365/cmd/spo/applicationcustomizer/applicationcustomizer-remove/)
- [spo listitem batch set](https://pnp.github.io/cli-microsoft365/cmd/spo/listitem/listitem-batch-set/)
- [spo site recyclebinitem move](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-recyclebinitem-move/)
- [spo site recyclebinitem clear](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-recyclebinitem-clear/)
- [spo tenant applicationcustomizer list](https://pnp.github.io/cli-microsoft365/cmd/spo/tenant/tenant-applicationcustomizer-list/)
- [spo tenant applicationcustomizer remove](https://pnp.github.io/cli-microsoft365/cmd/spo/tenant/tenant-applicationcustomizer-remove/)
- [spo tenant commandset remove](https://pnp.github.io/cli-microsoft365/cmd/spo/tenant/tenant-commandset-remove/)
- [spo tenant commandset set](https://pnp.github.io/cli-microsoft365/cmd/spo/tenant/tenant-commandset-set/)

### Working with Microsoft Teams

Several additional commands have been made available for Teams. You can now remove members from a group chat and get a list of meeting transcripts.

To remove a member from a Teams chat, run:

```sh
m365 teams chat member remove --chatId 19:8b081ef6-4792-4def-b2c9-c363a1bf41d5_5031bb31-22c0-4f6f-9f73-91d34ab2b32d@unq.gbl.spaces --userName john.doe@contoso.com
```

To get meeting transcripts for a meeting, run:

```sh
m365 teams meeting transcript list --meetingId MSo1N2Y5ZGFjYy03MWJmLTQ3NDMtYjQxMy01M2EdFGkdRWHJlQ
```

- [teams chat member remove](https://pnp.github.io/cli-microsoft365/cmd/teams/chat/chat-member-remove/)
- [teams meeting transcript list](https://pnp.github.io/cli-microsoft365/cmd/teams/meeting/meeting-transcript-list/)

## What's changed

### Working with the SharePoint Term Store

We've shipped several enhancements that are very useful when working with the SharePoint Term Store. You no longer need to be a SharePoint administrator to manage the term store. If you only have permissions as a term store administrator, you can manage terms, term sets and term groups in the global term store using the CLI for Microsoft 365. Aside from the global term store, you can now also manage site collection term stores. For both scenarios you'll need to use the new `--webUrl` option that's added to every command. The CLI for Microsoft 365 will now connect to the global or local term store, using the site you've specified. 

To get a list of terms of a global term set, without being a SharePoint admin, run:

```sh
m365 spo term list --termGroupName "DMS" --termSetName "Business process" --webUrl "https://contoso.sharepoint.com/sites/project-x"
```

To get a list of term sets of a global term group, without being a SharePoint admin, run:

```sh
m365 spo term set list --termGroupName "DMS" --webUrl "https://contoso.sharepoint.com/sites/project-x"
```

To get a list of terms of a local (site-specific) term set, run:

```sh
m365 spo term list --termGroupName "Sitecollection - contoso.sharepoint.com-sites-Project-x" --termSetName "Themes" --webUrl "https://contoso.sharepoint.com/sites/project-x"
```

The following commands were impacted:

- [spo term add](https://pnp.github.io/cli-microsoft365/cmd/spo/term/term-add/)
- [spo term get](https://pnp.github.io/cli-microsoft365/cmd/spo/term/term-add/)
- [spo term list](https://pnp.github.io/cli-microsoft365/cmd/spo/term/term-list/)
- [spo term group get](https://pnp.github.io/cli-microsoft365/cmd/spo/term/term-group-get/)
- [spo term group list](https://pnp.github.io/cli-microsoft365/cmd/spo/term/term-group-list/)
- [spo term set add](https://pnp.github.io/cli-microsoft365/cmd/spo/term/term-set-add/)
- [spo term set get](https://pnp.github.io/cli-microsoft365/cmd/spo/term/term-set-get/)
- [spo term set list](https://pnp.github.io/cli-microsoft365/cmd/spo/term/term-set-list/)

### Updating Azure AD Users

You could already update user information for Azure AD users. In the previous release, we added a lot of well-known options, like 'job title' and 'office location'. We've now extended this to any property, even if it's unknown to the CLI for Microsoft 365.

To update the employee hire date of a user, run:

```sh
m365 aad user set --userPrincipalName "adele.vance@contoso.com" --employeeHireDate "2022-01-01"
```

To create a new user and set the employee hire date, run:

```sh
m365 aad user add --displayName "Adele Vance" --userName "adele.vance@contoso.com" --password "SomePassw0rd" --companyName Contoso --department Sales --forceChangePasswordNextSignIn --employeeHireDate "2023-05-31"
```

- [aad user add](https://pnp.github.io/cli-microsoft365/cmd/aad/user/user-add/)
- [aad user set](https://pnp.github.io/cli-microsoft365/cmd/aad/user/user-set/)

### 🌍 One more thing: We've launched a new website!!

Updating our website was a thing we wanted to do for quite some time now. We've swapped to using a new static site generator: Docusaurus. It's been a major thing in terms of development time and discussions internally. But if we've done our job well, the changes should be minimal. 🤞 Of course, you may notice some styling changes... 😊some things have shifted slightly. We also temporarily dropped the search bar. (We'll get it back in due time!) But in the meantime, we fortunately have our AI assistant, so you can still search for answers to your questions.

We hope to hear your feedback on this one! Do drop us a comment using one of the available channels!

### And there's more

We've been working tirelessly to enhance our capabilities. 

Take a look at our release notes below for the full rundown of everything we've done. Check it out! We're very curious to hear your experiences.

- [Changelog v6.8.0](https://pnp.github.io/cli-microsoft365/about/release-notes/#v680)

## What's next

Here are some things that we are currently working on.

### More commands and enhancements

We are always looking to add more commands to CLI for Microsoft 365. 

We are busy implementing commands across several Microsoft 365 services, such as Power Platform, SharePoint Online, and Microsoft Purview.

If you have any ideas or suggestions for new commands, please let us know by creating a [new issue](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=new-command.yml&title=New+command%3A+%3Cshort+description%3E) in the GitHub Issues list, or reaching out to us on our [community Discord server](https://aka.ms/cli-m365/discord) to discuss.

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Ganesh Sanap](https://github.com/ganesh-sanap)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Nicolas Camara](https://github.com/nickscamara)
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
