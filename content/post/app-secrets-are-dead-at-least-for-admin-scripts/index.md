---
title: "App Secrets Are Dead—At Least for Admin Scripts"
date: 2026-04-28T00:20:00-01:00
author: "Hagen Deike"
githubname: samurai-ka
# don't change
categories: ["Community post"]
# link to the thumbnail image for the post
images:
- images/thumbnail.png
# don't change
tags: []
# don't change
type: "regular"
---

Why I protect admin scripts more deliberately than everyday automation—and why
hardware-bound certificates feel like the consistent next step.

## Possession as the Missing Factor

For years, most of my Microsoft 365 admin scripts authenticated in a
knowledge-based way. A secret sat in a vault. The script proved it “knew” the
value. That was convenient, and it avoided using a human admin account for
automation.

Interactive admin sign-ins have gone the other way. They increasingly require
proof beyond a password: a compliant device, a stronger authenticator, and a
session that is harder to reuse elsewhere. The message is simple: privileged
work should not rely on knowledge alone.

My change in thinking did not come from one event. It came from noticing a gap.
Many admin scripts can change tenant settings, permissions, and
compliance-relevant data at scale. In effect, they act like a privileged identity.
And honestly: who has not stored a login password as a SecureString at least once?
If I would not protect an admin account with “password only”, why would I accept
the script equivalent?

