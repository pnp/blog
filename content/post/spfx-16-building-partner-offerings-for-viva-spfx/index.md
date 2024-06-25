---
title: "Building partner offerings for Microsoft Viva Connections & Viva Home with SPFx"
date: 2023-01-23T04:00:00.000Z
author: Vesa Juvonen
githubname: VesaJuvonen
categories:
  - SPFx
images:
  - images/16-building-partner-offerings-viva-spfx.png
tags:
  - Microsoft Teams
  - Microsoft Viva
  - SharePoint Framework (SPFx)
type: regular
videos:
- https://www.youtube.com/watch?v=6VEYD11m0TA
- https://www.youtube.com/watch?v=DTKkWnu-0RE
draft: false
---

[SharePoint Framework](https://aka.ms/spfx) (SPFx) is an extensibility model for Microsoft 365 enabling developers to build different kinds of extensibility for Microsoft Viva, Microsoft Teams, Outlook, Microsoft 365 app (Office), and SharePoint. SPFx has multiple benefits like automatic Single Sign On, automatic hosting in the customer tenant, reuse same code across the service and industry standard web stack tooling.

-	*We have an existing SaaS service which we would like to expose for Microsoft Viva, any guidance for this?*
-	That is a great question. You'd be using SPFx to build the Viva Cards for the Viva Connections and Viva Home, which can easily connect to your SaaS services. It's a common scenario that you'd have an existing Microsoft Teams solution which is also extended in the Viva Dashboard - This provides you an new opportunity to expose your service(s) in the enterprise world. Your custom Viva Card then can expose the most relevant information directly in the Viva Dashboard and drive traffic to your Teams application for complex operations.

{{< notice note>}}
This blog post is part of a month long SPFx series for January 2023. Each business day we'll publish a new blog post covering different aspects of the SPFx.

* Previous blog post in this series - [Building a shared map solution for Microsoft Teams with SPFx](https://pnp.github.io/blog/post/spfx-15-building-a-shared-map-teams-solution-spfx/)
* Next blog post in this series - [Using Microsoft Graph Toolkit with SPFx solutions](https://pnp.github.io/blog/post/spfx-17-microsoft-graph-toolkit-spfx/)
{{< /notice >}}


## Building partner offerings for Microsoft Viva Connections & Viva Home with SPFx

There are few specific things to notice as you design your experience for Microsoft Viva and want to expose them within multiple tenants (multiple customers) as an offering. This is relatively common setup for any SaaS company which wants to expose their services to Microsoft Teams and take advantage of the additional opportunities which Microsoft Viva provides on reaching even more users.

Considerations and steps to implement your offering:

* You will need to register your API in Azure AD as multi-tenant hosted API, so that the other tenants (customers) can use it
* You'll build the API and ACE independently in your environment
* As customer deploys the SPFx solution - you can request them to grant access to the custom API as part of the administrative deployment - this has been supported with SPFx v1.15.2
* Customer ACE is deployed to their tenant and it's calling your centrally hosted API with automatic single sign on with Azure AD

We have provided a specific [reference solution](https://github.com/pnp/spfx-reference-scenarios/tree/main/samples/ace-pnp-contoso-orders) and scenario demonstrating the required steps and to provide you a blueprint model to follow.

Here's a great video from [Paolo Pialorsi](https://twitter.com/paolopia) on how the reference solution for this scenario works.

{{< youtube 6VEYD11m0TA >}}

As you build the experiences for the Microsoft Viva, you might be also interested on the Microsoft Viva ISV benefits program, which have set of benefits for partners who are building experiences for Microsoft Viva. Here's a video where [Gloria Sánchez](https://twitter.com/sglo_) (Microsoft) and [Vesa Juvonen](https://twitter.com/vesajuvonen) (me) are talking about this program and its benefits.

{{< youtube DTKkWnu-0RE >}}

Documentation and references on building partner offering for Microsoft Viva

- [Contoso Orders reference solution for ISV partner ACEs](https://adoption.microsoft.com/en-us/sample-solution-gallery/sample/pnp-spfx-reference-scenarios-ace-pnp-contoso-orders/)
- [Contoso Orders - Demo - Introduction](https://github.com/pnp/spfx-reference-scenarios/blob/main/samples/ace-pnp-contoso-orders/docs/Introduction.md)
- [API Implementation Details for your ACE](https://github.com/pnp/spfx-reference-scenarios/blob/main/samples/ace-pnp-contoso-orders/docs/APIs-Implementation-Details.md)
- [SPFx ACE Implementation Details](https://github.com/pnp/spfx-reference-scenarios/blob/main/samples/ace-pnp-contoso-orders/docs/ACEs-Implementation-Details.md)
- [Build, sell, and thrive with Microsoft 365 - Partner Benefits program for Microsoft Viva](https://cloudpartners.transform.microsoft.com/practices/modernworkisv)

## Frequent questions

**Do I have to use the Azure to host my API for the Microsoft Viva?**

Technically no, but the authentication with the Azure AD and your custom API is the easiest. This will give you the most secure channel as your simply rely on the automatic single-sign in the Microsoft 365 side and then use the user context to call the Azure AD secured APIs.

**Can I use any other authentication system than Azure AD?**

Theoretically yes, but things would get complicated on how to implement the mapping between the Azure AD secured person and the request to the API call. There is also now web sign-in support for the Viva ACE cards in the mobile view, at least for now, which is a consideration when the mobile native experience is used.

## References

Here are some initial references to get started with the SPFx in your development. Please do provide us with feedback and suggestions on what is needed to help you to get started with the SPFx development for Microsoft 365.

-	SPFx documentation – https://aka.ms/spfx
-	Issues and feedback around SPFx - https://aka.ms/spfx/issues
-	Microsoft 365 Platform Community – https://aka.ms/m365/community
-	Public SPFx and other community calls – https://aka.ms/m365/calls
    - These calls are for everyone to take advantage to stay up to date on the art of possible within Microsoft 365 and to provide guidance for beginners and more advance users.
-	SPFx samples in the Microsoft 365 Unified Sample gallery – https://aka.ms/m365/samples

- - -

We will provide more details on the different options and future direction of the SPFx in upcoming blog posts. This post focused on the getting started steps with SPFx - more details coming up with this series with one post within each business day of January 2023.
