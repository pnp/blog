---
title: "M365 Across App scenarios - Teams apps and SPFx"
date: 2022-11-07T10:30:12.185Z
author: "Markus Moeller"
githubname: mmsharepoint
categories: ["Community post"]
images:
- images/SecurityLock.jpg
tags: []
type: "regular"
summary: "This post shall show various application development scenarios that can be used across different products inside Microsoft 365. The basis for this can either be SharePoint Framework (SPFx) or Teams application development."
---

With [TeamsJS SDK 2.0](https://learn.microsoft.com/en-us/microsoftteams/platform/tabs/how-to/using-teams-client-sdk?view=msteams-client-js-latest&tabs=javascript%2Cmanifest-teams-toolkit#whats-new-in-teamsjs-version-20?WT.mc_id=M365-MVP-5004617) and Teams manifest 1.13 and above it is possible to extend Microsoft Teams applications across Microsoft 365 so you can also use  those apps in Outlook or Office.

As you can also use SharePoint Framework (SPFx) to create Microsoft Teams applications you can now use SPFx across Microsoft 365 as well.

# Platform
## Teams 
A Microsoft Teams application can be personal or configurable Tab, a Bot, a messaging extension or a connector. It can be a standalone  app or tailored to specific scenarios such as a team, a channel or a meeting.

## Outlook
Outlook can either reuse a personal tab as standalone app or it can use a search-based messaging extension in mail composer, that is while a mail is created. The context of an incoming mail cannot be used, yet. Also the more flexible action based messaging extension cannot be used, yet.  

## Office 

# Teams extension options
## Personal app


![Personal App In Teams](images\PersonalAppInActionInTeams.png)

![Same Personal App In Outlook](images\PersonalAppInActionInOutlook.png)

## Search based messaging extension
A search-based messaging extension allows you to select from a defined resultset of existing objects, such as documents or people and insert this selection into a compose message without any modification to the selected object.

![Search based messaging extension](images\SearchBasedMessagingExtension.png)

## Action based messaging extension
Instead of the search-based messaging extension the action-based variant allows to interact with the user about selection or modification or even creation of that selection. Instead of a simple pick here you can create custom forms or at least more customized selection areas.

![Invoke Action based messaging extension](images\ActionBasedMessagingExtensionInvoke.png)

![Action based messaging extension task module](images\ActionBasedMessagingExtensionSelectTaskModule.png)

# Development approaches
## Teams native App
A teams native app is a web application including Teams JS SDK and can be built either by the yo teams generator or the Teams Toolkit for Visual Studio (code). The teams manifest (with JSON based notation) declares the app as a Teams application. For hosting you need a separate web application, for instance an Azure app service. 

## SPFx
SharePoint Framework (SPFx) provides full support for client-side SharePoint development. But despite the name SharePoint it’s much more than that. It can also be extended to other Microsoft 365 scenarios. SharePoint framework is self hosting. So no need to acquire additional resources for this. SharePoint framework runs client-side only and in user context. For user impersonation  or well performing backend operations you might still need backend components. Although direct access to Microsoft Graph is available within, [the security model is debatable](https://pnp.github.io/blog/post/microsoft-365-development-security/#spfx-3rd-party-api-and-issues) and might also need the implementation of backend components.

# Supported scenarios 
(partially preview)

&nbsp;|Teams|Outlook|Office
-|:-----:|:-------:|:------:
**Personal app**|Teams App <br /> SPFx|Teams App <br /> SPFx|Teams App <br /> SPFx
**Search based messaging extension**|Teams App|Teams App|-
**Action based messaging extension**|Teams App <br /> SPFx| :pray: | :pray:

# Summary

I hope you enjoyed this post and found some helpful information. I expect a lot more to come with "development across Microsoft 365 and I am highly interested in moving (with) this forward and adapt new capabilities.

Feel free to leave a comment here, in the referenced blog posts or directly reach out to me on [Twitter](https://twitter.com/moeller2_0/)