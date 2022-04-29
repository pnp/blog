---
title: "CLI for Microsoft 365 v4"
date: 2021-10-07T12:08:00-04:00
author: "Garry Trinder"
githubname: garrytrinder
categories: ["CLI for Microsoft 365"]
images:
- images/banner-cli-m365.png
tags: ["CLI for Microsoft 365"]
type: "regular"
---
 

We've just published a new major version of the CLI for Microsoft 365
with new commands & enhancements for working with and managing Microsoft
365 tenants and SharePoint Framework projects on any platform.

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
 
## New major version for CLI Microsoft 365 -- v4 
 
As we kept extending CLI for Microsoft 365 with new functionality during
the last year, we noticed a few areas that we could improve to simplify
using the CLI. As such, this new major version is evolutionary.
Following is the overview of the most noteworthy changes introduced in
CLI for Microsoft 365 v4. For the full list of changes, see the [release
notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v400).
 
***To help you upgrade to v4, we prepared a summary of breaking changes
and the recommended actions. For more information see the [v4 Upgrade
Guidance](https://pnp.github.io/cli-microsoft365/v4-upgrade-guidance) in
our docs.***
 
### Change to JSON as default output mode 
 
We noticed that when scripts were written using CLI for Microsoft 365
that it was common for commands to use the JSON output mode, as our
default was to use the text output mode, this required script creators
to include the *\--output* option in the command execution. We decided
that in this new version we would change the default output to use JSON
to help simplify these scenarios.
 
### Consistent JSON output for list commands 
 
We noticed that some of our list commands were not consistent in the way
they returned a response using the JSON output mode, a typical example
of this is where we returned the *value* array property in some commands
and not others. This required you to modify your scripts to cater for
this inconsistency. In v4, we have removed the value array property and
return the array values to you directly making for a much more
consistent experience.
 
### Removal of deprecated file path options 
 
Earlier in the year we introduced a new way of passing complex inputs to
command options by using the @ file reference syntax to tell the CLI
that you want to use a local file as the option input. This helped
simplify our commands as we no longer required you to use specific
options created for reading from files such*\--filePath*. Therefore, we
have taken the decision to remove these options in favour of using the @
syntax from the following commands.
 
-   `outlook mail send --bodyContentsFilePath`
-   `spo theme set --filePath`
-   `teams team add --templatePath`

## Updates 
 
In addition to the notable evolutionary changes introduced in this major
version and following our monthly release cadence, we've released some
new capabilities. Here are a few of the most noteworthy additions.
 
### Upgrade SharePoint Framework projects to SPFx v1.13 preview 

Recently, Microsoft released a new [preview version of the SharePoint
Framework -
v1.13](https://developer.microsoft.com/sharepoint/blogs/announcing-public-preview-of-sharepoint-framework-1-13-with-viva-connections-extensibility/).
This version of SPFx, introduces new exciting capabilities for extending
Viva Connections using Adaptive Card Extensions.
 
To help you try these capabilities in your projects, we extended CLI for
Microsoft 365 with support for upgrading your existing SharePoint
Framework projects to SharePoint Framework v1.13.0-beta.20.
 
To upgrade your SPFx project to this preview version, change the working
directory to your project and execute:
 
 
 
```bash
m365 spfx project upgrade --preview --output md > report.md
```
 
 
 
We also recommend that you try a richer upgrade report based on the
Visual Studio Code CodeTour extension:
 
 
 
```bash
m365 spfx project upgrade --preview --output tour
```
 
 
For more information about upgrading SharePoint Framework projects, see
the [CLI
documentation](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade/).
 
### List all members of a SharePoint Group 
 
In this version of CLI for Microsoft 365, we introduced a new command to
list all the members of a SharePoint Group in a given site. To list all
the members of a group, execute:
 
 
```bash
m365 spo group user list --webUrl https://contoso.sharepoint.com/sites/SiteA --groupName "Contoso Site Members"
```
 
 
 
### Upgrading commands to Microsoft Graph v1.0 endpoint 
 
When adding new commands to CLI for Microsoft 365, we sometimes take
advantage of Microsoft Graph Beta endpoint to provide new capabilities,
over time however these endpoints mature and reach General Availability,
being made available in the Microsoft Graph v1.0 endpoint.
 
As part of our regular review of commands, we highlighted some commands
that could be upgraded. The following commands have been upgraded as
part of this release:
 
-   `teams channel list`
-   `teams conversationmember list`
-   `teams conversationmember add`
-   `aad siteclassification disable`
-   `aad o365group teamify`
 
## New Sample Scripts 

CLI for Microsoft 365 is a great tool both for quick adjustments to the
configuration of your Microsoft 365 tenant as well as automating more
complex tasks. Because CLI for Microsoft 365 is cross-platform you can
use it on any OS and in any shell. To help you get started using the CLI
for Microsoft 365 for automation scenarios, we started gathering some
[sample
scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/).
 
If you have any scripts that you use frequently, please
[share](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=sample.md&title=New+sample+script%3A+%3Cshort+description%3E)
them with us so that we can learn more about the common automation
scenarios.
 
### List all team members in Microsoft Teams teams 
 
This [sample
script](https://pnp.github.io/cli-microsoft365/sample-scripts/teams/list-all-teammembers-teams/)
shows how to retrieve all the team members in a Microsoft Teams teams
and export the results to a CSV file.
 
### Get all the Teams a specific user is part of 
 
This [sample
script](https://pnp.github.io/cli-microsoft365/sample-scripts/teams/list-all-teammembers-teams/)
shows how to retrieve all the Microsoft Teams teams that a user is a
member of and export the results to a CSV file.
 
## Contributors 
 
This release wouldn't be possible without the help of (in alphabetical
order):
 
-   [Aakash Bhardwaj](https://github.com/aakashbhardwaj619)
-   [Vipul Kelkar](https://github.com/vipulkelkar)
-   [Sudharsan Kesavanarayanan](https://github.com/sudharsank)
-   [Shantha Kumar](https://github.com/ktskumar)
-   [Veronique Lengelle](https://github.com/veronicageek)
-   [Michaël Maillot](https://github.com/michaelmaillot)
-   [Waldek Mastykarz](https://github.com/waldekmastykarz)
-   [Arjun Menon](https://github.com/arjunumenon)
-   [Abderahman Moujahid](https://github.com/Abderahman88)
-   [Nanddeep Nachan](https://github.com/nanddeepn)
-   [Smita Nachan](https://github.com/SmitaNachan)
-   [Albert-Jan Schot](https://github.com/appieschot)
-   [Dipen Shah](https://github.com/dips365)
-   [Garry Trinder](https://github.com/garrytrinder)
-   [Mark van Dijk](https://github.com/MarksPoint)
 
## Work in progress 
 
Here are some things that we are currently working on.
 
## Themes 
 
Following our latest major release, we have started thinking about
themes for the coming year but we would love to know what you think we
should concentrate on next.
 
If you have any suggestions, please let us know by adding your
suggestion to our [open
discussion](https://github.com/pnp/cli-microsoft365/discussions/2708) on
GitHub.
 
### Upgrading commands to Microsoft Graph v1.0 
 
We are constantly evaluating the implementation of our commands to
ensure that we are using endpoints that provide the best stability and
support, therefore we are will be upgrading commands that use Microsoft
Graph Beta endpoint to use their equivalent endpoint in Microsoft Graph
v1.0.
 
In addition to upgrading commands that use Microsoft Graph, we have also
started work on upgrading commands that use, the now deprecated Azure
Active Directory Graph API, which will reach end of life in June 2022.
These commands will be be upgraded to use the appropriate Microsoft
Graph endpoints.
 
### Script examples 
 
In every release of the CLI for Microsoft 365, we introduce new commands
for managing Microsoft 365. With over 350 commands across the different
Microsoft 365 services, the CLI for Microsoft 365 has become a powerful
tool, not just for managing your tenant but also for automating your
daily work.
 
We'd love to show you how you can use the CLI for Microsoft 365 to build
automation scripts in PowerShell Core and Bash. If you have any scripts
using SPO or PnP PowerShell that you use frequently, please share them
with us so that we can learn more about the common automation scenarios.
 
## Try it today 
 
Get the latest release of the CLI for Microsoft 365 from npm by
executing:
 
 
 
 
 
```bash
npm i -g @pnp/cli-microsoft365
```
 
 
 
 
 
Alternatively, you can get the latest release from Docker by executing:
 
 
 
 
 
```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```
 
 
 
 
 
If you need more help getting started or want more details about the
commands, the architecture or the project, go
to [aka.ms/cli-m365](https://aka.ms/cli-m365).
 
If you see any room for improvement, please, don't hesitate to reach out
to us either
on [GitHub](https://github.com/pnp/cli-microsoft365/issues) or [twitter](https://twitter.com/climicrosoft365).
