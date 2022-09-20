---
title: "Microsoft Identity Platform community call – July 2022"
tags: ["Microsoft 365", "Azure", "Microsoft identity Platform"]
date: 2022-07-25T05:11:59-05:00
author: "Nandeesh Swami"
githubname: Nandeeshswami
categories: ["Microsoft identity platform community call"]
images:
- images/recording-identity-community-call-july-2022.png
type: "regular"
summary: "Integrate a React single-page app with the Microsoft identity platform. Enable SSO and get an access token for Microsoft Graph API. Subscribe to MSAL events, protect routes using MSAL Angular Guard, and acquire tokens with MSAL React hooks."
videos:
- https://www.youtube.com/watch?v=7oPSL5wWeS0
- draft: false
---


## Call summary

This month's in-depth topic: **Deep dive on using MSAL.js to integrate React
Single-page applications with Azure Active Directory.** In this session, we will
write the code required to successfully integrate a React single page app with
the Microsoft identity platform. We’ll start with the app enabling single
sign-on for its users. We will then proceed to get an access token for the
Microsoft Graph API. We will cover the coding required in detail, including how
to subscribe to MSAL events like user sign-in and sign-out, how to protect
routes using MSAL React templates, and how to acquire tokens with MSAL React
hooks. We will also touch upon some advanced concepts like how apps can prepare
themselves for Continuous Access Evaluation (CAE) events. We will cap the
session with showing you how to successfully deploy your app on Azure Static Web
Apps service. Microsoft Presenters [Doğan
Erişen](https://www.linkedin.com/in/doganerisen/), [Salman
Salem](https://www.linkedin.com/in/salman-salem/) and [Kalyan
Krishna](https://twitter.com/kalyankrishna1). Recorded July 21,2022

{{< youtube 7oPSL5wWeS0 >}}

## Referenced in this call

* Documentation - [Quickstart: Set up a SD
    tenant](https://docs.microsoft.com/azure/active-directory/develop/quickstart-create-new-tenant)
* Library - [Microsoft Authentication Library for JavaScript
    (MSAL.js)](https://github.com/AzureAD/microsoft-authentication-library-for-js)
* Documentation – [MSAL Browser
    docs](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/lib/msal-browser/docs)
* Documentation – [MSAL React
    docs](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/lib/msal-react/docs)
* Samples – [MSAL React
    samples](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-react-samples)
* Tutorial - [Tutorial: Enable your React single-page application to sign-in
    users and call APIs with the Microsoft identity
    platform](https://github.com/Azure-Samples/ms-identity-javascript-react-tutorial)
* Documentation - [Microsoft identity platform and OAuth 2.0 authorization
    code
    flow](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-auth-code-flow)
* Documentation - [Single sign-on with
    MSAL.js](https://docs.microsoft.com/azure/active-directory/develop/msal-js-sso)
* Documentation - [Continuous access
    evaluation](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-continuous-access-evaluation)
* Samples - [Microsoft identity platform code
    samples](https://docs.microsoft.com/azure/active-directory/develop/sample-v2-code)
    \| aka.ms/aadcodesamples
* Cheat Sheet - [Cross Site Scripting Prevention Cheat
    Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html)
* Demo - [Getting Started with Create React
    App](https://github.com/derisen/msal-react-demo)
* Documentation - [Microsoft identity platform ID
    tokens](https://docs.microsoft.com/azure/active-directory/develop/id-tokens)
    \| aka.ms/id-tokens
* Documentation - [Provide optional claims to your
    app](https://docs.microsoft.com/azure/active-directory/develop/active-directory-optional-claims)
    \| aka.ms/optionalclaims
* Documentation - [Claims challenges, claims requests, and client
    capabilities](https://docs.microsoft.com/azure/active-directory/develop/claims-challenge)
    \| aka.ms/ClaimsChallenge

## Actions

* Let us know how we’re doing and suggest topics for future calls, please
    complete this survey
    [https://aka.ms/IDDevCommunityCallSurvey](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Faka.ms%2FIDDevCommunityCallSurvey&data=04%7C01%7CChristos.Matskas%40microsoft.com%7C18e3d21d4b1a44823a7608d9deba552b%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637785715396882782%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C2000&sdata=I5LYE8pBSlftGEofnz98KPtVi5KfZFts7UZ7CHjRRQk%3D&reserved=0)
* Opt into PnP Recognition Program \| <https://aka.ms/m365pnp-recognition>
* Register for the [Microsoft 365 Developer
    Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn)
    covering Microsoft 365 platform capabilities including Learning Path -
    [Implement Microsoft identity –
    Associate](https://docs.microsoft.com/en-us/learn/paths/m365-identity-associate/)
* Mark your calendar for next call on August 22nd at 9:00am PT. Download the
    recurrent invite for this call \| <https://aka.ms/IDDevCommunityCalendar>

## Resources in General

* Documentation - [What is the Microsoft identity platform?](https://docs.microsoft.com/azure/active-directory/develop/v2-overview)
* Documentation - [Microsoft identity platform documentation](https://docs.microsoft.com/azure/active-directory/develop/)
* Developer – [Microsoft Identity Platform](https://developer.microsoft.com/identity)
* Microsoft 365 Unified Sample gallery - <https://aka.ms/m365/samples>

## Stay connected

* Twitter [https://twitter.com/microsoft365dev](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbkdvcDJHcGdzM2VIUkwzU3lOYkJaVFEzM0Q2QXxBQ3Jtc0ttM1NyaTQ2RjFSOFh3a0l4c1pralBRQVI1bDNSQ2RaVm9OdzJrRkdtV1Z1SW5VdmdwamNNLTBEaFdaSmZMc0lQNzdRZ2dDYV9WZVF1ZVIwc2dPQTZBRUZ3b3hoWUVJdDJoQWZUcWdCR2JKdmwtUU43RQ&q=https%3A%2F%2Ftwitter.com%2Fmicrosoft365dev)​ and **@azuread**
* Microsoft 365 Platform Community in YouTube - <https://aka.ms/m365/videos>
* Microsoft 365 Platform Community - <https://aka.ms/m365/community>
* YouTube [https://aka.ms/M365DevYouTube](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqa3RzWmpNU2VPRmh6dXBad3hKMmxySjBaQVl6Z3xBQ3Jtc0trVjYyeXZlSXZiX0JydHlyeHdqcTRSUnczX2xrVDloOWhzeGVCYXFibjBiM1VpXzFOd2dZX2dJdlNYQWYtekcyWXZOTHp3VkdoU2JsdmNVQ3dtdkw2ZHF0cVdCS29TQmJ1Z3hoVmJyd3JtYlFxUW92WQ&q=https%3A%2F%2Faka.ms%2FM365DevYouTube)​ (Developer channel)
* Blogs <https://aka.ms/m365/blog>

{{< attachments >}}
