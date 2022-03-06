---
title: "Microsoft Identity Platform community call -- December 2021"
date: 2021-12-30T12:21:00-05:00
author: "Steven Salazar Aray"
categories: ["Microsoft Identity platform community call recordings"]
images:
- images/blog/microsoft-identity-platform-community-call-december-2021/identity-call-THumbnail-November-2021.png
tags: []
type: "regular"


---

{{< image alt="identity-call-THumbnail-November-2021.png" src="images/blog/microsoft-identity-platform-community-call-december-2021/identity-call-THumbnail-November-2021.png" >}}
 

<<<<<<< HEAD

## Call Summary

=======
## Call summary
>>>>>>> 8b14bdbe3d758b1e8b4673fafae5dbfba74dbdc7


This month's in-depth topic:  **A Zero Trust primer for
developers**.  In this session, we begin by introducing developers
quickly to the core Zero Trust principles: **Verify explicitly**, **Use
least privilege access**, and **Assume breach**.  We then expand why
developer's participation is critical in supporting Zero Trust policy
rollouts by the IT team. We then proceed to lay down a few steps that
developers can take to begin their journey towards building a good Zero
trust ready app. We start with learning how to effectively use claims
provided in tokens to [verify a user/subject explicitly]{.underline},
and then continue to discuss recommended practices for mobile apps. The
**Continuous Access Evaluation (CAE)** feature is discussed in detail
for developers, and we hope it will help jumpstart a developer's journey
to this absolutely critical piece of security that is becoming a must
for all cloud apps. We then proceed to discuss a few steps to enable
**least privilege**, like how to best publish and consume permissions
for an API and then we finally move to discuss topics that help apps
[recover swiftly from breaches]{.underline}, like practicing solid
credential hygiene, and logging rich information.

 

Bottom line -- developers play a critical role in building trustworthy
applications as transition from *a culture of implicit trust to that of
explicit verification*.  The full developer guide of practices to build
a Zero trust app is available at **aka.ms/ztdev**.

 

This session was delivered by Kalyan Krishna - Sr Program Manager,
Microsoft.  Recorded December 16, 2021. Q&A in chat and at end of call.


**Referenced in this session:**

-   eBook - Developer guide to Zero Trust - [Zero Trust for the
    Microsoft identity platform developer](https://aka.ms/ztdev) |
    aka.ms/ztdev
-   Demo -- [Continuous Access Evaluation (CAE)
    demo](https://aka.ms/caedemo) | aka.ms/caedemo
-   Demo - [Managed Identities with KeyVault
    demo](https://aka.ms/midemo) | aka.ms/midemo
-   Sample -- [An ASP.NET Core web app that signs-in users with Azure AD
    and calls Microsoft
    Graph](https://aka.ms/identity-zerotrust-sample) |
    aka.ms/identity-zerotrust-sample
-   Documentation - [Building Zero Trust ready apps with the Microsoft
    identity platform](https://aka.ms/zerotrustforidentitydeveloper) |
    aka.ms/zerotrustforidentitydeveloper
-   Blog series - [Achieving Zero Trust readiness in your apps #1: Why
    it
    matters](https://aka.ms/ZTRappsblog-part1) | [aka.ms/ZTRappsblog-part1](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Faka.ms%2FZTRappsblog-part1&data=04%7C01%7CKalyan.Krishna%40microsoft.com%7Cfd791ab56eed4e55417608d9ca314d33%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637763136913157969%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=HLIINSwzxrzMbue6f3OJQ7abZ%2BJCwZSSh0w0fPWcx64%3D&reserved=0)
-   Documentation - [Code samples for
    developers](https://aka.ms/aadcodesamples) | [aka.ms/aadcodesamples](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Faka.ms%2Faadcodesamples&data=04%7C01%7CKalyan.Krishna%40microsoft.com%7Cfd791ab56eed4e55417608d9ca314d33%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637763136913157969%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=XLFsFAs6Kgbmc1T6ceXxrwKHalm9rBVssqCy8L%2BM6XI%3D&reserved=0)
-   Sample - [Add app roles to your application and receive them in the
    token](https://aka.ms/approles) | aka.ms/approles  
-   Sample - [Use groups & group claims to an ASP.NET Core Web app that
    signs-in users](https://aka.ms/groupssample)  | aka.ms/groupssample
-   Documentation -- [Token Validation](https://aka.ms/validatetokens)
    | aka.ms/validatetokens
-   Sample - [How to manually validate a JWT access token using the
    Microsoft identity
    platform](https://aka.ms/extendtokenvalidation) |
    aka.ms/extendtokenvalidation
-   Documentation - [Developers' guide to Conditional Access
    authentication context](https://aka.ms/stepupauthn) -
    aka.ms/stepupauthn
-   Documentation - [Claims challenges, claims requests, and client
    capabilities](https://aka.ms/ClaimsChallenge) | aka.ms/ClaimsChallenge 
-   Documentation - [Sign in any Azure Active Directory user using the
    multi-tenant application pattern](https://aka.ms/multi-tenant) |
    aka.ms/multi-tenant
-   Documentation - [Overview of the Microsoft Authentication Library
    (MSAL)](https://aka.ms/msal) | aka.ms/msal
-   Documentation - [Microsoft identity platform
    documentation](https://aka.ms/identityplatform) |
    aka.ms/identityplatform

 

<<<<<<< HEAD

**Actions:**
=======
## Actions
>>>>>>> 8b14bdbe3d758b1e8b4673fafae5dbfba74dbdc7



-   Download and go through the developer guide available at
    <https://aka.ms/ztdev>
-   Let us know how we're doing and suggest topics for future calls,
    please complete this
    survey [https://aka.ms/IDDevCommunityCallSurvey](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Faka.ms%2FIDDevCommunityCallSurvey&data=04%7C01%7CKalyan.Krishna%40microsoft.com%7Cfd791ab56eed4e55417608d9ca314d33%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637763136913157969%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=OPYLVi9n%2BfrA5qI%2B2Is1%2F6tYFfX6X6lPsE2Qt%2BdCeqQ%3D&reserved=0)
-   Join us for the next Microsoft Identity Platform community call
    on January 20^th^ at 9:00am PT

 

**Stay connected:**

-   Twitter
    [https://twitter.com/microsoft365dev](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbkdvcDJHcGdzM2VIUkwzU3lOYkJaVFEzM0Q2QXxBQ3Jtc0ttM1NyaTQ2RjFSOFh3a0l4c1pralBRQVI1bDNSQ2RaVm9OdzJrRkdtV1Z1SW5VdmdwamNNLTBEaFdaSmZMc0lQNzdRZ2dDYV9WZVF1ZVIwc2dPQTZBRUZ3b3hoWUVJdDJoQWZUcWdCR2JKdmwtUU43RQ&q=https%3A%2F%2Ftwitter.com%2Fmicrosoft365dev)​
    and **\@azuread**
-   YouTube
    [https://aka.ms/M365DevYouTube](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqa3RzWmpNU2VPRmh6dXBad3hKMmxySjBaQVl6Z3xBQ3Jtc0trVjYyeXZlSXZiX0JydHlyeHdqcTRSUnczX2xrVDloOWhzeGVCYXFibjBiM1VpXzFOd2dZX2dJdlNYQWYtekcyWXZOTHp3VkdoU2JsdmNVQ3dtdkw2ZHF0cVdCS29TQmJ1Z3hoVmJyd3JtYlFxUW92WQ&q=https%3A%2F%2Faka.ms%2FM365DevYouTube)​
    (Developer channel) and
    [https://aka.ms/m365pnp/videos](https://aka.ms/m365pnp-videos)
    (Community channel)
-   Blogs <https://aka.ms/m365pnp/community/blog>
-   Recurrent Invite <https://aka.ms/IDDevCommunityCalendar>

 