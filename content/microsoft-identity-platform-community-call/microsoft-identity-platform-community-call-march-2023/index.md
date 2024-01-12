---
title: "Microsoft Identity Platform community call – March 2023"
tags: ["Microsoft 365", "Azure", "Microsoft identity Platform"]
date: 2023-03-16T05:11:59-05:00
author: "Nandeesh Swami"
githubname: Nandeeshswami
categories: ["Microsoft identity platform community call"]
images:
- images/promo-identity-march-2023.png
type: "regular"
summary: "Leverage the latest MSAL features covering security, resiliency, and usability. Learn how to move from ADAL to MSAL to enable pro-active token refreshing, extended outage resiliency, and improved OIDC-compliant flows moving from implicit flow to auth code token."
videos:
- https://www.youtube.com/watch?v=Kex1zqARIQ0
- draft: false
---

## Call summary

This month’s in-depth topic: **Staying Up to Date with Authentication for JavaScript Applications**

Microsoft is continually improving the Microsoft Authentication Libraries (MSAL) to benefit Microsoft web properties and your custom JavaScript applications. By staying up to date with the latest MSAL versions, your web application will receive the latest innovations on security, resiliency, and usability as they are released. If your application is still on ADAL, migrating to MSAL will enable pro-active token refreshing, extended outage resiliency, and improved OIDC-compliant flows moving from implicit flow to auth code token. Join this session to learn more about how your JavaScript application can leverage the latest features. Microsoft Presenters: [Emily Lauber](https://www.linkedin.com/in/emlauber/) – Product Manager and [Doğan Erişen](https://github.com/derisen) - Software Engineer.

## Topic/Demo Summaries

**Staying Up to Date with Authentication for JavaScript Applications** – take advantage of continuous updates to the Microsoft Authentication Libraries (MSAL) features addressing security, resiliency, and usability as they are released. Presentation covers - what is MSAL.js?, what can you use it for?, what changed since ADAL?, why should you stay up-to-date on the latest MSAL version? Latest on app configuration authority differences, redirect URI differences, API permissions differences, and supported account types.

**Migrating your solutions from ADAL.js to MSAL** – will enable pro-active token refreshing, extended outage resiliency, and improved OIDC-compliant flows moving from implicit flow to auth code token. Coding demo stepping through sample migration of a SPA from ADAL to MSAL. Observe ADAL vs MSAL API surface (method name/signature changes, promises vs callbacks, accounts vs users, and error handling) and review token caching & renewal behavior.

This call was hosted by [Nandeesh Swami](https://twitter.com/Nandeesh_Swami) (Microsoft) \| @Nandeesh_Swami and <https://www.linkedin.com/in/nandeeshswami/> on March 16, 2023. Questions addressed live and in chat throughout the call.

{{< youtube Kex1zqARIQ0 >}}

## Agenda items

[00:00](https://youtu.be/Kex1zqARIQ0?t=0) – Intro - [Nandeesh Swami](https://twitter.com/Nandeesh_Swami) (Microsoft) \| @Nandeesh_Swami

[01:04](https://youtu.be/Kex1zqARIQ0?t=64) – Topic – Staying up to date with authentication for JavaScript applications – [Emily Lauber](https://www.linkedin.com/in/emlauber/) (Microsoft)

[10:26](https://youtu.be/Kex1zqARIQ0?t=626) – Demo – Migrating your solutions from ADAL.js to MSAL - [Doğan Erişen](https://github.com/derisen) - (Microsoft)

[35:24](https://youtu.be/Kex1zqARIQ0?t=2124) – Q & A related to demo

[51:49](https://youtu.be/Kex1zqARIQ0?t=3109) – Closing

## Referenced in the call

* Documentation - [Contributing to MSAL.js](https://ineleccom-my.sharepoint.com/personal/andrb_inelec_com/Documents/Desktop/Office%20Videos/Identity%20Calls/2023-03-16-Identity/Contributing%20to%20MSAL.js) \| <https://github.com/AzureAD/microsoft-authentication-library-for-js/blob/dev/contributing.md>
* Release notes: [microsoft-authentication-library-for-js](https://github.com/AzureAD/microsoft-authentication-library-for-js/releases) \| <https://github.com/AzureAD/microsoft-authentication-library-for-js/releases>
* Repo - [microsoft-authentication-library-for-js](https://github.com/AzureAD/microsoft-authentication-library-for-js/releases) \| <https://github.com/AzureAD/microsoft-authentication-library-for-js>
* Documentation - [How to migrate a JavaScript app from ADAL.js to MSAL.js](https://learn.microsoft.com/azure/active-directory/develop/msal-compare-msal-js-and-adal-js) \| <https://learn.microsoft.com/azure/active-directory/develop/msal-compare-msal-js-and-adal-js>
* Documentation - [Migrate a JavaScript single-page app from implicit grant to auth code flow](https://learn.microsoft.com/azure/active-directory/develop/migrate-spa-implicit-to-auth-code) \| <https://learn.microsoft.com/azure/active-directory/develop/migrate-spa-implicit-to-auth-code>
* Video - [Deep dive on using MSAL.js to integrate Angular single-page applications with Azure AD – August 2022](https://www.youtube.com/watch?v=EJey9KP1dZA) \| <https://www.youtube.com/watch?v=EJey9KP1dZA>
* Repo - [Using MSAL in iframed apps](https://github.com/AzureAD/microsoft-authentication-library-for-js/blob/dev/lib/msal-browser/docs/iframe-usage.md) \| <https://github.com/AzureAD/microsoft-authentication-library-for-js/blob/dev/lib/msal-browser/docs/iframe-usage.md>
* Repo - [Resources and Scopes](https://github.com/AzureAD/microsoft-authentication-library-for-js/blob/dev/lib/msal-browser/docs/resources-and-scopes.md) v2 \| <https://github.com/AzureAD/microsoft-authentication-library-for-js/blob/dev/lib/msal-browser/docs/resources-and-scopes.md>
* Documentation – [How to migrate a Node.js app from ADAL to MSAL](https://learn.microsoft.com/azure/active-directory/develop/msal-node-migration) \| <https://learn.microsoft.com/azure/active-directory/develop/msal-node-migration>
* Sample - [MSAL Node Standalone Sample: Refresh Token Grant](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-node-samples/refresh-token) \| <https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-node-samples/refresh-token>
* Documentation - [Application types for the Microsoft identity platform](https://learn.microsoft.com/azure/active-directory/develop/v2-app-types) \| <https://learn.microsoft.com/azure/active-directory/develop/v2-app-types>
* Samples – [Microsoft identity platform code samples](https://learn.microsoft.com/azure/active-directory/develop/sample-v2-code) \| <https://learn.microsoft.com/azure/active-directory/develop/sample-v2-code>
* SDK - [Microsoft Graph JavaScript Client Library](https://github.com/microsoftgraph/msgraph-sdk-javascript) \| <https://github.com/microsoftgraph/msgraph-sdk-javascript>

## Actions

* Let us know how we’re doing and suggest topics for future calls, please complete this survey [https://aka.ms/IDDevCommunityCallSurvey](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Faka.ms%2FIDDevCommunityCallSurvey&data=04%7C01%7CChristos.Matskas%40microsoft.com%7C18e3d21d4b1a44823a7608d9deba552b%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637785715396882782%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C2000&sdata=I5LYE8pBSlftGEofnz98KPtVi5KfZFts7UZ7CHjRRQk%3D&reserved=0)
* Opt into PnP Recognition Program \| <https://aka.ms/m365pnp-recognition>
* Register for the [Microsoft 365 Developer Program](https://aka.ms/m365/devprogram) and get a free developer tenant
* Get started with [free training modules](https://aka.ms/m365/dev/learn) covering Microsoft 365 platform capabilities including Learning Path - [Implement Microsoft identity – Associate](https://learn.microsoft.com/learn/paths/m365-identity-associate/)
* Mark your calendar for next call on April 20th at 9:00am PT. Download the recurrent invite for this call \| <https://aka.ms/IDDevCommunityCalendar>

## Resources in General

* Documentation - [What is the Microsoft identity platform?](https://learn.microsoft.com/azure/active-directory/develop/v2-overview)
* Documentation - [Microsoft identity platform documentation](https://learn.microsoft.com/azure/active-directory/develop/)
* Developer – [Microsoft Identity Platform](https://developer.microsoft.com/identity)
* Microsoft 365 Unified Sample gallery - <https://aka.ms/m365/samples>

## Stay connected

* Twitter [https://twitter.com/microsoft365dev](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbkdvcDJHcGdzM2VIUkwzU3lOYkJaVFEzM0Q2QXxBQ3Jtc0ttM1NyaTQ2RjFSOFh3a0l4c1pralBRQVI1bDNSQ2RaVm9OdzJrRkdtV1Z1SW5VdmdwamNNLTBEaFdaSmZMc0lQNzdRZ2dDYV9WZVF1ZVIwc2dPQTZBRUZ3b3hoWUVJdDJoQWZUcWdCR2JKdmwtUU43RQ&q=https%3A%2F%2Ftwitter.com%2Fmicrosoft365dev)​ and @azuread
* LinkedIn [Nandeesh Swami](https://www.linkedin.com/in/nandeesh-s-301a7514/) \| <https://www.linkedin.com/in/nandeesh-s-301a7514/>
* See the full blog post for this call in the Microsoft 365 platform community blog - <https://aka.ms/community/blog>
* Microsoft 365 Unified Sample gallery - <https://aka.ms/community/samples>
* Microsoft 365 Platform Community in YouTube - <https://aka.ms/community/videos>
* Microsoft 365 Platform Community - <http://aka.ms/community/home>

{{< attachments >}}
