---
title: Upcoming changes to PnP PowerShell for v3
summary: PnP PowerShell is a cross-platform PowerShell Module providing 739 (and increasing) cmdlets that work with Microsoft 365 environments and more specifically SharePoint Online, Microsoft Teams, Microsoft Planner and Power Automate.
date: 2024-11-28T13:22:34.170Z
author: Gautam Sheth
githubname: gautamdsheth
categories:
  - PnP PowerShell
images:
  - images/PnP-PS-30.png

tags:
  - .NET
  - Microsoft Entra ID
  - PnP PowerShell
  - Microsoft Teams
  - SharePoint
  - Microsoft Graph
type: trending
---

## PnP PowerShell

PnP PowerShell is a "swiss army knife" type of PowerShell Module providing 785 cmdlets (and increasing) that work with Microsoft 365 services such as SharePoint Online, Microsoft Teams, Microsoft Project, Security & Compliance, Entra ID, and more. The advantage is that you will have a consistent way to work with a broad range of Microsoft products from a single connection. No need to download different PowerShell Modules, which all work in a slightly different way, requiring different ways of connecting and authenticating.

PnP PowerShell runs on any device on any platform. This means you can run it i.e. from a Windows machine, Mac, Linux based device, Azure Function, Azure Runbook or even a Raspberry Pi. All in the same consistent way.

For more information about installing PnP PowerShell, please refer to [the documentation](https://pnp.github.io/powershell/articles/index.html).

## Why version 3 ? 

On November 12, 2024, support ended for .NET 6 and PowerShell 7.2. Now that it is no longer supported, we decided to update PnP PowerShell to v3 , which will be based on .NET 8 and PowerShell 7.4 which is now the major LTS version.

Since we are going for a major version bump, we decided to take that as on opportunity to introduce some breaking changes and improvments to the cmdlets.

## Major upcoming changes

### Requirements

- It requires `PowerShell 7.4.4` or later versions of it. You can get it from [here](https://github.com/PowerShell/PowerShell/releases/tag/v7.4.6).
- Any version of PowerShell prior to that will not be supported.
- It will work on all major OS like Windows, Linux and Mac, i.e wherever PowerShell 7.4 is supported.
- Azure functions will need to be upgraded to 7.4
- Azure automation doesn't support PowerShell 7.4 at the moment. Only PowerShell 7.2 is supported in there. You should keep using v2.12.0 in this scenario. Once support of 7.4 is added there, you can update to v3.

### Connect-PnPOnline breaking changes

- There's some behavioral changes that we have introduced in `Connect-PnPOnline` cmdlet.
- **`-Interactive` is now the default behavior of `Connect-PnPOnline`**. 
    - What this means is that when you execute this code, it will now open the default browser for authentication
    ```powershell
    Connect-PnPOnline "<site-url>" -ClientId <Entra ID client ID>
    ```
    - There's no need to explicitly specify `-Interactive` parameter.
    - It replaces `-Credentials` which was the default.
    - We decided to do it based on user feedback as well as keeping security, compliance, MFA etc policies in mind. 
    - `-Credentials` parameter will need to be explicitly specified if you want to use this mode of authentication.
- If `-DeviceLogin` parameter is specified, it will now open the default browser for authentication.
- We decided to get rid of the popup implementation because it was built on legacy dependencies such as IE engine. It didn't support modern Entra ID policies such as phishing proof browser, authentication strength etc. We also received feedback that it would sometimes freeze or would be hidden behind the console.
- The `-LaunchBrowser` parameter has also been removed because it will now always default to opening browsers, so it is not needed anymore.
- The `-SPOManagementShell` parameter has been removed. It reduces the risk of your scripts breaking in case Microsoft changes the underlying Entra ID app used. You should use your own Entra ID app instead.
- **The `-WebLogin` authentication mode has been removed**. It was insecure and used cookies for authentication. It only worked for SharePoint. Other M365 services like Microsoft Graph, Teams etc. wouldn't even work with cookie based auth. We recommend using `-Interactive` or `-DeviceLogin` as a replacement for this. 
- We have also enabled rate limiting for all cmdlets which are being executed under application permissions.
- For more information on how rate limiting works, you can read the blog [here](https://devblogs.microsoft.com/microsoft365dev/prevent-throttling-in-your-application-by-using-ratelimit-headers-in-sharepoint-online/)
- If you are using `ClientId + Client Secret` parameters to authenticate, we highly encourage you migrate away from this.    
    - `ClientId + Secret` is based on Azure ACS has now been [marked for retirement.](https://learn.microsoft.com/en-us/sharepoint/dev/sp-add-ins/retirement-announcement-for-azure-acs)
    - We recommend usage of Entra Id app with `ClientId + Certificate` or `Managed Identity` or any other Entra Id based modes for authentication.
    - There are no changes related to this in v3.
- We have also introduced **-PersistLogin** parameter for `-Interactive`, `-DeviceLogin`, `-OSLogin` and `-Credentials` parameter sets. It will utilize a persist cache containing your access token. The cache is encrypted and stored in a subfolder in your `$HOME` folder on Windows. On MacOS the cache is stored in the encrypted KeyChain.  In Linux, it is stored in the wallet such as `Gnome Keyring` or `KWallet` using LibSecret. Its contents can be visualised using tools such as `Gnome Seahorse`. You only have to specify `-PersistLogin` once when doing a Connect-PnPOnline, after that the cache entry will be used. The cache is persisted between PowerShell sesions and system reboots. To clear an entry from the cache use `Disconnect-PnPOnline -ClearPersistedLogin`.  It is insanely fast, secure and crazy good and we would totally love to hear more from you about its usage.

### Entra ID changes

- `Register-PnPEntraIDApp` and `Register-PnPEntraIDAppForInteractiveLogin` now open the default browser instead of a popup when creating/updating Entra ID apps.

### Other things to note

- **This also contains major security updates to MSAL, System.Text.Json, System.Text.Encodings.Web and other vulnerable nuget packages.**
- We are seeing quite a few speed upticks, lower memory consumption and performance improvements as result of the baseline changes underlying framework.
- Besides these changes, there are quite a few other changes as well. 
- You can find the in-progress migration document [here](https://github.com/pnp/powershell/blob/dev/MIGRATE-2.0-to-3.0.md)

We highly encourage you to try the latest nightly builds and provide us feedback.

The latest nightly builds of PnP PowerShell are available by executing this command.

```powershell
Install-Module PnP.PowerShell -AllowPrerelease
```

If you need more help getting started or want more details about the commands, the architecture or the project, go to [aka.ms/pnp/powershell](https://aka.ms/pnp/powershell).

If you see any room for improvement, please, don't hesitate to reach out to us either on [GitHub](https://github.com/pnp/powershell/discussions) or [Twitter/X](https://twitter.com/pnppowershell).
