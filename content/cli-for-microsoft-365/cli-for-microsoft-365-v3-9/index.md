---
title: "CLI for Microsoft 365 v3.9"
date: 2021-04-29T05:29:00-04:00
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
projects no matter which operating system or shell you use

While building solutions for Microsoft 365 expands beyond the Windows
operating system, managing many of the platform settings is possible
only through PowerShell on Windows. As more and more users work on
non-Windows machines, it's inconvenient for them to have to use a
Windows virtual machine to configure their tenants. With the CLI for
Microsoft 365, you can configure your tenant no matter which operating
system you use. Additionally, using CLI for Microsoft 365, you can
manage your SharePoint Framework projects.

## New version of CLI for Microsoft 365 -- v3.9


Following our monthly release cadence, we've released a new version of
the CLI for Microsoft 365 with some new capabilities. Here are a few of
the most noteworthy additions.


## Changes
 
We've continued improving CLI building upon the changes we've introduced
in the previous version.

**Support for upgrading SharePoint Framework (SPFx) projects to beta
versions**

With the new [public preview release of SharePoint Framework
1.12.1](https://developer.microsoft.com/sharepoint/blogs/announcing-public-preview-of-sharepoint-framework-1-12-1/)
and a new public quality assurance model that was announced with it, we
are delighted to announce that we have added support for upgrading your
SharePoint Framework projects to the latest beta release candidate.



 



To upgrade your SharePoint Framework project to the latest preview
version, execute:



 


```bash
    m365 spfx project upgrade --preview
```


As part of our beta release cadence, when new release candidates are
made available in npm, we will release support for upgrading to that new
version as soon as they are available.


**Support for creating Azure Active Directory (AAD) applications from a
manifest**



As part of our efforts to make development easier in Microsoft 365, we
have released support for creating Azure Active Directory application
registrations from an app manifest file.

A typical scenario for developers and administrators is to create app
registrations in the Azure Portal manually through the friendly user
interface, however this can be time-consuming and error prone to repeat
for multiple environments.


This update will enable you to copy the app manifest file that is
generated in the Azure Portal and pass it into the command to
confidently recreate app registrations.

```bash
    m365 aad app add --manifest @manifest.json
```

**Support for using relative URLs in SharePoint Online (SPO) commands**


 
CLI for Microsoft 365 contains a number of commands for managing
SharePoint Online. Each of these commands requires you to specify the
site or web on which you want to execute the command. For example, to
get information about a site collection located at
`https://contoso.sharepoint.com/sites/contoso`, you'd execute:
 
```bash
m365 spo site get --url https://contoso.sharepoint.com/sites/contoso
```

If you executed an *spo* command previously, CLI for Microsoft 365
already knows the hostname of your SharePoint Online tenant. In such
case, you can use a server-relative URL as well:
 
```bash
m365 spo site get --url /sites/contoso
```

If you try to use a server-relative URL but CLI for Microsoft 365
doesn't know of your SharePoint Online URL yet, you will see an error
prompting you to either use an absolute URL or set the SPO URL using the
*spo set* command:
 
```bash
m365 spo set --url https://contoso.sharepoint.com
```

You can also execute a command like *m365 spo site list* that will
automatically detect your SharePoint Online tenant URL for you.
 
To check if CLI detected the SPO URL previously, use the *m365 spo
get* command.


**Moved from adal-node to msal-node**



CLI for Microsoft 365 up to this point has been using the Microsoft
Azure Directory Authentication Library for nodejs (adal-node) for
handling authentication requests between the CLI and Microsoft 365,
however the ADAL library was put into maintenance mode and stopped
receiving updates on June 30th 2020.

With this release we have moved to use the Microsoft Authentication
Library for nodejs (msal-node) which replaces adal-node, ensuring that
the CLI for Microsoft 365 is able to receive updates and take advantage
of new authentication features added to msal-node going forwards. 



## New Commands
 
**Add a role to a specified Azure Active Directory (AAD) app
registration**
Role-based access control (RBAC) is a popular mechanism to enforce
authorization in applications. When using RBAC, an administrator grants
permissions to roles, and not to individual users or groups. The
administrator can then assign roles to different users and groups to
control who has access to what content and functionality.
 
To add a role to the Azure AD application registration specified by its
name, execute:
 
```bash
m365 aad app role add --appName "My app" --name Managers --description "Managers" --allowedMembers usersGroups --claim managers
```
 
**Add a new Microsoft Planner plan**
 
All teams need to track tasks, a quick and easy way to do that in
Microsoft 365 is to create a shared plan in Planner to manage and assign
those tasks to team members.
 
To add a new Microsoft Planner plan to a Microsoft 365 Group, execute:
 
```bash
m365 planner plan add --title "My Planner Plan" --ownerGroupName "My Planner Group"
```
 
**Add a specific application permissions to a SharePoint Online site**
 
On Feb 11, Microsoft announced [support for resource-specific consent in
SharePoint via Microsoft
Graph](https://developer.microsoft.com/microsoft-365/blogs/controlling-app-access-on-specific-sharepoint-site-collections/) in
this release we have added a new command to support adding permissions
to SharePoint Online sites.
 
To add a specific application permissions to a SharePoint Online site,
execute:

```bash
    m365 spo site apppermission add --siteUrl https://contoso.sharepoint.com/sites/project-x --permission read --appDisplayName Foo
```

**Return the User Profile properties of a specific SharePoint Online
user**
 
To return the user profile properties of specific user, execute:
 
```bash
m365 spo userprofile get --userName 'john.doe@mytenant.onmicrosoft.com'
```
 
**Create the Microsoft Viva Connections desktop app package to upload to
Microsoft Teams**
Microsoft Viva Connections was the first part of the Viva Employee
Experience features to be be made Generally Available to all Microsoft
365 tenants on 31st March 2020, however to enable Viva Connections in
your tenant a number of deployment steps that needed to be followed,
which includes the creation of the desktop app package that is deployed
to Microsoft Teams. So we have added a new command which simplifies the
creation of this app package for you.
 
To create the app package, execute:
 
```bash
m365 viva connections app create --portalUrl https://contoso.sharepoint.com --appName Contoso --description "Contoso company app" --longDescription "Stay on top of what's happening at Contoso" --companyName Contoso --companyWebsiteUrl https://contoso.com --coloredIconPath icon-color.png --outlineIconPath icon-outline.png
```
 
 To upload the app package to your Microsoft Teams app catalog, execute:
 
```bash
m365 teams app publish --filePath ./contoso.zip
```

## New script samples
 


CLI for Microsoft 365 is a great tool both for quick adjustments to the
configuration of your Microsoft 365 tenant as well as automating more
complex tasks. Because CLI for Microsoft 365 is cross-platform you can
use it on any OS and in any shell. To help you get started using the CLI
for Microsoft 365 for automation scenarios, we started gathering some
[sample
scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/introduction).

 


If you have any scripts that you use frequently, please
[share](https://github.com/pnp/cli-microsoft365/discussions) them with
us so that we can learn more about the common automation scenarios.


**Cleanup completed Microsoft To Do tasks**



Microsoft To Do is the go to personal task management tool of choice in
Microsoft 365, however completed tasks can sometimes get in the way.




This script helps [remove all completed Microsoft To Do
tasks](https://pnp.github.io/cli-microsoft365/sample-scripts/todo/cleanup-completed-todos/)
by iterating over all of your task lists and deleting tasks that have
been marked as completed.



**Create a Microsoft Teams team and bulk add members from CSV file**



Microsoft Teams is core to collaboration in Microsoft 365, but creating
several teams and adding new members to those Teams can be time
consuming.



This sample script shows you [how to create a Team and add members and
owners using a
CSV](https://pnp.github.io/cli-microsoft365/sample-scripts/teams/create-team-and-add-members-and-owners/).



**Setup an example SharePoint Online site**



When creating SharePoint Online sites, generally you want to make some
immediate changes after its creation.



\
This script is a good starting point for a [setup script to create site
with some assets like columns, content types, lists,
navigation](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/setup-example-site/)
etc.
 
The given example:

-   creates a site,
-   adds a site column and a content type,
-   adds list and modifies it's settings (add a content type to it and
    makes it hidden),
-   adds a document library with a custom column and some folder,
-   modifies the all items view of the document library,
-   modifies the site navigation links



**Upload local files and folders to SharePoint Online**



SharePoint Online is the backbone of Microsoft 365 for file storage and
sharing. This script shows how you can use the CLI to [upload files
located on a local folder to a SharePoint Online library or
subfolder](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/upload-local-files-and-folder/).



**Bulk add members to Microsoft Teams team from CSV file**



Adding new team members to an existing Team through the Teams user
interface can be time consuming, this script will [add users to existing
Teams contained in a .csv
file](https://pnp.github.io/cli-microsoft365/sample-scripts/teams/bulk-add-users-teams/). 



**Copy files to another SharePoint Library in another site**



This script helps you [copy files across different sites in SharePoint
Online](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/copy-files-to-another-library/),
it shows you how you can copy all files and folders from source library
to a different library in different SharePoint site keeping the same
folder and subfolder structure and copy all files from all folders and
subfolders from source library to a different library to a root folder
in different SharePoint

**Remove a Site Collection Admin User from all Site Collections**



When employees leave organisations or change job roles it is important
that access is removed where it is no longer required.



This script helps [remove a designated user in every SharePoint Online
site in the
tenant](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/remove-siteCollection-admin-user/)
if he/she is a Site Collection Admin. This applies to Group-connected
sites, non group-connected sites, or classic sites.

**Replace an owner in a Microsoft 365 Group or Microsoft Team**



This script helps [find all the Microsoft 365 Groups that a user is an
Owner of and replace them with someone
else](https://pnp.github.io/cli-microsoft365/sample-scripts/aad/replace-owner-with-a-different-one/)
useful for when an employee leaves and ownership needs to be updated.


**Add a SharePoint Site Collection Administrator using CSV file**


This script helps you [add a new SharePoint Site Collection
Administrator to many sites using a CSV
file](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/add-site-collection-admin-using-csv-file/),
this is useful for granting access to sites that are not visible in the
SharePoint Admin Center such as Microsoft Teams Private Channels.



## Contributors


This release wouldn't be possible without the help of (in alphabetical
order)

 
-   [Phil Harding](https://github.com/phillipharding)
-   [Patrick Lamber](https://github.com/plamber)
-   [Veronique Lengelle](https://github.com/veronicageek)
-   [Waldek Mastykarz](https://github.com/waldekmastykarz)
-   [Smita Nachan](https://github.com/SmitaNachan)
-   [Nanddeep Nachan](https://github.com/nanddeepn)
-   [Dipen Shah](https://github.com/dips365)
-   [Albert Jan-Schot](https://github.com/appieschot)
-   [Garry Trinder](https://github.com/garrytrinder/)
-   [Joseph Velliah](https://github.com/sprider)
-   [Rabia Williams](https://github.com/rabwill)
-   [Adam Wojcik](https://github.com/Adam-it)
 


Thank you all for the time you chose to spend on the CLI for Microsoft
365 and your help to advance it!


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
using SPO or PnP PowerShell that you use frequently, please share them
with us so that we can learn more about the common automation scenarios.


### 'ensure' commands
 


We've just shipped our first ensure command - an easy way to help you
that a site with specific settings exists. If it doesn't, CLI creates
it for you, if it does, CLI ensures it has the right properties. All in
one line of code. We'd love to hear from you how you like it and if
it's something you'd like us to implement for other commands as well.

 
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
commands, the architecture or the project, go to
[aka.ms/cli-m365](https://aka.ms/cli-m365).

 


If you see any room for improvement, please, don't hesitate to reach out
to us either on [GitHub](https://github.com/pnp/cli-microsoft365) or
[twitter](https://twitter.com/climicrosoft365).
