---
title: "Let's tame Dataverse: How to reference Many-to-Many-relationships in Azure Logic Apps"
date: 2021-11-18T08:40:00-04:00
author: "Luise Freese"
githubname: LuiseFreese
categories: ["Community post"]
images:
- images/platform.png
tags: ["Dataverse"]
type: "regular"
---

While building an app that stores data in Dataverse, I came across a
not easy to resolve problem. If you already follow me for a bit longer,
you may assume that this is
about [ProvisionGenie](https://provisiongenie.com/ "https://provisionGenie.com"), 
and so I will use this use case of provisioning Microsoft Teams teams
and storing data about that as an example. To explain the issue, we
first need to understand some basics, which I will cover here
first:

## What is Dataverse 

![platform.png](images/platform.png)

Dataverse is a is a secure and scalable SaaS data service, that sits
right in Power Platform. Dataverse's database is Azure SQL, and often,
people refer to Dataverse just as 'a database', but it is so much
more

![dataverse-saas.png](images/dataverse-saas.png)


I will not go into full detail in this blog post, but cover something
that people with a background in Microsoft 365/SharePoint might not be
aware of:

## How does Dataverse distinguish from SharePoint lists and what makes it a 'real database'?

In Dataverse, we store data in tables, we can either use predefined ones
or we can creates our own tables. We can choose from different kind of
column types to store data just as needed. The beautiful thing that get
our Dynamics 365 colleagues excited is, that Dataverse can serve as a
'relational database', which means that we can create all kinds of
relationships between data, which gives us a better overview on data as
we can put data into context.

Also, we have role-based access control (RBAC), which means that we can
granularly control who can view, edit, delete etc. data, while this
isn't possible with SharePoint lists. If we use a list as data source
for a Power Apps, we need to share the entire list with all users of
that application, which means that users can even bypass the app and
manipulate and delete data directly on the SharePoint site.

Now you may ask, what is it about relationships in Dataverse that makes
it so special?

## What kind of relationships do exist in Dataverse? 

[[![relationships.jpg](images/relationships.jpg)

### 1-to-many relationships

In a 1:N (1-to-many) relationship we associate a (1) row of a table to
many other rows in a related table with a lookup column. We can see a
list of the related rows that are associated with our primary table.

You will come across the term 'N:1(many-to-1)' as well - it is the
same thing as a 1:N relationship- just viewed from the related table,
not from the parent/primary table.

As an example, please imagine a table `Teams Requests` and another
related table `Teams Channels`. Each Team can have many channels, but a
channel can be only associated with one Team (represented in
the `Teams Request` table). This means, that we need to have a 1:N
relationship between `Teams Requests` table and
the `Teams Channels` table. We reference this like this:
 
[![TeamsChannel1N.png](images/TeamsChannel1N.png)

We get the correct environment, fetch the table `Team Channels` and
filter by `TeamsRequestId` so that only the related channels to that
Teams request will be returned.

### Many-to-many relationships

An N:N (many-to-many) relationship depends on a special relationship
table (intersect table), so that many rows of one table can be related
to many rows of another table. We can see a list of all rows in the
related table that our primary table is associated with.

As an example, please image now the `Teams Requests` table again that
needs to be related to a `Teams Users` table. In
this `Teams Users` table we want to store information on members and
owners of the teams in the `Teams Requests` table.

A Teams can have many users as members, and each user can be a member of
different Teams.

Also, a team can have many users as owners and these users can be owners
of several different teams.

This means, that we need to have two N:N relationships
between `teams Requests` table and `Teams Users` table.

[![TeamsRequests-TeamsUser.png](images/TeamsRequests-TeamsUser.png)

Now the intersection tables come into play: They make sure that we can
associate many rows of the related table to the primary table.

In Dataverse, we don't get to see these intersection tables, but we can
customize their name:

![TeamsRequests-TeamsUserNN.png](images/TeamsRequests-TeamsUserNN.png)

and we can make them visible when we create a model of the data in Power
BI. This also helps us understand, what the intersection table is and
how this works: \
\
The intersection tables sit in between of the primary table and the
related table: primary table (1) \--\>(N) intersection table(N) \<\--
related table\
![datamodel.png](images/datamodel.png)


## How can you reference Many-to-Many Relationships in Azure Logic Apps?

Now that the distinguishing element between an Owner of a Team and a
Member of that Team is in the relationship, we need to reference that
intersection table in a Logic App flow in order to fetch the right rows
from the Teams User table to add them with the correct role to the Team
that we want to provision.

In order to do so, we select the correct environment, and type the name
of the relationship table followed by a `set`, then we filter for the
correct Teams Request ID so that only members for that specific team
will be returned.

![ListRowsForMembers.png](images/ListRowsForMembers.png)

The very same applies to the relationship table for the owners.

![ListRowsForOwners.png](images/ListRowsForOwners.png)

## Conclusion

Before you build your Power Platform solution, its absolutely worth it
to spend a couple of thoughts on the data model. If you

-   need more relationships than a simple lookup column
-   need granular control who can access which rows
-   a performant place to store data
-   a highly scalable solution

then its very likely, that Dataverse is a service that you should
consider.

In order to take full advantage of Dataverse's capabilities in terms of
being a 'relational database' its worth it to understand what is an
intersection table and how you can reference it.

Let me know what you think in the comments :)
