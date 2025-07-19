---
title: "Per-App-as-You-Go"
date: 2025-07-14T08:00:00+02:00
author: "Jakub Bajla"
githubname: JakubBJL
categories: ["Community post"]
tags: [Power Platform, Power Apps, Power Automate, Microsoft 365, Microsoft Entra ID, Governance, ALM]
type: "regular"
---

## Quick Overview or TL;DR

We built a licensing model for a nonprofit’s Power App that mimicked Pay-As-You-Go behavior using Per-App licenses, Power Automate, and security groups.

---

## Introduction & context

Licensing is often overlooked when designing Power Platform solutions, especially in environments with mature governance or existing premium entitlements. However, when building your first enterprise-grade app in a cost-conscious organization, licensing becomes a core architectural consideration.

In our case, we worked with a nonprofit deploying their first enterprise-grade Power Platform solution. One role in the app was designed to be tenant-wide — available to everyone, but only used by a small subset of users, and only occasionally (sometimes never). This surfaced licensing as a design constraint, not just a budget item.

The challenge: how to accommodate a large, undefined user base without overcommitting licenses or compromising governance. The licensing model would directly influence how we structured environments, provisioned access, and automated onboarding and offboarding processes.

---

## About Licensing Sources

Microsoft provides two primary resources for evaluating Power Platform licensing models:

- **Power Platform Licensing Guide**: A downloadable PDF that outlines license entitlements, supported scenarios, and use rights across all Power Platform products.
- **Microsoft Learn documentation**: Continuously updated technical guidance covering licensing behavior, environment configuration, and governance considerations.

Both are essential when validating assumptions, designing access models, or aligning architecture with licensing constraints.

---

## Problem & Requirements


We needed a model that provided elastic access for a large, mostly inactive user base, with license assignment based on actual usage—not eligibility. Integration with identity-based access control and automated license recovery were key requirements, all while aligning with Enterprise Agreement cost structures.

Static license assignment would either overcommit resources or require manual intervention to manage consumption, which was not sustainable for our scenario.

---

## Alternatives

### Pay-As-You-Go (PAYG)

PAYG is billed through Azure and charges only when a user launches the app. It is ideal when you do not know how many users you will have or how often they will use the app. It is flexible, usage-based, and does not require upfront license commitments.

The PAYG model is defined as a measure of the number of unique, active users who open a single PAYG-enabled app in an environment one or more times in a month. This makes it attractive for scenarios with unpredictable or infrequent usage.

But here is the catch. My customer had an Enterprise Agreement (EA), which meant negotiated rates were in play. Under an EA, discounts are typically tied to projected license revenue, primarily Microsoft 365 or Business Applications, and are often approved based on committed project plans. Azure consumption, on the other hand, falls under a different revenue category. It usually requires a separate commitment and sometimes even a separate contractual motion.

In practice, this means that PAYG licenses, billed through Azure, are discounted through a different channel than Per-App or Premium licenses. And that distinction matters. It is not just accounting, it is strategic. The two motions are treated differently by Microsoft’s internal teams, and the incentives do not always align with what is best for the Power Platform project or the customer.

In our case, the Business Applications bucket received a significantly higher discount than Azure. Specifically, our discount for Business Applications licenses was nearly four times greater than what we received for Azure consumption. And when you factor in that PAYG is already roughly twice the cost of Per-App at list price, the economics became clear: Per-App licensing was substantially more cost-effective, even if PAYG offered more flexibility.

So while PAYG may seem more flexible on paper, the licensing motion behind it can make it less favorable in EA-governed environments. Sometimes, especially in early-stage projects or initial business value assessments, even these nuances can have a significant impact, and they need to be factored in when building on the platform.

### Per-App Licensing

Per-App licenses are assigned to an environment, not directly to users. Once a user is granted access to any app in that environment, either by being shared the app or added to a security group, **they consume a Per-App license for each app they are assigned to**. If a user is given access to multiple apps, **each app assignment consumes a Per-App license**—this is the "stacking" behavior.

Key behaviors:
- Licenses are consumed as soon as access is granted, regardless of whether the app is used.
- Licenses do not return to the pool unless access is explicitly revoked.
- If a user is assigned to multiple apps in the same environment, they will consume multiple Per-App licenses (one per app).

This stacking behavior is intentional. It is a bridge between PAYG and Premium licenses. At $5 per app, once a user stacks four licenses, it makes sense to upgrade them to a $20 Premium license. The Premium license allows users to run unlimited apps and access unlimited Power Pages websites, which becomes cost-effective in broader usage scenarios.

But for our use case, occasional users in a cost-conscious organization, this model was a bit too sticky unless we automated governance and access revocation.


---

## Reality Check: The Hidden Risk of Over-Assignment

Considering all of the above means that if we added our entire tenant to a security group tied to the app environment (group created to be tied to that one particular role), every member of that group will start consuming a license, even if they never open the app. The system does not wait for usage, it assigns licenses based on access.

So in theory, if your tenant has 2,000 users and you only have 500 Per-App licenses, only the first 500 users in the group (based on internal ordering) will get licenses. The rest will be blocked from access unless more licenses are added. This behavior is subtle but important, and it is why governance matters.

That's why, when considering Per-App licenses, it's crucial to think about all access considerations. This ensures your license pool is used efficiently and avoids silent license exhaustion.

---

## Our Decision

While the previous section highlighted the risks of Per-App licensing—particularly how licenses are consumed upon access rather than usage, from an architectural standpoint, Per-App licensing also gave us the flexibility to build a governance model that directly addressed those risks.

By automating access provisioning and revocation, we could ensure that licenses were only consumed when truly needed and returned to the pool promptly. This allowed us to neutralize the “stickiness” of Per-App behavior and turn it into a scalable, cost-efficient solution.

Moreover, the lower cost of Per-App licenses under our EA meant we could engage more users within the same budget. For a first enterprise-grade app, this was critical. It allowed us to demonstrate business value early, reach a broader audience, and lay the foundation for future apps—all without overcommitting on licensing.

We ruled out Access Packages (via myaccess.microsoft.com) because they require either Azure AD Premium P2 licenses or the Microsoft Entra ID Governance add-on for every user who might request access. Both options come at an additional cost, which wasn’t feasible for our tenant-wide audience. That said, if your organization already has P2 via M365 E5 or has invested in the Governance add-on, Access Packages might be a viable option.

In summary, we chose Per-App licensing because:
- It was significantly cheaper under our circumstances compared to PAYG
- We could control access through security groups
- We could build a governance layer to simulate PAYG-like behavior

---

## Implementation: Automated Governance

To address the licensing behavior of Per-App licenses—where access, not usage, consumes a license—we built a lightweight governance model using Power Automate. The goal was to ensure that licenses are only consumed when needed and automatically released when no longer required.

For this particular end-user group—occasional users with tenant-wide eligibility but low-frequency access—we designed a tailored onboarding experience. Their journey begins with a Microsoft Form embedded directly into the process documentation. This form acts as the official entry point for requesting access to the app. Once submitted, the request is handled by a Power Automate flow that governs access provisioning. The flow can be fully automated or include an approval step, depending on the organization’s governance preferences.

### Step 1: Request Access via Microsoft Form

Users initiate access by submitting a Microsoft Form. This form is tailored to their role and embedded in the documentation they already use, making it easy to find and understand.

#### Why this matters:
- It provides a documented, auditable entry point for access.
- It aligns with business-led app adoption, where users may not be familiar with IT processes.
- It ensures that only eligible users trigger license consumption.

#### Flow Logic:
1. **Trigger**: When a new response is submitted in Microsoft Forms.
2. **Validation**: The flow checks if the responder’s email ends with the organization’s domain (e.g., `@contoso.com`). If not, the request is rejected with a friendly message.
3. **Access Provisioning**: If valid, the user is added to a security group tied to the app environment. This grants access and consumes a Per-App license.
4. **Notifications**: Confirmation is sent to the user, and the system admin is notified for visibility.

### Step 2: Revoke Access Automatically

To avoid license waste, we implemented automated offboarding using two strategies:

- **Time-Based Expiry**: A scheduled flow runs on a fixed cadence (e.g., monthly) and removes all users from the relevant security group. This is ideal when the business process has a predictable duration.
- **Process Completion-Based Removal**: For more dynamic scenarios, access is revoked as soon as the user completes their task. This is triggered by business logic—for example, when a submission is marked complete in Dataverse or SharePoint.

Both approaches ensure that licenses are recycled efficiently, supporting a sustainable and scalable licensing model.

---
## Result

We achieved:
- Cost savings by avoiding PAYG and Access Packages
- License recycling through automated access management
- Scalable governance without premium add-ons

The solution is simple, transparent, and works well for occasional access scenarios, especially in organizations where every dollar counts.

If you want to see or try the actual Power Automate flows described in this blog, check out the repository here:  
[JakubBJL/per-app-as-you-go on GitHub](https://github.com/JakubBJL/per-app-as-you-go/tree/main)

---

## Final Thoughts

If you’re building your first enterprise app in Power Platform, don’t treat licensing as an afterthought. It’s not just a cost—it’s a constraint, a design factor, and sometimes a creative challenge.

Thanks for reading. If you’re facing a similar licensing puzzle, feel free to connect. I’m Jakub, still learning, still experimenting, and always happy to share what’s worked (and what hasn’t).

Special thanks to **Yannick**, who assured me of the basics when I started figuring this out (and replied to my message at 1:30 AM!), and to **Zilong**, my talented padawan, who brings my design ideas and architectures to life.

## Resources & Further Reading

- [Per-App Licensing Governance Flows Repository](https://github.com/JakubBJL/per-app-as-you-go/tree/main)  
  (Contains Power Automate flows, setup instructions, and more context)
- [Power Platform Licensing Guide (PDF)](https://go.microsoft.com/fwlink/?linkid=2085130)
- [Microsoft Learn documentation](https://learn.microsoft.com/power-platform/admin/power-platform-licensing)

