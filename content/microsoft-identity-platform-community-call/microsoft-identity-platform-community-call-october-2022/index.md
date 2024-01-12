---
title: "Microsoft Identity Platform community call – October 2022"
tags: ["Microsoft 365", "Azure", "Microsoft identity Platform"]
date: 2022-10-20T05:11:59-05:00
author: "Nandeesh Swami"
githubname: Nandeeshswami
categories: ["Microsoft identity platform community call"]
images:
- images/promo-identity-call-october-2022.png
type: "regular"
summary: "Deep dive on using MSAL Node to integrate Electron desktop applications with Azure AD.  Overview of MSAL Node, OAuth 2.0 native app best practices, enabling single sign-on (SSO), acquiring a token for Microsoft Graph, calling Microsoft Graph and Q & A."
videos:
- https://www.youtube.com/watch?v=JOykhyP0x8M
- draft: false
---


## Call summary

This month’s in-depth topic: **Deep dive on using MSAL Node to integrate Electron desktop applications with Azure AD.** In this session, we will walk through the steps required to integrate a cross-platform Electron desktop application with the Microsoft identity platform. We’ll start with discussing how to enable single sign-on (SSO) for users. We will then proceed to get an access token for the Microsoft Graph API. We will cover the coding required in detail, including how to use the system browser for authentication, how to subscribe to MSAL events like user sign-in and sign-out, and how to cache tokens on disk for performance. We will cap the session by responding to your questions about using MSAL Node for desktop apps. Microsoft Presenters are [Emily Lauber](https://www.linkedin.com/in/emlauber/), [Doğan Erişen](https://www.linkedin.com/in/doganerisen/) and [Salman Salem](https://www.linkedin.com/in/salman-salem/). This call was hosted by [Nandeesh Swami](https://twitter.com/Nandeesh_Swami) (Microsoft) \| @Nandeesh_Swami on October 20, 2022. Questions addressed live and in chat throughout the call.

{{< youtube JOykhyP0x8M >}}

## Referenced in this call

* Sample - [An Electron desktop application using MSAL Node on Microsoft identity platform](https://github.com/Azure-Samples/ms-identity-javascript-nodejs-desktop)
* RFC - [OAuth 2.0 for Native Apps](https://www.rfc-editor.org/rfc/rfc8252)
* Documentation - [Microsoft identity platform ID tokens](https://learn.microsoft.com/azure/active-directory/develop/id-tokens) \| aka.ms/id-tokens
* Library - [Microsoft Authentication Library for JavaScript (MSAL.js)](https://github.com/AzureAD/microsoft-authentication-library-for-js)
* Documentation – [MSAL Node Docs](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/lib/msal-node/docs)
* Samples - [MSAL Angular v2 Samples](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-angular-v2-samples)
* Documentation - [Microsoft identity platform and OAuth 2.0 authorization code flow](https://learn.microsoft.com/azure/active-directory/develop/v2-oauth2-auth-code-flow)
* Documentation - [Continuous access evaluation](https://learn.microsoft.com/azure/active-directory/conditional-access/concept-continuous-access-evaluation)
* Documentation - [Microsoft identity platform code samples](https://learn.microsoft.com/azure/active-directory/develop/sample-v2-code)
* SDK - [Microsoft Graph JavaScript Client Library](https://github.com/microsoftgraph/msgraph-sdk-javascript)
* Zero Trust
    * Guide - [Zero Trust for the Microsoft identity platform developer](https://azure.microsoft.com/resources/zero-trust-for-the-microsoft-identity-platform-developer/) \| aka.ms/ztdev
    * Sample - [Enable your ASP.NET Core web app to sign in users and call Microsoft Graph with the Microsoft identity platform](https://github.com/Azure-Samples/active-directory-aspnetcore-webapp-openidconnect-v2/blob/master/2-WebApp-graph-user/2-1-Call-MSGraph/README.md) \| aka.ms/identity-zerotrust-sample
    * Sample - [How to manually validate a JWT access token using the Microsoft identity platform](https://github.com/Azure-Samples/active-directory-dotnet-webapi-manual-jwt-validation/blob/master/README.md) \| aka.ms/extendtokenvalidation
    * Documentation - [Add app roles to your application and receive them in the token](https://learn.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) \| aka.ms/approles
    * Sample - [Add authorization using groups & group claims to an ASP.NET Core Web app that signs-in users with the Microsoft identity platform](https://github.com/Azure-Samples/active-directory-aspnetcore-webapp-openidconnect-v2/blob/master/5-WebApp-AuthZ/5-2-Groups/README.md) \| aka.ms/groupssample
    * Article - [Achieving Zero Trust readiness in your apps \#1: Why it matters](https://techcommunity.microsoft.com/t5/microsoft-entra-azure-ad-blog/achieving-zero-trust-readiness-in-your-apps-1-why-it-matters/ba-p/2959972) \| aka.ms/ZTRappsblog-part1
* Previous sessions on related to this topic
    * Call - [Deep dive on using MSAL.js to integrate Angular single-page applications with Azure Active Directory](https://pnp.github.io/blog/microsoft-identity-platform-community-call/microsoft-identity-platform-community-call-august-2022/)
    * Call - [Deep dive on using MSAL.js to integrate React Single-page applications with Azure Active Directory](https://pnp.github.io/blog/microsoft-identity-platform-community-call/microsoft-identity-platform-community-call-july-2022/)

## Actions

* Let us know how we’re doing and suggest topics for future calls, please complete this survey [- aka.ms/IDDevCommunityCallSurvey](https://aka.ms/IDDevCommunityCallSurvey)
* Opt into PnP Recognition Program \| [aka.ms/m365pnp-recognition](https://aka.ms/m365pnp-recognition)
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities including Learning Path - [Implement Microsoft identity – Associate](https://learn.microsoft.com/learn/paths/m365-identity-associate/)
* Mark your calendar for next call on November 17th at 9:00am PT. Download the recurrent invite for this call \| [aka.ms/IDDevCommunityCalendar](https://aka.ms/IDDevCommunityCalendar)

## Resources in General

* Documentation - [What is the Microsoft identity platform?](https://learn.microsoft.com/azure/active-directory/develop/v2-overview)
* Documentation - [Microsoft identity platform documentation](https://learn.microsoft.com/azure/active-directory/develop/)
* Developer – [Microsoft Identity Platform](https://developer.microsoft.com/identity)
* Samples - [Microsoft 365 Unified Sample gallery](https://adoption.microsoft.com/sample-solution-gallery/) \| aka.ms/m365/samples

## Stay connected

* Twitter [https://twitter.com/microsoft365dev](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbkdvcDJHcGdzM2VIUkwzU3lOYkJaVFEzM0Q2QXxBQ3Jtc0ttM1NyaTQ2RjFSOFh3a0l4c1pralBRQVI1bDNSQ2RaVm9OdzJrRkdtV1Z1SW5VdmdwamNNLTBEaFdaSmZMc0lQNzdRZ2dDYV9WZVF1ZVIwc2dPQTZBRUZ3b3hoWUVJdDJoQWZUcWdCR2JKdmwtUU43RQ&q=https%3A%2F%2Ftwitter.com%2Fmicrosoft365dev)​ and **@azuread**
* Microsoft 365 Platform Community in YouTube - [aka.ms/m365/videos](https://aka.ms/m365/videos)
* Microsoft 365 Platform Community - [aka.ms/m365/community](http://aka.ms/m365/community)
* YouTube [- aka.ms/M365DevYouTube](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqa3RzWmpNU2VPRmh6dXBad3hKMmxySjBaQVl6Z3xBQ3Jtc0trVjYyeXZlSXZiX0JydHlyeHdqcTRSUnczX2xrVDloOWhzeGVCYXFibjBiM1VpXzFOd2dZX2dJdlNYQWYtekcyWXZOTHp3VkdoU2JsdmNVQ3dtdkw2ZHF0cVdCS29TQmJ1Z3hoVmJyd3JtYlFxUW92WQ&q=https%3A%2F%2Faka.ms%2FM365DevYouTube)​ (Developer channel)
* Blogs - [aka.ms/m365pnp/blog](https://aka.ms/m365pnp/blog)

{{< attachments >}}{{< /attachments >}}
