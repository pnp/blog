---
title: "CLI for Microsoft 365 v3.11"
date: 2021-06-30T10:45:00-04:00
author: "Garry Trinder"
githubname: garrytrinder
categories: ["CLI for Microsoft 365"]
images:
- images/banner-cli-m365.png
tags: ["CLI for Microsoft 365"]
type: "regular"
---
 
[Manage Microsoft 365 and SharePoint Framework projects on any
platform]


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

New version of CLI for Microsoft 365 -- v3.11

Following our monthly release cadence, we've released a new version of
the CLI for Microsoft 365 with some new capabilities. Here are a few of
the most noteworthy additions.



 
## Changes


We've continued improving the CLI, building upon the changes we've
introduced in the previous version.



 





**Upgrading commands to use Microsoft Graph v1.0 endpoints**






When new capabilities are added to the Microsoft Graph they are usually
added to the beta endpoint, this is to give developers early access to
new capabilities however this is based on an assumption that these
endpoints are subject to change until they reach general availability
where they are added to the v1.0 endpoint.



 



Sometimes when we add new commands to the CLI for Microsoft 365 we make
use of beta endpoints to add new capabilities to the CLI, for example,
we recently added several Microsoft To Do commands that used the beta
endpoints when they were initially released.



Over time however these endpoints have matured, reaching general
availability and are now available in the v1.0 endpoint, therefore we
have updated our code to reflect this.



 



We have updated the following commands in this version of the CLI to use
v1.0 endpoints.



 

-   todo list add
-   todo list list
-   todo list remove
-   todo list set
-   teams user app remove
-   teams user app add
-   teams team set
-   teams message reply list
 
**Retrieve details of a Power App by its name**
Previously we only supported retrieving details of a Power App from an
environment using its ID, however in this release we have enhanced the
command to enable you to return a Power App by its name making it much
more user friendly.
 
To retrieve details of a Power App by its name, execute:

```bash
m365 pa app get --displayName App
```
 
**Update description of a SharePoint Online site**
Previously we supported the ability to update properties on SharePoint
Online site, however one property that was not supported was the
description property. In this release, we have enhanced commands to
provide support for updating this on both modern and classic sites.
 
To update the description on a modern SharePoint Online site, execute:

```bash
m365 spo site set --url https://contoso.sharepoint.com/sites/ModernSite --description "something"
```
 
To update the description on a classic SharePoint Online site, execute:

``` {.lia-code-sample .language-applescript}
m365 spo site classic set --url https://contoso.sharepoint.com/sites/ClassicSite --description "something"
```
 
**SPFx v1.12.1 support added to spfx doctor**
The *spfx doctor* command has been updated to support the latest version
of SharePoint Framework.
 
The command helps you verify that all prerequisites for building
solutions using a particular version of the SharePoint Framework are met
in your development environment. It starts by detecting the version of
SharePoint Framework that you want to use.
 
First, it looks at the current project. If you didn't run the command
in the context of a SharePoint Framework project, the command will try
to determine the SharePoint Framework version based on the SharePoint
Framework Yeoman generator that you have installed either in the current
directory or globally.
 
Based on the determined version of the SharePoint Framework, the command
will look at other dependencies such as Node.js, npm, Yeoman, Gulp,
React and TypeScript to verify if their meet the requirements of that
particular version of the SharePoint Framework.
 
If you miss any required tools or use a version that doesn't meet the
SharePoint Framework requirements, the command will give you a list of
recommendation how to address these issues.
 
To verify if your environment meets the requirements to work with the
SharePoint Framework, execute:

```bash
m365 spfx doctor
```

## New Commands
 
**Remove role from Azure AD application**
In the previous CLI release we added a command that enabled to you
define custom roles on Azure AD applications that you can use to assign
permissions to users or apps. In this release we have added the ability
to remove a custom role.
 
To remove a role published by an Azure AD application registration by
its name, execute:
 
```bash
m365 aad app role delete --appName "My app" --claim "Product.Get"
```
 
**Update Azure AD application registration**
We have added a new command that gives you the ability to update an
Azure AD application registration.
 
In this first iteration of the command, we only support the ability to
update the application URI property value.  
 
To update the application URI of an Azure AD application registration
specified by its name, execute:

```bash
m365 aad app set --name "My app" --uri https://contoso.com/e75be2e1-0204-4f95-857d-51a37cf40be8
```
 
**Clear Microsoft 365 Groups from the tenant recycle bin**
When Microsoft 365 Groups are deleted in a Microsoft 365 tenant, they
are soft deleted and are moved to the tenant recycle bin which they will
remain for 30 days at which point they will be automatically hard
deleted, however whilst the group remains in the recycle bin it is not
possible to create new groups with the same name.
 
Whilst an administrator can manually hard-delete groups from the recycle
bin via the Microsoft 365 Admin Portal however this can be inconvenient
if you wish to bulk hard-delete these groups. We have added a command
that removes all of the groups in the recycle bin in a single command to
make this easier.
 
To remove all deleted Microsoft 365 Groups in the tenant, execute:

```bash
m365 aad o365group recyclebinitem clear
```
 
**Reset CLI configuration option to its default value**
We recently introduced commands that enables you to personalise the
behaviour of the CLI to your own preferences using the *cli
config* commands. In this release we have added the ability for you to
reset these options back to their default values.
 
To reset the *showHelpOnFailure* to its default value, execute:

```bash
m365 cli config reset --key showHelpOnFailure
```
 
Alternatively, to reset all configuration options to their default
values, execute:

```bash
m365 cli config reset
```
 
**Microsoft 365 Activation Report Commands**
We have added commands that enables administrators get an understanding
of how many users have activated Microsoft 365 on desktops and devices
as well as who has made those activations.
 
To get the count of Microsoft 365 activations on desktops and devices,
execute:

```bash
m365 tenant report office365activationcounts
```
 
To get the count of users that are enabled and those that have activated
the Office subscription on desktop or devices or shared computers,
execute:

```bash
m365 tenant report office365activationsusercounts
```
 
To get details about users who have activated Microsoft 365, execute:

```bash
m365 tenant report office365activationsuserdetail
```
 
**Generate SharePoint Framework solution from a HTML file**
SharePoint Framework is the extensibility model of choice in Microsoft
365, whether that is extending SharePoint Online or Microsoft Teams, it
is the go-to framework for in house development.
 
We have introduced a command that simplifies the creation of a
SharePoint Framework solution package that generates a SharePoint
Framework web part that uses a local HTML file as the contents of the
web part.
 
To generate a web part that shows the weather for Amsterdam, load web
part contents from a local file, allow the web part to be deployed to
all sites and expose the web part in Teams as a personal tab, execute:
    m365 spfx package generate --webPartTitle "Amsterdam weather" --webPartDescription "Shows weather in Amsterdam" --packageName amsterdam-weather --html @amsterdam-weather.html --allowTenantWideDeployment --enableForTeams all

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

**Resubmit all failed Power Automate Flow runs for a specific flow in an
environment**



Have you ever been forced to resubmit lot of failed Power Automate flow
runs manually?
 
This
[script](https://pnp.github.io/cli-microsoft365/sample-scripts/flow/resubmit-all-failed-flow-runs/)
will resubmit all failed flow runs of a Power Automate flow created in
an environment. 


**Cancel all running Power Automate Flow runs for a Flow in an
environment**



Do you want to automate the cancellation of running Power Automate Flow
runs?

This
[script](https://pnp.github.io/cli-microsoft365/sample-scripts/flow/cancel-all-running-flow-runs/)
will cancel all running flow runs of a Power Automate flow created in an
environment.


**Remove SharePoint API permissions**



[When building SharePoint Framework solutions connected to APIs secured
with Azure Active Directory, you might need to clear the list of granted
API permissions.]



 



This
[script](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/remove-api-permissions/)
helps you to quickly remove SharePoint API permissions.
 
**Remove pending SharePoint API permission requests**
When building SharePoint Framework solutions connected to APIs secured
with Azure Active Directory, you'll easily end up with many pending
permission requests.
 
This
[script](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/remove-pending-api-permission-requests/)
helps you to quickly remove pending SharePoint API permission requests.

## Contributors


This release wouldn't be possible without the help of (in alphabetical
order)

 
-   [Mohamed Ashiq Faleel](https://github.com/ashiqf)
-   [Vipul Kelkar](https://github.com/vipulkelkar)
-   [Shantha Kumar](https://github.com/ktskumar)
-   [Waldek Mastykarz](https://github.com/waldekmastykarz)
-   [Abderahman Moujahid](https://github.com/Abderahman88)
-   [Nanddeep Nachan](https://github.com/nanddeepn)
-   [Smita Nachan](https://github.com/SmitaNachan)
-   [Albert Jan-Schot](https://github.com/appieschot)
-   [strafe](https://github.com/strafe)
-   [Garry Trinder](https://github.com/garrytrinder/)
-   [Siddharth Vaghasia](https://github.com/siddharth-vaghasia)
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
