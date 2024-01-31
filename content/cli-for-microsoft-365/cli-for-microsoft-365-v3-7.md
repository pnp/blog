---
title: "CLI for Microsoft 365 v3.7"
date: 2021-03-17T12:22:00-04:00
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
 
## New version of CLI for Microsoft 365 -- v3.7

With the release of SharePoint Framework v1.12, we release this new
version of CLI for Microsoft 365 to help you upgrade your projects.
Along with it, we included some new commands and improvements. Here are
some of the most noteworthy additions. For the full list of changes, see
our [release
notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v370).
 
### Upgrade SharePoint Framework projects to v1.12

Microsoft has just released a new version of SharePoint Framework v1.12.
The most notable improvements are support for Node@12, including custom
Teams manifests and support for building Teams meetings apps. For the
full list of features, see the
[documentation](https://learn.microsoft.com/sharepoint/dev/spfx/roadmap?WT.mc_id=m365-19903-wmastyka).
 
Upgrading SharePoint Framework projects goes beyond updating
dependencies to the latest version. Often, there are changes to the
different files in the project. To help you upgrade your SPFx project to
the latest version and benefit from the latest improvements, we offer
you a one-command upgrade.
To get a list of changes necessary to upgrade your project to the latest
version of the SharePoint Framework, execute in the folder of your
SharePoint Framework project:

``` sh
m365 spfx project upgrade --output md > report.md
```
 
This will generate a Markdown report with all findings. From the summary
section of the report, you can copy a complete set of commands to run to
update all packages.
 
If you want to better understand what's changed and where, I'd
recommend you use the
[CodeTour](https://marketplace.visualstudio.com/items?itemName=vsls-contrib.codetour)
report, which you can get by executing:

``` sh
m365 spfx project upgrade --output tour
```

When you open your SharePoint Framework project in VSCode, you will get
an interactive tour of all the locations in your project that needs an
update.
 
### Ensure that you have all prerequisites for building apps using SharePoint Framework v1.12

SharePoint Framework v1.12 comes with a new set of prerequisites. To
build apps on SPFx v1.12, you need to be using Node v12 and Gulp v4. To
help you double check that you have all prerequisites and won't hit any
errors, we offer the `spfx doctor` command.
 
To check if your machine has all prerequisites for building apps using
SPFx v1.12, install the SharePoint Framework Yeoman generator v1.12 and
run:

``` sh
m365 spfx doctor
```
 
The command will check if your machine for all prerequisites and tell
you if there is anything missing.
 
### Configure CLI to your personal preferences

As more and more people use CLI for Microsoft 365, we get more feedback
about what they'd prefer CLI to work. Some of our users, prefer for
example to automatically get command help when running the command
fails. Others, prefer to see help only when they explicitly ask for.
When you use CLI for building scripts, you might want it to use the JSON
output by default. On the other hand, if you use it for quickly looking
things up, you'd prefer to use the text mode.
 
Because the only person knowing best how to work is you, we want to give
you the ability configure CLI to your personal preferences. In this
release we introduce support for configuring CLI. The first option that
you can set, is to choose if you want to automatically see help when
running command failed. It's turned on by default, and to turn it off
you can run:


``` sh
m365 cli config set --key showHelpOnFailure --value false
```
 
We're planning to introduce the ability to configure the default output
mode next. And if there are other things that you'd like to be able to
configure, please [let us
know](https://github.com/pnp/cli-microsoft365/issues).
 
### List application permissions for SharePoint sites

Recently, Microsoft released [a new way of granting apps access to
SharePoint
sites](https://developer.microsoft.com/office/blogs/controlling-app-access-on-specific-sharepoint-site-collections/?WT.mc_id=m365-19903-wmastyka).
Rather than having apps access all sites, you can let them access
selected sites only.
 
In this version of CLI for Microsoft 365, we introduce support for
retrieving app permissions set on a specific site.
 
To get the list of permissions granted to apps on a specific site,
execute:



``` sh
m365 spo site apppermission list --siteUrl https://contoso.sharepoint.com/sites/project-x
```
 
To get more information about a specific site app permission, execute:

``` sh
m365 spo site apppermission get --siteUrl https://contoso.sharepoint.com/sites/project-x --permissionId aTowaS50fG1zLnNwLmV4dHw4OWVhNWM5NC03NzM2LTRlMjUtOTVhZC0zZmE5NWY2MmI2NmVAZGUzNDhiYzctMWFlYi00NDA2LThjYjMtOTdkYjAyMWNhZGI0
```
 
In the future versions of CLI for Microsoft 365, you can expect more
commands allowing you to manage app permissions for SharePoint sites.
 
### Changes

We've continued improving CLI, building upon the changes we've
introduced in the previous version.
 
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
 
#### Added Remote Development container

One of the things that often stand in the way of contributing to open
source projects is setting up the dev environment. Often, specific
projects require specific tools and sometimes even specific versions of
them. If you're not using the particular stack in your daily work, it
can be cumbersome to even get started.
 
To help you contribute to CLI for Microsoft 365, we'd like to introduce
a Remote Developer container. Using GitHub Codespaces, it allows you to
get up and running your dev environment in minutes, without worrying
about installing dependencies. We'll provide instructions on how to get
started using the Remote Development container shortly.
 
### Sample scripts

CLI for Microsoft 365 is a great tool both for quick adjustments to the
configuration of your Microsoft 365 tenant as well as automating more
complex tasks. Because CLI for Microsoft 365 is cross-platform you can
use it on any OS and in any shell. To help you get started using the CLI
for Microsoft 365 for automation scenarios, we started gathering some
sample scripts.
 
If you have any scripts that you use frequently, please share them with
us so that we can learn more about the common automation scenarios.
 
#### Provision a Team with channels and assign a custom icon

A sample script which [creates a Microsoft 365 Group, associates a logo
to it and some
members](https://pnp.github.io/cli-microsoft365/sample-scripts/teams/create-team-from-group/).
Afterward, it teamyfies the Group and creates two public channels.
 
#### List site collections and their lists

This script helps you to [list and export all site collection and their
lists SharePoint Online
sites](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/list-site-collection-lists/),
ideal for getting insights into the size of your environment.
 
#### List all external users in all site collections

This script helps you to [list all external users in all SharePoint
Online
sites](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/list-site-externalusers/).
It provides insights in who the users are, and if available who they
where invited by.
 
#### Delete all Microsoft 365 groups and SharePoint sites

There are so many different ways to create Microsoft 365 groups. Teams,
Planner, SharePoint team sites, etc. --- you can accumulate a lot of
them very fast. Use this script to [delete the ones you no longer
need](https://pnp.github.io/cli-microsoft365/sample-scripts/aad/delete-m365-groups/).
 
## Contributors

This release wouldn't be possible without the help of (in alphabetical
order) [Aakash Bhardwaj](https://github.com/aakashbhardwaj619), [Luise
Freese](https://github.com/LuiseFreese), [Patrick
Lamber](https://github.com/plamber), [Michaël
Maillot](https://github.com/michaelmaillot), [Waldek
Mastykarz](https://github.com/waldekmastykarz), [Arjun
Menon](https://github.com/arjunumenon), [Abderahman
Moujahid](https://github.com/Abderahman88), [Nanddeep
Nachan](https://github.com/nanddeepn), [Albert-Jan
Schot](https://github.com/appieschot), [Elio
Struyf](https://github.com/estruyf), [Fredrik
Thorild](https://github.com/fthorild), [Garry
Trinder](https://github.com/garrytrinder/) and [Rabia
Williams](https://github.com/rabwill). Thank you all for the time you
chose to spend on the CLI for Microsoft 365 and your help to advance it!
 
## Work in progress

Here are some things that we're currently working on.
 
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

``` sh
npm i -g @pnp/cli-microsoft365
```
 
Alternatively, you can get the latest release from Docker by executing
in the command line:

``` sh
docker run --rm -it m365pnp/cli-microsoft365:latest
```
 
If you need more help getting started or want more details about the
commands, the architecture or the project, go to
[aka.ms/cli-m365](https://aka.ms/cli-m365).
 
If you see any room for improvement, please, don't hesitate to reach out
to us either on
[GitHub](https://github.com/pnp/office365-cli/discussions) or
[twitter](https://twitter.com/climicrosoft365).
