---
title: "Microsoft Graph Fundamentals learning path -- Module 2"
date: 2021-04-05T04:28:00-04:00
author: "Luise Freese"
githubname: LuiseFreese
categories: ["Community post"]
images:
- images/GraphAccessTokenTicket.png
tags: ["Microsoft Graph"]
type: "regular"

---

Welcome back to my series about the [Microsoft Graph Fundamentals
learning
path](https://docs.microsoft.com/learn/paths/m365-msgraph-fundamentals/) on
Microsoft Learn. This is part 2; if you did not read [part
1](https://m365princess.com/microsoft-graph-fundamentals-learning-path-module-1/) yet,
this is your chance to catch up! I will stay here and wait for you with
a coffee

This module is called **Configure a JavaScript application to retrieve
Microsoft 365 data using Microsoft Graph** and we start with an

## intro

We are still sticking to the business scenario from module 1: We want to
create an app that can access email, chats, files, meetings. To
authenticate users, Microsoft 365 uses Microsoft Identity, and we will
need to use Microsoft Identity and Microsoft Graph to get the data we
want to display in our app by using [Microsoft Authentication
Library(MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Wait, what? Don't worry if you did not completely understand this. We
will do this step-by-step.

## Understand the role of Azure Active Directory with Microsoft Graph

OK, we already understood that Microsoft Graph is THE API to access data
in Microsoft 365 - but of course, this data needs to be secured because
we don't want everyone to access them, right? This is what we need
Microsoft Identity platform for. Microsoft identity ensures that only
authorized users (delegated permissions) and apps (application
permissions) access data stored in Microsoft 365. The challenge now is
to link Microsoft Identity (of which we will use Azure Active Directory)
to our Microsoft Graph powered app. The module explains in detail how
you register your app in Azure AD and retrieve your application ID.
Later on, you will add this ID into the MSAL (Microsoft Authentication
Library)'s code of your app to link to your Azure Active directory.

But before we do this in an exercise, we will learn some theoretical
stuff that we need later on.

## Understand Microsoft Graph permissions and consent 

Crucial to understand that a user or admin needs to consent before the
app requests permission to access Microsoft 365 data via Graph, which is
why we need to know a little bit more about:

### Scopes

All resources have specific scopes, like *User.Read* (lets you read the
profile of the signed-in user) or *User.Read.All* lets you read the
profiles of all users present in this directory. Of course, you will
want only to allow scopes that are necessary for the application. You
can look up scopes for each request in the [official
documentation](https://docs.microsoft.com/graph/api/overview?toc=.%2Fref%2Ftoc.json&view=graph-rest-1.0) and
also learn about them while trying out requests in [Graph
Explorer](https://aka.ms/ge).

### Permission types

We can perform requests on behalf of a user (delegated permission), and
we can run background processes like creating, reading, updating, or
deleting events of all calendars without the requirement of a signed-in
user. This means that an admin will need to pre-consent to these
permissions.

### Access tokens

The unit also describes how the magic with an access token works - and
uses a great comparison for that! An access token is like a movie
ticket - but your application gives it to Graph to show it has
permission to access the requested data in Microsoft 365. LOVE this
explanation so much!

![GraphAccessTokenTicket.png](images/GraphAccessTokenTicket.png)

We use this movie ticket/access token in the Authorization header of our
HTTP request.

## Register an application with Azure Active Directory

In this unit, you learn which account type you can select when
registering an app in AD and that web and single-page apps will require
a redirect URI so that identity platform redirects and sends security
tokens after authentication.

In case you wondered: There is a big difference between authentication
and authorization.

![GraphFunAuth.png](images/GraphFunAuth.png)

## Exercise - Register an application with Azure Active Directory

This exercise walks us step by step through registering an app in Azure
AD- I highly recommend following this unit if you never registered an
application before:

![appreg.png](images/appreg.png)

Let's now

## Retrieve an access token using MSAL

MSAL will make Token interaction more effortless for you because we can
acquire tokens from the identity platform to authenticate users and
access Microsoft Graph.

![auth.gif](images/auth.gif)

Now that we understood the authentication flow, it's time to get our
hands dirty with

## Exercise - Retrieve an access token using MSAL

To get this straight - you will clone a repository either using git or
downloading a zip file. After opening this in Visual Studio Code (or any
other editor), you will need to replace two placeholders with tenant ID
and app ID from your Azure app registration.

The unit walks you through some crucial parts of your app and lets you
map this code to the authentication flow.

![GraphApp.png](images/GraphApp.png)

Congrats! - you made it!

![GraphFun-didit2.png](images/GraphFun-didit2.png)

## Conclusion

I loved this module - even if I already knew how to register
applications and what Microsoft Graph does - it clarified the
authentication flow once again and walked me nicely through some crucial
parts of the code that I cloned from the MSLearn repository. Some basic
understanding of JavaScript was beneficial to let the app run and know
WHY and HOW it runs.
