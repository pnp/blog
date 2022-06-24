---
title: "PnP PowerShell v1.10"
summary: "PnP PowerShell is a cross-platform PowerShell Module providing over 600 cmdlets that work with Microsoft 365 environments and more specifically SharePoint Online, Microsoft Teams, Microsoft Planner and Power Automate."
date: 2022-04-19T12:17:00-05:00
author: "Gautam Sheth"
githubname: "gautamdsheth"
categories: ["PnP PowerShell"]
images:
- images/banner-pnp-powershell.PNG

tags: ["Azure AD","PnP PowerShell","Microsoft Teams", "SharePoint"]
type: "regular"
---

## PnP PowerShell

PnP PowerShell is a "swiss army knife" type of PowerShell Module providing over 600 cmdlets that work with Microsoft products such as SharePoint Online, Microsoft Teams, Microsoft Project, Security & Compliance, Azure Active Directory, and more. The advantage is that you will have a consistent way to work with a broad range of Microsoft products from a single connection. No need to download different PowerShell Modules, which all work in a slightly different way, requiring different ways of connecting and authenticating.

PnP PowerShell runs on any device on any platform. This means you can run it i.e. from a Windows machine, Mac, Linux based device, Azure Function, Azure Runbook or even a Raspberry Pi. All in the same consistent way.

For more information about installing PnP PowerShell, please refer to [the documentation](https://pnp.github.io/powershell/articles/index.html).

## New version of PnP PowerShell – v1.10

We have released a new version, 1.10, of PnP PowerShell with some new capabilities, improvements and bug fixes. Here are some of the most noteworthy changes and additions.

You can find the full changelog [here](https://github.com/pnp/powershell/releases/tag/v1.10.0).

### Microsoft Teams cmdlets additions and improvements

- New-PnPTeamsTeam
- Add-PnPTeamsUser

Both these cmdlets now support adding multiple owners and members. Prior to this, you could only add one user at a time. With this release, you can add multiple users in a Teams team. If, for example, you want to add 1000 users in a team, earlier this would mean 1000 HTTP requests, now it is just 5 requests. This is possible because we are now using a different Microsoft Graph API which allows us to add 200 users in a single HTTP request. This will dramatically improve performance and lower your chances of running into throttling.

These cmdlets now also support addition of guest users.

For more information about these cmdlets, see the documentation [New-PnPTeamsTeam](https://pnp.github.io/powershell/cmdlets/New-PnPTeamsTeam) and [Add-PnPTeamsUser](https://pnp.github.io/powershell/cmdlets/Add-PnPTeamsUser).

- Update-PnPTeamsUser

This cmdlet was added to change role of a user in an existing Teams team. So, you can change an owner to a member role and vice versa.

- Get-PnPTeamsPrimaryChannel 

This cmdlet was added to get the primary Teams channel, General, of a Team.

- Copy-PnPTeamsTeam 

This cmdlet was added which allows an existing Teams team to be copied into a new Team.

### List designs (templates)

- Add-PnPListDesign
- Remove-PnPListDesign
- Invoke-PnPListDesign
- Get-PnPListDesign

Microsoft List designs (aka list templates) enable your users to create custom repeatable list templates (in SharePoint, Teams, and within the Lists app itself) in your organization. They can use `Get-PnPSiteScriptFromList` cmdlet to extract the list template and then use the site script to create a new list template using `Add-PnPListDesign` for the whole organization.

You can find the documentation for that [here](https://pnp.github.io/powershell/cmdlets/Add-PnPListDesign).

### Microsoft 365 Group settings

- Get-PnPMicrosoft365GroupSettings
- New-PnPMicrosoft365GroupSettings
- Remove-PnPMicrosoft365GroupSettings
- Set-PnPMicrosoft365GroupSettings
- Get-PnPMicrosoft365GroupSettingTemplates 

Consider a scenario where you want to block certain words from your group display names or define whether guest users are allowed to be group owners. We added these cmdlets to make it easier to create those configurations for your Microsoft 365 groups.

You can find the documentation here to get started: [New-PnPMicrosoft365GroupSettings](https://pnp.github.io/powershell/cmdlets/New-PnPMicrosoft365GroupSettings)

### SharePoint content types

- Publish-PnPContentType
- Unpublish-PnPContentType
- Get-PnPContentTypePublishingStatus
- Get-PnPCompatibleHubContentTypes

Remember the Content type hub (CTHub)? Based on the newly available CSOM SDK, we added a these cmdlets to interact with Content Types in a content type hub. Usually, whenever a new Tenant is created, there is a default site collection already present under the URL (https://tenant-name.sharepoint.com/sites/contenttypehub). This site collection is the default location for Content types that you want to publish to other site collections in the tenant.

With the addition of these cmdlets, you will be able to Publish or Unpublish a content type from the Hub. We can also retrieve the publishing status of the content types. We can also retrieve the list of content types present in content type hub site that can be added to the root web or a list on a target site.

### Message center announcement for the current user

- Set-PnPMessageCenterAnnouncementAsRead
- Set-PnPMessageCenterAnnouncementAsUnread 
- Set-PnPMessageCenterAnnouncementAsArchived
- Set-PnPMessageCenterAnnouncementAsNotArchived
- Set-PnPMessageCenterAnnouncementAsFavorite
- Set-PnPMessageCenterAnnouncementAsNotFavorite

The Microsoft 365 message center is the place to get notified about planned changes and new upcoming features in your tenant. With the addition of these cmdlets, you will be able to programmatically interact with the message center announcements. These cmdlets replace some of the ones we've had before in PnP PowerShell.

### Other notable stuff

```Connect-PnPOnline``` is used quite heavily since it is the first cmdlet that you use to interact with Microsoft 365 when using PnP PowerShell. It was facing a memory leak issue. Consider a scenario where you want to switch between thousands of site collections in a single script. In this release, we fixed a memory leak issue which occured due to application insights.

```Rename-PnPTenantSite``` is a cmdlet that we added in response to community request. Using this, you now have the ability to change the URL of a site collection. Consider a scenario where you created a site collection and realized that there is a typo, duh, in the URL. You can now just change the site collection URL from `/sites/tst` to `/sites/test`

```Sync-PnPSharePointUserProfilesFromAzureActiveDirectory``` is a cmdlet which you can use to synchronize user profiles from Azure Active Directory into the SharePoint Online User Profiles. This has also been improved to handle special characters and accents and should perform more reliable overall. It has been tested in organizations featuring more than 100,000 users, so should work well at scale as well.

```Add-PnPFile``` has also been improved with the addition of `-Content` parameter. If it is specified, it allows creating a new file on SharePoint Online and directly provide its textual content, i.e. to upload a log file of the execution.

## Contributors

This release wouldn’t be possible without the help of:

*   [Michael Vasiloff](https://github.com/mikevasiloff)
*   [svermaak](https://github.com/svermaak)
*   [Russell Gove](https://github.com/russgove)
*   [Mike Park](https://github.com/mikeparkie)
*   [Jerker Vallbo](https://github.com/jerval53)
*   [Gaurav Mahajan](https://github.com/mahajangaurav)
*   [Dennis](https://github.com/expiscornovus)
*   [Veronique Lengelle](https://github.com/veronicageek)
*   [Jasey Waegebaert](https://github.com/Jwaegebaert)
*   [Swapnil Shrivastava](https://github.com/swapnil1993)
*   [Hugo Bernier](https://github.com/hugoabernier)
*   [Brendon Lee](https://github.com/brenle)
*   [Johan Brännmar](https://github.com/brannmar)
*   [Lschockaert](https://github.com/Lschockaert)
*   [Leon Armston](https://github.com/LeonArmston)
*   [Arleta Wanat](https://github.com/PowershellScripts)
*   [Guillaume Bordier](https://github.com/gbordier)
*   [reusto](https://github.com/reusto)
*   [Reshmee Auckloo](https://github.com/reshmee011)
*   [Gautam Sheth](https://github.com/gautamdsheth)
*   [Koen Zomers](https://github.com/koenzomers)
*   [Erwin van Hunen](https://github.com/erwinvanhunen)

## Work in Progress

Here are some things that we’re currently working on:

### Autocomplete

PowerShell autocomplete !

Based on the fantastic work done by the Azure PowerShell SDK team for the Az.Tools.Predictor, we are looking into adding some predictive intelligence into the PnP PowerShell cmdlets. You will also start seeing the ability to show all available parameters easily. Check out [this PR](https://github.com/pnp/powershell/pull/1763) for more details on this handy feature.

### V2.0

We are in very early stage discussion around 2.0 version. This is one version where we want to focus on and reduce the dependency on CSOM itself for the cmdlets. The replacement for CSOM would be SharePoint REST APIs or Microsoft Graph APIs where possible.

What else could we improve, add and fix? Let us know what you think by helping out with one of our [open issues](https://github.com/pnp/powershell/issues) or chime in on our [open discussion](https://github.com/pnp/powershell/discussions)! If you're having dev skills yourself, we very much welcome your contribution to the source code by submitting PRs, after all PnP PowerShell is a community effort. Sharing is caring!

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
