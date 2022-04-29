---
title: "ProvisionGenie - an open-source provisioning engine for Microsoft Teams"
date: 2021-09-29T08:40:00-04:00
author: "Luise Freese"
githubname: LuiseFreese
categories: ["Community post"]
images:
- images/TeansResult.png
tags: ["Microsoft Teams", "Dataverse", "Azure", "Power Apps"]
type: "regular"
---

## Once upon a time

I teamed up with my friend and partner in crime [Carmen
Ysewijn](https://twitter.com/CarmenYsewijn "https://twitter.com/CarmenYsewijn").
We both work as Power Platform developers and Microsoft 365 consultants,
and got both tired of doing the same things over and over again:

Organizations would roll out Microsoft Teams, and either not make too
much fuzz on meeting user's needs and just assume that *changing
working behavior* would magically happen or they would get a business
consultant (us) who would then sit with each and every single team and
explain

-   why cascading folder structures in SharePoint are a bad idea
-   how to keep track of what really matters
-   how we do not drown in information and notification overload
-   how to excel at the art of teamwork
  
### Our idea

Now, when #poweraddicts really get tired of doing something, they will
spend a huge amount of time on automating this. Our idea was to create a
process, that

1.  walks users through these considerations
2.  ask them how the "team of their dreams" would look like:

    - Which channels would they need?
    - Which columns in an additional SharePoint library could support
    their work?
    - How about Microsoft lists?
    - What would they use to keep track of their tasks?

3. as a result provisions the Team for them.

We agreed on making this both open-source and enterprise-grade, which
affected all of our

## Architecture decisions

-   For our UI, we chose a Power Apps canvas app - following the design
    guidelines of the Teams UI toolkit so that our app looks and feels
    like a Teams native app.
-   As our database, we decided that Dataverse would be the best option
    to log all requests in
-   We created security roles in Dataverse to ensure that data wouldn't
    get over-exposed
-   For automation, we went with Azure Logic Apps, as this gave us not
    only a better developer experience, but would also make deployment
    easier
-   Authentication in our Logic Apps is handled by a Managed Identity

We also needed to make some hard decisions, like

### No Microsoft Planner provisioning 

As the Microsoft Planner API doesn't support application-level
permissions, we chose to not provision a Planner part with
ProvisionGenie until Planner comes up with a fully working API. This
meant, that we needed to come with an alternative for user to manage
their tasks. Optionally, we provision a Microsoft List, that mimics the
experience of Planner and introduce users to the gallery view.

### Deleting the Teams Wiki

The Teams Wiki isn't everyone's darling and we don't like it for some
reasons- but the fact why we decided to delete it as part of the
provisioning process for all channels is that, once the Wiki is
(accidentally?) removed, all content is hard-deleted.

## Making ProvisionGenie a deployable solution 

![xkcd.png](images/xkcd.png)

To make this solution available, it was not enough to only provide the
(opaque) .zip file for the canvas app. We provide

-   a Power Platform solution including
    -   1 canvas app
    -   5 Dataverse tables
    -   2 security roles
-   5 Logic Apps, ready to be deployed with ARM template files,
    including
    -   authentication handled by a Managed Identity
    -   a script to deploy the files
    -   a script to handle the Microsoft Graph permissions for the
        Managed Identity
-   proper documentation

As a result, the app looks like this:
![TeansResult.png](images/TeansResult.png)
We open-sourced ProvisionGenie 🧞 and just shipped our first release,
you can find the repository here - with guidance how to get the app and
how to contribute to
it: <https://provisiongenie.com>


We would love to get your feedback and improve our
solution!

-   [Yannick
    Reekmans](https://twitter.com/YannickReekmans "https://twitter.com/YannickReekmans"),
    for debugging, guidance, emotional support and introducing me to
    Carmen
-   [Michael
    Roth](https://twitter.com/MichaelRoth42 "https://twitter.com/MichaelRoth42") for
    all ProvisionGenie visuals :purple_heart:
-   [Lee
    Ford](https://twitter.com/lee_ford "https://twitter.com/lee_ford") for
    listening to my endless rants during debugging
