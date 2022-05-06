---
title: "CLI for Microsoft 365 v3.12"
date: 2021-07-30T02:28:00-04:00
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


## New version of CLI for Microsoft 365 -- v3.12 


Following our monthly release cadence, we've released a new version of
the CLI for Microsoft 365 with some new capabilities. Here are a few of
the most noteworthy additions.


### New Commands 
 
We've continued improving the CLI, adding new commands and we've
introduced in the previous version.

#### Create a bucket in a Microsoft Planner plan 
 
We have added a new command that gives you the ability to create new
buckets in your Microsoft Planner Plans.
 
To create a new bucket in a given plan, execute:
 
    m365 planner bucket add --name "My Planner Bucket" --planName "My Planner Plan" --ownerGroupName "My Planner Group"
 
#### Retrieve buckets from a Microsoft Planner plan 
 
We have added a new command that gives you the ability list the existing
buckets in a given Microsoft Planner Plan.
 
To retrieve information about buckets in a given plan, execute:
 
    m365 planner bucket list --planName "My Plan" --ownerGroupName "My Group"
 
#### Retrieve a list of Microsoft Planner plans 
 
We have added a new command that gives you the ability list the
Microsoft Planner plans associated with a given Microsoft 365 Group.
 
To retrieve information about the plans in a given group, execute:
 
    m365 planner plan list --ownerGroupName "My Planner Group"
 
#### List OneDrive sites 
 
We have added a new command that gives you the ability to list
information about all of the OneDrive sites in a Microsoft 365 tenant.
 
To retrieve a list of OneDrive sites, execute:
 
    m365 onedrive list
 
#### cli doctor 
 
We have introduced a new command that to make it easier for you to
provide all the necessary diagnostic information needed to triage and
debug CLI issues without exposing any security-sensitive details.
 
To retrieve diagnostic information about the current environment,
execute:
 
    m365 cli doctor
 


### Changes 


We've continued improving the CLI, building upon the changes we've
introduced in the previous version.


#### Upgraded commands to use Microsoft Graph v1.0 endpoints 


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


-   teams user app list
-   teams channel get
 
#### Project upgrade support for latest SharePoint Framework developer preview 
 
The *spfx project upgrade* command has been updated to support the
latest developer preview versions.
 
Starting with SharePoint Framework (SPFx) v1.12, developers can try
preview releases of new SPFx generator packages as part of a developer
preview.
 
This release adds the ability to upgrade SharePoint Framework projects
to version 1.13.0-beta.15 which previews Viva Connections extensibility
with Adaptive Card Extensions.
 
To generate instructions for upgrading to the latest preview version,
execute:
 
    m365 spfx project upgrade --preview
 
#### Retrieve Associated Groups of a site  
 
The *spo web get* command can be used to return information about a
given site, previously this did not include returning information about
its associated groups such as Owners, Members and Visitors groups
however in this release we have updated the command to return this
information.
 
To retrieve information about a given site along with it's associated
groups, execute:

```bash
    m365 spo web get --webUrl https://contoso.sharepoint.com/subsite --withGroups
```

### New script samples 
 


CLI for Microsoft 365 is a great tool both for quick adjustments to the
configuration of your Microsoft 365 tenant as well as automating more
complex tasks. Because CLI for Microsoft 365 is cross-platform you can
use it on any OS and in any shell. To help you get started using the CLI
for Microsoft 365 for automation scenarios, we started gathering some
[sample
scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/).

 


If you have any scripts that you use frequently, please
[share](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=sample.md&title=New+sample+script%3A+%3Cshort+description%3E) them
with us so that we can learn more about the common automation scenarios.


#### Add multiple lists in multiple sites 
 


When provisioning lists in SharePoint Online, sometimes we want to
replicate the same list across multiple site collections.

This
[script](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/add-multiple-lists-in-multiple-sites/)
will create multiple lists in multiple sites, including also mapping a
content type to the created lists.

#### Identify failed Site Designs executions 

When people in your organization create new SharePoint sites, you often
need to ensure some level of consistency. For example, you may need
proper branding and theming applied to each new site when they are
created, Site Designs enable to run scripts and code automatically on
the creation of those sites.

This
[script](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/list-failed-sitedesigns/)
will iterate through all site collections in the tenant and returns a
list of site design executions that have errors.

#### List number of files in all lists and folders in a site

When carrying out migrations it is useful to understand the number of
files in a given site and where they are before moving files to a new
location.




This
[script](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/list-all-list-folders-itemcount/)
will iterate over all lists, folders and subfolders in a given site and
return the item count for each.


### Contributors 

This release wouldn't be possible without the help of (in alphabetical
order)


-   [Aakash Bhardwaj](https://github.com/aakashbhardwaj619)
-   [Vipul Kelkar](https://github.com/vipulkelkar)
-   [Sudharsan Kesavanarayanan](https://github.com/sudharsank)
-   [Shantha Kumar](https://github.com/ktskumar)
-   [Patrick Lamber](https://github.com/plamber)
-   [Waldek Mastykarz](https://github.com/waldekmastykarz)
-   [Arjun Menon](https://github.com/arjunumenon)
-   [Abderahman Moujahid](https://github.com/Abderahman88)
-   [Albert Jan-Schot](https://github.com/appieschot)
-   [Dipen Shah](https://github.com/dips365)
-   [Rabia Williams](https://github.com/rabwill)
 
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
