---
title: PnP PowerShell v3 released!
summary: PnP PowerShell is a cross-platform PowerShell Module providing 815 (and counting) cmdlets that work with Microsoft 365 environments and more specifically SharePoint Online, Microsoft Teams, Microsoft Planner and Power Automate.
date: 2025-03-27T09:53:00.000Z
author: Erwin van Hunen
githubname: erwinvanhunen
categories:
  - PnP PowerShell
images:
  - images/PnP-PS-RELEASE-30.png

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

It has been in the works for a long time, but finally we're excited to announce that PnP PowerShell 3.0 has been released.

We released version 3 for various reasons:

On November 12, 2024, support ended for .NET 6 and PowerShell 7.2. Now that it is no longer supported, we decided to update PnP PowerShell to v3, which will be based on .NET 8 and PowerShell 7.4 which is now the major LTS (Long-Term Support) version.

It is important to realize that this is at some levels a _breaking_ release. We did a lot of cleaning up and removed outdated switches and cmdlets, and some other functionality is now gone because it was not supported anymore on M365.

All in all this is our biggest major release ever. We optimized memory usage and we increased the performance for many cmdlets. We urge you to check out the differences first between version 2.x and 3.0. Also see the paragraph below how to run version 3.0 side by side with version 2.0 and check it's functionality.

To see what has changed we made two comprehensive lists:

The changelog in general can be found here: https://github.com/pnp/powershell/blob/master/CHANGELOG.md

We also created a migration document which explains what has changed or removed and what is being replaced with it: https://github.com/pnp/powershell/blob/dev/MIGRATE-2.0-to-3.0.md

## What will you notice

Some highlights of things that might affect you immediately:

### Changes to to Connect-PnPOnline

#### Defaults to Interactive login
In previous versions you where required to specify `-Interactive` in order to use the Interactive Entra ID authentication. This is now the default. E.g. after registering your EntraID application you only need to specify the `-ClientId` parameter with the appropriate Application Client Id to launch the interactive authentication.

#### UseWebLogin has been removed
We removed `UseWeblogin` from `Connect-PnPOnline`. We realize that many of you where still using that, but the technology used for that was severaly outdated, not secure anymore and limited. For instance when you used `UseWebLogin` authentication we couldn't make Graph calls behind the scenes. The implementation of UseWebLogin in PnP PowerShell was several years old, and involved us hijacking a cookie. This is not the way we should do things so it was time to deprecate and remove this method. If your workflow depends on `UseWebLogin` you can always consider to not upgrade, but we strongly advice you to revisit your approach and move to more modern ways of authenticating.

#### We introduced token caching
It is now possible to cache your authentication tokens in a safe and secure manner. To use this you will have to specify the `-PersistLogin` switch when using `Connect-PnPOnline`. The cache will automatically store the entry associated with the tenant url you specified and the client id you entered. 

Notice that you only have to use this once. Once you're authenticated we will store the token in a secure cache, which is located when you use Windows in an encrypted format located in your $HOME/.m365pnppowershell folder. In the case of MacOS we store the token cache in your keychain. We also create a settings.json file located in the same folder (for both Windows and MacOS) which allows you to tweak certain settings. I recommend you to check out the file.

The next time you use Connect-PnPOnline you will not have to go through the authentication workflow, as we will retrieve the token from the secure cache. The only thing you need to specify is the URL of the site collection you want to connect to.

If the token expires, we will automatically refresh the token for you. So all in all this is an extremely convenient way to authentication. Keep in mind that the cache is limited to use on the computer were it was created. So you cannot move the cache over to another system and use it from there.

If for whatever reason (for instance, if you change the permissions on the App Registration you used for authentication) you want to remove the token from the cache, use `Disconnect-PnPOnline -ClearPersistedLogin`

#### Changes to authentication UI behavior

We do not show a popup anymore for you to enter your username and password, instead we follow a pattern which is common in various other products (like VSCode) which is that we open a tab in the default browser. This has the benefit for you for instance that after opening you can use all the functionality of the browser (like username/password fill-in, or send the tab to another profile).

#### Use in Azure Automation and Azure Functions

PowerShell support in Azure Automation is lagging behind the current state of PowerShell in general. Right now we do not support PnP PowerShell 3.0 on Azure Automation as it's running PowerShell 7.4.0. Azure Functions run PowerShell 7.4.6, and PnP PowerShell 3.0 is supported on that.

## Requirements

- PnP PowerShell 3.0 requires `PowerShell 7.4.6` or later versions of it. You can get it from [here](https://github.com/PowerShell/PowerShell/releases/tag/v7.4.6).
- Any version of PowerShell prior to that will not be supported.
- It will work on all major OS like Windows, Linux and Mac, i.e wherever PowerShell 7.4.6 or newer is supported.
- Azure functions will need to be upgraded to 7.4
- Azure automation supports an earlier version of PowerShell 7.4 at the moment. You should keep using v2.12.0 in this scenario. Once support of 7.4.6 (notice the version) is added there, you can update to v3.

## Running version 3.0 on the side of version 2.0

Instead of installing PnP PowerShell 3.0 from the gallery and overwriting your v2 installation, you can run the new and old version side by side.

Create a folder somewhere where you want to store the module. It does not matter where that folder is located, as long as you remember where it is. In the example below we created a folder called `PS` in `C:\TEMP`. We then save the module to that folder. Notice that it will create a subfolder with the name of the module and the version number of the module. 

After downloaded we import the downloaded module into the current PowerShell session. Notice that if you have used PnP PowerShell v2 in the current session you will first have to close PowerShell and reopen it before you execute the code below to import the module (you can however download/save the module without any problem).

```powershell
cd C:\TEMP\PS
Save-Module -Name PnP.PowerShell -Path .
Import-Module C:\TEMP\PS\PnP.PowerShell\3.0.0\PnP.PowerShell.psd1
```

For subsequent runs on the side loaded PnP PowerShell you obviously do not need to save the module first; you can directly import it as stated in the example above.


