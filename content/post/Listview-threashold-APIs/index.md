---
title: "Dealing with the 5k item limit in SharePoint APIs"
author: "Dan Toft"
githubname: Tanddant
date: 2023-04-11T17:25:17.737Z
# don't change
categories: ["Community post"]
# link to the thumbnail image for the post
images:
- images/thumbnail.webp
# don't change
tags: ["SharePoint"]
# don't change
type: "regular"
canonicalUrl: https://blog.dan-toft.dk/2023/04/dealing-5k-item-limit-sharepoint-apis/
---


Before we even get started talking about the list view threshold, let's make one thing *VERY* clear!

> Microsoft lists is **not** a relational database!

Now that we've got that out of the way this post will summarize my experiences working with large lists, some with upwards of 500k elements, without folders, it's more than possible - is it a good idea? - let's have a look.

## What is the list view threshold, and why it's there

If you've worked with SharePoint as a dev for some time, you've eventually run into the issue of ["The number of items in this list exceeds the list view threshold"](https://learn.microsoft.com/en-us/sharepoint/troubleshoot/lists-and-libraries/items-exceeds-list-view-threshold), Microsoft has a few tips on it, the main one being "use modern" - well that doesn't help you when you're using the APIs, not even via Graph API, so what do you do?

Firstly, I want to address why it's there, I've seen a lot of people saying Microsoft should just remove the limit, you could do that on-premise, but I genuinely disagree with this stance, it's there for performance reasons, but also as a dev you should really stop and think "am I doing something wrong here" anytime you're fetching 5000 rows at once from a SharePoint list.

So the limit is there to save the system from performance degradation, but also limit just how slow a query you're doing can get, not just to prevent timeouts, but also to prevent a bad user experience.

Now If you're getting the message there are a few things you can do to get around the issue, let's have a look at those:

## Filtering

Firstly, the most simple thing to do, and something you should always be doing, is to make sure that you're filtering the dataset to limit how much data you're fetching, using the REST APIs you can do this with OData filters, or [CAML](/blog/post/caml-query-what-is-it/), both have the same limits in terms of the 5000 items, so really just go for whichever one you're most comfortable with.

### The filtering order matters! 

Now something that took me longer then I would like to admit to wrap my head around is that the order in which you write your filter actually matters, coming from an SQL background, I'm sure the same applies there, but you don't notice it in the same way since there aren't the same limits.

Now due to the nature of how this limit is applied, no specific part of your query can result in a result set of 5.000 items, this means choosing the order of your filters can have a huge impact.

Looking at the [contacts list](#sample-data---contacts-list) at the bottom of this page, let's say I want to receive a list of all consultants at Evobis, I could filter in two ways:

`Job title == 'Consultant' and Company == 'Evobis'` or `Company == 'Evobis' and Job title == 'Consultant'`

Both will leave me with the same result, but depending on how the rest of my data looks, one might work and the other might fail.

They're evaluated left to right, so the two statements executing will look something like this:

`Job title == 'Consultant' and Company == 'Evobis'` - Give me everyone with the job title 'Consultant' - **2 results** - of those, give the ones who work at 'Evobis' - **1 result**


`Company == 'Evobis' and Job title == 'Consultant'` - Give the the ones who work at 'Evobis' - **1 result** - of those, give me the ones with the job title 'Consultant' - **1 result**

Now this is a fairly simple example, but if our list had more then 5001 people with the job title consultant, the first statement would actually fail, same goes the other way around.

So keep the order in mind when you're designing your query, always query by the most distinct property first, and then narrow down from there.

## Indexing

Now we've talked a lot about filters in the above sections, once your list grows beyond 5.000 items you'll need to index columns in order to filter using them, think of indexing as marking a column for query - [behind the scenes](https://www.vrdmn.com/2012/11/sharepoint-list-indexes-under-hood.html) a lot more is going on that we'll not worry about today.

Most of the time if your list just grows slowly, SharePoint (Online) will actually automatically setup indexes for you, but in some cases I've found that to not work, so just set them up manually if you know you'll be using them.

This is done by going to **list settings** under the columns press the **Indexed columns** link, **Create a new index** and you're off to the races, you'll be given the option to add a secondary column, here in theory this is supposed to improve performance when those two columns are queried together, but it does not change any of the limits, and from [my twitter feed](https://twitter.com/tanddant/status/1644069468476264456) it seems to be mostly theoretical.

## Dynamic data

Now common for the two things above is that they hardly require any changes to your codebase, maybe a rewrite of your filter, but that should really be about it.

If the above two do not solve your problems, maybe we're attacking the issue in the wrong way, if your app shows a long list of data you really should consider loading in more data as needed, for instance when I scroll to the bottom of the list, this can be done using paging, or better yet the [RenderListDataAsStream API](https://learn.microsoft.com/en-us/dotnet/api/microsoft.sharepoint.client.list.renderlistdataasstream?view=sharepoint-csom), that's how the modern list views manage to show large lists (and also why you sometimes see the **load more** button on the page).

This will not only allow you to show data from a very large list, but also really improve the user experience of your app, as you're no longer fetching all the data before showing it, but rather you're fetching it as you need it, this does of course mean that you have to do a bit more of code rewrite, so do be sure to test that the API does what you need it to before going down this route.

## Archive data

Another option is to archive data - and here I'm not talking about having a **inactive** flag on your items, although that could actually work, I've seen it done as a "temporary" fix - a flow that sets a boolean on every list item at the start of every week, and every query to the list just has `Archived eq 0` but at this point you're already peeing your pants to stay warm, please don't actually do this unless it's very temporary.

The right solution is to move your data off to somewhere else, this could be an SQL instance, Dataverse, or even just a separate SharePoint list, it's important to realize that data has a lifetime, and while you might not want to delete the data, you should still archive it once it's no longer actively being worked on!

## Other data sources

### SQL

Something I realized at one point while helping out an individual who was stuck with a list view threshold issue was that the person knew that SharePoint lists wasn't the correct approach, but really liked the provided APIs from SharePoint, and I mean, who can disagree, OData is pretty awesome, but something that not everyone knows, is that OData is a library that you can easily implement in something like Azure functions, checkout this sample [Azure Functions with OData](https://github.com/xuzhg/WebApiSample/tree/main/AzureFuncDemo), now combine that with Entity Framework, and you're off to the races.

This way you won't have any problems dealing with many thousands of items at a time.

### Dataverse

Another option is [Dataverse](https://learn.microsoft.com/da-dk/power-apps/maker/data-platform/data-platform-intro), Dataverse is the database behind the Power Platform, it's essentially an end user database that's easily setup and managed by a power user, and easily connects with the Power Platform.

While Dataverse does come with a slight license cost, so does running an SQL server in Azure, here you're given everything from security to APIs right out of the box.

## TL;DR

The threshold is there to ensure the performance of your app, make sure you index your columns, filter in a smart and efficient way, and consider using modern APIs like RenderListDataAsStream if you're building a responsive app.

And remember, data has a lifecycle, **archive it!**

## Resources
### Sample Data - Contacts list

| First Name | Last Name | Company   | Job title  |
| ---------- | --------- | --------- | ---------- |
| Dan        | Toft      | Evobis    | Consultant |
| Casey      | Smith     | Microsoft | Manager    |
| Jim        | Smith     | OpenAI    | Manager    |
| Brian      | Jacobsen  | Contoso   | Consultant |
| John       | Doe       | Contoso   | CEO        |
| ...        |           |           |            |

### Read more

[Community docs - Living Large with Large Lists and Large Libraries](https://learn.microsoft.com/en-us/microsoft-365/community/large-lists-large-libraries-in-sharepoint) - great tips if you do deiced to stay in a SharePoint list, or you're on-prem.
