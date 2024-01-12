---
title: "What is a Microsoft 365 Developer, and how to get started"
date: 2022-06-30T03:43:00-04:00
author: "Eli Schei"
githubname: eli-schei
categories: ["Community post"]
images:
- images/image.jpg
tags: ["Microsoft 365"]
type: "regular"
canonicalURL: "https://elischei.com/what-is-a-microsoft-365-developer-and-how-to-get-started/"
---

Since you have found this corner of the internet, chances are that you already have some idea of what a Microsoft 355 Developer does. But often, when I talk to other developers – outside of the the “Microsoft 365 sphere”, they have no idea what it means to be a “Microsoft 365 Developer”. So I thought I should write a blogpost about it and try to give an overview of what we do.

## What does it mean to be a Microsoft 365 Developer?

In a lot of aspects – its just like being any other type of developer. You write code, you create things, you use source control, you deploy stuff and so on. Where it differst from ‘regular development’ is that where you typically have a stack of technologies that you use to build a webiste or app of some sort from scratch – in Microsoft 365 you work with a lot of different products which all can be used as is. And the main task of the developer is to extend/build on top of the exisiting capabilites of these products.

### What even is Microsoft 365?

If you are brand new to this area you might not have a clear picture of what Microsoft 365 is, so lets start there. Microsoft 365 (M365) is Microsofts productivity cloud. It is a collection of tools that you can use to work and collaborate with your colleagues. It includes the Office suite (Word, Excel, Power point), OneDrive, SharePoint and Teams.

And then there is Power Platform, which is in the same sphere as M365, but still a little on its own. And then there is a logical connection from Power Platform to Dynamics 365.

And of course there is Azure – with Azure AD, and app registrations that play a big part in M365 development. To make it more confusing there are different development lifecycles and tools for a lot of these different products.

### So what does a Microsoft 365 developer typically do?

Work patterns and workflows will differ between companies – so even though a lot of companies use the same (M365) tools – they might want to use them differently. Thats why Microsoft supports all kinds of different ways to extend M365. It is possible to build custom apps that give you total control of the user experience, or you can extend existing functionallity with smaller changes/extensions.

As I mentioned previously we typically “extend the capabilities of the products in the Microsoft 365 sphere”, or add new capabilites. Or we create the links between different M365 products so they can ‘talk to each other’.

## How can you build on top of Microsoft 365?

So this is where it gets fun – and also kind of overwhelming.

SharePoint webparts, Teams apps, Teams extensions, Teams bots, SPfx apps, SPfx extensions, Office Addßins, Power Apps (no code/low code), PCF components….. you might have heard of all of these, some of them, or none of them. As mentioned there are a lot of ways to build on top of Microsoft 365 and I’ll try to give you a simplified overview.

To do this lets divide Microsoft 365 into four main developer areas: SharePoint Online, Teams, Power Platform and Office.

### SharePoint Online

SharePoint is a collaboration tool that offers a simple way to create pages, lists and work on documents together. It is often used as an intranet solution, where you can find internal news, tools and documentation.

There are different ways to extend SharePoint. You can [crete webparts](https://learn.microsoft.com/en-us/sharepoint/dev/spfx/web-parts/overview-client-side-web-parts) (apps) and you can [create extensions](https://learn.microsoft.com/en-us/sharepoint/dev/spfx/extensions/overview-extensions). You can use the same framwork for these, and that is [SharePoint Framework](https://learn.microsoft.com/en-us/sharepoint/dev/spfx/sharepoint-framework-overview) – also called SPfx for short. SPfx is a framwork for client side SharePoint development, and it uses JavaScript/TypeScript and React. There are tools and examples that will show you how to use something other than React if you prefer.

### Teams

Most people think of Teams as a meeting and chat tool – which is not wrong – but Teams is actually built on top of SharePoint as a collaboration tool – an easy way to work in teams and share documents, tasks etc.

From a developer perspective – how do you extend Teams? You can [build apps](https://learn.microsoft.com/en-us/learn/modules/intro-microsoft-teams-apps/2-microsoft-teams-apps), embed a webpage in a[ Teams tab](https://learn.microsoft.com/en-us/learn/modules/embedded-web-experiences/), create [conversational bots](https://learn.microsoft.com/en-us/learn/modules/msteams-conversation-bots/) to solve different tasks, you can create[ message extensions](https://learn.microsoft.com/en-us/learn/modules/msteams-messaging-extensions/), or collect user input with something that’s called ‘[task modules](https://learn.microsoft.com/en-us/learn/modules/msteams-task-modules/)‘ (wich is basically pop-ups/modals). And you can connect to different services using webhooks or [Office 365 connectors](https://learn.microsoft.com/en-us/learn/modules/msteams-webhooks-connectors/).

You can actually use [SharePoint Framework to build apps for Teams](https://learn.microsoft.com/en-us/microsoftteams/platform/sbs-gs-spfx?tabs=vscode%2Cviscode), or you can use the [Teams toolkit](https://learn.microsoft.com/en-us/microsoftteams/platform/toolkit/visual-studio-code-overview). The toolkit also [supports development in .NET](https://devblogs.microsoft.com/visualstudio/build-apps-for-microsoft-teams-with-net/) if you are more comfortable backend.

### Power Platform

#### Power Apps

Power Apps is itself a tool for creating apps. It provides an easy no-code/low-code drag and drop solution to build apps. But you also have Power Apps Component framework that lets you create your own component that can be used inside a power app. These components can also be used inside Dynamics 365.

#### Power Automate

Power Automate is a service to help you create workflows. This is also a low-code solution where you can drag and drop different steps together to create your flow. This is an easy way to get the different parts of M365 talking together.

### Office

Most people use the office suite and never conciders that it can be extended with add-ins. An [Office add-in is almost like a miniature webapp that embedded in the office clients](https://learn.microsoft.com/en-us/office/dev/add-ins/overview/learning-path-beginner).

### Azure

Ok, so Azure is strictly speaking not a part of Microsoft 365, but as a Microsoft 365 developer you should still be familiar with some parts of it. The most important part (from a M365 developer perspective) is [Azure App registrations](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app) which we use to grant the apps/extensions access to resources. Azure functions are also very useful, but in my personal definition of M365 Development I don’t consider Azure Functions part of it so I won’t cover that here.

### Microsoft Graph

Another tool you should know about if you want to get started with Microsoft 365 Development is [Microsoft Graph](https://learn.microsoft.com/en-us/graph/overview). This is an API that you can use to get information from different parts of M365. This can be current user, documents, list elements and so on. You can also use it to edit/add information, [upload files](https://elischei.com/upload-files-to-sharepoint-with-javascript-using-microsoft-graph/) ++.

## How to get started as a Microsoft 365 developer?

First you should [sign up for the Microsoft 365 Developer program](https://developer.microsoft.com/en-us/microsoft-365/dev-program). It is free and it will give you access to your own M365 developer tenant that you can use to test the apps/extensions that you build.

When working with Power Apps you also [need to get the Power Apps developer plan](https://powerapps.microsoft.com/en-us/developerplan/) (this is also free).

And from there – start by following some guides/tutorials and just jump into it. I’ve added a lot of links to different resources in the previous sections, but I’ll also add a list of links in the end of this blogpost.

### Frontend or backend

A lot of the M365 developer toolkits are offered for both .NET and JavaScript/TypeScript, but you don’t always have a choice. The best is probably to be comfortable in both worlds.

In my experience a lot of the M365 development are now client-side focused, and you can almost always find an example on how to do something in JavaScript/TypeScript. But since I’m a frontend developer I haven’t really looked for that many backend resources – so there might be many out there. I can only speak from my own experience and I will always choose TypeScript (or JavaScript) if I can – but I know enough C#/.NET to do small simple things if I absolutely have to. And that combination of skills works great for me.

## Resources

I’ve previusly written a blogpost “[A collection of resources for Microsoft 365 Developers](https://pnp.github.io/blog/post/a-collection-of-resources-for-m365-devs/)” so take a look at that too. But here are some good resources if you are completely new to this area of development.

* [Introduction to the Microsoft 365 Developer program](https://www.youtube.com/watch?v=2JWUr6zBtwg) (youtube video)
* [Microsoft 365 Developer program](https://developer.microsoft.com/en-us/microsoft-365/dev-program)
* [Extend Microsoft 365 – Fundamental](https://learn.microsoft.com/en-gb/learn/paths/m365-extend-fundamental/) (Microsoft Learn module)
* [Introduction to SharePoint Framwork](https://learn.microsoft.com/en-us/sharepoint/dev/spfx/sharepoint-framework-overview) (Microsoft docs)
* [Get started building Microsoft Teams apps](https://www.youtube.com/watch?v=EQuB8l4sccg&list=PLWZJrkeLOrbblzC_s22pIBOotBV66erf-) (youtube course)
* [A comprehensive guide to PCF components](https://elischei.com/a-comprehensive-guide-to-power-apps-component-framework-pcf-part-1-getting-started/)
