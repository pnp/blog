---
title: Microsoft 365 self-service using Power Apps
date: 2022-01-12T06:00:00-05:00
author: Jan Bakker
githubname: BakkerJan
categories:
  - Community post
images:
  - images/1641653378.png
tags: ["Power Apps"]
type: regular
preview: 
  - images/1641653378.png
---

Many organizations are moving towards a modern workplace. And most of the time, that does not happen overnight. It's a big change for both end-users, management, and IT staff.

I’m a big fan of self-service and believe that organizations can benefit from it as well. It improves adoption and lowers help desk calls. Being a consultant, I'm involved in a lot of projects around Microsoft 365, Microsoft Endpoint Manager, and Azure AD. And projects often start with pilots. Most of the time, those pilots are narrowed down to IT folks. But wouldn't it be cool if the 'regular user' could also participate in pilots, those who are eager to learn, explore and test out new features? This solution is built upon Power Apps and can serve many, many use-cases.

This blog post is a showcase for a Power App around self-service. It is also a perfect example of fusion development. Microsoft made sure we have an API we can use to assign the settings we want. The Power App is already set up to use those connections, and you as a citizen developer only need to make sure the app interacts with those as you desire, with a minimum of coding effort.

![1641653378.png](images/1641653378.png)

## The idea behind the app

The concept of this app is straightforward: it puts users into groups. And the best part is: they can do it themselves. Now, Microsoft 365 offers a broad set of self-service capabilities already, but for some organizations, that can be really scary. By default, users can even create their own groups and teams themselves, but this feature is often disabled by IT.  It also might not be the most user-friendly option.  

Back to the concept of groups. These can be either security or Microsoft 365 groups. Using this app, you can offer self-service to your end-users, while staying in control. Next to that, you can make it a user-friendly experience, because you can design your own User Interface around it. So, you can put additional information in the UI, as we did in this app. Since it can be used for every group in Azure AD, this can be used within all integrated services like Office 365, Microsoft Endpoint Manager, and even security features like Azure AD Authentication policies, and Conditional Access.

The ultimate goal of this app thus is a UI where any end-user in the organization can select what pilot programs they want to be part of. In the demo, there are several different UI elements to help users with their selection ranging from toggles to sliders.  

## Features

The idea behind the slider is to bring your users in control of their modern workplace, easier put: on what pace updates will get delivered to their Windows device. By choosing a different update channel, they will be assigned to a specific Windows Update for Business ring in the back-end.

![1641747471.png](images/1641747471.png)

The toggles can be used to let the user participate in different pilots or features that Microsoft 365 offers. It can also be used to request licenses, for example, if the user needs Power-BI Pro for a specific project. You could even build an additional flow that will ask for manager approval first, or you can make use of Azure Active Directory Access Reviews to review the groups periodically.

### Group-based licensing

Leveraging Azure Premium P1, we could use group-based licensing to automatically assign licenses to users based on group membership.  

In the Azure portal, go to Azure Active Directory -> Licenses. Select the preferred licenses, then go to the Licensed groups blade, and select + Assign.

![1641917465.png](images/1641917465.png)

From the list, select the underlying services that you want to assign to the group.

![1641748265.png](images/1641748265.png)

As soon as the user is added to the group, the license is automatically assigned. When the user is removed, also the license will be unassigned.

How does the app work under the hood?

The app is using Power Automate to connect to the Graph API. Inside the Power Automate flow, we use the HTTP connector to send out the API calls. Based on the parameters that we define in Power Apps, the user is either added or removed from the group.

![PowerAppsFlow.png](images/PowerAppsFlow.png)

The flow is using the switch feature to determine what action should be taken. This can be either “add”,”remove”, or “fetch”. More details on the app and flow can be found in the extended documentation on GitHub.  

[![1641918438.png](images/1641918438.png)

![JanBakker_0-1641843830957.png](images/JanBakker_0-1641843830957.png)

## How to get started?

This demo app is on [GitHub](https://github.com/BakkerJan/M365Portal) and can be up and running in minutes. Reach out to this repository for detailed information and step-by-step instructions Also [make sure to check out [this YouTube video](https://www.youtube.com/watch?v=MzH1Ps6gG7A) for a short tutorial

## Conclusion

We hope to have provided some inspiration in facilitating your end users with a  self-service experience using the Power Platform. Allowing your users to interact with an easy interface and requesting [the features they feel add[ value will make sure you stay in control!
