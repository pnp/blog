---
title: "CLI for Microsoft 365 v3.6"
date: 2021-02-27T02:51:00-05:00
author: "Waldek Mastykarz"
githubname: WaldekMastykarz
categories: ["CLI for Microsoft 365"]
tags: ["CLI for Microsoft 365"]
type: "regular"
---
We've just published a new version of the CLI for Microsoft 365 with new
commands for working with and managing Microsoft 365 tenants and
SharePoint Framework projects on any platform.

## Manage Microsoft 365 and SharePoint Framework projects on any platform

CLI for Microsoft 365 is a cross-platform CLI that allows you to manage
various configuration settings of Microsoft 365 and SharePoint Framework
projects no matter which operating system or shell you use.
While building solutions for Microsoft 365 expands beyond the Windows
operating system, managing many of the platform settings is possible
only through PowerShell on Windows. As more and more users work on
non-Windows machines, it's inconvenient for them to have to use a
Windows virtual machine to configure their tenants. With the CLI for
Microsoft 365, you can configure your tenant no matter which operating
system you use. Additionally, using CLI for Microsoft 365, you can
manage your SharePoint Framework projects.
 
## New version of CLI for Microsoft 365 -- v3.6 

Following our monthly release cadence, we released this new version of CLI for Microsoft 365 with some new commands and improvements. Here are some of the most noteworthy additions. For the full list of changes, see our [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v360).

### Ensure SharePoint site

When building provisioning scripts, you often need to check if a
particular site already exists. If it doesn't, you need to create it.
If it does, you need to check if it has the necessary settings.
Depending what exactly you need to check, this logic can become pretty
elaborate. If you need to create a couple of sites, you're quickly
looking at lengthy scripts that you not only need to write but also
maintain.

To help you easily ensure that sites with the right configuration
exists, we introduce the `spo site ensure` command. Using this command,
you can for example easily ensure that a site exists at the specified
URL and create one if it doesn't:

```sh
m365 spo site ensure --url https://contoso.sharepoint.com/sites/team1 --alias team1 --title "Team 1"
```      

Using the command you can also ensure that the site that exists has the
right type and properties:

```sh
m365 spo site ensure --url https://contoso.sharepoint.com/sites/team1 --alias team1 --title "Team 1" --isPublic --shareByEmailEnabled
```

This is the first `ensure` command that we introduce in CLI for
Microsoft 365. We'd love you to give it a try and tell us what you
think. For more information about what's possible, see the [command's
documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-ensure/).

### Configure SharePoint site chrome

Microsoft is continuously investing in modernizing SharePoint. With
every update, we get more features to build rich portals in a robust and
future-ready way. One of the recently introduced features is site chrome
that allows you to control how the site's header and footer look like.
 
In this version of CLI for Microsoft 365, we introduce a command that
allows you to control site's chrome.
To show site's header in compact mode, execute:

```sh
m365 spo site chrome set --url https://contoso.sharepoint.com/sites/project-x --headerLayout Compact
```
 
To show site's header in extended mode and align the logo to the right,
execute:

```bash
m365 spo site chrome set --url https://contoso.sharepoint.com/sites/project-x  --headerLayout Extended --logoAlignment Right
```
 
To disable the footer, execute:

```bash
m365 spo site chrome set --url https://contoso.sharepoint.com/sites/project-x --disableFooter true
```
 
For the full list of supported settings, see the [command's
documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-chrome-set/).
 
### Copy SharePoint pages and page templates

When working with pages and page templates, you might want to copy
specific pages or page templates in bulk. The easiest way to automate
it, is using CLI for Microsoft 365.
 
In this version we introduce a command that let's you copy the
specified page or page template. To copy a page template, execute:

```bash
m365 spo page copy --webUrl https://contoso.sharepoint.com/sites/team-a --sourceName "templates/PageTemplate.aspx" --targetUrl "page.aspx"
```

To copy a page to another site, execute:

```bash
m365 spo page copy --webUrl https://contoso.sharepoint.com/sites/team-a --sourceName "templates/PageTemplate.aspx" --targetUrl "https://contoso.sharepoint.com/sites/team-b/sitepages/page.aspx"
```
 
For the full list of supported options, see the [command's
docs](https://pnp.github.io/cli-microsoft365/cmd/spo/page/page-copy/).
 
### Manage Power Apps

More and more organizations use Power Apps to automate their work. With
Power Apps, they can build applications for their business processes
with little to no code.
 
To help organizations manage their Power Apps, we introduce in this
version three new commands.
First, we let you get the list of your Power Apps environments, by
executing:

```bash
m365 pa environment list
```
 
To get more information about a specific environment, execute:

```bash
m365 pa environment get --name Default-d87a7535-dd31-4437-bfe1-95340acd55c5
```
 
To get information about a specific app, execute:

```bash
m365 pa app get --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d
```

These commands extend our set of Power Platform commands. For the list
of all commands for Power Platform, see the
[documentation](https://pnp.github.io/cli-microsoft365/cmd/pa/environment/environment-list/).

### Changes

We've continued improving CLI, building upon the changes we've
introduced in the previous version.
 
#### Browser-based login

Many organizations become more and more conscious about their security
posture. As their awareness matures, they implement more measure to
ensure that they can work securely. One of such measures is conditional
access that allows organizations enforce specific checks on clients
authenticating against their Microsoft 365 tenant.
 
To let organizations who enforce conditional policies use CLI for
Microsoft 365, we introduced a browser-based way to login to Microsoft
365.
 
After executing: `m365 login --authType browser`, CLI for Microsoft 365
will launch a browser, let you sign in and obtain an access token on
your behalf. If you have the browser with the right user profile active,
the automatically opened login page will give you a smooth login
experience without having to copy & paste device code.
 
From that point on, CLI for Microsoft 365 will work exactly the same way
you're used to it, allowing you to run scripts and automate managing
your tenant.
 
#### Improved managing SharePoint pages and sites 

CLI for Microsoft 365 is a great tool for automating managing your
Microsoft 365 tenant and SharePoint Framework projects. It's also great
as an engine to build other tools on top!
 
Elio Struyf has build a static site generator for SharePoint named
[Doctor](https://github.com/estruyf/doctor). If you want to author
product documentation or a knowledgebase in Markdown but publish it to
SharePoint, Doctor is the tool for the job! As Elio is extending Doctor
with new capabilities, he's contributed a number of enhancements to
managing pages and sites with CLI for Microsoft 365.
 
#### Improved creating Azure AD apps 

Recently we've introduced an [easy way to create Azure AD
apps](https://pnp.github.io/cli-microsoft365/cmd/aad/app/app-add/) with
CLI for Microsoft 365. With just one line of code, you can create an app
registration full configured to support your scenario.
 
In this version of CLI for Microsoft 365, we extended the command so
that it returns the ID of your Azure AD directory, which you need to
include in your code when building single-tenant apps.
 
We've also improved the mechanism to lookup service principal in cases
where their names end with a `/` (slash).

#### Simplified retrieving access token for SharePoint 

When building apps for Microsoft 365, you often need an access token to
quickly test your code. The easiest way to get it, is using CLI for
Microsoft 365.
 
In this version, we made it even easier by introducing an alias for the
resource. If you called SharePoint previously using CLI for Microsoft
365, you can quickly get an access token for SharePoint by executing:

```bash
m365 util accesstoken get --resource sharepoint
```
 
Rather than having to specify the full URL of your SharePoint tenant,
you can use `sharepoint` instead. It's that easy! Are there any other
aliases that we should add?
 
### Sample scripts

CLI for Microsoft 365 is a great tool both for quick adjustments to the
configuration of your Microsoft 365 tenant as well as automating more
complex tasks. Because CLI for Microsoft 365 is cross-platform you can
use it on any OS and in any shell. To help you get started using the CLI
for Microsoft 365 for automation scenarios, we started gathering some
sample scripts.
 
If you have any scripts that you use frequently, please share them with
us so that we can learn more about the common automation scenarios.

#### Export conversations from Microsoft Teams Channels

*We utilize Teams during incidents and create channels for each. We
would like to be able to export conversation history.*

To help you quickly export conversations from the teams your members of,
Joseph Velliah contributed a [sample
script](https://pnp.github.io/cli-microsoft365/sample-scripts/teams/export-teams-conversations/)
that iterates over your Teams and channels and exports conversations to
a JSON fil
 
## Contributors

This release wouldn't be possible without the help of (in alphabetical
order) [Hugo Bernier](https://github.com/hugoabernier), [Luise
Freese](https://github.com/LuiseFreese), [Patrick
Lamber](https://github.com/plamber), [Waldek
Mastykarz](https://github.com/waldekmastykarz), [Nanddeep
Nachan](https://github.com/nanddeepn), [Smita
Nachan](https://github.com/SmitaNachan), [John
Rafael](https://github.com/jcads), [Albert-Jan
Schot](https://github.com/appieschot), [Elio
Struyf](https://github.com/estruyf), [Fredrik
Thorild](https://github.com/fthorild), [Garry
Trinder](https://github.com/garrytrinder/), [Joseph
Velliah](https://github.com/sprider) and [Rabia
Williams](https://github.com/rabwill). Thank you all for the time you
chose to spend on the CLI for Microsoft 365 and your help to advance it!

## Work in progress


Here are some things that we're currently working on
 
### More commands, what else 

Microsoft 365 is evolving and new capabilities are being released every
day. With CLI for Microsoft 365, we aim to help you manage your tenant
on any platform in a consistent way, no matter which part of Microsoft
365 you interact with. While we keep adding new commands to CLI for
Microsoft 365 each release, we still barely scratched the surface with
what's possible in Microsoft 365. In the upcoming versions of the CLI
for Microsoft, you can expect us to add more commands across the
different workloads in Microsoft 365.
 
### Improved managing SharePoint pages

Microsoft keeps investing in modern SharePoint pages continuously
introducing new capabilities to let us publish rich content. We're
looking into extending our support for managing modern SharePoint pages
to let you use them to their full potential.
 
### Improved creating Azure AD apps


Recently, we've introduced a command to easily create Azure AD app
registrations. Because they're backbone of every app you'd build on
Microsoft 365, we think you should be able to create them as easily as
possible. So with CLI for Microsoft 365, you can create a fully
configured Azure AD app for the most common scenarios with just one line
of code.
 
In the future versions of CLI for Microsoft 365 you can expect us extend
the capabilities with additional scenarios and features supported by
Azure AD.
 
### Script examples 

In every release of the CLI for Microsoft 365, we introduce new commands
for managing Microsoft 365. With over 350 commands across the different
Microsoft 365 services, the CLI for Microsoft 365 has become a powerful
tool, not just for managing your tenant but also for automating your
daily work.
We'd love to show you how you can use the CLI for Microsoft 365 to build
automation scripts in PowerShell Core and Bash. If you have any scripts
using SPO or PnP PowerShell that you use frequently, please
[share](https://github.com/pnp/cli-microsoft365/issues) them with us so
that we can learn more about the common automation scenarios.

### `ensure` commands 

We've just shipped our first `ensure` command - an easy way to help you
that a site with specific settings exists. If it doesn't, CLI creates
it for you, if it does, CLI ensures it has the right properties. All in
one line of code. We'd love to hear from you how you like it and if
it's something you'd like us to implement for other commands as well.

## Try it today

Get the latest release of the CLI for Microsoft 365 from npm by
executing in the command line:

```bash
npm i -g @pnp/cli-microsoft365
```

Alternatively, you can get the latest release from Docker by executing
in the command line:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

If you need more help getting started or want more details about the
commands, the architecture or the project, go to
[aka.ms/cli-m365](https://aka.ms/cli-m365).
If you see any room for improvement, please, don't hesitate to reach out
to us either on
[GitHub](https://github.com/pnp/office365-cli/discussions) or
[twitter](https://twitter.com/climicrosoft365).
