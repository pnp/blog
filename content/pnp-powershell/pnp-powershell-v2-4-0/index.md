---
title: PnP PowerShell v2.4.0
summary: PnP PowerShell is a cross-platform PowerShell Module providing over 650 cmdlets that work  with Microsoft 365 environments and more specifically SharePoint Online, Microsoft Teams, Microsoft Planner and Power Automate.
date: 2024-03-04T13:22:34.170Z
author: Gautam Sheth
githubname: gautamdsheth
categories:
  - PnP PowerShell
images:
  - images/PnP-PowerShell-2-4-0-release.png

tags:
  - .NET
  - Entra ID
  - PnP PowerShell
  - Microsoft Teams
  - SharePoint
type: popular
---

## PnP PowerShell

PnP PowerShell is a "swiss army knife" type of PowerShell Module providing over 650 cmdlets that work with Microsoft 365 services such as SharePoint Online, Microsoft Teams, Microsoft Project, Security & Compliance, Entra ID, and more. The advantage is that you will have a consistent way to work with a broad range of Microsoft products from a single connection. No need to download different PowerShell Modules, which all work in a slightly different way, requiring different ways of connecting and authenticating.

PnP PowerShell runs on any device on any platform. This means you can run it i.e. from a Windows machine, Mac, Linux based device, Azure Function, Azure Runbook or even a Raspberry Pi. All in the same consistent way.

For more information about installing PnP PowerShell, please refer to [the documentation](https://pnp.github.io/powershell/articles/index.html).

## New version of PnP PowerShell – v2.4.0

We have released a new version, `2.4.0`, of PnP PowerShell with quite a lot new features, improvements and lots of bug fixes.

**This is also an important security update which fixes a moderate level vulnerability related to handling of access tokens. We highly recommend you to update to this latest version.**

### Major additions and changes

In this release, we added 15 new cmdlets and improved so many more.

Some key new features and cmdlets that we added with 2.4.0 release:

- Added `Get-PnPDeletedContainer`, `Restore-PnPDeletedContainer`, `Remove-PnPContainer`, `Get-PnPContainerTypeConfiguration`, `New-PnPContainerType`, `Remove-PnPContainerType` cmdlets to handle operations related to SharePoint Embedded.
- Added `Convert-PnPFile` cmdlets to allow converting a file from one format to another. It is especially useful if you want to convert office files like Word, Excel, PowerPoint to PDF.
- Added `Get-PnPFileAnalyticsData` and  `Get-PnPSiteAnalyticsData` cmdlet to retrieve analytics information about a particular file or a site respectively,
- All cmdlets which work for Power Platform now also support US Gov, US Gov High, US DoD and other cloud environment support. There has also been a change in the HTTP endpoints that we used for these cmdlets to retrieve access token. This was a breaking change we had to do due to changes in backend.
- Added `Set-PnPRetentionLabel` and `Reset-PnPRetentionLabel` cmdlets to support setting a retention label on list item.

Besides adding these new cmdlets, we also improved quite a lot of existing ones.

- `Set-PnPTenant` cmdlet received quite a few new parameter additions which you can use to manipulate the tenant or the SharePoint sites.
- `Add-PnPGroupMember` cmdlet now also supports batch addition of members to a SharePoint group.
- `Grant-PnPAzureADAppSitePermission`, `Add-PnPHubSiteAssociation` and `Register-PnPManagementShellAccess` and `Register-PnPAzureADApp` also now better support other cloud environments.
- `Enable-PnPPageScheduling` and `Disable-PnPPageScheduling` cmdlets now also support Viva connections enabled sites in a tenant.

You can find the full changelog [here](https://github.com/pnp/powershell/releases/tag/v2.4.0).

## Contributors

This release wouldn't have been possible without the help of (random order):

- [Arleta Wanat](https://github.com/PowershellScripts)
- [Jenny Wu](https://github.com/msjennywu)
- [Aimery Thomas](https://github.com/a1mery)
- [Nils Andresen](https://github.com/nils-a)
- [Konrad K.](https://github.com/wilecoyotegenius)
- [Leon Armston](https://github.com/LeonArmston)
- [Daniel Cecil](https://github.com/danielcecil)
- [Rohit Devmore](https://github.com/rohit404404)
- [Kunj Balkrishna Sangani](https://github.com/kunj-sangani)
- [Koen Zomers](https://github.com/koenzomers)
- [Reshmee Auckloo](https://github.com/reshme011)
- [Nishkalank Bezawada](https://github.com/NishkalankBezawada)
- [Jørgen Wiik](https://github.com/joHKwi)
- [Siddharth Vaghasia](https://github.com/siddharth-vaghasia)
- [Jürgen Rosenthal-Buroh](https://github.com/JuergenRB)

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
