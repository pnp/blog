---
title: "CLI for Microsoft 365 v3.10"
date: 2021-05-30T11:31:00-04:00
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

Following our monthly release cadence, we've released a new version of
the CLI for Microsoft 365 with some new capabilities. Here are a few of
the most noteworthy additions.

 
## Changes


We've continued improving CLI building upon the changes we've introduced
in the previous version.



**Added support for printing errors as JSON in JSON output**

When scripting using the CLI, it is common to use the JSON output from
commands which makes it easier to work with command responses. In the
example below that uses PowerShell we can convert the JSON response into
a PowerShell object using the *ConvertFrom-Json* cmdlet.

```bash
$lists = m365 todo list list -o json | ConvertFrom-Json
```


However if an error was thrown, the CLI would return the error as a
plain text string and this can be inconvenient as your script is
expecting a JSON response.

To help with error handling when using this approach, we have added
support for changing the default error output type to JSON. To set the
default output type for errors, execute:


```bash
m365 cli config set --key printErrorsAsPlainText --value false
```


**Enhanced spo site apppermission commands**



When working with site app permissions using the CLI we previously did
not return information about the app roles which can be defined,
therefore we have added returning the app roles when using the *spo site
apppermission get* and *spo site apppermission list* commands in the
response.



## New Commands

**Gets Azure AD app registration roles**
When creating applications that use Azure AD authentication we can
define custom roles that we can assign permissions to users or apps. The
application defines and publishes the app roles and interprets them as
permissions during authorization. 
 
To return the roles published by an Azure AD application registration by
its name, execute:
 
```bash
m365 aad app role list --appName "My app"
```
 
**Get the value of a CLI for Microsoft 365 configuration option**
We recently announced that we added support for configuring the CLI to
your own preferences using the *cli config set* command, this enables
you to change some of the default settings such as changing all command
outputs to be JSON rather than text.
 
To return the current value of a CLI configuration option, execute:
 
```bash
m365 cli config get --key output
```
 
**Upload files using Microsoft Graph**
The ability to upload files has been possible in the CLI for some time
using the *spo file add *command, this command however uses
SharePoint-based APIs to perform the upload and does not support new
authorisation features such as the ability to control app access to
specific site collections using the *Sites.Selected* permission scope.
 
To add support for the new permission scope, we have added a new command
that uses the Microsoft Graph in its implementation, the existing *spo
file add* command will remain to provide backwards compatibility.
 
To add a file to a specific site, execute:
 
```bash
m365 file add --filePath file.pdf --folderUrl "https://contoso.sharepoint.com/Shared Documents"
```
 
**Remove a specified Power App**
Microsoft Power Apps is a popular no/low code business application
development platform in Microsoft 365 and managing apps created by
business users is an important maintenance tasks for administrators. We
have extended our support for Power Apps by introducing a command to
remove Power Apps from an environment.
 
To remove a specified Microsoft Power App, execute: 
 
```bash
m365 pa app remove --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d
```
 
**Updates a specific application permission for a site**
The Microsoft Graph gives us the ability to create site permissions on
SharePoint Online or OneDrive sites, which has been possible in the CLI
using the *spo site apppermission add* command, however it was not
possible to update these registrations so we have added a new command to
add that support.
 
To update a specific application permission by its name on a given site
collection, execute:
 
```bash
m365 spo site apppermission set --siteUrl https://contoso.sharepoint.com/sites/project-x --appDisplayName Foo --permission read
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


**Replace user in Microsoft 365 Group or Microsoft Team with another
user**



When an employee leaves an organisation you may want to find and replace
the employee account with another account.


This script helps [update the
membership](https://pnp.github.io/cli-microsoft365/sample-scripts/aad/replace-membership-of-selected-groups/)
by accepting the old user to be replaced, the new user that will be
added and a CSV file containing the groups or teams to be iterated over.

**Monitor site collection storage usage**



As a SharePoint Administrator one of your tasks is to ensure that the
storage being used in your Microsoft 365 tenant does not exceed the
allowance of your tenant so this does not negatively impact daily usage.


This
[script](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/monitor-site-collection-storage-usage/)
helps by iterating over all SharePoint Online sites in your Microsoft
365 tenant, listing any sites that are over a defined storage threshold
and emails the results to a specific email address.



**Add multiple folders in libraries using a CSV file**



When adding files into SharePoint Online, a common task is to create a
defined folder structure in target document libraries within a target
SharePoint Online site before adding the files.

This
[script](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/add-multiple-folders-in-libraries-using-csv-file/)
helps by showing how to create folder structures in different document
libraries using a CSV file as an input.

**Replace SharePoint Online Site Collection Administrator with another
user**


When an employee leaves an organisation you may want to find and replace
the employee account with another account.

The
[script](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/replace-site-collection-admin/)
helps by removing a user from a given SharePoint Online site collection
and adds a new user as a Site Collection Administrator.

**Search Power Automate Flows for specific connections**

Microsoft Power Automate is a very powerful workflow tool in Microsoft
365 which use connectors to integrate with different platforms, a common
connector that is used is the SharePoint Online connector which help
simplify requests made to SharePoint Online, however it can be difficult
to get a view of which Power Automate Flows are connected to specific
SharePoint Online sites.


This
[script](https://pnp.github.io/cli-microsoft365/sample-scripts/flow/search-flows-for-connection/)
helps by iterating over all Power Automate Flows in your Microsoft 365
tenant, searches the exported Flows for a given Site Collection URL and
returns the results.



## Contributors
 
This release wouldn't be possible without the help of (in alphabetical
order)

 
-   [Cas van Iersel](https://github.com/casvaniersel)
-   [Vipul Kelkar](https://github.com/vipulkelkar)
-   [Patrick Lamber](https://github.com/plamber)
-   [Veronique Lengelle](https://github.com/veronicageek)
-   [Waldek Mastykarz](https://github.com/waldekmastykarz)
-   [Abderahman Moujahid](https://github.com/Abderahman88)
-   [Nanddeep Nachan](https://github.com/nanddeepn)
-   [Albert Jan-Schot](https://github.com/appieschot)
-   [Garry Trinder](https://github.com/garrytrinder/)
 


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


### Updating Azure AD apps
 


Recently, we introduced a command to easily create Azure AD app
registrations. Because they're backbone of every app you'd build on
Microsoft 365, we think you should be able to create them as easily as
possible. So with CLI for Microsoft 365, you can create a fully
configured Azure AD app for the most common scenarios with just one line
of code.


We're currently working on adding support for updating Azure AD app
registration which will be helpful for example when building apps for
Microsoft Teams. Stay tuned!


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
 


Recently, we shipped our first ensure command - an [easy way to help you
that a site with specific settings
exists](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-ensure/).
If it doesn't, CLI creates it for you, if it does, CLI ensures it has
the right properties. All in one line of code. We'd love to hear from
you how you like it and if it's something you'd like us to implement
for other commands as well.

 
## Try it today


Get the latest release of the CLI for Microsoft 365 from npm by
executing:

 


```PowerShell
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
