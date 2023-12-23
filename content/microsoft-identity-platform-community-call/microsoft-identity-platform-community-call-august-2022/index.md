---
title: "Microsoft Identity Platform community call – August 2022"
tags: ["Microsoft 365", "Azure", "Microsoft identity Platform"]
date: 2022-08-18T05:11:59-05:00
author: "Nandeesh Swami"
githubname: Nandeeshswami
categories: ["Microsoft identity platform community call"]
images:
- images/recording-identity-community-call-august-2022.png
type: "regular"
summary: "Integrate an Angular single page app with the Microsoft identity platform.
Integrate SSO and get an access token for Microsoft Graph API. Subscribe to MSAL
events, protect routes using MSAL Angular Guard, and acquire tokens with MSAL
Angular Interceptor."
videos:
- https://www.youtube.com/watch?v=EJey9KP1dZA
- draft: false
---


## Call summary

This month’s in-depth topic: **Deep dive on using MSAL.js to integrate Angular
single-page applications with Azure Active Directory.** In this session, we will
walk through the steps and coding required to successfully integrate an Angular
single page app with the Microsoft identity platform. We’ll start with the app
integrating single sign-on for its users. We will then next proceed to get an
access token for the Microsoft Graph API. We will cover the coding required in
detail, including how to subscribe to MSAL events like user sign-in and
sign-out, how to protect routes using MSAL Angular Guard, and how to acquire
tokens with MSAL Angular Interceptor. We will also touch upon some advanced
concepts like how apps can prepare themselves for Continuous Access Evaluation
(CAE) events. We will cap the session with showing you how to successfully
deploy your app on Azure Static App Service. Microsoft Presenters [Doğan
Erişen](https://ca.linkedin.com/in/doganerisen), [Salman
Salem](https://ca.linkedin.com/in/salman-salem) and [Kalyan
Krishna](https://twitter.com/kalyankrishna1). Recorded August 18, 2022

{{< youtube EJey9KP1dZA >}}

## Referenced in this call

* Demo - [Using MSAL.js to integrate React Single-page applications with Azure Active Directory – July 2022](https://youtu.be/7oPSL5wWeS0)
* Repo - [Msal Angular Demo](https://github.com/derisen/msal-angular-demo)
* Tutorial - [Tutorial: Enable your Angular single-page application to sign-in users and call APIs with the Microsoft identity platform](https://github.com/Azure-Samples/ms-identity-javascript-angular-tutorial/blob/main/README.md) \| aka.ms/msalangulartutorial
* Samples - [Microsoft identity platform code samples](https://docs.microsoft.com/azure/active-directory/develop/sample-v2-code) \| aka.ms/aadcodesamples
* Documentation - [OWASP Cross Site Scripting (XSS) Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html)
* CAE Code sample - [Angular single-page application using MSAL Angular to sign-in users with Azure Active Directory and call the Microsoft Graph API](https://github.com/Azure-Samples/ms-identity-javascript-angular-tutorial/tree/main/2-Authorization-I/1-call-graph)
* Library - [Microsoft Authentication Library for JavaScript (MSAL.js)](https://github.com/AzureAD/microsoft-authentication-library-for-js)
* Documentation – [MSAL Browser docs](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/lib/msal-browser/docs)
* Documentation - [Microsoft-authentication-library-for-js](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/lib/msal-angular/docs)
* Testing samples - [MSAL Angular v2 Samples](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-angular-v2-samples)
* Documentation - [Microsoft identity platform and OAuth 2.0 authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-auth-code-flow)
* Documentation - [Single sign-on with MSAL.js](https://docs.microsoft.com/azure/active-directory/develop/msal-js-sso)
* Documentation - [Continuous access evaluation](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-continuous-access-evaluation)
* Documentation – [Using MSAL in iframed apps](https://github.com/AzureAD/microsoft-authentication-library-for-js/blob/dev/lib/msal-browser/docs/iframe-usage.md)
* Documentation – [Angular single-page application using MSAL Angular to sign-in users against Azure AD B2C](https://github.com/Azure-Samples/ms-identity-javascript-angular-tutorial/blob/main/1-Authentication/2-sign-in-b2c/README-incremental.md)

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
* Mark your calendar for next call on September 15th at 9:00am PT. Download the
    recurrent invite for this call \| <https://aka.ms/IDDevCommunityCalendar>

## Resources in General

* Documentation - [What is the Microsoft identity platform?](https://docs.microsoft.com/azure/active-directory/develop/v2-overview)
* Documentation - [Microsoft identity platform documentation](https://docs.microsoft.com/azure/active-directory/develop/)
* Developer – [Microsoft Identity Platform](https://developer.microsoft.com/identity)
* Microsoft 365 Unified Sample gallery - <https://aka.ms/m365/samples>

## Stay connected

* Twitter [https://twitter.com/microsoft365dev](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbkdvcDJHcGdzM2VIUkwzU3lOYkJaVFEzM0Q2QXxBQ3Jtc0ttM1NyaTQ2RjFSOFh3a0l4c1pralBRQVI1bDNSQ2RaVm9OdzJrRkdtV1Z1SW5VdmdwamNNLTBEaFdaSmZMc0lQNzdRZ2dDYV9WZVF1ZVIwc2dPQTZBRUZ3b3hoWUVJdDJoQWZUcWdCR2JKdmwtUU43RQ&q=https%3A%2F%2Ftwitter.com%2Fmicrosoft365dev)​ and @azuread
* Microsoft 365 Platform Community in YouTube - <https://aka.ms/m365/videos>
* Microsoft 365 Platform Community - <https://aka.ms/m365/community>
* YouTube [https://aka.ms/M365DevYouTube](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqa3RzWmpNU2VPRmh6dXBad3hKMmxySjBaQVl6Z3xBQ3Jtc0trVjYyeXZlSXZiX0JydHlyeHdqcTRSUnczX2xrVDloOWhzeGVCYXFibjBiM1VpXzFOd2dZX2dJdlNYQWYtekcyWXZOTHp3VkdoU2JsdmNVQ3dtdkw2ZHF0cVdCS29TQmJ1Z3hoVmJyd3JtYlFxUW92WQ&q=https%3A%2F%2Faka.ms%2FM365DevYouTube)​ (Developer channel)
* Blogs <https://aka.ms/m365/blog>

{{< attachments >}}{{< /attachments >}}
