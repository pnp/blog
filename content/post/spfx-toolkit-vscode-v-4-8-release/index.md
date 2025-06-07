---
title: "SharePoint Framework Toolkit v4.8.0 minor release"
date: 2025-06-07T01:00:00.000Z
# post thumb
images:
  - images/main.png
#author
author: "Nico De Cleyre"
githubname: nicodecleyre
# description
description: "SharePoint Framework Toolkit is a Visual Studio Code extension that aims to boost your productivity in developing and managing SharePoint Framework solutions helping at every stage of your development flow, from setting up your development workspace to deploying a solution straight to your tenant without the need to leave VS Code. With the SharePoint Framework, you can use modern web technologies and tools in your preferred development environment to build productive experiences and apps that are responsive and mobile-ready allowing you to create solutions to extend SharePoint, Microsoft Teams, Microsoft Viva Connections, Outlook, and Microsoft365.com."
summary: "SharePoint Framework Toolkit is a Visual Studio Code extension that aims to boost your productivity in developing and managing SharePoint Framework solutions, helping at every stage of your development flow, from setting up your development workspace to deploying a solution straight to your tenant without the need to leave VS Code. With the SharePoint Framework, you can use modern web technologies and tools in your preferred development environment to build productive experiences and apps that are responsive and mobile-ready, allowing you to create solutions to extend SharePoint, Microsoft Teams, Microsoft Viva Connections, Outlook, and Microsoft365.com."
# Taxonomies
categories: ["Community post"]
tags: ["VS Code", "SharePoint Framework (SPFx)"]
type: "regular"
---

## 🗒️ Quick intro

[SharePoint Framework Toolkit](https://marketplace.visualstudio.com/items?itemName=m365pnp.viva-connections-toolkit) is a Visual Studio Code extension that aims to boost your productivity in developing and managing [SharePoint Framework solutions](https://learn.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview?WT.mc_id=m365-15744-cxa) helping at every stage of your development flow, from setting up your development workspace to deploying a solution straight to your tenant without the need to leave VS Code, it even allows you to create a CI/CD pipeline to introduce automate deployment of your app and also comes along with a dedicated @spfx Copilot Chat participant who is your AI assistant grounded for SharePoint Framework development.

Just check out the features list 👇 it's a looot 🤯.

![features](images/features.png)

Sounds cool 😎? Let's see some new enhancements we added in this minor release

##  Adds LLM tools for GitHub Copilot agent mode

This is the first prototype of LLM Tools integrated into the SPFx Toolkit. The goal? To explore how GitHub Copilot in agent mode can help you create, manage, and edit SharePoint content like sites, lists, and items directly from VS Code.
This is just the beginning: we’re limited to 70–80 tools for now, so we’re focusing purely on SharePoint scenarios. Expect more refinement and expansion in future updates.

![llm](images/llm.png)

## Hides app management context menu actions from command palette

To reduce noise and improve clarity, app management actions that are only relevant in context menus have been hidden from the command palette. 

## Support for installing the correct Node.js version

No more guessing which Node.js version you need. The toolkit now provides direct links and guidance for installing the correct version, including tips for using NVM or NVS based on your OS.

![nodejs](images/nodejs.png)

## Fixes setting form customizer list form on root site

A bug that prevented setting a form customizer on the root site has been fixed. This included improved URL validation to ensure smoother setup.

## Shortened command category names ✂️

We’ve shortened the command category prefix from “SharePoint Framework Toolkit” to “SPFx Toolkit” across all actions. Cleaner, faster to scan, and easier to use.

## Default action for SPFx App is now “Install”

The default action when working with SPFx apps is now set to install, because that’s what most of us are doing most of the time.

![install](images/install.png)

## `/manage` is now `/info`

The `/manage` chat command has been renamed to `/info` to better reflect its purpose: retrieving information from your SharePoint Online tenant.
Heads up: this change will also be reflected in the updated wiki guidance.

![info](images/info.png)

To read more about it, check out our [wiki](https://github.com/pnp/vscode-viva/wiki/8.-SPFx-Toolkit-GitHub-Chat-Participant#info).

## Adds Gulp Operations to VS Code Extension Commands

You can now run all major gulp tasks directly from the command palette. This includes:

- build
- clean
- serve
- test
- trust-dev-cert
- deploy-azure-storage

No more jumping to the terminal, just run what you need, when you need it.

## Align gulp task icons

We’ve aligned the icons for gulp tasks across the tree view and command palette for a more consistent visual experience.

![gulptaskicons](images/gulptaskicons.png)

## Teams Toolkit → M365 Agents Toolkit

All references to the Teams Toolkit have been updated to reflect the new name: Microsoft 365 Agents Toolkit. This includes code, docs, and UI elements.

## Updated Wiki Link

The wiki link has been updated to point to [the new documentation site](https://pnp.github.io/vscode-viva/). Make sure to update your bookmarks!

## Dependency Updates

We’ve updated most extension dependencies to their latest stable versions. Along the way, we:
- Updated the vsce package used in our workflows
- Cleaned up unused packages
- Switched type packages to use exact versions
- Upgraded tailwindcss and adjusted styles
- Bumped typescript to v5
- Added a qna link in package.json to direct users to our GitHub Discussions
- Did some minor code cleanup

## Add Tenant App Catalog & Add/Remove Site App Catalog
You can now:
- Add a tenant app catalog (if one doesn’t exist)
- Add or remove a site app catalog

All from within the toolkit, no need to jump into the admin center.

![appcatalog](images/appcatalog.png)

## Smarter App Install Handling

We’ve improved how SPFx Toolkit handles app installations, especially when things don’t go as planned. If you try to install an app that’s already installed, the toolkit now detects it and suggests the next best step:
- Upgrade if it’s the same app but a newer version
- Remove if it’s a different app with the same version number

This update also introduces progress notifications for SPFx actions, so you’ll always know what’s happening behind the scenes.

## 👏 You ROCK 🤩

This release would not have been possible without the help of some really awesome folks who stepped in and joined our journey in creating the best-in-class SharePoint Framework tooling in the world. We would like to express our huge gratitude and shout out to:

- [Nirav Raval](https://github.com/nirav-raval)
- [Nishkalank Bezawada](https://github.com/NishkalankBezawada)
- [Adam Wójcik](https://github.com/Adam-it)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Nico De Cleyre](https://github.com/nicodecleyre)

## 🗺️ Future roadmap

We don't plan to stop, we are already thinking of more awesome features we plan to deliver with v5 release. If you want to check what we are planning, check out our [issues from this milestone](https://github.com/pnp/vscode-viva/milestone/6). Feedback is appreciated 👍.

## 👍 Power of the community

This extension would not have been possible if it hadn’t been for the awesome work done by the [Microsoft 365 & Power Platform Community](https://pnp.github.io/). Each sample gallery: SPFx web parts & extensions, and ACE samples & scenarios, is populated with the contributions made by the community. Many of the functionalities of the extension, like upgrading, validating, and deploying your SPFx project, would not have been possible if it weren’t for the [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) tool. I would like to thank all of our awesome contributors sincerely! Creating this extension would not have been possible if it weren’t for the enormous work done by the community. You all rock 🤩.

![PnP community](images/parker-pnp.png)

If you would like to participate, the community welcomes everybody who wants to build and share feedback around Microsoft 365 & Power Platform. Join one of our [community calls](https://pnp.github.io/#community) to get started and be sure to visit 👉 https://aka.ms/community/home.

## 🙋 Wanna help out?

Of course, we are open to contributions. If you would like to participate, do not hesitate to visit our [GitHub repo](https://github.com/pnp/vscode-viva) and start a discussion or engage in one of the many issues we have. We have many issues that are just ready to be taken. Please follow our [contribution guidelines](https://github.com/pnp/vscode-viva/blob/main/contributing.md) before you start.
Feedback (positive or negative) is also more than welcome.

## 🔗 Resources

- [Download SharePoint Framework Toolkit at VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=m365pnp.viva-connections-toolkit)
- [SPFx Toolkit GitHub repo](https://github.com/pnp/vscode-viva)
- [Microsoft 365 & Power Platform Community](https://pnp.github.io/#home)
- [Join the Microsoft 365 & Power Platform Community Discord Server](https://discord.gg/YtYrav2VGW)
- [SPFx Toolkit Wiki](https://pnp.github.io/vscode-viva/)
- [Join the Microsoft 365 Developer Program](https://developer.microsoft.com/en-us/microsoft-365/dev-program)
- [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)
- [Sample Solution Gallery]( https://adoption.microsoft.com/en-us/sample-solution-gallery/)
