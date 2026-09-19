---
title: "The Last Mile of SharePoint Classic: Why the Real Risk Isn't Technical"
date: 2026-09-12T00:00:00-00:00
author: "Josiah Opiyo"
githubname: ojopiyo
categories: ["Community post"]
images:
  - images/cover.png
tags: ["Microsoft 365", "SharePoint"]
type: "regular"
draft: false
---

For years, SharePoint modernization has felt like one of those background projects organisations know they should tackle but rarely prioritise. Classic pages still load, alerts still fire, and older add-ins still behave well enough that nobody wants to disturb them. But Microsoft's retirement timelines have changed the tone. This isn't a theoretical "someday" problem anymore. It's a calendar-driven shift with real consequences for HR onboarding, finance workflows, operations approvals, and intranet experiences that quietly depend on classic components.

What caught my attention recently is how many organisations don't realise they're carrying these dependencies. Classic SharePoint isn't always obvious. It hides inside a Script Editor web part someone added eight years ago, an ACS-based integration nobody has touched since the migration to Microsoft 365, or an alert a department relies on because "that's how we've always done it." When Microsoft retires these components, the impact won't show up as a neat error message. It will show up as broken processes, missing notifications, and governance gaps that surface at the worst possible moment.

## When Legacy Becomes a Business Risk

The retirement of SharePoint Alerts is a good example. Microsoft has already published milestones that block new alerts and eventually retire the feature entirely. For teams that still rely on alerts for approvals, document changes, or onboarding steps, this isn't a cosmetic change. It's a workflow disruption. The same applies to SharePoint Add-Ins and the legacy ACS authentication model. If your organisation still uses provider-hosted add-ins or older app-only access patterns, those dependencies will eventually fail unless they're remediated.

The deeper issue is that classic SharePoint often underpins business-critical processes. HR policy sites, finance document workflows, operations forms, department portals, and project sites all carry classic-era patterns that were never modernised. When they break, the business feels it first-missing notifications, pages that don't render, failed automation, or security workarounds that create audit headaches later. Modern Microsoft 365 governance also assumes modern patterns. Purview's auditing, retention, eDiscovery, and policy-based controls work best when the underlying environment isn't anchored in legacy components.

## How Organisations End Up Here

Most organisations didn't choose to stay on classic SharePoint. They arrived here gradually. Migrations were scoped to "lift and shift," not "lift and modernise." Custom scripts were left untouched because they still worked. Add-ins were considered too risky to replace. Alerts were "good enough." Over time, these decisions created a quiet dependency chain that only becomes visible when Microsoft announces retirement dates.

The trade-off was convenience: keep things running now, deal with modernization later. The cost is that "later" has arrived.

## A Practical Path Forward

The most useful lesson I've learned is that modernization isn't about converting everything. It's about reducing risk intentionally. A focused dependency inventory is the single most valuable step. Identify classic pages, templates, alerts, scripts, add-ins, ACS dependencies, and legacy workflows. Prioritise by business criticality, not site count. Many organisations discover entire site collections that can be retired instead of migrated.

From there, decide what gets transformed versus rebuilt. Straightforward classic pages can often be modernised in place. Anything tied to complex workflows, branding, or compliance usually needs a rebuild. Modernization is also the right moment to reset governance-information architecture, lifecycle management, audit readiness, and access models. This is where Microsoft Purview becomes the missing layer that turns modernization into actual risk reduction.

Alerts deserve special attention. Replacing them isn't a technical task; it's a workflow conversation. What events matter? Who needs to know? What's the escalation path? Modern notification patterns-rules, Power Automate, or other governed approaches-are more reliable and auditable.

## The People Who Need to Be in the Room

Modernization fails when it's treated as an IT-only project. Platform owners, architects, SharePoint engineers, security and compliance teams, HR, finance, operations leaders, power users, and change management all play a role. The people closest to the process often know where the real dependencies live.

## Resources

- **[https://learn.microsoft.com/en-us/sharepoint/classic-user-created-page-deprecation](https://learn.microsoft.com/en-us/sharepoint/classic-user-created-page-deprecation)**
- **[https://learn.microsoft.com/en-us/sharepoint/dev/transform/modernize-classic-sites](https://learn.microsoft.com/en-us/sharepoint/dev/transform/modernize-classic-sites)**
- **[https://learn.microsoft.com/en-us/sharepoint/dev/transform/modernize-userinterface-site-pages](https://learn.microsoft.com/en-us/sharepoint/dev/transform/modernize-userinterface-site-pages)**
- **[https://learn.microsoft.com/en-us/sharepoint/dev/transform/modernize-userinterface-site-pages-powershell](https://learn.microsoft.com/en-us/sharepoint/dev/transform/modernize-userinterface-site-pages-powershell)**

## Community Discussion

The next phase of retirement will push more organisations to confront classic dependencies. The question worth exploring is how to modernise without simply recreating old patterns in new tools. 

- What approaches have worked for your organisation?
- Where are you finding hidden dependencies?
