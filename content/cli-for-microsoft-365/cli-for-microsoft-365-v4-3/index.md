---
title: "CLI for Microsoft 365 v4.3"
date: 2022-01-08T11:19:00-05:00
author: "Garry Trinder"
githubname: garrytrinder
categories: ["CLI for Microsoft 365"]
images:
- images/banner-cli-m365.png
tags: ["CLI for Microsoft 365"]
type: "regular"
---

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
 
## New version of CLI for Microsoft 365 -- v4.3 

Following our monthly release cadence, we've released a new version of
the CLI for Microsoft 365 with some new capabilities. Here are a few of
the most noteworthy additions.
 
## Changes 

We've continued improving the CLI, building upon the changes we
introduced in the previous version.
 
### Upgrade SharePoint Framework projects to SPFx v1.14.0 Public Preview 

With the announcement of the availability of public preview of the
SharePoint Framework (SPFx) 1.14 -- with updates for Viva Connections,
Microsoft Teams and SharePoint Online experiences, we have added support
for upgrading your SPFx projects to the latest preview
version, v1.14.0-beta.4.
 
To upgrade your SPFx project to this version, change the working
directory to your project and execute:
 
 
 
``` {.lia-code-sample .language-applescript}
m365 spfx project upgrade --preview --output md > report.md
```
 
 
 
We'd also recommend that you try a richer upgrade report based on the
Visual Studio Code CodeTour extension:
 
 
 
``` {.lia-code-sample .language-sh}
m365 spfx project upgrade --preview --output tour
```
 
 
 
For more information about upgrading SharePoint Framework projects, see
the [CLI
documentation](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade/).
 
### CSV output mode 

In this release we have added a new global output mode to return
information from Microsoft 365 in CSV format, adding to the JSON and
Text output modes that we already have.
 
To retrieve information about a given SharePoint site as CSV output,
execute:
 
 
 
```bash
m365 spo web get --webUrl https://contoso.sharepoint.com --output csv
```
 
 
 
### Support for returning Power Apps in a given environment 

An *environment* is a space to store, manage, and share your
organization's business data, apps, chatbots, and flows. It also serves
as a container to separate apps that might have different roles,
security requirements, or target audiences. Previously you could only
return a list of Power Apps in the default environment, however we have
extended the pa app list command so that you can return a list of apps
from any environment in your tenant.
 
To retrieve a list of Power Apps in a given environment, execute:
 
 
 
```bash
m365 pa app list --environment Default-d87a7535-dd31-4437-bfe1-95340acd55c5
```
 
 
 
### Support for returning Azure AD users by email 

We've simplified returning information about a given Azure AD user, by
adding support for using their email address as an identifier, adding to
ID and UPN which we also support.
 
To retrieve information about a given user by their email address,
execute:
 
 
 
```bash
m365 aad user get --email AarifS@contoso.onmicrosoft.com
```
 
 
## New commands 

We've introduced several commands in this release providing new
capabilities across Microsoft 365. 
 
### Retrieve Azure AD app registration 

When building apps and integrations against Microsoft 365, the first
thing you need to do is authenticate and for that you need to register
Azure AD applications to setup that trust and assign permissions
accordingly. We've added a new command that returns information about
given Azure AD app registrations.
 
To retrieve an Azure AD app registration by its name, execute:
 
 
 
```bash
m365 aad app get --name "My app"
```
 

### Check a user's password against the organisation's password validation policy 

In Azure Active Directory you can you can define fine-grained password
policies that control account lockout settings or minimum password
length and complexity. We've added a new command that simplifies the
ability for you to test and validate example passwords against
your organisation's policy.
 
To validate the password *cli365P@ssW0rd* against your organisation's
password validation policy, execute:
 
 
 
```bash
m365 aad user password validate --password "cli365P@ssW0rd"
```
 
 
 
### List API permissions for current Azure AD app 

Previously we added the ability for you to create an Azure AD app
registration and store information about the registration in a file
called *.m365rc.json*, in this release we have added a new command that
retrieves the API permissions of the app registration stored locally.
 
To create a new Azure AD app registration with a specified name and
store the information locally in a *.m365rc.json* file, execute:
 
 
```bash
m365 aad app add --name 'My AAD app' --save
```
 
 
 
To list the API permissions for the Azure AD app registered in the
*.m365rc.json* file, execute:
 
 
 
```bash
m365 app permission list
```
 
 
 
### Create new external connection for Microsoft Search 

Microsoft Search indexes all your Microsoft 365 data to make it
searchable for users. Using the Microsoft Graph to create new external
connections, your organization can index third-party data so it appears
in Microsoft Search results, for example, indexing HR data in SQL
Server. We've added a new command that helps you expand the types of
content sources that are searchable in your Microsoft 365 productivity
apps and the broader Microsoft ecosystem.
 
To create a new external connection definition for Microsoft Search,
execute:
 
 
 
```bash
m365 search externalconnection add --id MyApp --name "My application" --description "Description of your application"
```
 
 
 
### Create new Planner task 

Microsoft Planner provides a simple visual way to organise teamwork,
we've added a new command that provides the ability to create new tasks
in a Planner board but also assign those tasks to team members and set
due dates. 
 
To create a task in a given plan and bucket by their IDs, execute:
 
 
 
```bash
m365 planner task add --title "My Planner Task" --planId "8QZEH7b3wkSbGQobscsM5gADCBa" --bucketId "IK8tuFTwQEa5vTonM7ZMRZgAKdna"
```
 
 
 
To create a completed task in a plan owned by a group, execute:
 
 
 
```bash
m365 planner task add --title "My Planner task" --planName "My Planner Plan" --ownerGroupName "My Planner Group" --bucketId "IK8tuFTwQEa5vTonM7ZMRZgAKdna" --percentComplete 100
```
 
 
 
To create a task assigned to multiple users and set the due date,
execute:
 
 
 
```bash
m365 planner task add --title "My Planner Task" --planId "8QZEH7b3wkSbGQobscsM5gADCBa" --bucketId "IK8tuFTwQEa5vTonM7ZMRZgAKdna" --assignedToUserNames "Allan.Carroll@contoso.com,Ida.Stevens@contoso.com" --dueDateTime "2021-12-16"
```
 
 
 
### Retrieve list of installed languages in a SharePoint site 

If your organisation spans a diverse population, you may want to make
content in your SharePoint sites available in multiple
languages. SharePoint Online currently supports 50 different languages
and we've added a command to return the list of installed languages in
a give SharePoint site to help you identify the languages available for
use in that site.
 
To retrieve all installed languages from a given site, execute: 
 
 
 
```bash
m365 spo web installedlanguage list --webUrl https://contoso.sharepoint.com
```

## New script samples 
 



CLI for Microsoft 365 is a great tool both for quick adjustments to the
configuration of your Microsoft 365 tenant as well as automating more
complex tasks. Because CLI for Microsoft 365 is cross-platform you can
use it on any OS and in any shell. To help you get started using the CLI
for Microsoft 365 for automation scenarios, we started gathering some
[sample
scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/).
</div>
 


If you have any scripts that you use frequently, please
[share](https://github.com/pnp/cli-microsoft365/discussions) them with
us so that we can learn more about the common automation scenarios.

### Copy list items between SharePoint lists 


This script helps you to [copy SharePoint List
Items](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/copy-listitems-sharepointlist/)
from a destination SharePoint Online list to another target
SharePoint Online list in another Site Collection.
</div>
 
## Contributors 

This release wouldn't be possible without the help of (in alphabetical
order):
 
- [Robert Dyjas](https://github.com/robdy)
- [Vipul Kelkar](https://github.com/vipulkelkar)
-   [Patrick Lamber](https://github.com/plamber)
-   [Waldek Mastykarz](https://github.com/vipulkelkar)
-   [Kevin McDonnell](https://github.com/kevmcdonk)
-   [Arjun Menon](https://github.com/arjunumenon)
-   [Abderahman Moujahid](https://github.com/vipulkelkar)
-   [Nanddeep Nachan](https://github.com/vipulkelkar)
-   [Albert-Jan Schot](https://github.com/appieschot)
-   [Danish Shafi](https://github.com/builtbydans)
-   [Sekar Thangavel](https://github.com/SekarThangavel)
-   [Jasey Waegebaert](https://github.com/Jwaegebaert)
-   [Adam Wójcik](https://github.com/Adam-it)
 
## Work in progress 

Here are some things that we're currently working on.
 
### CLI for Microsoft 365 v4 Themes 

Following our latest major release, we have started thinking about
themes for the coming year but we would love to know what you think we
should concentrate on next. We are of course looking at topics as
Microsoft Viva and the Power Platform but if you have any suggestions,
please let us know by adding your suggestion to our [open
discussion](https://github.com/pnp/cli-microsoft365/discussions/2708) on
GitHub. 
 
### Microsoft 365 app commands  

When building apps for Microsoft 365, next to your code, you also need
to manage how your app is exposed to Microsoft 365. You need to register
your application in Azure Active Directory, and depending what type of
app you build, you might need to deploy it to an app catalog as well.
All these properties are managed in different locations and we're
thinking of ways that we could simplify it for you.
 
What else could we simplify? Let us know what you think by helping out
with one of our [open
issues](https://github.com/pnp/cli-microsoft365/issues/2813) or chime in
on our [open
discussion](https://github.com/pnp/cli-microsoft365/discussions/2708)!
 
### Power Platform commands 

Business application built using the Power Platform, most notably Power
Apps and Power Automate, are becoming ubiquitous with Microsoft 365. We
are looking at adding more commands in the future to simplify the
management of your Power Apps, Flows and Solutions, starting with the
ability to register Power Apps management applications in your
environments.
 
What else could we simplify? Let us know what you think by helping out
with one of our [open
issues](https://github.com/pnp/cli-microsoft365/issues/2813) or chime in
on our [open
discussion](https://github.com/pnp/cli-microsoft365/discussions/2708)!
 
### More commands, what else 

Microsoft 365 is evolving and new capabilities are being released every
day. With CLI for Microsoft 365, we aim to help you manage your tenant
on any platform in a consistent way, no matter which part of Microsoft
365 you interact with. While we keep adding new commands to CLI for
Microsoft 365 each release, we still barely scratched the surface with
what's possible in Microsoft 365. In the upcoming versions of the CLI
for Microsoft, you can expect us to add more commands across the
different workloads in Microsoft 365.
 
### Azure AD Graph API Deprecation 

We have started to prepare changes for the next major version of CLI for
Microsoft 365 which will introduce breaking changes. Some of the changes
we are looking to make are to refactor commands where we currently use
the Azure AD Graph API, which will be officially deprecated on 30th June
2022, to instead use supported endpoints in the Microsoft Graph API.
 
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
 
 
 
``` {.lia-code-sample .language-sh}
npm i -g @pnp/cli-microsoft365
```
 
 
 
Alternatively, you can get the latest release from Docker by executing:
 
 
 
``` {.lia-code-sample .language-sh}
docker run --rm -it m365pnp/cli-microsoft365:latest
```
 
 
 
If you need more help getting started or want more details about the
commands, the architecture or the project, go
to [aka.ms/cli-m365](https://aka.ms/cli-m365).
 
If you see any room for improvement, please, don't hesitate to reach out
to us either
on [GitHub](https://github.com/pnp/cli-microsoft365/issues) or [twitter](https://twitter.com/climicrosoft365).
