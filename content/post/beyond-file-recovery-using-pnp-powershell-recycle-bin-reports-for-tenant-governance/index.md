---
title: "Beyond File Recovery: Using PnP PowerShell Recycle Bin Reports for Tenant Governance"
date: 2026-06-18T00:00:00-00:00
author: "Josiah Opiyo"
githubname: ojopiyo
categories: ["Community post"]
images:
  - images/recyclebin.jpg
tags: ["Microsoft 365", "SharePoint"]
type: "regular"
draft: false
---

For a long time, I barely thought about the SharePoint Online Recycle Bin.

That's probably not unusual. Most of us spend our time dealing with active content, active users, active problems. Storage growth, external sharing, permissions sprawl, compliance requirements, migrations, lifecycle management - the list never really gets shorter.

The recycle bin sat in the background. Users deleted things. Sometimes they restored them. Eventually Microsoft removed them permanently. It seemed like one of those systems that just quietly did its job.

At least that's what I thought.

The reality hit me during a storage review for a tenant that had been around for years. It wasn't a particularly messy environment. Governance wasn't perfect, but it wasn't neglected either. We were looking at storage consumption trends and trying to understand where the growth was coming from.

What surprised me wasn't the active content.

It was the amount of storage tied up in deleted content.

Not a few gigabytes. Hundreds.

The uncomfortable part was that nobody really knew it was there. Not because the data was hidden, but because nobody was looking at it in a meaningful way.

That was probably the moment I started paying attention to the recycle bin as more than just a recovery mechanism.

What followed eventually became three reporting scripts, each answering a question I kept encountering in different tenants.

The interesting thing is that none of the questions started as governance exercises. They all started as operational problems.

The first script was the SharePoint Online Recycle Bin Capacity and Retention Report.

Originally, I just wanted visibility.

I was tired of not having an answer when someone asked how much storage was sitting inside recycle bins across the tenant.

The native tools could show me individual sites. I could investigate manually. But when you're dealing with hundreds or thousands of sites, manual inspection stops being realistic very quickly.

Once I started collecting the data across all sites, some patterns emerged.

Certain departments consistently generated far more deleted content than others.

Large migration projects would leave significant amounts of data sitting in recycle bins for months.

Sites that looked relatively small from a storage perspective suddenly appeared much larger when deleted content was included.

The report wasn't particularly complicated, but it gave me something I didn't have before: context.

I could finally see where deleted content was accumulating and, more importantly, how close that content was to being permanently removed.

That last part turned out to be more valuable than I expected.

There is a big difference between knowing a site has 50 GB in its recycle bin and knowing that 45 GB of that content is scheduled to disappear within the next few weeks.

That realization led naturally to the second script.

One thing I've learned after years of tenant administration is that storage conversations are rarely just technical discussions.

Eventually somebody wants forecasts.

Eventually somebody asks whether more storage needs to be purchased.

Eventually somebody asks why storage consumption keeps increasing.

The answer is rarely as straightforward as people expect.

I remember one review where concerns were being raised about future SharePoint storage requirements. Everyone was looking at active content growth. Everyone was projecting forward.

What nobody had looked at was how much storage was already scheduled to disappear naturally through recycle bin expiration.

When I started calculating those numbers, the conversation changed.

Not dramatically.

But enough.

The Storage Recovery Forecast Report came from that experience.

Instead of focusing on how much storage currently existed, it focused on how much storage would likely be reclaimed over time.

I found that surprisingly useful because it introduced something that's often missing in Microsoft 365 administration: predictability.

We spend a lot of time reacting.

Incidents happen.

Projects happen.

Business requirements change.

Predictability is valuable because it allows you to have better conversations before decisions are made.

Sometimes the forecast showed meaningful storage recovery over the next 30 or 60 days. Sometimes it didn't.

Either way, we were making decisions based on data rather than assumptions.

The third script came from a much more familiar situation.

Most administrators have experienced some variation of it.

A user raises a ticket.

A manager gets involved.

A project document has gone missing.

Someone remembers deleting it a few months ago.

The inevitable question follows:

"Can we still recover it?"

Sometimes the answer is yes.

Sometimes the answer is no.

The frustrating part is that by the time the question gets asked, the outcome is often already determined.

I realised I was spending too much time reacting to recovery requests and not enough time identifying content that was approaching permanent deletion.

That became the motivation behind the Recycle Bin Expiry Notification Report.

This one probably had the biggest operational impact of the three.

Not because it saved huge amounts of storage.

Not because it generated impressive dashboards.

Because it changed timing.

Instead of discovering a problem after permanent deletion, we could identify risk beforehand.

It's a subtle difference, but an important one.

I've found that many governance improvements are really timing improvements.

The information already exists.

The challenge is getting it to the right people before it becomes irrelevant.

Once site owners started receiving information about content nearing expiry, some interesting things happened.

Most ignored it.

That's reality.

But some didn't.

And those few cases often involved exactly the kind of content that would have generated high-priority recovery requests later.

Avoiding even a handful of those situations justified the effort.

Looking back, the biggest lesson wasn't about recycle bins.

It was about visibility.

Microsoft 365 contains a huge amount of operational data. The challenge isn't usually collecting it. The challenge is turning it into information that influences decisions.

Before these reports existed, recycle bins were largely invisible in the environments I managed.

Afterwards, they became part of regular conversations.

Storage discussions became more accurate.

Recovery risks became easier to identify.

Site owners became more aware of content lifecycle responsibilities.

None of this happened because of the scripts themselves.

The scripts simply exposed information that had always been there.

That's something I've come to appreciate over the years. Good governance rarely starts with enforcement. It starts with visibility.

When administrators can see what's happening, they make better decisions.

When site owners can see what's happening, they take more ownership.

When leadership can see what's happening, conversations become more grounded in reality.

The recycle bin isn't the most exciting part of SharePoint Online. It's certainly not the feature most people think about when discussing governance.

But some of the most valuable operational insights I've found in recent years have come from understanding what happens after content is deleted rather than before.

And that's probably the lesson that stayed with me.

In mature Microsoft 365 environments, the biggest risks aren't always hidden in complex security configurations or advanced compliance settings.

Sometimes they're sitting quietly in places everyone assumes are taking care of themselves.
