---
title: "CLI for Microsoft 365 v4.2"
date: 2021-11-26T06:38:00-05:00
author: "Albert-Jan Schot"
githubname: appieschot
categories: ["CLI for Microsoft 365"]
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
 
## New version of CLI for Microsoft 365 -- v4.2 

Following our monthly release cadence, we've released a new version of
the CLI for Microsoft 365 with some new capabilities. Here are a few of
the most noteworthy additions.
 
## Updates 
 
### Upgrade SharePoint Framework projects to SPFx v1.13.1  
 
With the [release of SharePoint Framework
v1.13.1](https://docs.microsoft.com/sharepoint/dev/spfx/release-1.13.1 "SharePoint Framework v1.13.1") we
made sure to provide you with the tools to upgrade your solutions using
the CLI for Microsoft 365. 
 
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
 
You can verify your environment configuration for using the specific
version of the SharePoint Framework using the following command: 
 
``` {.lia-code-sample .language-applescript}
m365 spfx doctor
```
 
For more information about upgrading SharePoint Framework projects, see
the [CLI
documentation](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade/).
 
### Extended 'aad app add' with *save*  

With the new *save* option, when creating a new Azure AD app, you
can store the information about the created app in a local
*.m365rc.json* file. By storing this information, you can keep track
which app(s) you use in your current project. In the future versions of
CLI for Microsoft 365, we'll release dedicated commands that allow you
to easily manage Azure AD apps used in your solutions without having to
manually look them up in the Azure Portal!
 
For more information about the different settings when creating new
apps with the CLI for Microsoft 365 see [the
documentation](https://pnp.github.io/cli-microsoft365/cmd/aad/app/app-add/).
 
### Adding a service principal to a registered Azure AD app 

If you register an application in the portal, an application object as
well as a service principal object are automatically created in your
home tenant. If you register an application using CLI for Microsoft 365
or the Microsoft Graph, you'll need to create the service principal
separately. With the new `aad sp add` command, you can now add a service
principal to an existing Azure AD app.
 
For more information about the adding service principals and the options
see [the
documentation](https://pnp.github.io/cli-microsoft365/cmd/aad/sp/sp-add/).
 
### Retrieving files  

In this version of CLI for Microsoft 365 we introduced the
new  `file list` command. This command is an improved version of
the `spo file list` command. The main difference between the two
commands is, that `file list` uses Microsoft Graph and properly supports
retrieving files from large lists and folders.
 
For more information about retrieving files using this new command and
the options see [the
documentation](https://pnp.github.io/cli-microsoft365/cmd/file/file-list/).
 
### New script samples 

CLI for Microsoft 365 is a great tool both for quick adjustments to the
configuration of your Microsoft 365 tenant as well as automating more
complex tasks. Because CLI for Microsoft 365 is cross-platform you can
use it on any OS and in any shell. To help you get started using the CLI
for Microsoft 365 for automation scenarios, we started gathering
some [sample
scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/).
 
If you have any scripts that you use frequently,
please [share](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=sample.md&title=New+sample+script%3A+%3Cshort+description%3E) them
with us so that we can learn more about the common automation scenarios.
 
#### Use CLI for Microsoft 365 access token  

This [sample
script](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/perform-operations-not-covered-by-cli-for-microsoft-365/) shows
how to handle scenario's where the CLI for Microsoft 365 does not
provide you with a command. It shows how to use the CLI for Microsoft
365 access token and call a REST method to retrieve information around
attachments. Something currently not available in the CLI for Microsoft
365. 
 
#### Export all channels from a team 

This [sample
script](https://pnp.github.io/cli-microsoft365/sample-scripts/teams/export-all-channels-teams/) shows
how to all channels from a Microsoft Teams team to a CSV including
details like description and e-mail address.
 
## Contributors 

This release wouldn't be possible without the help of (in alphabetical
order):

-   [Joakim Högberg](https://github.com/joakimhogberg)
-   [Sudharsan Kesavanarayanan](https://github.com/sudharsank)
-   [Vipul Kelkar](https://github.com/vipulkelkar)
-   [Patrick Lamber](https://github.com/plamber)
-   [Michaël Maillot](https://github.com/michaelmaillot)
-   [Waldek Mastykarz](https://github.com/vipulkelkar)
-   [Abderahman Moujahid](https://github.com/vipulkelkar)
-   [Nanddeep Nachan](https://github.com/vipulkelkar)
-   [Smita Nachan](https://github.com/SmitaNachan)
-   [Joseph Velliah](https://github.com/sprider)
-   [Adam Wójcik](https://github.com/Adam-it)
-   [Rabia Williams](https://github.com/rabwill)
 
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
 
In this version of CLI for Microsoft 365, we introduced the ability for
you to store the information about your Azure AD app in your current
project. In the future versions, we'll add commands to help you manage
Azure AD apps like changing the redirect URI or managing API
permissions. What else could we simplify? Let us know what you think by
helping out with one of our [open
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
 