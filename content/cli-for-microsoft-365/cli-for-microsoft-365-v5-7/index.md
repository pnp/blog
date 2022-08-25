---
title: CLI for Microsoft 365 v5.7
date: 2022-08-23T12:53:34.970Z
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
type: popular
---

We've just published a new minor version of the CLI for Microsoft 365 with new commands for working with and managing Microsoft 365 and SharePoint Framework projects on any platform.

## Manage Microsoft 365 and SharePoint Framework projects on any platform

CLI for Microsoft 365 is a cross-platform CLI that allows you to manage various configuration settings of Microsoft 365 and SharePoint Framework projects no matter which operating system or shell you use.

While building solutions for Microsoft 365 expands beyond the Windows operating system, managing many platform settings is possible only through PowerShell on Windows. As more and more users work on non-Windows machines, it's inconvenient for them to use a Windows virtual machine to configure their tenants. With the CLI for Microsoft 365, you can configure your tenant no matter which operating system you use. Additionally, using CLI for Microsoft 365, you can manage your SharePoint Framework projects.

## New version of CLI for Microsoft 365 – v5.7

Following our monthly release cadence, we've released a new version of the CLI for Microsoft 365 with some new capabilities. Here are a few of the most noteworthy additions.

> For the complete list of what's new and changed, see the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v570).

### Checking Bookings

Meetings are a crucial part of any organization's business. Microsoft Bookings makes scheduling and managing appointments a breeze. Currently we added new commands to the CLI for Microsoft 365 that will help you list all bookings or get a specific booking.

To get the full list of bookings that are created for the tenant simply run the following command:

```sh
m365 booking business list
```

In order to retrieve the specified Microsoft Bookings business with name business name.

```sh
m365 booking business get --name 'business name'
```

For more information see the [business list](https://pnp.github.io/cli-microsoft365/cmd/booking/business/business-list/) and [business get](https://pnp.github.io/cli-microsoft365/cmd/booking/business/business-get/)

### SharePoint Online permission management

Managing permissions in SharePoint Online is a tedious task. With the CLI for Microsoft 365, you can manage permissions in SharePoint Online in a simple and easy way. In current release we introduced a couple of new commands that will help you with that. New commands allow to add or remove role assignment on list level as well as resetting role inheritance on web.

In order to add role assignment to list for a group with role definition name 'Full Control' run the following command:

```sh
m365 spo list roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --groupName "saleGroup" --roleDefinitionName "Full Control"
```

To do the same for a specific user simply do:

```sh
m365 spo list roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --upn "someaccount@tenant.onmicrosoft.com" --roleDefinitionName "Full Control"
```

In order to remove a role assignment given for a group we may run:

```sh
m365 spo list roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --listTitle "someList" --groupName "saleGroup"
```

To restore role inheritance for subsite

```sh
m365 spo web roleinheritance reset --webUrl https://contoso.sharepoint.com/sites/project-x
```

For more information see the [spo list roleassignment add](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-roleassignment-add/), [spo list roleassignment remove](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-roleassignment-remove/) and [spo web roleinheritance reset](https://pnp.github.io/cli-microsoft365/cmd/spo/web/web-roleinheritance-reset/)

### Removing external connection in Microsoft Search

There is no better place to find what you are looking for than Microsoft Search. We are constantly adding more and more commands to help you manage a variety of settings in Search. Now we allow the administrator to remove a specific external connection.

Removes external connection with id MyApp

```sh
m365 search externalconnection remove --id "MyApp"
```

For more information see the [search externalconnection remove](https://pnp.github.io/cli-microsoft365/cmd/search/externalconnection/externalconnection-remove/)

### Improvements to CLI for Microsoft 365 web page

CLI for Microsoft 365 has a large range of commands that you may use. Browsing the CLI for Microsoft 365 docs is a common thing to do in order to find the proper command or setting you might want to use. It's important that using our site is convenient and easy. In this release we added dark mode which may be turned on or off in the page header just next to the search bar. We also added a new page that presents the list of maintainers and contributors. If you are looking for someone who might help you out with CLI, well this is the page that might have that information.

For more information see the [CLI for Microsoft 365 team](https://pnp.github.io/cli-microsoft365/about/team/)

### Extend adding app command to support granting admin consent

It's always better if you may do something with just a single line of code. In order to streamline the process of app registration in Azure AD we extended the command with a new option which allows you to grant admin consent. Try it out today and see how easy and fast it is to register your new app.

In order to create a new Azure AD app registration for a app with specified Microsoft Graph application permissions, including admin consent

```sh
m365 aad app add --name 'My AAD app' --apisApplication 'https://graph.microsoft.com/Group.ReadWrite.All' --grantAdminConsent
```

For more information see the updated docs for [aad app add command](https://pnp.github.io/cli-microsoft365/cmd/aad/app/app-add/)


### Verify your environment configuration for using the latest version of the SharePoint Framework

Are you using the SPFx v1.15.2 release? Not sure if your environment is configured correctly? Well this single command is the answer to all of you problems. This commands helps you to verify if your environment meets all prerequisites for building solutions using a particular version of the SharePoint Framework. Node.js, npm, Yeoman, Gulp, TypeScript... you name it. All is verified if their meet the requirements of that particular version of the SharePoint Framework. If you miss any required tools or use a version that doesn't meet the SharePoint Framework requirements, the command will give you a list of recommendation how to address these issues. This is a must use command in order to be sure you are all set up and ready to start coding.

Verify if your environment meets the requirements to work with the SharePoint Framework

```sh
m365 spfx doctor
```

For more information see the [spfx doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor/)

### What else

These features are just the tip of the ice berg of what we've shipped in this version. Check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v570) for the complete list of what's new and improved.

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Arjun Menon](https://github.com/arjunumenon)
- [Garry Trinder](https://github.com/garrytrinder)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Michaël Maillot](https://github.com/michaelmaillot)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Patrick Lamber](https://github.com/plamber)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

Thank you all for the time you chose to spend on CLI for Microsoft 365 and for your help to advance it!

## Work in progress

Here are some things that we're currently working on.

### New Request command 

We're constantly seeking for ways to let you work with CLI for Microsoft 365 more efficiently and freely. Currently we are working on a new command that allows you to send a raw request to the targeted API. This command might be used for more advanced scenarios where CLI would take away all additional work regarding creating a request and passing authorization token or for some functionality which is not (yet) covered by a dedicated CLI command. For more information on that topic please do check [New command: request issue](https://github.com/pnp/cli-microsoft365/issues/3512) 

### SharePoint Online permission management commands

We're working on new commands that will help manage permissions in SharePoint Online on web, list and list item level (file and folder as well). The commands allow to break or reset role inheritance and add or remove role assignments to users and groups. If you are interested in our current progress please do check the [Fill void around spo permission management issue](https://github.com/pnp/cli-microsoft365/issues/3540)

### Microsoft 365 app commands

When building apps for Microsoft 365, next to your code, you also need to manage how your app is exposed to Microsoft 365. You need to register your application in Azure Active Directory, and depending what type of app you build, you might need to deploy it to an app catalog as well. All these properties are managed in different locations and we're thinking of ways that we could simplify it for you.

### Discussions 

CLI for Microsoft 365 is constantly growing and evolving. We're always looking for ways to improve. There are still many areas not covered by the CLI as well as many amazing ideas for unique features the tool might provide. Currently we are considering adding support with commands which will allow you to manage file versioning, document sets and comments a user may add to a list item or page in SharePoint Online. Your feedback will help us make the right decisions in which areas we should focus on. If you want to help out please do join the currently open [discussions](https://github.com/pnp/cli-microsoft365/discussions)

What else could we simplify? Let us know what you think by helping out with one of our [open issues](https://github.com/pnp/cli-microsoft365/issues) or chime in on our [discussions](https://github.com/pnp/cli-microsoft365/discussions)!

## Try it today

Get the latest release of CLI for Microsoft 365 from npm by executing:

```bash
npm i -g @pnp/cli-microsoft365
```

Alternatively, you can get the latest release from Docker by executing:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

If you need more help getting started or want more details about the commands, architecture, or project, go to [aka.ms/cli-m365](https://aka.ms/cli-m365). And if you see any room for improvement, please, don't hesitate to reach out to us either on [GitHub](https://github.com/pnp/cli-microsoft365/discussions) or [Twitter](https://twitter.com/climicrosoft365).
