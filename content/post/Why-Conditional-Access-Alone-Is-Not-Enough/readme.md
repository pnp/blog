---
title: "Why Conditional Access Alone Is Not Enough"
date: 2026-02-08T00:00:00-00:00
author: "Josiah Opiyo"
githubname: ojopiyo
categories: ["Community post"]
images:
  - images/image.png
tags: ["Microsoft 365"]
type: "regular"
draft: false
---


# Why Conditional Access Alone Is Not Enough

## Introduction

Conditional Access (CA) has become the default answer to many Microsoft 365 security questions. Need MFA? Use CA. Want to block risky sign-ins? CA. Enforce device compliance? CA again. Over time, this has led to an uncomfortable reality in many tenants: Conditional Access is treated not as one control among many, but as the control. In evolved, multi-year tenants with legacy decisions, shifting business models, and human-driven processes, that assumption quietly introduces risk. Not because CA is weak — but because identity security fails in the gaps CA was never designed to cover.

---

## What Conditional Access Does (Operationally)

At its core, Conditional Access is a **policy evaluation engine:**
- It evaluates **signals** (user, device, location, risk)
- At **authentication or token issuance time**
- And enforces **access requirements** (MFA, compliant device, block, etc.)

Operationally, CA is:
- Reactive, not continuous
- Policy-driven, not state-aware
- Blind to intent, context outside sign-in, and most human workflows

It does not:
- Manage identity lifecycle
- Validate authorization appropriateness
- Monitor post-authentication behavior
- Detect slow, legitimate-looking misuse

Understanding this boundary is critical.

---

## Why Conditional Access Is Not Enough
1. **Identity Lifecycle Gaps Are Where Real Risk Lives**

Conditional Access assumes identities are already correct.

In real tenants:
- Users change roles without timely access review
- Leavers retain accounts longer than expected
- Guest accounts outlive their business purpose
- Service accounts accumulate permissions quietly

CA will happily enforce MFA for a user who should not exist anymore.

If your joiner/mover/leaver processes are human-driven, inconsistent, or loosely audited, CA becomes a **false sense of control** rather than a safeguard.

---

2. **Authorization Is Often the Bigger Problem Than Authentication**

Most incidents are not caused by failed authentication controls — they’re caused by over-entitled users doing legitimate things at the wrong time.

Conditional Access:
- Protects how users sign in
- Does not validate what they are allowed to do once inside

Examples seen repeatedly:
- Legacy admin roles left in place “temporarily”
- SharePoint and Teams permissions granted ad hoc and never reviewed
- App registrations with excessive Graph permissions that bypass user CA entirely

Strong authentication does not compensate for weak authorization design.

---

3. **Conditional Access Has Limited Visibility After Sign-In** 

Once a token is issued:
- CA is effectively out of the picture
- Long-lived sessions persist
- API access continues silently
- Non-interactive sign-ins bypass many controls

This is where:
- Token theft
- Consent abuse
- Background data exfiltration

actually happen.

Without **monitoring and alerting**, CA policies become static guardrails with no feedback loop.

---

4. **Human Process Failures Undermine Technical Controls**

Conditional Access policies are designed by humans, approved by humans, and modified under pressure.

Common realities:
- Emergency exclusions added and never removed
- Break-glass accounts tested once, then ignored
- “Temporary” policy exceptions that become permanent
- CA policies cloned without understanding original intent

CA does not enforce governance discipline. It reflects it.

---

## Organizational Impact of Treating CA as “Enough”

When Conditional Access is treated as the primary control, organizations tend to experience:
- **Security drift:** policies exist but no longer match risk posture
- **Operational fragility:** small changes cause wide impact
- **Audit stress:** controls are hard to explain end-to-end
- **False confidence:** leadership believes identity risk is “handled”

Conversely, when CA is positioned correctly — as one layer — it becomes an enabler rather than a liability.

---

## How M365 Engineers Should Actually Use Conditional Access
### Conditional Access should be paired with:

**Governance**
- Access reviews for users, guests, and privileged roles
- Clear ownership of app registrations and service principals
- Defined processes for exceptions and expiry

**Monitoring**
- Sign-in and audit log review with context
- Alerts for policy changes, exclusions, and risky app behavior
- Correlation with Defender and Entra ID signals

**Identity Lifecycle Controls**
- Automated joiner/mover/leaver flows
- Time-bound access where possible
- Regular validation of “who should exist” vs who does

**Human Accountability**
- Documented policy intent (not just configuration)
- Change control for identity-impacting updates
- Engineers owning outcomes, not just deployments

Conditional Access works best when:
- Its limitations are explicitly acknowledged
- Its scope is intentionally constrained
- Its outputs are continuously observed 

---


## Conclusion

Conditional Access is a powerful control — but it is not an identity strategy. In mature Microsoft 365 tenants, real risk emerges not from missing features, but from unmanaged assumptions: that identities are correct, permissions are justified, and humans always follow process. Senior M365 engineers should treat Conditional Access **as a policy enforcement layer within a broader governance and monitoring model**, not a security blanket. When designed and operated this way, CA stops being a checkbox and becomes what it was always meant to be: one dependable layer in a system that expects — and plans for — human imperfection.

---



## Additional Resources

- [Conditional Access overview](https://learn.microsoft.com/en-us/entra/identity/conditional-access/overview)  
- [Microsoft Entra ID Governance overview](https://learn.microsoft.com/en-us/entra/id-governance/identity-governance-overview)  
- [Deploying policies for access governance with Microsoft Entra](https://learn.microsoft.com/en-us/entra/id-governance/identity-governance-applications-deploy)  
- [Overview page outlining the role of Conditional Access in identity access protection.](https://www.microsoft.com/en-gb/security/business/identity-access/microsoft-entra-conditional-access)  



## Contributors 👨‍💻

[Josiah Opiyo](https://github.com/ojopiyo)

*Built with a focus on automation, governance, least privilege, and clean Microsoft 365 tenants—helping M365 admins gain visibility and reduce operational risk.*
