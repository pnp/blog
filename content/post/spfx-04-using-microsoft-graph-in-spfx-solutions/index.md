---
title: "Using Microsoft Graph with SPFx solutions"
date: 2023-01-05T08:00:00.000Z
author: Vesa Juvonen
githubname: VesaJuvonen
categories:
  - SPFx
images:
  - images/04-using-microsoft-graph-with-spfx-solutions.png
tags:
  - Microsoft Teams
  - Microsoft Viva  
  - SharePoint
  - SharePoint Framework (SPFx)
type: regular
videos:
- https://www.youtube.com/watch?v=tHzbh5JoC-A
---

[SharePoint Framework](https://aka.ms/spfx) (SPFx) is an extensibility model for Microsoft 365 enabling developers to build different kinds of extensibility for Microsoft Viva, Microsoft Teams, Outlook, Microsoft 365 app (Office), and SharePoint. SPFx has multiple benefits like automatic Single Sign On, automatic hosting in the customer tenant, reuse same code across the service and industry standard web stack tooling.

-	*I need to access user and organization specific information in Microsoft 365 - how would I do that within SPFx solution?*
-	That is a great question. You'd be of course using the Microsoft Graph which is the gateway to data and intelligence in Microsoft 365.

{{< notice note>}}
This blog post is part of a month long SPFx series for January 2023. Each business day we'll publish a new blog post covering different aspects of the SPFx.

* Previous blog post in this series - [Getting started with SPFx extensions for SharePoint Online](https://pnp.github.io/blog/post/spfx-03-getting-started-with-spfx-extensions-for-spo/)
{{< /notice >}}


## Introduction on using Microsoft Graph APIs with SPFx

[Microsoft Graph APIs](https://learn.microsoft.com/en-us/graph/overview) provides you an easy way to access the user or organizational information within Microsoft 365. SPFx has a great abstraction layer for using the Microsoft Graph, including simplified development experience with following benefits:

- Automatic Single Sign-On when using Microsoft Graph APIs
- Automatic handling of access token - developers will not need to worry about where to get the token(s) for the API calls
- Centralized approval for Microsoft 365 tenant administrators on which Graph APIs are available for SPFx solutions
- Native access to Microsoft Graph v3 JavaScript SDK with the benefits with improved exception handling for throttling etc.

Using Microsoft Graph APIs with SPFx solution is easy and the recommended option to access the Microsoft 365 information. Process of using the Microsoft Graph APIs is as follows for any new solution which is getting deployed.

1. Define the used Graph APIs in SPFx solution in solution manifest (`package-solution.json`)
2. Deploy SPFx solution to tenant app catalog as the administrator
3. Grant permissions for the used APIs - API calls will be blocked unless the APIs are specifically allowed by administrator. This is a security feature to avoid any accidental access on unnecessary information.

See following resources for the official documentation on how to use Microsoft Graph with SPFx solutions

- [Use Microsoft Graph in your solution](https://learn.microsoft.com/en-us/sharepoint/dev/spfx/web-parts/get-started/using-microsoft-graph-apis)
- [Use the MSGraphClientV3 to connect to Microsoft Graph](https://learn.microsoft.com/en-us/sharepoint/dev/spfx/use-msgraph)
- [Consume the Microsoft Graph in the SharePoint Framework](https://learn.microsoft.com/en-us/sharepoint/dev/spfx/use-aad-tutorial)
- [Build a SharePoint web part with the Microsoft Graph Toolkit](https://learn.microsoft.com/en-us/graph/toolkit/get-started/build-a-sharepoint-web-part)

Here's a bit [outdated video](https://www.youtube.com/watch?v=tHzbh5JoC-A&list=PLR9nK3mnD-OXvSWvS2zglCzz4iplhVrKq&index=7) on using Microsoft Graph APIs with the SPFx solution - User interface elements have evolved a bit, but the basic steps are still exactly the same.

{{< youtube tHzbh5JoC-A >}}

## Frequent questions around using Microsoft Graph with SPFx solutions

**Can code access any Microsoft Graph APIs without administrative approval?** 

No. All Microsoft Graph APIs are by default blocked for the SPFx solutions in the tenant, so administrator will need to specifically enable the allowed APIs. This provides a bit complexity for the deployment, but model exists to provide required level of security within customer tenants.

**Can I use PowerShell to grant the permission request** 

Yes. This is an option if you are an administrator within the tenant. You can use either the user interface or script the required steps. You cannot approve the permissions unless you have sufficient permissions at the tenant level using PowerShell.

**When I grant API permissions, will those be granted for all SPFx solutions?** 

By default yes. Model works in a way that by default administrators are granting the allowed API permissions to all SPFx solutions. You can however do this also in the solution-by-solution level if that's the preferred model.

**What if I'm using Microsoft Graph Toolkit - is the process different?** 

No. Process is not different when you'd be using Microsoft Graph Toolkit. Same API level approvals are still needed for the Microsoft Graph API calls to succeed. We will cover the Microsoft Graph Toolkit option more detailed later in this blog post series.


## References

Here are some initial references to get started with the SPFx in your development. Please do provide us with feedback and suggestions on what is needed to help you to get started with the SPFx development for Microsoft 365.

- Microsoft Graph overview - https://learn.microsoft.com/en-us/graph/overview
-	SPFx documentation – https://aka.ms/spfx
-	Issues and feedback around SPFx - https://aka.ms/spfx/issues
-	Microsoft 365 Platform Community – https://aka.ms/m365/community
-	Public SPFx and other community calls – https://aka.ms/m365/calls 
    - These calls are for everyone to take advantage to stay up to date on the art of possible within Microsoft 365 and to provide guidance for beginners and more advance users
-	SPFx samples in the Microsoft 365 Unified Sample gallery – https://aka.ms/m365/samples

- - -

We will provide more details on the different options and future direction of the SPFx in upcoming blog posts. This post focused on the getting started steps with SPFx - more details coming up with this series with one post within each business day of January 2023.
