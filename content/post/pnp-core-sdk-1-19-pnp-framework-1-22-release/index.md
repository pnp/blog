---
title: "PnP Core SDK v1.19.0 and PnP Framework 1.22.0 release"
date: 2026-11-05T01:00:00.000Z
author: "Adam Wójcik"
githubname: adam-it
categories: ["Community post"]
images:
- images/main.png
tags: [".Net", "SDK", "PnP Core SDK", "PnP Framework", "SharePoint"]
type: "regular"
summary: "PnP Core SDK v1.19.0 and PnP Framework 1.22.0 are out — and with them the first official release of PnP.Core.Provisioning, the PnP provisioning engine built on PnP Core SDK. On top of that: Microsoft 365 Copilot Retrieval API support, transitive group membership, page modernization improvements and a big batch of community fixes."
description: "PnP Core SDK v1.19.0 and PnP Framework 1.22.0 are out — and with them the first official release of PnP.Core.Provisioning, the PnP provisioning engine built on PnP Core SDK. On top of that: Microsoft 365 Copilot Retrieval API support, transitive group membership, page modernization improvements and a big batch of community fixes."
---

## 🗒️ Quick intro

[PnP Core SDK](https://github.com/pnp/pnpcore) is a modern .NET SDK designed to work for Microsoft 365. It provides a unified object model for working with SharePoint Online and Teams which is agnostic to the underlying APIs being called.

[PnP Framework](https://github.com/pnp/pnpframework) is a .NET library targeting Microsoft 365 containing the PnP Provisioning engine and a ton of other useful extensions.

Both libraries received a fresh release, and this time they brought a new friend along 🎉 Let's walk through what's new 👇

## 🚀 PnP.Core.Provisioning 1.19.0: the first official release

The biggest news of this release sits right between the two libraries. **[PnP.Core.Provisioning 1.19.0](https://www.nuget.org/packages/PnP.Core.Provisioning/1.19.0)** is out, and it's the first official (non-nightly) release of the PnP provisioning engine built on top of PnP Core SDK.

If you missed it, we covered the background in detail in [PnP.Core.Provisioning is out!](https://pnp.github.io/blog/post/pnp-framework-roadmap-update-2/). The short version: as part of [phase 1 of the PnP Framework roadmap](https://github.com/pnp/pnpframework/issues/1237), the provisioning engine that powers `Get-PnPSiteTemplate` and `Invoke-PnPSiteTemplate` is moving from PnP Framework to PnP Core SDK. Until now you could only get it from nightly builds (`1.18.x-nightly`). Starting with 1.19.0 it ships as a regular release, side by side with `PnP.Core` and `PnP.Core.Admin`, and it's versioned in lockstep with them.

### The community is already testing it 💪

Nightly builds have been out for a few weeks, and people are already putting the new engine through real-world templates. These fixes made it into 1.19.0:

- **Unpublished news pages keep their news lifecycle**: during extraction, a news page was only recognized as news when it was published (`PromotedState.Promoted`). Unpublished news pages (`PromoteOnPublish`) were extracted as regular pages and lost their news lifecycle on the target site. Both states are now handled.
- **Choose whether extracted pages are published**: extraction used to always mark pages as `Publish = true`, so a draft page on the source site became a published page on the target site. That's not great when you copy a site full of news that still needs editing. A new `ExtractPageAsPublished` option (`extractPageAsPublished` in JSON extract configuration) controls this. It defaults to `true` to keep the existing behavior.
- **`{termsetid:…}` tokens resolve again**: the token parser loaded term groups and term sets in a single nested `QueryProperties` call, which Graph doesn't support. The `{termsetid:<GroupName>:<TermSetName>}` token was never replaced, so taxonomy fields failed validation. The query is now split up, and the related logging gives more detail.
- **Content type bindings on lists**: when a template added a child content type to a list and removed its parent in the same `ListInstance`, the engine removed both. Content types that the template explicitly adds are now excluded from removal.

The first two are ports of fixes that also land in PnP Framework 1.22.0 (more on that below). The last two were found by people who switched their templates from PnP Framework to the new engine. That's exactly the feedback loop we were hoping for 🙏

### Give it a spin

The engine ships as its own NuGet package:

```shell
dotnet add package PnP.Core.Provisioning
```

From there, everything starts from your `PnPContext`:

```csharp
using (var context = await pnpContextFactory.CreateAsync("SiteToWorkWith"))
{
    var manager = context.GetProvisioningManager();

    var template = await manager.GetTemplateAsync(new ExtractConfiguration
    {
        Pages = { IncludeAllClientSidePages = true, ExtractPageAsPublished = false },
        ProgressDelegate = (step, current, total) => Console.WriteLine($"{current}/{total} {step}"),
        MessagesDelegate = (message, type) => Console.WriteLine($"[{type}] {message}")
    });
}
```

Applying a template works the same way through `ApplyTemplateAsync`, and tenant templates use `GetTenantTemplateAsync` and `ApplyTenantTemplateAsync`. If you'd rather stay in PowerShell, add the `-Experimental` switch to the provisioning cmdlets in the PnP PowerShell nightly builds, and they'll run on PnP.Core.Provisioning instead of PnP Framework. Check out [The experimental PnP.Core.Provisioning engine](https://pnp.github.io/powershell/articles/experimental-provisioning.html) for the details, including the extra permissions the new engine needs.

### What it means for PnP Framework provisioning

The provisioning engine in PnP Framework is now deprecated. New features and fixes go to PnP.Core.Provisioning, so please open provisioning issues and ideas in [pnp/pnpcore](https://github.com/pnp/pnpcore/issues). Your existing code keeps working, and the PnP Framework packages stay on NuGet.

Before we made the switch, we went through the open PnP Framework provisioning PRs and merged the important ones, as announced in [pnp/pnpframework#1286](https://github.com/pnp/pnpframework/issues/1286). You'll find all of them in the PnP Framework 1.22.0 section below. If you know of an important fix that's still waiting, let us know in that issue.

## 🔥 What's new in PnP Core SDK v1.19.0

### Added

- **Microsoft 365 Copilot Retrieval API support**: a new `context.Copilot` entry point lets you call the [Microsoft 365 Copilot Retrieval API](https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/api/ai-services/retrieval/overview) straight from the SDK. You send a natural language query and get back the most relevant text extracts from SharePoint, OneDrive or Copilot connectors content, filtered by what the calling user is allowed to see. It's a great building block for grounding your own AI solutions in Microsoft 365 data. This is the first step of the broader [Copilot API support epic](https://github.com/pnp/pnpcore/issues/1741), and PnP PowerShell support is on the wish list too.

- **`ISharePointUser.GetTransitiveGroups`**: a user can belong to a SharePoint group without being listed in it directly, for example through a (nested) Entra ID security group, or as a member or owner of a Microsoft 365 group. The new `GetTransitiveGroups` / `GetTransitiveGroupsAsync` methods resolve those paths using Microsoft Graph `checkMemberGroups` and group owners. Graph is only called when the site actually uses such claims, and those calls need `GroupMember.Read.All`. Note that "Everyone" and "Everyone except external users" aren't Entra ID groups, so they're out of scope.

  ```csharp
  var user = await context.Web.EnsureUserAsync("john@contoso.onmicrosoft.com");

  // Direct SharePoint group membership
  var directGroups = await user.Groups.ToListAsync();

  // Also includes groups reached via Entra ID security groups and Microsoft 365 groups
  var allGroups = await user.GetTransitiveGroupsAsync();
  ```

- **Delete by id on `IWeb.SiteUsers` and `IWeb.SiteGroups`**: when you only have the id, you no longer need to load a user or group before you can remove it. Both collections now expose `DeleteById`, `DeleteByIdAsync` and the batch variants, just like other collections in the SDK:

  ```csharp
  await context.Web.SiteGroups.DeleteByIdAsync(12);
  await context.Web.SiteUsers.DeleteByIdAsync(42);
  ```

- **`ExpirationDateTime` for user sharing links**: `UserLinkOptions` now has an `ExpirationDateTime`, and the expiration is passed through when you create sharing links for files, folders and list items. This was requested for `Add-PnPFolderUserSharingLink` in [pnp/powershell#5484](https://github.com/pnp/powershell/issues/5484), and it brings user links on par with organizational and anonymous links.
- **List item validation error details**: when adding or updating a list item fails SharePoint field validation, the `SharePointRestError` now carries the error code and message that SharePoint returned. That works both when the exception is thrown and for non-throwing batch results, so you finally know *why* the validation failed.

### Changed and fixed

- **`ISharePointUser.Groups` now returns only the groups the user belongs to**: `await user.Groups.ToListAsync()` used to query `_api/Web/SiteGroups` and return **every** group in the site. It now queries the user's own groups (direct membership).
- **Works with Application Insights SDK v3**: apps that referenced `Microsoft.ApplicationInsights` v3 crashed at startup with a `MissingMethodException`, because PnP Core SDK telemetry still used the `InstrumentationKey` setter that v3 removed. Telemetry setup now works with v3.
- **`Web.NewPage()` no longer freezes WPF and WinForms apps**: an async enumeration captured the UI synchronization context and could deadlock desktop apps. A `ConfigureAwait(false)` in the right place fixes it.
- **Site collection details work on new tenants**: on newer tenants, the hidden lists in the SharePoint admin center have longer URLs, so `GetSiteCollectionManager().GetSiteCollectionWithDetailsAsync()` failed with a 404. These lists are now looked up by title, which works on both old and new tenants without extra requests.
- **No more crashes on duplicate GETs in a batch**: loading the same object twice in one batch (for example, two `GetByIdBatchAsync` calls for the same list) made the SDK merge the second model into the first. Paging then tried to read the merged-away model and threw a `TargetInvocationException`. Those models are now skipped, and the surviving model gets the union of both projections.
- **Folders created in lists show up in the UI**: creating a folder in a regular (non-library) list produced a folder with no list item behind it, so it was invisible in SharePoint. For lists, folders are now created with `AddSubFolderUsingPath`. Document libraries keep the existing behavior.
- **Visible no-image page headers survive load and save**: loading a modern page with a visible `NoImage` header and saving it again cleared the header, along with its byline and topic fields. The header is now recognized and preserved, and intentional header removal still works as before.

### ⚠️ Removed

Some features that Microsoft has retired or moved on from are no longer in the SDK. Both changes remove public APIs, so please check your code before you upgrade:

- **Viva Topics support was removed**: Microsoft retired Viva Topics on 22 February 2025, so the related APIs and tests are gone.
- **SharePoint Syntex support was removed**: the Syntex content center and document understanding model APIs (for example `IsSyntexEnabledAsync`, `IsSyntexContentCenterAsync`, `AsSyntexContentCenterAsync`, `GetSyntexModelsAsync` and model publishing) were removed, along with their docs and tests.

### Samples

- **Samples updated to .NET 10**: `Demo.ConsoleApp`, `Demo.Blazor` and `Demo.ASPNetCore` now target .NET 10 and come with a few quality-of-life improvements, including environment-specific `appsettings` support. Together with the WPF sample refresh in the previous release, the samples are a solid starting point again.

For the full list of changes, check the [PnP Core SDK release notes](https://github.com/pnp/pnpcore/releases/tag/1.19.0).

## 🔥 What's new in PnP Framework v1.22.0

PnP Framework is still maintained, and this release shows it. Two themes stand out: a nice set of **page modernization** improvements, and the **final batch of provisioning fixes** we merged before shifting provisioning work to PnP.Core.Provisioning.

### Page modernization

- **In-place publishing page transformation**: you can now transform publishing pages into modern pages within the same web, through the new opt-in `PublishingPageTransformator.CreateInPlace` factory. The source publishing page is kept, the web needs a writable Site Pages library, and existing target pages are never overwritten by accident. The existing constructors still reject a null target, so current callers aren't affected. PnP PowerShell support is being worked on in [pnp/powershell#5490](https://github.com/pnp/powershell/pull/5490).
- **Transformation fixes**: target page names are normalized properly. When image dimensions are missing or the image file can't be found, image mappings now fall back to safe defaults instead of leaving unresolved tokens behind. Root web metadata loading also avoids a service-side failure.
- **Missing embedded documents no longer break transformation**: a single broken embed (a deleted video, for example) used to abort the whole page migration. The original reference is now kept, the metadata comes back empty, and you get a warning that tells you which path to check.
- **Opt-in Enterprise Wiki modernization**: set `EnableEnterpriseWikiCapabilities` (default `false`) to migrate Enterprise Wiki category and rating metadata along with the page. It reuses compatible existing site columns, and rating history is only copied when voters and scores are consistent. You can also insert the Enterprise Wiki sidebar with `IncludeEnterpriseWikiSidebar`, which requires renderer support on the destination.
- **Built-in `WelcomeTOC.aspx` page layout mapping**: pages that use this layout now transform out of the box. The page image and content are stacked in a first section, the top zone gets a full-width section, and the left and right zones become two equal columns. Custom mappings still take precedence.

### Provisioning

- **Shared Teams channels**: channels with membership type `Shared` in a tenant template are now provisioned as shared channels instead of standard ones.
- **Connected web parts stay connected**: exported templates now keep each web part's `instanceId`. Before, web parts linked through Dynamic Data (like PnP Modern Search filters and results) got new instance ids when the template was applied, and the connection between them broke.
- **Choose whether extracted pages are published**: the new `ProvisioningTemplateCreationInformation.ExtractPageAsPublished` option (default `true`) controls whether extracted pages are applied as published or as drafts.
- **Unpublished news pages are detected during extraction**: news pages are now recognized as news whether they're published or not.
- **Missing `ContentTypeId` when extracting data from a sub site**: content types inherited from the root web are now resolved, so list items, folders and files extracted from a sub site get the right `ContentTypeId`.
- **Hidden `FieldRef`s in content type enabled lists are exported**: hidden fields that only exist on a list-level content type were left out of the exported template, so they never got provisioned. They're now included.

For the full list of changes, check the [PnP Framework release notes](https://github.com/pnp/pnpframework/releases/tag/1.22.0).

## 🙌 Community and contributors

These releases would not have been possible without the help of some really awesome folks who stepped in and kept things moving. We would like to express our huge gratitude and shout out to (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Christian Zuellig](https://github.com/czullu)
- [Gautam Sheth](https://github.com/gautamdsheth)
- [gszdev](https://github.com/gszdev)
- [Guflly](https://github.com/Guflly)
- [lockerbill](https://github.com/lockerbill)
- [Magnus-K-work](https://github.com/Magnus-K-work)
- [Marcin Wojciechowski](https://github.com/mgwojciech)
- [Miguel Angel García Martínez](https://github.com/magarma)
- [Per Jakobsen](https://github.com/singingknight)
- [Rene Nicolao](https://github.com/nicolaor)
- [svermaak](https://github.com/svermaak)
- [Tianyi Tao](https://github.com/TaoziZ03)
- [wuxiaojun514](https://github.com/wuxiaojun514)
- [Yifeng](https://github.com/YifengMao)

And to everyone in the wider **PnP community** who raised issues, shared feedback, contributed code, and kept the momentum going — that feedback mattered. A lot.

## 🐞 Found something?

If you run into issues or have suggestions, please open an issue on the repos (provisioning issues, whether you use PnP Framework or PnP.Core.Provisioning, now belong in PnP Core SDK):

👉 [PnP Core SDK issues](https://github.com/pnp/pnpcore/issues)

👉 [PnP Framework issues](https://github.com/pnp/pnpframework/issues)

You can also contribute with a PR — we'd love to see it!

## 📥 Get the package

👉 [PnP.Core 1.19.0 on NuGet](https://www.nuget.org/packages/PnP.Core/1.19.0)

👉 [PnP.Core.Provisioning 1.19.0 on NuGet](https://www.nuget.org/packages/PnP.Core.Provisioning/1.19.0)

👉 [PnP.Framework 1.22.0 on NuGet](https://www.nuget.org/packages/PnP.Framework/1.22.0)
