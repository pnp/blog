---
title: PnP Core SDK v1.8
summary: The PnP Core SDK is a modern .NET SDK designed to work for Microsoft 365. It
  provides a unified object model for working with SharePoint Online and Teams
  which is agnostic to the underlying API's being called.
date: 2022-11-09T13:32:34.170Z
author: Bert Jansen
githubname: jansenbe
categories:
  - PnP Core SDK
images:
  - images/PnP-core-sdk-1-8-0-release.png

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

The SDK targets .NET Standard 2.0, .NET 5.0, [.NET 6.0](https://devblogs.microsoft.com/dotnet/announcing-net-6/) and [.NET 7.0](https://devblogs.microsoft.com/dotnet/announcing-dotnet-7/). Use the .NET 6.0 (LTS) or .NET 7.0 builds if you're using a modern .NET version, use .NET Standard 2.0 for backwards compatibility with .NET Framework 4.6.1+.

## New version of PnP Core SDK – v1.8

Key new features introduced with the 1.8 release are:

- Support for [.NET 7](https://devblogs.microsoft.com/dotnet/announcing-dotnet-7/). Note: this is the last release that will ship with .NET 5 binaries, .NET 5 is not supported anymore and it's highly recommended to upgrade your projects to .NET 6 (LTS version) or .NET 7.
- Support for getting and setting column defaults
- A new `IPnPContext` interface on `PnPContext` which supports mocking for use in testing
- Working with indexed properties and requesting re-indexing of a list or web
- RateLimit header support to prevent getting throttled
- For the admin library:
  - Removing site collections from the site collection recycle bin
  - Passing along group members when creating group connected sites

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Bert Jansen](https://github.com/jansenbe)
- [Heinrich Ulbricht](https://github.com/heinrich-ulbricht)
- [Hilton Giesenow](https://github.com/HiltonGiesenow)
- [Ivan Wilson](https://github.com/spg-iwilson)
- [Jens Haile](https://github.com/LeHailender)
- [Koen Zomers](https://github.com/koenzomers)
- [Landon Petzoldt](https://github.com/clurdish)
- [Llewellyn Roos](https://github.com/lroos)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Loitzl](https://github.com/mloitzl)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [soebje](https://github.com/soebje)
- [Stefan Schoof](https://github.com/StefanSchoof)

Thank you all for the time you chose to spend on PnP Core SDK and for your help to advance it!

## Change log

### Added functionality

- Added support for using RefinementFilters via the `IWeb.Search` methods #924 [lroos - Llewellyn Roos]
- Adds Getusereffectivepermissions for IWeb, IList and IListItem #926 [MathijsVerbeeck - Mathijs Verbeeck]
- Added license information in the generated Nuget packages #945 [clurdish - Landon Petzoldt]
- `Author` property for `IWeb` #947 [jansenbe - Bert Jansen]
- `IPnPContext` interface on `PnPContext` to support mocking for use in testing #948 [jansenbe - Bert Jansen]
- Support for getting, setting and clearing of (folder based) column defaults #949 [jansenbe - Bert Jansen]
- Requesting re-indexing of a web or list #950 [jansenbe - Bert Jansen]
- RateLimit header processing capability, turned off by default [jansenbe - Bert Jansen]
- Added `DeleteRecycledSiteCollection` methods to delete site collections from the recycle bin [jansenbe - Bert Jansen]
- Admin library: ability to specify ResourceBehaviorOptions when creating a Group using application permissions #978 [koenzomers - Koen Zomers]
- Admin library: Ability to specify members on team site creation time #981 [LeHailender - Jens Haile]
- Added add and remove functionality for indexed web properties #1006 [LeHailender - Jens Haile]
- Added .NET 7 binaries [jansenbe - Bert Jansen]
- Moved to C# 10 [jansenbe - Bert Jansen]
- Support for configuring field visibility in display, edit and new forms #999 [jansenbe - Bert Jansen]
- Add ITermSet.GetTermsByCustomProperty method to retrieve a list of terms with a certain custom property key and value #1021 [mloitzl - Martin Loitzl]

### Changes and bug fixes

- Fix: Wrong if condition combination & instead of && in `BaseQueryableDataModelCollection` method `GetAsyncEnumerator` #911 [jansenbe - Bert Jansen]
- Fix: Using multiple owners when creating modern team site using delegated permissions failed [jansenbe - Bert Jansen]
- Simplified model for working url, user, lookup, and taxonomy fields #915 [jansenbe - Bert Jansen]
- Add KANBAN to the ViewType2 enum #930 [martinlingstuyl - Martin Lingstuyl]
- Add MODERNCALENDAR  to the ViewType2 enum #939 [martinlingstuyl - Martin Lingstuyl]
- Fix search sort direction with new POST approach #937 [lroos - Llewellyn Roos]
- Ensure the Name property is loaded #955 [jansenbe - Bert Jansen]
- VerifyProperties fails to detect other model types loaded via `QueryProperties` as dirty #961 [jansenbe - Bert Jansen]
- Getting pages with ".aspx" in file name fails #974 [jansenbe - Bert Jansen]
- Fix for failure at getting list items with a column entitled "Comments" #979 [jansenbe - Bert Jansen]
- Adding missing property IsVisible property to AdaptiveCardAction #986 [koenzomers - Koen Zomers]
- GetAvailableThemesAsync throws exception when 'isInverted' or 'name' values missing from JSON response #990 [jansenbe - Bert Jansen]
- Lists.GetByTitle should be case insensitive #991 [jansenbe - Bert Jansen]
- Making RichTextEditorInstanceId setable to enable consuming libraries to set inline images #997 [heinrich-ulbricht - Heinrich Ulbricht]
- Escape characters in inline image `Caption`, `AltText` and `Link` properties to prevent malformed JSON #995 [jansenbe - Bert Jansen]
- Added support for also loading the additional fields returned by a lookup field when using `LoadListDataAsStreamAsync` [jansenbe - Bert Jansen]
- Drop redundant Microsoft.Extensions.Logging.Abstractions reference [jansenbe - Bert Jansen]
- Moved to a language neutral approach for translating SharePoint timezones to .NET `TimeZoneInfo` instances and provided a new public `GetTimeZoneInfo` method on `ITimeZone` [jansenbe - Bert Jansen]
