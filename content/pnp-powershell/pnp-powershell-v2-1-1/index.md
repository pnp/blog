---
title: PnP PowerShell v2.1.1
summary: PnP PowerShell is a cross-platform PowerShell Module providing over 650 cmdlets that work  with Microsoft 365 environments and more specifically SharePoint Online, Microsoft Teams, Microsoft Planner and Power Automate.
date: 2023-04-04T13:32:34.170Z
author: Gautam Sheth
githubname: gautamdsheth
categories:
  - PnP PowerShell
images:
  - images/PnP-PowerShell-2-1-1-release.png

tags:
  - .NET
  - Azure AD
  - PnP PowerShell
  - Microsoft Teams
  - SharePoint
type: regular
---

## PnP PowerShell

PnP PowerShell is a "swiss army knife" type of PowerShell Module providing over 650 cmdlets that work with Microsoft products such as SharePoint Online, Microsoft Teams, Microsoft Project, Security & Compliance, Azure Active Directory, and more. The advantage is that you will have a consistent way to work with a broad range of Microsoft products from a single connection. No need to download different PowerShell Modules, which all work in a slightly different way, requiring different ways of connecting and authenticating.

PnP PowerShell runs on any device on any platform. This means you can run it i.e. from a Windows machine, Mac, Linux based device, Azure Function, Azure Runbook or even a Raspberry Pi. All in the same consistent way.

For more information about installing PnP PowerShell, please refer to [the documentation](https://pnp.github.io/powershell/articles/index.html).

## New version of PnP PowerShell – v2.1.1

We have released a new version, `2.1.1`, of PnP PowerShell with some new capabilities, improvements , bug fixes and breaking changes.

### Changes

The earlier versions of PnP PowerShell (1.x) were based on `.NET Framework 4.6.2` and `.NET Core 3.1`. 

In December 2022, Microsoft deprecated `.NET Core 3.1`. 

We took this opportunity to change our base framework to `.NET 6`. We also decided to completely drop support for `.NET Framework`.

**What this means is that, PnP PowerShell will no longer work on `PowerShell 5.1` and `PowerShell ISE`**

We decided to drop support for PowerShell 5.1 since it is maintainence mode only. PS 5.1 was based on .NET Framework. 
.NET Framework itself is in kind of a maintainence mode. It no longer receives new features and it does not work cross-platform.
Same applies to PS 5.1 which also doesn't work cross-platform and only receives security fixes.

Going forward, `.NET Core` or as Microsoft calls it `.NET` will be the one that is supported.
`PowerShell 7.2` is based on `.NET 6`. We highly recommend moving to this version or a later version of PowerShell.
`PnP.PowerShell` version `2.1.1` and the versions coming in the future will only be supported on `PS 7.2 or later` versions.

If you or your organizations need to use `PS 5.1`, you can keep using `1.12.0` version of PnP.PowerShell.
If there are any issues in `PnP.PowerShell`, they will be fixed only for `2.1.1` or later versions.

### Major additions and changes

Key new features introduced with the 2.1.1 release are:

- Removed support for PowerShell 5, only PowerShell 7.2 and later will be supported from here onwards.
- Based fully on .NET 6 which brings all the underlying improvements that have been done in .NET.
- We have also bumped versions of quite a few underlying dependencies that we use such as `MSAL.NET`.
- It will use `HTTP/2` where possible which brings improvements to HTTP requests.
- Added support for listing Azure AD Service Principal and modifying their permissions.
- Improved support for using Managed Identity by adding support for User Assigned Managed Identity.
- `Get-PnPField` will by default return the typed field object instead of the generic field object.
- Improved support for restoring and deleting items from the recycle bin to support large number of items.
- `Send-PnPMail` is now majorly improved with additional support for sending mails via Microsoft Graph.

You can find the full changelog [here](https://github.com/pnp/powershell/releases/tag/v2.1.0) and [here](https://github.com/pnp/powershell/releases/tag/v2.1.1).

## Migration Guide

Since this is a major version update, there are quite a few breaking changes.

We have created a [migration guide](https://github.com/pnp/powershell/blob/dev/MIGRATE-1.0-to-2.0.md) for you.

## Contributors

This release wouldn't have been possible without the help of (random order):

* Sumit Kumar [https://github.com/sumitkumar0608]
* msjennywu [https://github.com/msjennywu]
* enthusol [https://github.com/enthusol]
* Chris R. [https://github.com/ChrisRo89]
* Aimery Thomas [https://github.com/a1mery]
* Ganesh Sanap [https://github.com/ganesh-sanap]
* Markus Hanisch [https://github.com/m-hanisch]
* Kasper Larsen [https://github.com/kasperbolarsen]
* Arnaud Rompen [https://github.com/rompenar]
* [https://github.com/reusto]
* Ronald Mavarez [https://github.com/ronaldmavarez]
* [https://github.com/lilealdai]
* Martin Lingstuyl [https://github.com/martinlingstuyl]
* Reshmee Auckloo [https://github.com/reshmee011]
* Arleta Wanat [https://github.com/PowershellScripts]
* Leon Armston [https://github.com/LeonArmston]
* Robin Meure [https://github.com/robinmeure]
* Rohit Varghese [https://github.com/rohitvarghese96]
* Erwin van Hunen [https://github.com/erwinvanhunen]
* Marc Studer [https://github.com/studermarc]
* [https://github.com/vin-ol]
* Koen Zomers [https://github.com/koenzomers]

Thank you all for the time you chose to spend on PnP PowerShell and for your help to advance it.

## Try it today

Get the latest major release of the PnP PowerShell from PowerShell gallery by executing:

```bash
Install-Module PnP.PowerShell
```

If you want to get the latest from the dev branch of PnP PowerShell, you can get it by executing:

```bash
Install-Module PnP.PowerShell -AllowPrerelease
```

If you need more help getting started or want more details about the commands, the architecture or the project, go to [aka.ms/pnp/powershell](https://aka.ms/pnp/powershell).

If you see any room for improvement, please, don’t hesitate to reach out to us either on [GitHub](https://github.com/pnp/powershell/issues) or [Twitter](https://twitter.com/pnppowershell).
