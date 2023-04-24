---
title: PnP Core SDK v1.9
summary: The PnP Core SDK is a modern .NET SDK designed to work for Microsoft 365. It
  provides a unified object model for working with SharePoint Online and Teams
  which is agnostic to the underlying API's being called.
date: 2023-03-30T13:32:34.170Z
author: Bert Jansen
githubname: jansenbe
categories:
  - PnP Core SDK
images:
  - images/PnP-core-sdk-1-9-0-release.png

tags:
  - .Net
  - PnP Core SDK
  - Microsoft Teams
  - SharePoint
type: regular
---

We've just published a new minor version of the [.NET PnP Core SDK](https://aka.ms/pnp/coresdk/docs) ([GitHub repo](https://aka.ms/pnp/coresdk)) with new features to use in your cross-platform SharePoint Online and Microsoft Teams projects.

## Build SharePoint Online and Teams solutions in .NET on any platform using PnP Core SDK

The [PnP Core SDK](https://aka.ms/pnp/coresdk/docs) is an SDK designed to work for Microsoft 365. It provides a unified object model for working with SharePoint Online and Microsoft Teams which is agnostic to the underlying APIs being called. The SDK provides an object model that's API agnostic, when you as a developer for example load a model (List, Team, Web,...) the SDK will use the best possible API for loading that model being for the most part Microsoft Graph v1.0 and SharePoint REST. Depending on the needs the SDK will use Microsoft Graph Beta calls and in some cases the CSOM endpoint (client.svc) is called. But the good thing is that all of this is transparent for you as developer! You'll have a consistent development experience regardless of the underlying APIs being called.

The SDK targets .NET Standard 2.0, [.NET 6.0](https://devblogs.microsoft.com/dotnet/announcing-net-6/) and [.NET 7.0](https://devblogs.microsoft.com/dotnet/announcing-dotnet-7/). Use the .NET 6.0 (LTS) or .NET 7.0 builds if you're using a modern .NET version, use .NET Standard 2.0 for backwards compatibility with .NET Framework 4.6.1+.

## New version of PnP Core SDK – v1.9

Key new features introduced with the 1.9 release are:

- Support for custom cloud environments by allowing to specify custom Azure AD and Microsoft Graph endpoints
- New methods to get an `IFile` by a link (e.g. sharing link) or by id
- Audience targeting support for navigation entries and lists
- Bulk user validation (e.g. for when configuring a user field) via `ValidateUsersAsync` and `ValidateAndEnsureUsersAsync` methods on `IWeb`
- Added `RenameAsync` methods for `IFile` and `IFolder`
- Sharing links can now be updated
- Option to move list items to another path in the same list
- Dropped support for .NET 5
- Improved support for using Moq as test framework
- For the admin library:
  - Additional properties for `ITenantProperties` and `ISiteCollectionProperties`
  - Option to enumerate the site collections behind shared and private Teams channels
  - Support for listing, approving, adding and revoking permission grants for installed applications
  - Support for disabling/enabling the SharePoint principal of the tenant
  - Enumerate Azure ACS principals and SharePoint AddIns

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Amartya Yadav](https://github.com/amartyadav)
- [Bert Jansen](https://github.com/jansenbe)
- [Jake Stanger](https://github.com/JakeStanger)
- [Jens Haile](https://github.com/LeHailender)
- [Kinga](https://github.com/kkazala)
- [Martin Loitzl](https://github.com/mloitzl)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Patrick Lamber](https://github.com/plamber)
- [Suman Tokori](https://github.com/stokuri)

Thank you all for the time you chose to spend on PnP Core SDK and for your help to advance it!

## Change log

### Added functionality

- Support for custom cloud environments by setting Environment to `Custom` followed by specifying the needed Graph and Azure AD endpoints #1014 [jansenbe - Bert Jansen]
- Implements support for the access request configuration #1040 [plamber - Patrick Lamber]
- Option to specify the `X509Certificate2` when using the `OnBehalfOfAuthenticationProvider`, similar to the support there is for this in the `X509CertificateAuthenticationProvider` #1047 [mloitzl - Martin Loitzl]
- Option to get a file by unique id using the `GetFileById` methods on `IWeb` [jansenbe - Bert Jansen]
- Option to get a file by link (any fully qualified link to a file, including sharing links) using the `GetFileByLink` methods on `IWeb` #1054 [jansenbe - Bert Jansen]
- Configure whether the web templates dialog shows up or not via the `WebTemplatesGalleryFirstRunEnabled` property on `IWeb` #1057 [jansenbe - Bert Jansen]
- Added `EnableAudienceTargeting` methods on `IList` [jansenbe - Bert Jansen]
- Added support for adding, updating and removing audiences on navigation nodes #1065 [jansenbe - Bert Jansen]
- Admin library: added 43 new properties to `ITenantProperties` [jansenbe - Bert Jansen]
- Admin library: added 15 new properties to `ISiteCollectionProperties` [jansenbe - Bert Jansen]
- Bulk user validation method `ValidateUsersAsync` and `ValidateAndEnsureUsersAsync` on `IWeb` [jansenbe - Bert Jansen]
- When using the `GetSiteCollectionsWithDetailsAsync` method you now can choose to also return the site collections linked to private and shared Teams channels #1076 [jansenbe - Bert Jansen]
- Fix URL encoding for use in SPO REST ...Path methods (e.g. `getFolderByServerRelativePath`) #1077 [jansenbe - Bert Jansen]
- Added `Rename` methods on `IFolder` to make it easier to rename a folder #1080 [jansenbe - Bert Jansen]
- Support for reading and cloning News Digest pages #1086 [jansenbe - Bert Jansen]
- Add capabilities to grant or revoke permissions to existing sharing link #1094 [MathijsVerbeeck - Mathijs Verbeeck]
- Support for listing, approving and denying api access requests after installing an app #1100 [mloitzl - Martin Loitzl]
- Added `Rename` methods on `IFile` to make it easier to rename a file #1109 [jansenbe - Bert Jansen]
- Added feature to enable or disable the SharePoint service principal #1117 [mloitzl - Martin Loitzl]
- Method to ensure the 'Everyone except external users' user for any site language #1127 [plamber - Patrick Lamber] 
- Added support for listing, adding and revoking permission grants for a SharePoint service principal #1132 [mloitzl - Martin Loitzl]
- Admin library: added support for listing Azure ACS principals and SharePoint AddIns [jansenbe - Bert Jansen]
- Support for moving a ListItem to a sub folder #1146 [mloitzl - Martin Loitzl]

### Changes and bug fixes

- Lookup, Url and User fields were not loaded for list item versions #1031 [jansenbe - Bert Jansen]
- Fix issue when loading freshly added page comments without reloading the actual page [jansenbe - Bert Jansen]
- Fix modern team site creation when no valid description was passed in #1037 [LeHailender - Jens Haile]
- Fix for adding site collection term group #1041 [jansenbe - Bert Jansen]
- The JSON controldata sectionindex value of page could not be converted to System.Int32 : Handle Pnp Provisioning template extraction failure from Project Management site template #1058 [stokuri - Suman Tokori]
- Improve code consistency for the eventhub model [jansenbe - Bert Jansen]
- Added `DefaultViewUrl` property for `IList` [jansenbe - Bert Jansen]
- Added more values for `ListTemplateType` [jansenbe - Bert Jansen]
- Added `UserCustomActions` to `IList` [jansenbe - Bert Jansen]
- Fixed enum order for `ListExperience` [jansenbe - Bert Jansen]
- Extended the `IPnPContext` interface to contain all the public method and properties to better support mocking in unit tests #1083 [jansenbe - Bert Jansen]
- Fix SiteCollectionManager.GetSiteCollectionWithDetailsAsync returning null when getting root site collection #1089 [jansenbe - Bert Jansen]
- Removed `BlockDownloadFileTypeIds` and `ExcludedBlockDownloadGroupIds` properties from Tenant properties as they could not be saved preventing other property updates #1087 [jansenbe - Bert Jansen]
- Added the `RetainEditorAndModifiedOnMove` property to the `MoveCopyOptions` and optimized file copy/move operations to use the cross site API as much as possible #989 #1091 [jansenbe - Bert Jansen]
- Dropped .NET 5 support as it's not supported anymore [jansenbe - Bert Jansen]
- Fix for IFile/IListItem - CheckIfUserHasPermissionsAsync Throws ->System.NullReferenceException: #1097 [jansenbe - Bert Jansen]
- Improved model for `PnPContext` extensions allowing them to be used by mocking frameworks in unit tests #1083 [plamber - Patrick Lamber]
- Chars ' and . are allowed in alias and urls [jansenbe - Bert Jansen]
- Add possibility to get the `IServicePrincipal` via `IAppManager` #1116 [mloitzl - Martin Loitzl]
- Don't set `BaseAddress` of `MicrosoftGraphClient` when there's no change #1114 [jansenbe - Bert Jansen]
- Option to create private/shared Teams channels #1126 [JakeStanger - Jake Stanger]
- Bump Nuget package version dependencies to align with PnP PS needs [jansenbe - Bert Jansen]
