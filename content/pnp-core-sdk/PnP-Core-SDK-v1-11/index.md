---
title: PnP Core SDK v1.11
summary: The PnP Core SDK is a modern .NET SDK designed to work for Microsoft 365. It
  provides a unified object model for working with SharePoint Online and Teams
  which is agnostic to the underlying API's being called.
date: 2023-12-12T13:00:00.000Z
author: Bert Jansen
githubname: jansenbe
categories:
  - PnP Core SDK
images:
  - images/PnP-core-sdk-1-11-0-release.png

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

The SDK targets .NET Standard 2.0, [.NET 6.0](https://devblogs.microsoft.com/dotnet/announcing-net-6/), [.NET 7.0](https://devblogs.microsoft.com/dotnet/announcing-dotnet-7/) and [.NET 8.0](https://devblogs.microsoft.com/dotnet/announcing-dotnet-8/). Use the .NET 6.0 (LTS), .NET 7.0 or .NET 8.0 (LTS) builds if you're using a modern .NET version, use .NET Standard 2.0 for backwards compatibility with .NET Framework 4.6.1+.

## New version of PnP Core SDK – v1.11

Key new features/fixes introduced with the 1.11 release are:

- Support for .NET 8.0
- Support for using the ILongRunningOperation interface to track the progress of long running operations
- Calling LoadAsync or EnsurePropertiesAsync on IFolder was broken
- Fixed the encoding of IPropertyValues (property bag) values when any of these chars was used in the property name: -./:<>|[]

- For the auth library:
  - Option to invoke external access provider asynchronously when using the ExternalAuthenticationProvider authentication provider

- For the admin library:
  - Group connecting team sites use the Microsoft Graph api for both application and delegated permissions
  - Fix issue to enumerate private/shared channel sites
  - Switched to the new multi-geo aware site enumeration endpoint
  - Leave 'Teamify' loop when Team already existed
  - Fix setting site collection admins for 'groupified' sites

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Daniel Pastoor](https://github.com/danielpastoor)
- [frfrox92](https://github.com/frfrox92)
- [Jake Stanger](https://github.com/JakeStanger)
- [Koen Zomers](https://github.com/koenzomers)
- [Martin Loitzl](https://github.com/mloitzl)
- [quails4Eva](https://github.com/quails4Eva)
- [valpvt](https://github.com/valpvt)

Thank you all for the time you chose to spend on PnP Core SDK and for your help to advance it!

## Change log

### Added functionality

- Support for using the ILongRunningOperation interface to track the progress of long running operations #1245 [JakeStanger - Jake Stanger]
- Option to invoke external access provider asynchronously when using the ExternalAuthenticationProvider authentication provider #1269 [quails4Eva - David Petchey]
- Support for .NET 8.0 [jansenbe - Bert Jansen]

### Changes and bug fixes

- Fixed Graph paging for US Government, Germany and China clouds + removed some hardcoded references to graph.microsoft.com [jansenbe - Bert Jansen]
- Admin library: Group connected team sites use the Microsoft Graph api for both application and delegated permissions #1220 [danielpastoor - Daniel Pastoor]
- Added Poland to the GeoLocation enum #1232 [jansenbe - Bert Jansen]
- Fix issue to enumerate private/shared channel sites #1238 [valpvt]
- Removed ExcludedBlockDownloadGroupIds properties from ISiteCollectionProperties as that prevented unlocking a site collection via the LockState property #1251 [jansenbe - Bert Jansen]
- Upload of large files (chunked upload) also uses the addusingpath method, just like the regular upload #1256 [jansenbe - Bert Jansen]
- Added IList.DefaultItemOpenInBrowser property #1248 [jansenbe - Bert Jansen]
- Calling LoadAsync or EnsurePropertiesAsync on IFolder was broken #1236 [jansenbe - Bert Jansen]
- Fixed the encoding of IPropertyValues (property bag) values when any of these chars was used in the property name: -./:<>|[] #1263 [jansenbe - Bert Jansen]
- Currently only support getting SensitivityLabelId on ISite [jansenbe - Bert Jansen]
- Admin library: Fixed issues with loading SharePoint Add-Ins [jansenbe - Bert Jansen]
- Admin library: Extra parameters to configure the SharePoint Add-In and Azure ACS principal loading [jansenbe - Bert Jansen]
- Changed IList.DraftVersionVisibility to use enum DraftVisibilityType instead of an int #1286 [jansenbe - Bert Jansen]
- Fixing URL too long issue when downloading files #1290 [koenzomers - Koen Zomers]
- Fixed regression coming from #1290 #1297 [jansenbe - Bert Jansen]
- Admin library: switched to the new multi-geo aware site enumaration endpoint [jansenbe - Bert Jansen]
- Fixed LoadListDataAsStream paging issue when item count was a multiple of the page size #1296 [jansenbe - Bert Jansen]
- Made it easier to set a IField internal name [jansenbe - Bert Jansen]
- Leave 'Teamify' loop when Team already existed #1319 [jansenbe - Bert Jansen]
- Fixed 'hot reload' warning when debugging [jansenbe - Bert Jansen]
- Fix setting site collection admins for groupified sites #1323 [mloitzl - Martin Loitzl]
