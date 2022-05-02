---
title: "Modernization lives on in PnP Framework"
date: 2021-03-02T11:40:00-05:00
author: "Paul Bullock"
githubname: pkbullock
categories: ["Community post"]
images: []
tags: ["SharePoint"]
type: "regular"
---
Using the Modernization tooling, classic SharePoint pages can be
converted to Modern pages residing in Microsoft 365 Team or
Communication sites.

The overall benefit of using this tooling, is that you can scan the
environment to get an inventory by using the Modernization scanner
(SharePoint Online only); and then with the Page Transformation tools,
you then have the option to move your classic content to the modern
experience - this supports either an on-premises SharePoint system or
sites in SharePoint Online. The tooling is focused on the pages in
classic sites and will allow you to keep and convert that content in
which you have invested in resources to produce.

 

There is currently a major multi-step project to move away from older
versions of PnP Sites Core and PnP PowerShell to taking advantage of
modern .NET 5 and refocus the SDK to Graph first. For details of this
project check out this blog for more details about the long term plans
for the project for [General Availability of the new PnP Framework
library for automating SharePoint Online
operations](https://developer.microsoft.com/sharepoint/blogs/general-availability-of-the-new-pnp-framework-library-for-automating-sharepoint-online-operations/)

 

![Diagram to show the transition of PnP Modernisation tooling in the underlying framework](images/Modernisation-Transition.png)
 

The modernization tooling is dependent on the PnP Sites Core, we are
pleased to announce this now has been ported and integrated into PnP
Framework as part of the steppingstone of improvements -- meaning you
can continue to take advantage of this tooling, if you wish, via either
new [PnP.PowerShell
library](https://www.powershellgallery.com/packages/PnP.PowerShell) that
contains the cmdlets required to perform page transformation or the
[PnP.Framework NuGet
package ](https://www.nuget.org/packages/PnP.Framework)to use in your
.NET applications.

 

There is one caveat with the move to PnP Framework, that we have no
longer support for SharePoint 2010, due to the widening gaps between
Office 365 APIs and the older SharePoint 2010 APIs (which is also coming
up for [retirement in April
2021](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/revised-end-of-support-date-for-sharepoint-server-2010-april-13/ba-p/1285559)).

 

To resolve the issues, we would have to spend significant time
engineering a fix and we feel that better value of time can be used to
continue integrating into the newest frameworks. If you wish to use the
tooling with SharePoint 2010 support then [please download the older
versions](https://github.com/pnp/PnP-PowerShell/releases/tag/3.28.2012.0)
Alternatively, you can use a migration tool to copy the classic sites to
SharePoint Online and then convert to modern.

 

  ------------------------------------------------------------------------------------------------------------------------ -----------------------------------------------------------------
  **Old GitHub Repository Location**                                                                                       **New GitHub Repository Location**
  [PnP-Sites-Core repository (archived)](HTTPS://GitHub.com/PnP/PnP-Sites-Core)                                            [PnP Framework repository](Https://GitHub.com/PnP/pnpframework)
  [PnP-PowerShell repository (archive](HTTPS://GitHub.com/PnP/pnp-powershell)[d)](HTTPS://GitHub.com/PnP/pnp-powershell)   [PnP.PowerShell repository](https://github.com/PnP/powershell)
  [SP-Dev-Modernization repository](https://github.com/PnP/sp-dev-modernization)                                           [PnP Framework repository](Https://github.com/PnP/pnpframework)
  ------------------------------------------------------------------------------------------------------------------------ -----------------------------------------------------------------

 

As PnP Sites Core and older PnP PowerShell GitHub repositories are now
archived, this will mean these are no longer updated and there will be
no further releases of PnP PowerShell (classic) and PnP Sites Core.

Updates to the modernization tool, specifically the page transformation
tool are no longer being released as this would require a new release of
the  underlying archived frameworks; updates will now be released via
the PnP Framework repository and as these now have builds either nightly
or monthly, you will be able to take advantage of updates the next day
-- to use these nightly versions, you can install the prerelease version
of the PowerShell modules from the gallery or grab the latest NuGet
packages.

 

The Modernization scanner is currently being maintained for the time
being in the [SP-Dev-Modernization
repository](https://github.com/PnP/sp-dev-modernization), as this tool
is , any [issues
found](https://github.com/pnp/sp-dev-modernization/issues) with this
tool can continue to be posted to this repository.

For bugs, enhancements with the page transformation tooling, please post
to the [issues list on the PnP Framework
page](https://github.com/pnp/pnpframework/issues) -- these will then be
investigated and any bug or enhancement that is written as a outcome of
the issue will be included in the nightly builds of PnP Framework.

 

Currently, the [PnP Core SDK](https://aka.ms/pnp/coresdk/docs) that will
eventually replace PnP Framework is currently in beta and is currently
under active development. When this is complete, the next steps are to
transition all the tooling, PnP Framework, PnP PowerShell, and
Modernization tooling to utilize this library -details on timelines
and what features are included will be announced on a later date.
