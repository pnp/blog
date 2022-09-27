---
title: CLI for Microsoft 365 v5.8
date: 2022-09-26T22:00:00.000Z
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

We've just published a new minor version of the CLI for Microsoft 365 with new commands for working with and managing Microsoft 365 and SharePoint Framework projects on any platform.

## Manage Microsoft 365 and SharePoint Framework projects on any platform

CLI for Microsoft 365 is a cross-platform CLI that allows you to manage various configuration settings of Microsoft 365 and SharePoint Framework projects no matter which operating system or shell you use.

While building solutions for Microsoft 365 expands beyond the Windows operating system, managing many platform settings is possible only through PowerShell on Windows. As more and more users work on non-Windows machines, it's inconvenient for them to use a Windows virtual machine to configure their tenants. With the CLI for Microsoft 365, you can configure your tenant no matter which operating system you use. Additionally, using CLI for Microsoft 365, you can manage your SharePoint Framework projects.

## New version of CLI for Microsoft 365 – v5.8

Following our monthly release cadence, we've released a new version of the CLI for Microsoft 365 with some new capabilities. Here are a few of the most noteworthy additions.

> For the complete list of what's new and changed, see the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v580).

### Execute any web request using CLI for Microsoft 365 

The CLI for Microsoft 365 covers a lot of workloads and functionality. But what if you run into a situation where you need that specific functionality that's not available yet? Or what if you want to leverage your extensive knowledge of APIs and call specific endpoints in your scripts. You can now use the new `request` command to do just that. Authentication and web request specifics like throttling and compression are taken care of for you. Adding things like headers and body is super easy. 

Calling the Microsoft Graph beta endpoint is as easy as running:

```sh
m365 request --url "https://graph.microsoft.com/beta/me"
```

Calling the SharePoint REST API using a GET request with a constructed URL containing expands, filters and selects? It's now super easy:

```sh
m365 request --url "https://contoso.sharepoint.com/sites/project-x/_api/web/siteusers?\$filter=IsShareByEmailGuestUser eq true&\$expand=Groups&\$select=Title,LoginName,Email,Groups/LoginName" --accept "application/json;odata=nometadata"

```

For more information, see the [request](https://pnp.github.io/cli-microsoft365/cmd/request/) command documentation.

### Manage SharePoint Online permissions and updating Content Types

Managing permissions in SharePoint Online is a tedious task. With the CLI for Microsoft 365, you can manage permissions in SharePoint Online in a simple and easy way. In the current release we introduced a couple of new commands that will help you with that. The new commands allow you to add or remove role assignments on web level, removing a role assignment on listitem level and adding new role definitions.

In order to add a role assignment to a web for a user with role definition name 'Full Control' run the following command:

```sh
m365 spo web roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --groupName "saleGroup" --roleDefinitionName "Full Control"
```

In order to remove a role assignment given for a group we may run:

```sh
m365 spo web roleassignment remove --webUrl "https://contoso.sharepoint.com/sites/contoso-sales" --groupName "saleGroup"
```

To create a brand new role definition named _test_ with certain permissions, we may run:

```sh
m365 spo roledefinition add --webUrl https://contoso.sharepoint.com/sites/project-x --name test --description "test description" --rights "ViewListItems,AddListItems,EditListItems,DeleteListItems"
```

Another important change in managing SharePoint Online, is that it's now possible to update existing content types.

To move a content type to a new group, execute:

```sh
m365 spo contenttype set --id 0x001001 --webUrl https://contoso.sharepoint.com --Group "My group"
```

For more information, see the [spo web roleassignment add](https://pnp.github.io/cli-microsoft365/cmd/spo/web/web-roleassignment-add/), [spo web roleassignment remove](https://pnp.github.io/cli-microsoft365/cmd/spo/web/web-roleassignment-remove/), [spo roledefinition add](https://pnp.github.io/cli-microsoft365/cmd/spo/roledefinition/roledefinition-add/), [spo listitem roleassignment remove](https://pnp.github.io/cli-microsoft365/cmd/spo/listitem/listitem-roleassignment-remove/) and [spo contenttype set](https://pnp.github.io/cli-microsoft365/cmd/spo/contenttype/contenttype-set/) commands.

### Retrieving Microsoft Graph insights

This update to the CLI for Microsoft 365 also brings extras that are useful in the developer workflow. As the API surface of the Microsoft Graph is huge, it's sometimes a lot of work to get at the latest changes in the area you are interested in. You can now retrieve specific API-level changes in the Microsoft Graph using the new `graph changelog list` command. It offers options such as digging into specific services of the Graph and querying changes within a specific timeframe. All from the command line, using the tool you're familiar with.  

Get a list of all changes in the Groups and Users services:

```sh
m365 graph changelog list --services 'Groups,Users'
```

Get all security related additions to the Microsoft Graph since january 2022:

```sh
m365 graph changelog list --services 'Security' --changeType Addition --startDate 2022-01-01
```

For more information, see the [graph changelog list](https://pnp.github.io/cli-microsoft365/cmd/graph/changelog/changelog-list/) command documentation.

### Listing OneNote Notebooks

This update also brings a command targeted at a new workload for the CLI for Microsoft 365: OneNote. It's now super easy to get a list of OneNote notebooks.

Retrieving OneNote Notebooks for the current user is as easy as running:

```sh
m365 onenote notebook list
```

But it's also possible to get them for Microsoft 365 Groups:

```sh
m365 onenote notebook list --userName user1@contoso.onmicrosoft.com
```

And there are more possibilities, like getting notebooks for a specific user or SharePoint site. For more information, see the [onenote notebook list](https://pnp.github.io/cli-microsoft365/cmd/onenote/notebook/notebook-list/) command documentation.

### Extending outlook mail send

Another notable change is the updates to the outlook mail send command. This includes sending from a shared mailbox or even sending email from another account. This opened up the possibility to send emails using an application identity, making it easy to send email notifications from automated scripts running in Azure. Some extra options have also been added to set cc, bcc and the important fields of an email. And we're not done here. Sending emails with attachments is coming soon as well! 

Sending an email on behalf of a shared sales mailbox, marked as _highly important_ is as easy as running:

```sh
m365 outlook mail send --to chris@contoso.com --subject "DG2000 Data Sheets" --bodyContents "The latest data sheets are in the team site" --sender svc_project@contoso.com --mailbox sales@contoso.com --importance high
```

For more information, see the [outlook mail send](https://pnp.github.io/cli-microsoft365/cmd/outlook/mail/mail-send/) command documentation.

### What else

These features are just the tip of the ice berg of what we've shipped in this version. The code base of the CLI for Microsoft 365 has received a huge update as well, making it easier for maintainers and contributors to create new functionality. And so many other fixes.
Check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v580) for the complete list of what's new and improved.

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Aaron Sotelo](https://github.com/AaronS16)
- [Adam Wójcik](https://github.com/Adam-it)
- [Albert-Jan Schot](https://github.com/appieschot)
- [Cyril Kurian](https://github.com/cyrilckurian)
- [Don Kirkham](https://github.com/DonKirkham)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Otto](https://github.com/berot3)
- [Patrick Lamber](https://github.com/plamber)
- [Vipul Kelkar](https://github.com/vipulkelkar)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

Thank you all for the time you chose to spend on CLI for Microsoft 365 and for your help to advance it!

## Work in progress

Here are some things that we're currently working on.

### SharePoint Online permission management commands

We're working on new commands that will help manage permissions in SharePoint Online on web, list and list item level (file and folder as well). The commands allow to break or reset role inheritance and add or remove role assignments to users and groups. If you are interested in our current progress please do check the [Fill void around spo permission management issue](https://github.com/pnp/cli-microsoft365/issues/3540)

### Power Platform commands

We're working on a series of new commands that will help manage Power Platform solutions, the dataverse, Power Platform settings, etc. There's a lot of work to be done here, so if you like to join in, you're very welcome to checkout our [Power Platform epic issue](https://github.com/pnp/cli-microsoft365/issues/3670). 

### Hacktoberfest

Have you met [hacktoberfest](https://hacktoberfest.com/)? It's an annual event that encourages people to contribute to open source throughout the month of October. We've registered there as well and we hope a good dose of Microsoft 365 developers will make the community proud by signing up and doing some of the work we will all benefit from. If you're wondering how you can contribute? Just register at the site and pick up issues in our repository with the [hacktoberfest label](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aopen+is%3Aissue+label%3Ahacktoberfest) and...well... start hacking!   

### Discussions 

CLI for Microsoft 365 is constantly growing and evolving. We're always looking for ways to improve. There are still many areas not covered by the CLI as well as many amazing ideas for unique features the tool might provide. Currently we are considering adding support with commands which will allow you to manage file versioning or document sets in SharePoint Online. Your feedback will help us make the right decisions in which areas we should focus on. If you want to help out please do join the currently open [discussions](https://github.com/pnp/cli-microsoft365/discussions)

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