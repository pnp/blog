---
title: PnP PowerShell v2.2.0
summary: PnP PowerShell is a cross-platform PowerShell Module providing over 650 cmdlets that work  with Microsoft 365 environments and more specifically SharePoint Online, Microsoft Teams, Microsoft Planner and Power Automate.
date: 2023-07-03T13:22:34.170Z
author: Gautam Sheth
githubname: gautamdsheth
categories:
  - PnP PowerShell
images:
  - images/PnP-PowerShell-2-2-0-release.png

tags:
  - .NET
  - Azure AD
  - PnP PowerShell
  - Microsoft Teams
  - SharePoint
type: popular
---

## PnP PowerShell

PnP PowerShell is a "swiss army knife" type of PowerShell Module providing over 650 cmdlets that work with Microsoft products such as SharePoint Online, Microsoft Teams, Microsoft Project, Security & Compliance, Azure Active Directory, and more. The advantage is that you will have a consistent way to work with a broad range of Microsoft products from a single connection. No need to download different PowerShell Modules, which all work in a slightly different way, requiring different ways of connecting and authenticating.

PnP PowerShell runs on any device on any platform. This means you can run it i.e. from a Windows machine, Mac, Linux based device, Azure Function, Azure Runbook or even a Raspberry Pi. All in the same consistent way.

For more information about installing PnP PowerShell, please refer to [the documentation](https://pnp.github.io/powershell/articles/index.html).

## New version of PnP PowerShell – v2.2.0

We have released a new version, `2.2.0`, of PnP PowerShell with some new capabilities, improvements and lots of bug fixes.

### Major additions and changes

In this release, we added 19 new cmdlets and improved so many more.

Some key new features that we added with 2.2.0 release:

- Added `Get-PnPLargeListOperationStatus` cmdlet to retrieve the status of a large list operation.
- Added `Move-PnPTerm` and `Move-PnPTermSet` cmdlets to allow moving the terms and termsets.
- Added `Get-PnPListItemVersion`, `Restore-PnPListItemVersion` and `Remove-PnPListItemVersion` cmdlet to interact with SharePoint list item versions.
- Added `Get-PnPUnfurlLink` cmdlet to support unfurling a link to get more information about the link. 

We had limited support for file and folder sharing capabilities. To address that, we added quite a few new cmdlets using which you can share files and folders with specific people, within an organization , anonymously or even invite users.

The new cmdlets are:

- `Add-PnPFileOrganizationalSharingLink` and `Add-PnPFolderOrganizationalSharingLink` to allow creating organizational sharing links for files and folders.
- `Add-PnPFileUserSharingLink` and `Add-PnPFolderUserSharingLink` to allow creating sharing links for files and folders to share them with specified list of users.
- `Add-PnPFileAnonymousSharingLink` and `Add-PnPFolderAnonymousSharingLink` to create anonymous sharing links.
- `Add-PnPFileSharingInvite` and `Add-PnPFolderSharingInvite`  to invite users to a file or a folder. 
- `Remove-PnPFileSharingLink` and `Remove-PnPFolderSharingLink`  to delete sharing links associated with files and folders.

Besides adding these new cmdlets, we also improved quite a lot of existing ones.

- `Set-PnPTenant`, `Set-PnPTenantSite` and `Set-PnPSite` cmdlets received quite a few new parameter additions which you can use to manipulate the tenant or the SharePoint sites.
- We also now support adding links in a new tab when using the `Add-PnPNavigationNode` cmdlet. This will only work when the location is `QuickLaunch`. It was a highly requested feature from our community.
- Audience targeting is also now supported for SharePoint lists.
- `Send-PnPMail` cmdlet now also supports attachments when used with Microsoft Graph specific parameters.
- Using `New-PnPSite` cmdlet is now also supported on non-commerical M365 cloud environments.
- `Add-PnPPageSection` cmdlet also supports `VerticalZoneEmphasis` for setting background colour in vertical section layouts.
- `Add-PnPDataRowsToSiteTemplate` cmdlet now also supports large lists. We managed to improve its performance as well as fix a regression. 

You can find the full changelog [here](https://github.com/pnp/powershell/releases/tag/v2.2.0).

## Contributors

This release wouldn't have been possible without the help of (random order):

* Arleta Wanat [https://github.com/PowershellScripts]
* Michał Romiszewski [https://github.com/mromiszewski]
* Kasper Larsen [https://github.com/kasperbolarsen]
* Ganesh Sanap [https://github.com/ganesh-sanap]
* Giacomo Pozzoni [https://github.com/jackpoz]
* James Eccles [https://github.com/jameseccles]
* Kunj Balkrishna Sangani [https://github.com/kunj-sangani]
* Dayana Hristova [https://github.com/makarovv]
* Rodrigo Pinto [https://github.com/ScoutmanPt]
* [https://github.com/reusto]
* Dan Toft [https://github.com/Tanddant]
* [https://github.com/dhiabedoui]
* Reshmee Auckloo [https://github.com/reshmee011]
* Erwin van Hunen [https://github.com/erwinvanhunen]
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
