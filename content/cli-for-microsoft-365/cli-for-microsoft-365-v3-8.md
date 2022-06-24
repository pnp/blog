---
title: "CLI for Microsoft 365 v3.8"
date: 2021-03-30T10:00:00-04:00
author: "Garry Trinder"
githubname: garrytrinder
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


## New version of CLI for Microsoft 365 -- v3.8 

Following our monthly release cadence, we've released a new version of
the CLI for Microsoft 365 with some new capabilities. Here are a few of
the most noteworthy additions.

## Changes 

We've continued improving CLI building upon the changes we've introduced
in the previous version.


### Added support for configuring default command output 

In the previous release, we added a new command \`m365 cli config set\`
which gave you the ability to configure the CLI to your personal
preferences, so with this release we have added the ability to configure
the default output for all commands.


To set the default output for all commands to JSON, execute:




```bash
m365 cli config set --key output --value json
```


To set the default output for all commands to test, execute:


 
```bash
m365 cli config set --key output --value text
```
 


If there are other options that you would like to be able to configure,
[please let us
know](https://github.com/pnp/cli-microsoft365/discussions).

### Improved error messages 

In the 3.2.0 release of CLI for Microsoft 365, we replaced the
request library with axios which we use to handle our requests to
Microsoft 365 APIs. 




Unfortunately, this change also changed the way that we handled error
messages and instead of replying with the error message from the API we
instead returned a generic error message which was meaningless.




So in this release, we have reverted back to our previous behaviour and
so now error messages will be returned direct from the API call.

## New Commands 
 
### Return Policies from Azure AD 
 


Azure Active Directory (Azure AD) uses policies to control Azure AD
feature behaviors in your organization. Policies are custom rules that
you can enforce on applications, service principals, groups, or on the
entire organization they are assigned to.


Administrators currently need to call multiple endpoints in the
Microsoft Graph to return a list of policies based on policy type, as
there are eight types of policies that can be listed this is not a
trivial task, so we have We've introduced a single command that can
return all policies created or policies of a specific type.


To return all policies from Azure AD, execute:


```bash
m365 aad policy list
```


To return only Authorization policies, execute:


```bash
m365 aad policy list --policyType authorization
```


For information on the policy types that can be returned, checkout our
[documentation](https://pnp.github.io/cli-microsoft365/cmd/aad/policy/policy-list/) for
this command.


 
## New script samples 
 


CLI for Microsoft 365 is a great tool both for quick adjustments to the
configuration of your Microsoft 365 tenant as well as automating more
complex tasks. Because CLI for Microsoft 365 is cross-platform you can
use it on any OS and in any shell. To help you get started using the CLI
for Microsoft 365 for automation scenarios, we started gathering some
[sample
scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/).


If you have any scripts that you use frequently, please
[share](https://github.com/pnp/cli-microsoft365/discussions) them with
us so that we can learn more about the common automation scenarios.


 
### Monitor and notify Microsoft 365 health status 
 


This script helps [monitor the health status of your Microsoft 365
tenant and notifies if something is not
normal](https://pnp.github.io/cli-microsoft365/sample-scripts/tenant/tenant-monitor-notify-healthstatus/).
It creates a SharePoint List and will add the outage content to that and
will also send an email notification to a specified mailbox to notify
that an ouage has occured.


 
### Grant API permissions to SharePoint Azure Active Directory (AAD) Application 
 


This script helps you to automate a common manual task by [granting API
permissions to an Azure Active Directory
application](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/grant-api-permissions-aad/) for
use in a SharePoint Framework (SPFx) project.


 
### List all Microsoft Teams team's Owners and Members 
 


This script helps you to [list all Teams team's owners and
members](https://pnp.github.io/cli-microsoft365/sample-scripts/teams/list-teams-owners-and-members/) and
export them into a CSV file.


 
## Contributors 
 


This release wouldn't be possible without the help of (in alphabetical
order)


 
-   [Patrick Lamber](https://github.com/plamber)
-   [Michaël Maillot](https://github.com/michaelmaillot)
-   [[Waldek
    Mastykarz]](https://github.com/waldekmastykarz)
-   [Arjun Menon](https://github.com/arjunumenon)
-   [Garry Trinder](https://github.com/garrytrinder/)
-   [Joseph Velliah](https://github.com/sprider)


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
[twitter](https://twitter.com/climicrosoft365)
