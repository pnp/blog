---
title: What You Need to Know - Microsoft 365 Developer Program Changes in 2024

# Add a summary to convince readers to read your article (recommended). It will display on the homepage.
summary: Understand the recent changes in the Microsoft 365 Developer Program, why they were made, and when you can get a free M365 developer/sandbox tenants again.
date: 2024-05-23T11:20:19-04:00

# Author. Your own name
author: "Andrew Connell"

# GitHub username.
githubname: "andrewconnell"

# Featured image
# To use, add an image named `thumbnail.jpg/png` to your page's images folder. Make sure to replace the placeholder image
images:
- images/feature.png

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
# Community posts should always use "Community post" as the categories
tags: ["Microsoft 365 Developer Program","Microsoft 365 "]
categories: ["Community post"]
canonicalURL: https://www.voitanos.io/blog/microsoft-365-developer-program-status-summer-2024/
---
> This article originally appeared on Andrew Connell's site, **[What You Need to Know - Microsoft 365 Developer Program Changes in 2024](https://www.voitanos.io/blog/microsoft-365-developer-program-status-summer-2024/?utm_medium=website&utm_source=pnpblog&utm_campaign=blog&utm_content=What%20You%20Need%20to%20Know%20-%20Microsoft%20365%20Developer%20Program%20Changes%20in%202024)**.

Lately, I've been receiving numerous inquiries from my students and other Microsoft 365 developers regarding how to access the free Microsoft 365 developer tenants referenced in various Microsoft Learning modules, Microsoft's documentation, and my classes. Since its inception, the Microsoft 365 Developer Program and these free developer tenants have been the preferred method for learning and developing custom solutions. They provide an excellent starting point for developers to build and test Microsoft 365 solutions.

However, changes have occurred within the Microsoft 365 Developer Program in recent months. It's been challenging to get a comprehensive understanding of what transpired, what has changed, the current status of the program and the developer tenants, and what to anticipate in the future.

This article aims to clarify these points.

Let's begin with a recap.

## Recap: Microsoft 365 Developer Program and Free M365 Developer Tenants

The Microsoft 365 Developer Program launched in November 2020, and by March 2021, it began offering developers a free Microsoft 365 tenant. This developer tenant was also referred to as a *sandbox subscription*. The tenant included sample data and multiple user licenses for developers to create and test solutions for Microsoft 365.

Provided the tenants were used for development purposes and not misused, Microsoft would renew them annually. Since their introduction, I've advised all my students to join the developer program and create a developer tenant to use as a hosted development environment for testing their Microsoft 365 solutions.

This is a great option for learning and testing as it's free and identical to a commercial Microsoft 365 tenant. There's no difference between a developer tenant and a commercial one, except that developer tenants are free, expire after a year, and are monitored to ensure they're used for development. If they are, they're automatically renewed. If not, they expire after a certain period.

However, things changed earlier this year. In January, Microsoft abruptly ceased creating developer tenants for users, which led to a surge of errors and considerable confusion. Developer started to see the following error when they tried to create a new developer tenant: ***You don't current qualify for a Microsoft 365 Developer Program sandbox subscription.***

So… what happened?

## Current state of Microsoft 365 developer tenants

In February, [Microsoft updated a blog post from late January that explained the change](https://devblogs.microsoft.com/microsoft365dev/stay-ahead-of-the-game-with-the-latest-updates-to-the-microsoft-365-developer-program/), but did not provide any specifics. All they said was:

> **February 2024 Update:** At this time, we are limiting access to the Microsoft 365 developer subscription to developers and/or organizations with active subscriptions to Visual Studio Enterprise.
>
> - [Blog: Stay ahead of the game with the latest updates to the Microsoft 365 Developer Program](https://devblogs.microsoft.com/microsoft365dev/stay-ahead-of-the-game-with-the-latest-updates-to-the-microsoft-365-developer-program/)

In the next section, I'll explain why they took this action, but essentially, they needed to secure their systems temporarily while they strengthened them.

As a result, you couldn't create a Microsoft 365 developer tenant (sandbox) through the Microsoft 365 Developer Program. This started in January of 2024.

**But why?**

## Validate the identity of Microsoft 365 Developer Program customers

Before 2024, all you needed to sign up for the Microsoft 365 Developer Program was an email address. This could be quickly created using Gmail, Outlook.com, or any other service.

**The issue with this approach was that it didn't validate the identity of the person signing up.**

Consider this – anyone (*or even some nefarious organization*) could create numerous bogus emails, sign up for the Microsoft 365 Developer Program, obtain a sandbox tenant, and send out millions of emails. These were real tenants, and even if Microsoft detected this activity, they couldn't identify the responsible party.

Microsoft needed to ensure they could validate the identity of every person receiving one of these tenants.

> **How does Azure handle this?**
> Microsoft Azure provides developers with $200 in credits to create resources and test out Microsoft Azure. However, they control fraud and misuse by requiring a credit card from the user as proof of identity.
>
> This prevents malicious organizations from setting up numerous Azure subscriptions to run VMs for crypto mining or to establish a bot farm for potential DDOS attacks.

### Identity Validation in the Microsoft 365 Developer Program

The Microsoft 365 Developer Program required a method to validate the identities of users signing up for the program. There are both short-term and long-term solutions for this issue.

Currently, the short-term solution provides several ways to obtain a Microsoft 365 developer/sandbox tenant.

**Option 1:** As previously mentioned, you can get a tenant if you have an active [Visual Studio Enterprise subscription](https://visualstudio.microsoft.com/subscriptions/).

**Option 2:** You can participate in one of the [Microsoft AI Cloud Partner Programs](https://partner.microsoft.com/). Contact your Microsoft partner to be added to an allow list to receive these developer subscriptions. This includes the following groups:

- ISV Success Program
- Solutions Partner Program
- Specialization Experts
- Managed Partners
- Premier or Unified Support Plan members

**Option 3:** Another way to get a tenant is by purchasing a license, such as an E3 license or a business premium license. You can then use this Microsoft 365 tenant for your development purposes.

Why did Microsoft take this action?

## What Happened - Locking down developer tenants

Although Microsoft hasn't explicitly stated the reason for the strict measures implemented in January, the timing seems more than coincidental. It's almost certain that this was in response to the swift adoption and deployment of Microsoft's **[Zero Trust](https://learn.microsoft.com/security/zero-trust/zero-trust-overview)** policy, which was a countermeasure to the company being compromised during the Midnight Blizzard attack.

> **Microsoft & Midnight Blizzard**
> Learn more about Midnight Blizzard, the Russian state-sponsored actor known as Nobelium from these Microsoft Security Response Center articles:
>
> - [Microsoft Actions Following Attack by Nation State Actor Midnight Blizzard](https://msrc.microsoft.com/blog/2024/01/microsoft-actions-following-attack-by-nation-state-actor-midnight-blizzard/) - January 19, 2024
> - [Update on Microsoft Actions Following Attack by Nation State Actor Midnight Blizzard](https://msrc.microsoft.com/blog/2024/03/update-on-microsoft-actions-following-attack-by-nation-state-actor-midnight-blizzard/) - March 8, 2024

So what does this imply for the future?

## Going forward - What you can expect

Microsoft fully acknowledges the issue and its impact on customers, particularly those who are new students and developers testing solutions on Microsoft 365.

The company recently stated that a solution is in the works, with an estimated implementation time of September 2024. Until then, options for obtaining a free developer account are limited. I’ve outlined the three (3) options in this article.

Yeah, it stinks… and I understand how customers are impacted & get why they’re complaining.

But do keep in mind, that for the most part, the cost of the tools we use to create solutions for Microsoft 365 are very affordable, or near free. Other than a computer an an internet connection, you can build SharePoint Framework (SPFx) solutions, Microsoft Teams apps, and so much for nothing.

I’m not dismissing the impact this change is having, but I do want to keep it in perspective. A [single Microsoft 365 Business Basic license is $72 USD/year](https://www.microsoft.com/microsoft-365/business/compare-all-microsoft-365-business-products) ($6/mo/user with an annual commitment) while [Microsoft 365 Business Premium license is $264 USD/year](https://www.microsoft.com/microsoft-365/business/compare-all-microsoft-365-business-products) ($22/mo/user with an annual commitment).

But I sure am looking forward to those sandbox tenants coming back!
