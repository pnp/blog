---
title: "CLI for Microsoft 365 v4.1"
date: 2021-10-22T04:48:00-04:00
author: "Garry Trinder"
githubname: garrytrinder
categories: ["CLI for Microsoft 365"]
images: 
- images/CLI for Microsoft 365 v4.1
tags: ["CLI for Microsoft 365"]
type: "regular"
---
 
We've just published a new version of the CLI for Microsoft 365 with
new commands for working with and managing Microsoft 365 tenants and
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
 
## New version of CLI for Microsoft 365 -- v4.1 
 
Following our monthly release cadence, we've released a new version of
the CLI for Microsoft 365 with some new capabilities.
 
Here are a few of the most noteworthy additions.
 
## Updates 

### Upgrade SharePoint Framework projects to SPFx v1.13 
 
Recently, Microsoft announced that SPFx v1.13, which was previously in
public preview, has now been made Generally Available, introducing new
exciting capabilities for extending Viva Connections using Adaptive Card
Extensions. To learn more about extending Viva Connections [see the new
learning path](https://aka.ms/extend-viva-connections).
 
To upgrade your SPFx project to v1.13 version, change the working
directory to your project and execute:
 
 
```bash
m365 spfx project upgrade --output md > report.md
```
 
 
We'd also recommend that you try a richer upgrade report based on the
Visual Studio Code CodeTour extension:
 
 
```bash
m365 spfx project upgrade --output tour
```
 
 
For more information about upgrading SharePoint Framework projects, see
the [CLI
documentation](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade/).

### Updates information of a specified Azure AD user 
 
User management is one of the core activities of every Microsoft 365
tenant admin. We've introduced a new command that enables you to update
Azure AD users properties and the ability to enable or disable those
accounts.
 
To update the properties of a specific user, execute:
 
 
```bash
m365 aad user set --userPrincipalName steve@contoso.onmicrosoft.com --Department "Sales & Marketing" --CompanyName Contoso
```
 
 
To disable a specific user, execute:
 
 
```bash
m365 aad user set --userPrincipalName steve@contoso.onmicrosoft.com --accountEnabled false
```
 
 
For more information about managing Azure AD user accounts, see the [CLI
documentation](https://pnp.github.io/cli-microsoft365/cmd/aad/user/user-set/).
 
### Upgrading commands to Microsoft Graph v1.0 endpoint 
 
When adding new commands to CLI for Microsoft 365, we sometimes take
advantage of Microsoft Graph Beta endpoint to provide new capabilities,
over time however these endpoints mature and reach General Availability,
being made available in the Microsoft Graph v1.0 endpoint.
 
As part of our regular review of commands, we highlighted some commands
that could be upgraded. The following commands have been upgraded as
part of this release:
 
-   aad siteclassification get
-   aad siteclassification enable
-   aad siteclassification set
 
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
 
### Flow runs day summary report 
 
This [sample
script](https://pnp.github.io/cli-microsoft365/sample-scripts/flow/flow-runs-day-summary/)
creates a report of all flow runs from current day and sends the report
as an adaptive card to the provided url.
 
### Add users to the Associated SharePoint Groups of a site from a CSV File 
 
This [sample
script](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/add-users-associatedspgroup-site-csv-file/)
adds multiple users to associated SharePoint groups (Owners, Members,
Visitors) of a site from a CSV file.
 
### List Microsoft Teams teams, channels, and tabs in the tenant

This [sample
script](https://pnp.github.io/cli-microsoft365/sample-scripts/teams/list-teams-channels-tabs-for-tenant/)
will list some information about each Teams, channels, and tabs within
the tenant.
 
## Contributors 
 
This release wouldn't be possible without the help of (in alphabetical
order):
 
-   [Atharva321](https://github.com/Atharva321)
-   [Shantha Kumar](https://github.com/ktskumar)
-   [Veronique Lengelle](https://github.com/veronicageek)
-   [Waldek Mastykarz](https://github.com/waldekmastykarz)
-   [Arjun Menon](https://github.com/arjunumenon)
-   [Abderahman Moujahid](https://github.com/Abderahman88)
-   [Nanddeep Nachan](https://github.com/nanddeepn)
-   [Garry Trinder](https://github.com/garrytrinder)
-   [Rabia Williams](https://github.com/rabwill)
-   [Adam Wojcik](https://github.com/Adam-it)

## Work in progress 
 
Here are some things that we are currently working on.
 
### CLI for Microsoft 365 v4 Themes 
 
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
