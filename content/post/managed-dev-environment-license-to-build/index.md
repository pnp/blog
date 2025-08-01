---
title: "Managed DEV Environment Bottleneck: License to Build"
date: 2025-07-30T08:00:00+02:00
author: "Jakub Bajla"
githubname: JakubBJL
categories: ["Community post"]
tags: [Power Platform, Power Apps, Power Automate, Microsoft 365, Governance, ALM, Managed Environments]
type: "regular"
---

## Quick Overview or TL;DR
We built a governance model for onboarding new Power Platform makers using Managed Environments. By leveraging environment group and environment routing features, we ensured that new makers are automatically directed away from the Default environment and into their own personal, developer-type Managed Environments. The solution detects when a trial license is silently provisioned, informs the maker with clear guidance, and keeps admins in the loop with reminders and escalation logic.

---

## Introduction & Context
Managed Environments offer advanced governance capabilities for Power Platform, but they require premium licenses. When onboarding new makers, especially in large organizations, this licensing requirement can become a bottleneck.

It's important to note that “premium” in this context doesn’t mean only Power Apps Premium (Power Apps per user plan) — it also includes trial licenses, and in some cases, even Per-App entitlements. This piece of information is at the core of both the challenge and the solution.

To streamline onboarding while maintaining governance, we leveraged environment routing, developer environments, and Power Automate to create a scalable, automated solution that ensures compliance and supports makers throughout their journey.

---

## Problem & Requirements
When a new maker starts building in Power Platform, environment routing sends them to a personal developer environment. This routing is triggered the first time the user accesses https://make.powerapps.com. If the environment already exists, routing simply redirects them there. If it has been deleted, a new developer environment is provisioned automatically.

This routing mechanism is part of the environment group feature and is designed to keep makers away from the Default environment — a space that often lacks governance, visibility, and control. But this use case goes beyond just isolation. It’s about creating a more advanced and streamlined experience for admins and makers alike. For admins, it brings visibility into who is building, when, and under what license. For makers, it ensures their work is protected and that timely support can be provided. It also aligns with Microsoft’s product direction, as recent release waves have introduced more capabilities exclusive to Managed Environments.

Access to build or edit within a Managed Environment requires premium license rights. These rights can come from:
- A Power Apps Premium (Power Apps per user plan) license already assigned to the user.
- A Per-App pass granted when the user is given access to an app they want to edit.

If none of these apply, and the user has never had a Power Apps trial before, a trial license is automatically provisioned in the background (unless your organization has specifically disabled trial provisioning via Power Platform admin settings). This silent provisioning is what enables the Managed Environment to function - but it also introduces a governance blind spot.

We want unaware makers away from Default, but routing only works with environment groups - and the full benefits of automatic personal dev environment creation and isolation are only available when using Managed Environments. While environment routing can be configured for non-managed environments, the advanced features described here require Managed Environments.

This raises several challenges:
- Admins have no visibility into trial provisioning.
- Makers may be unaware of licensing implications.
- Governance teams need assurance that work won’t be lost.
- Licensing must be upgraded if the maker’s solution is accepted for production.

We needed a solution that:
- Detects when a trial is provisioned.
- Notifies the maker with clear, comforting guidance.
- Keeps admins informed and prompts follow-up actions.
- Supports ALM and solution promotion workflows.

---

## Solution Architecture

### Environment Routing
- Environment group is configured with routing enabled.
- New makers are automatically routed away from the Default environment and into personal developer-type Managed Environments.

This architecture assumes that your organization has implemented a basic “maker experience” — a set of onboarding practices that help new makers understand where they’ve landed and what to do next. This typically includes enabling the **Maker Welcome Message** feature, which appears when a new environment is provisioned. That message can link to training materials, explain the purpose of the environment, and point to internal support channels or documentation. For example, you might link to a SharePoint site or Azure DevOps wiki that outlines how to request promotion of a solution from an individual dev environment to a shared dev environment — such as the Solution Promotion Guide used in our organization. This is all part of a broader journey: enabling makers, supporting their growth, and helping them move from ideas to production-ready apps.

For more technical details on environment groups and routing, see Microsoft’s official documentation:  
- [Managed Environments overview](https://learn.microsoft.com/power-platform/admin/managed-environments-overview)  
- [Environment groups and routing](https://learn.microsoft.com/power-platform/admin/environment-groups)

### Trial Detection
- Environment creation is logged in Microsoft Purview (or in the unified audit log, if enabled). Ensure that Purview or unified audit logging is enabled and that log retention meets your organization's needs for robust monitoring and tracking.
- **Note:** There is no direct audit log for license provisioning events. Our solution infers trial provisioning by monitoring related activities, such as environment creation and license assignment through associated audit events.  
- Trial provisioning is inferred using audit events such as `EnvironmentCreated` or `PowerPlatformEnvironmentProvisioned`, which indicate when a new environment is created.
- A Power Automate flow monitors these logs and identifies the environment creator/owner.
- The flow uses Microsoft Graph API to check the creator’s assigned licenses. Note: This requires the flow to have appropriate permissions (such as Directory.Read.All) in Entra ID, and these should be granted securely with admin consent and proper credential management for production scenarios.
- The flow queries the `/users/{id}/licenseDetails` endpoint to retrieve assigned SKUs. This includes trial SKUs such as `POWERAPPS_P2_VIRAL`, if visible based on tenant settings.
- If the user does not have a premium or Dynamics 365 license, but holds a trial SKU (e.g., POWERAPPS_P2_VIRAL), the flow infers that a trial was provisioned.
- The user is then notified via email with onboarding or governance guidance (next step).

For more on trial license provisioning and monitoring, refer to Microsoft Docs:  
- [Power Platform licensing FAQ](https://learn.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq)  
- [Official Power Platform Licensing Guide (PDF)](https://go.microsoft.com/fwlink/?linkid=2223452)  
- [Auditing in Power Platform](https://learn.microsoft.com/power-platform/admin/auditing-power-platform)

> **Best Practice:**  
> When using Microsoft Graph API in Power Automate flows, grant permissions via a secure Azure AD application and follow your organization’s credential management standards. Regularly review permissions and API usage for compliance.

### Maker Notification
- The flow sends a personalized email to the maker explaining:
  - Why the trial was provisioned.
  - What Managed Environments are.
  - What happens when the trial expires.
  - How their work will be preserved.
  - How to submit their solution for promotion.
  - Who will help them and where to find guidance.

### Admin Notification & Reminder
- The flow also notifies Power Platform admins that a trial-based environment was created.
- It schedules reminders at 20 and 25 days after the initial notification to prompt license review or escalation.

---

## Maker Email Template

Subject: Welcome to Your Power Platform Developer Environment

Hi [Maker Name],

Welcome to Power Platform! A personal development environment has been created for you so you can start building apps and automations.

To enable this, a free trial license was automatically activated for you. This trial is only used to give you access to a Managed Environment — a workspace with advanced features like enhanced security, monitoring, and support.

✅ What you should know:
- You can start building right away — no action needed.
- Your work is safe. Even if the trial expires, you won’t lose anything.
- When your trial expires, you will lose access to Managed Environment features and any premium capabilities (such as premium connectors or Dataverse) unless you have another valid premium license (Power Apps Premium (Power Apps per user plan), Per-App, or Pay-As-You-Go). Your work remains stored and accessible. You can continue building in a standard (unmanaged) development environment, but premium features will only be available if your license supports them.

📚 Getting Started  
You may have already seen a welcome message in your environment — this is part of our Maker Onboarding Experience. It includes links to training materials, development guidelines, and support contacts. If you missed it, you can access the same resources here:  
👉 [Insert link to Maker Onboarding Portal or SharePoint site]

🚀 What happens if your idea gets approved?  
If your prototype is submitted and selected for further development:
- Your solution will be moved to a team development environment that flows through our deployment pipeline to production.
- You’ll be given a full license so you can continue working in Managed Environments without limitations.
- Please note: Moving solutions between environments may require admin or elevated permissions, so this process is not always fully self-service for makers.

📌 What if your idea isn’t meant for production?  
If your current project is exploratory or not intended for production, you can request a standard (unmanaged) development environment instead. Just reach out to your Power Platform admin or team sponsor.

📈 Want help getting your solution ready for production?  
You can review the full process for promoting your solution here:  
👉 [Insert link to Solution Promotion Guide on SharePoint or Azure DevOps]  
And if you’d like advisory support with your development efforts — from architecture to ALM — feel free to contact us directly.

If you have any questions, we’re here to help.

Happy building,  
[Your Team or Admin Name]

---

## Admin Notification & Reminder Flow

### Flow: Trial Detection & Notification

Trigger:
- Scheduled or Purview-based detection of new environment creation.

Steps:
1. Get environment metadata and owner.
2. Check owner’s license type via Power Platform Admin APIs.
3. If no premium or Dynamics 365 license:
   a. Send email to maker (template above).
   b. Notify Power Platform admins.
   c. Schedule reminders at +20 and +25 days.

### Flow: Admin Reminder Logic

Trigger:
- Scheduled flow triggered 20 and 25 days after initial notification.

Steps:
1. Lookup environment and maker.
2. Check if license has been upgraded.
3. If not:
   a. Send reminder to Power Platform admins.
   b. Optionally escalate to licensing or governance team.

These notifications and reminders serve a strategic purpose. Within 3–4 weeks of a maker starting their journey, it should become clear whether their work is exploratory and better suited for an unmanaged development environment, or whether it shows potential business value. In the latter case, the maker can be invited into a team-managed development environment — one that already has licensing investments in place, whether through Power Apps Premium (Power Apps per user plan), Per-App passes, or Pay-As-You-Go. This transition not only empowers the maker but also aligns their efforts with the organization’s ALM pipeline and ROI goals.

---

## Result
We achieved:
- Seamless onboarding for new makers.
- Transparent communication about licensing.
- Automated governance and admin visibility.
- Support for ALM and solution promotion.

This solution ensures that licensing constraints don’t block innovation, while maintaining control and compliance across the platform.

---

## Final Thoughts
By combining environment routing, audit logs, and Power Automate, we created a scalable governance model that supports makers and admins alike.

Thanks for reading. If you’re building similar onboarding flows or facing licensing challenges, I’d love to hear how you’re approaching it — feel free to connect, share your story, or ask questions. We’re all learning together.

---
