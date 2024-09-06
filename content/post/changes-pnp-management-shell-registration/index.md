---
title: "Changes in PnP Management Shell registration in Microsoft 365"
date: 2024-08-21T02:32:38.770Z
author: Vesa Juvonen
githubname: VesaJuvonen
categories:
  - PnP PowerShell
  - CLI for Microsoft 365
images:
  - images/pnp-management-shell-blog-post-news-v2.png
tags:
  - Microsoft Entra ID
  - PnP PowerShell
  - CLI for Microsoft 365
  - SharePoint
  - Microsoft Teams
  - Microsoft Viva
  - Microsoft Entra
type: regular
videos:
  - https://www.youtube.com/watch?v=VNgc4k_gCT0
draft: false
---

 We are **introducing changes on how the PnP PowerShell and CLI for Microsoft 365 can be used to connect to Microsoft 365**, which might have an impact on your scripts and automation. Previously you were able to use a multi-tenant app registration called PnP Management Shell to grant the needed permissions for the scripts. This **multi-tenant app registration will be, however, deleted on September 9, 2024** which might impact your existing scripts.

This change is provided to help customers to **improve their security posture by encouraging the use of single tenant app registrations with on just the scopes and permissions which are needed**. Both PnP PowerShell and CLI for Microsoft 365 support registering a tenant specific app for the permissions needed and there's no changes on the required user permissions. Similarly, as previously with the multi-tenant app registration, single tenant registration requires that you are tenant administrator and have the needed permissions in the Azure side.

{{< notice important>}}
Any existing script which is dependent on the multi-tenant authentication option will be impacted on this change starting from September 9, 2024. Please confirm your authentication model from your script(s).
{{< /notice >}}

Please see the documentation below on references of the details on how to perform single tenant app registration.

In the following video [Erwin van Hunen](https://www.linkedin.com/in/erwinvanhunen/) (MondayCoffee), [Waldek Mastykarz](https://www.linkedin.com/in/waldekmastykarz/) (Microsoft) and [Vesa Juvonen](https://www.linkedin.com/in/vesajuvonen/) (Microsoft) are talking about the impact of the change.

{{< youtube VNgc4k_gCT0 >}}

We are further looking into providing additional quick videos and guidance on setting up the single-tenant app registrations as defined in the documentation for both PnP PowerShell and CLI for Microsoft 365.

## Support

PnP PowerShell and CLI for Microsoft 365 are community provided open-source tools which does not have direct support from Microsoft. Please see https://aka.ms/pnpsupport as the supportability guidance on these community provided tools.

If you have any questions, please use the specific issue list(s) for the questions:

* [PnP PowerShell GitHub issue list](https://github.com/pnp/powershell/issues)
* [CLI for Microsoft 365 issue list](https://github.com/pnp/cli-microsoft365/issues)

## Documentation

Here's the specific guidance for the PnP PowerShell and CLI for Microsoft 365 to use tenant specific app registration.

* **PnP PowerShell** - [Connect using your own Entra ID Application](https://pnp.github.io/powershell/articles/connecting.html#connect-by-using-your-own-entra-id-application)
* **CLI for Microsoft 365** - [Using your own Microsoft Entra identity](https://pnp.github.io/cli-microsoft365/user-guide/using-own-identity/)

Here are also guidance videos on how to get started with the PnP PowerShell and CLI for Microsoft 365 in single tenant registration

* [Getting started with PnP PowerShell - Installation and app registration](https://www.youtube.com/watch?v=ecRZrHOucz4)

## Frequently asked questions

**Why is this happening?**
We are following up on the updated focus for customer security across the ecosystem and want to drive the usage of PnP PowerShell and CLI for Microsoft 365 towards more scoped permissions. Multi-tenant registration option was great to speed up the onboarding, but it resulted often too many scopes to get granted and even though they are delegated scopes (user permissions matter) - less is always better.

**Does this change impact existing implementations?**
This depends. Change will impact authentication flow on every script which has been using the multi-tenant app registration pattern. Please double check the authentication model you are using and update accordingly. Otherwise, there will not be any changes required for the scripts.

**Will existing scripts work after the authentication is changed with single tenant app registration?**
Yes. You'll need to potentially update the authentication/connections section, but otherwise all the cmdlets and commands are working similarly with the multi-tenant and single tenant app registrations.