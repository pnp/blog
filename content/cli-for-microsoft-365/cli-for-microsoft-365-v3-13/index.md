---
title: "CLI for Microsoft 365 v3.13"
date: 2021-08-30T11:35:00-04:00
author: "Waldek Mastykarz"
githubname: WaldekMastykarz
categories: ["CLI for Microsoft 365"]
images:
- images/banner-cli-m365.png
tags: ["CLI for Microsoft 365"]
type: "regular"
---
 
We've just published a new version of the CLI for Microsoft 365 with
new commands for working with and managing Microsoft 365 tenants and
SharePoint Framework projects on any platform.
 
Manage Microsoft 365 and SharePoint Framework projects on any platform
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
 
## New version of CLI for Microsoft 365 -- v3.13

Following our monthly release cadence, we've released a new version of
the CLI for Microsoft 365 with some new capabilities. Here are a few of
the most noteworthy additions.
 
### Upgrade SharePoint Framework projects to SPFx v1.13 preview

Recently, Microsoft released a new [preview version of the SharePoint
Framework -
v1.13](https://developer.microsoft.com/sharepoint/blogs/announcing-public-preview-of-sharepoint-framework-1-13-with-viva-connections-extensibility/).
This version of SPFx, introduces new exciting capabilities for extending
Viva Connections using Adaptive Card Extensions.
 
To help you try these capabilities in your projects, we extended CLI for
Microsoft 365 with support for upgrading your existing SharePoint
Framework projects to SharePoint Framework v1.13.0-beta.17.
 
To upgrade your SPFx project to this preview version, change the working
directory to your project and execute:

``` sh
m365 spfx project upgrade --preview --output md > report.md
```
 
We'd also recommend that you try a richer upgrade report based on the
Visual Studio Code CodeTour extension:

``` sh
m365 spfx project upgrade --preview --output tour
```

For more information about upgrading SharePoint Framework projects, see
the [CLI
documentation](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade/).
 
### Login with client ID and secret

When using CLI for Microsoft 365 in unattended scenarios, like building
monitoring solutions or long-running automations, it's recommended that
you login to Microsoft 365 using a certificate. If for some reason
you're unable to do that, you can now fallback to logging in using a
client ID and secret registered with your custom Azure Active Directory
application.
 
To login to Microsoft 365 using client ID and secret, execute:

``` sh
m365 login --authType secret --secret topSeCr3t@007
```
 
For more information about the different abilities to login to Microsoft
365 with CLI for Microsoft 365 see [the
documentation](https://pnp.github.io/cli-microsoft365/cmd/login/).
 
### Retrieve apps installed in a SharePoint site

A part of governance of every Microsoft 365 tenant is keeping track of
which applications are installed where in the tenant. Since Microsoft
365 doesn't provide this information readily for you, it's a common
scenario for automation scripts to scan all sites in the tenant and
retrieve this information periodically.
 
In this version of CLI for Microsoft 365, we introduced a new command
for retrieving the list of apps installed in the given site. To retrieve
the list of installed apps, execute:

``` sh
m365 spo app instance list --siteUrl https://contoso.sharepoint.com/sites/site1
```
 
For more information about managing apps with the CLI for Microsoft 365,
see the
[documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/app/app-instance-list/).
 
### Add one or more users to a SharePoint group

Permission management is one of the core activities of every Microsoft
365 tenant admin. Whenever someone joins or leaves the organization or
switches jobs, they need to adjust permissions in the tenant to reflect
this change. There are many ways to implement permissions in Microsoft
365. One way is to add users to SharePoint groups.
 
In this version of CLI for Microsoft 365 we introduced a command to add
one or more users to a SharePoint group. To add users to a SharePoint
group, execute:

``` sh
m365 spo group user add --webUrl https://contoso.sharepoint.com/sites/SiteA --groupId 5 --userName "Alex.Wilber@contoso.com"
```
 
For more information about managing users in SharePoint groups, see the
[documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/group/group-add/).
 
### Manage application permissions for SharePoint sites

When building applications, one of the common requirements is to grant
these applications access to information stored in SharePoint. Typically
though, applications should only have access to information stored in
specific sites rather than the whole tenant. To support this need,
recently Microsoft released a new set of permissions that allow you to
grant an application access to a specific site.
 
In the previous versions of CLI for Microsoft 365 we introduced support
for managing application permissions for SharePoint sites. In this
version, we extend the support with removing application permissions. To
remove an application permission from the specific site, execute:

``` sh
m365 spo site apppermission remove --siteUrl https://contoso.sharepoint.com/sites/project-x --appDisplayName "My app"
```
 
For more information about managing application permissions for
SharePoint sites, see the
[documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-apppermission-remove/).
 
### Retrieve information about a Microsoft Planner plan

In the previous versions of CLI for Microsoft 365, we introduced support
for managing Microsoft Planner plans. In this version, we extended it,
with retrieving the information about a specific plans. To retrieve it,
execute:

``` sh
m365 planner plan get --title "MyPlan" --ownerGroupName "My Planner Group"
```
 
For more information about managing Microsoft Planner plans, see the
[documentation](https://pnp.github.io/cli-microsoft365/cmd/planner/plan/plan-get/).
 
### New script samples

CLI for Microsoft 365 is a great tool both for quick adjustments to the
configuration of your Microsoft 365 tenant as well as automating more
complex tasks. Because CLI for Microsoft 365 is cross-platform you can
use it on any OS and in any shell. To help you get started using the CLI
for Microsoft 365 for automation scenarios, we started gathering some
[sample
scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/introduction).
 
If you have any scripts that you use frequently, please
[share](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=sample.md&title=New+sample+script%3A+%3Cshort+description%3E)
them with us so that we can learn more about the common automation
scenarios.
 
#### Share social champions to Teams

This [sample
script](https://pnp.github.io/cli-microsoft365/sample-scripts/teams/share-socialchampions/)
shows how to retrieve activities for SharePoint Online, Teams and Yammer
and shares the top 3 contributors for each category as an adaptive card
to the specified webhook url.
 
#### Recognize most active users for a specific Team

This [sample
script](https://pnp.github.io/cli-microsoft365/sample-scripts/teams/recognize-most-active-users-specific-team/)
shows how to retrieve all activities for a specific Microsoft Teams Team
and shares the top 3 contributors based on their score as an adaptive
card to the specified webhook url.
 
## Contributors

This release wouldn't be possible without the help of (in alphabetical
order):

-   [Vipul Kelkar](https://github.com/vipulkelkar)
-   [Shantha Kumar](https://github.com/vipulkelkar)
-   [Waldek Mastykarz](https://github.com/vipulkelkar)
-   [Arjun Menon](https://github.com/vipulkelkar)
-   [Abderahman Moujahid](https://github.com/vipulkelkar)
-   [Nanddeep Nachan](https://github.com/vipulkelkar)
-   [Albert-Jan Schot](https://github.com/appieschot)
-   [Dipen Shah](https://github.com/appieschot)
-   [Garry Trinder](https://github.com/appieschot)
Thank you all for your help and effort to improve CLI for Microsoft 365
for our users.

## Work in progress

Here are some things that we're currently working on.
 
### CLI for Microsoft 365 v4

For the last few months we've been working on a new major version of
CLI for Microsoft 365 - v4. The v4 release is a result of the evolution
of the CLI over time. We planned it, to improve the consistency of the
CLI and make it more intuitive to use. Some changes required us to
introduce breaking changes, which is why we'll be releasing a new major
version. Along with these changes, v4 will contain new and improved
commands, just as we ship them in each release.
 
CLI for Microsoft 365 v3.13 is the last v3.x version of the CLI.
Starting with our next monthly release, scheduled for the end of
September, we will start releasing v4.x versions. v3.13, as well as all
previous versions, will remain available and working, but won't be
updated, which is why we recommend that you upgrade to v4. Along with
the release, we'll publish an upgrade guidance to help you determine
the impact of the upgrade on your work.
 
### More commands, what else

Microsoft 365 is evolving and new capabilities are being released every
day. With CLI for Microsoft 365, we aim to help you manage your tenant
on any platform in a consistent way, no matter which part of Microsoft
365 you interact with. While we keep adding new commands to CLI for
Microsoft 365 each release, we still barely scratched the surface with
what's possible in Microsoft 365. In the upcoming versions of the CLI
for Microsoft, you can expect us to add more commands across the
different workloads in Microsoft 365.
 
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

``` sh
npm i -g @pnp/cli-microsoft365
```
 
Alternatively, you can get the latest release from Docker by executing:

``` sh
docker run --rm -it m365pnp/cli-microsoft365:latest
```
 
If you need more help getting started or want more details about the
commands, the architecture or the project, go to
[aka.ms/cli-m365](https://aka.ms/cli-m365).
 
If you see any room for improvement, please, don't hesitate to reach out
to us either on [GitHub](https://github.com/pnp/cli-microsoft365/issues)
or [twitter](https://twitter.com/climicrosoft365).
