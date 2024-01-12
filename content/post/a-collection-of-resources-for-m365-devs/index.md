---
title: "A collection of resources for Microsoft 365 developers"
date: 2022-06-26T03:43:00-04:00
author: "Eli Schei"
githubname: eli-schei
categories: ["Community post"]
images:
- images/resources.jpg
tags: ["Microsoft 365"]
type: "regular"
canonicalURL: "https://elischei.com/a-collection-of-resources-for-microsoft-365-developers/"
---

Being a Microsoft 365 developer can mean a lot of things. Backend, frontend, low-code, nocode. Teams, SharePoint, Power Apps, Office… and so on. And it can be hard to navigate the ocean of good resources for Microsoft 365 developers on each of these topics. Thats why I have been collecting resources for a while now, and I thought it was about time I share them with you!

This collection lists the resources I myself have found usefull in my day to day work. I have not worked with every different type of “M365 development” so some sections might be lacking, and some won’t be here at all.

And I’m sure there are a lot of other good resources out there too that I have never had the pleasure of stumbeling upon, so please drop a comment below if you have some you’d like to share!

> Some resources may appear multiple times if they are relevant in different categories.

### Common resources for Microsoft 365 developers

* [Pattern and practices – a collection of best practices, guides, samples, solutions, SDKs, Tools and forums](https://pnp.github.io/#guidance)

**Youtube channels**

* [Microsoft 365 Developer](https://www.youtube.com/c/Microsoft365Developer)
* [Microsoft 365 Community](https://www.youtube.com/channel/UC_mKdhw-V6CeCM7gTo_Iy7w)

**Podcasts**

Keep up to date with what is moving in the community by listening to podcasts

* [Microsoft 365 developer podcast](https://www.m365devpodcast.com/)
* [PnP weekly](https://pnpweekly.podbean.com/)
* [Microsoft Cloud show](https://www.microsoftcloudshow.com/) Note, this podcast 'retired' in 2022, but a lot of the content is still relevant.

**Other resources**

* [PnP JS Library](https://pnp.github.io/pnpjs/)
* [HtwoO – open source alternative for Microsoft’s Fluent UI Web Design system](https://lab.n8d.studio/htwoo/)
* [Fluent UI Web Design system](https://developer.microsoft.com/fluentui)
* [Learn about Microsoft Authentication Library (MSAL)](https://learn.microsoft.com/azure/active-directory/develop/msal-overview)

### SharePoint framework (SPfx) resources

**Getting started with SPfx**

* [Get a developer tenant](https://developer.microsoft.com/microsoft-365/dev-program) (Microsoft 365 Developer program)
* [Getting started with SharePoint Framework](https://blog.mastykarz.nl/getting-started-sharepoint-framework/) (Blogpost by [Waldek Mastykarz](https://twitter.com/waldekm))
* [Youtube video that shows the M365 developer program](https://www.youtube.com/watch?v=2JWUr6zBtwg)
* [Set up environment](https://learn.microsoft.com/sharepoint/dev/spfx/set-up-your-development-environment) (Microsoft Docs)
* [Understanding the difference between SharePoint generator related packages](https://www.voitanos.io/blog/understand-difference-sharepoint-framework-generator-library-packages/) (Blogpost by [Andrew Connell](https://twitter.com/andrewconnell) – voitanos.io)

**Extensions / helpfull tools**

* [SPfx fast-serve](https://github.com/s-KaiNet/spfx-fast-serve)
* [SPfx snippets](https://marketplace.visualstudio.com/items?itemName=eliostruyf.spfx-snippets)
* [SPfx debug extension](https://marketplace.visualstudio.com/items?itemName=eliostruyf.spfx-debug)
* [Rencore deploy package extension](https://marketplace.visualstudio.com/items?itemName=RencoreGmbH.vscode-spfx-deploy-package)
* [Node Version Manager (nvm)](https://elischei.com/how-to-use-nvm-for-windows/)
* [PnP generator](https://github.com/pnp/generator-spfx) (Github – Community driven yeoman generator)

**Samples**

* [WebPart samples](https://github.com/pnp/sp-dev-fx-webparts)
* [Extension samples](https://github.com/pnp/sp-dev-fx-extensions)

**Other resources**

* [SharePoint framework documentaion github repo](https://github.com/SharePoint/sp-dev-docs)
* [SPfx PnP Powershell cheat sheet](https://github.com/Eli-Schei/resource-sheets/blob/main/M365/spfx/spfx-pnp-powershell-cheat-sheet.md)
* [Mastering the SharePoint Framework course](https://www.voitanos.io/course-master-sharepoint-framework) (the starter bundle is free). (Course by [Andrew Connell](https://twitter.com/andrewconnell) – – Voitanos.io)
* [Optimize bundles by disabling IE11 support in SPfx projects](https://www.voitanos.io/blog/optimize-spfx-bundles-ditch-ie11-support/) (Blogpost by [Andrew Connell](https://twitter.com/andrewconnell)  – – Voitanos.io)

### Microsoft Graph resources

**Documentation**

* [Official Microsoft Graph documentation](https://learn.microsoft.com/graph/)
* [Official documentation github repo](https://learn.microsoft.com/graph/overview)
* [Microsoft Graph authentication overview](https://learn.microsoft.com/graph/auth/)

**Tutorials/guides**

* [Build a JavaScript single-page app with Microsoft Graph](https://learn.microsoft.com/graph/tutorials/javascript)

**Libraries**

* [Microsoft Graph JavaScript Client Library](https://www.npmjs.com/package/@microsoft/microsoft-graph-client)

**Tools**

* [Graph explorer](https//developer.microsoft.com/graph/graph-explorer)
* [Discover the Microsoft Graph toolkit](https://www.youtube.com/watch?v=HdQlVv3Wekk) (youtube video)
* [Microsoft graph toolkit](https://learn.microsoft.com/graph/toolkit/overview) (Microsoft docs)

### Teams development resources
Tip, you can use [SPfx to develop Teams apps](https://learn.microsoft.com/microsoftteams/platform/sbs-gs-spfx?tabs=vscode%2Cviscode), so have a look at the SPfx resources too.

**Getting started**

* [Get started with apps for Microsoft Teams](https://learn.microsoft.com/microsoftteams/platform/get-started/get-started-overview)
* [What are Teams apps](https://learn.microsoft.com/microsoftteams/platform/overview)
* [Teams toolkit](https://learn.microsoft.com/microsoftteams/platform/toolkit/teams-toolkit-fundamentals)
* [Yeoman generator for Teams](https://github.com/pnp/generator-teams)

**Manage apps, and app settings in tenant**

* [Manage your apps with the developer portal for Microsoft Teams](https://learn.microsoft.com/microsoftteams/platform/concepts/build-and-test/teams-developer-portal)
* [Manage app setup policies in Microsoft Teams](https://learn.microsoft.com/microsoftteams/teams-app-setup-policies), see also my blogpost about [enabling sideloading of apps in teams](https://elischei.com/enable-sideloading-of-apps-in-microsoft-teams/).

### Power Apps and Power Apps Component framework (PCF) resources

**Getting started with Power Apps**

* [Introduction to Power Platform for developers](https://learn.microsoft.com/learn/modules/introduction-developing-power-platform/1-introduction)
* [Overview of all available Power Apps learning modules](https://learn.microsoft.com/learn/browse/?expanded=power-platform&products=power-apps)

**Getting started with PCF**

* [Introduction to PCF](https://learn.microsoft.com/learn/modules/get-started-component-framework/)
* [Build a Power App component](https://learn.microsoft.com/learn/modules/build-power-app-component/)
* [Use advanced features with PCF](https://learn.microsoft.com/learn/modules/component-framework-advanced-topics/)
* [PCF cheat sheet](https://github.com/Eli-Schei/resource-sheets/blob/main/M365/Power%20Apps%20and%20PCF/PCF-cheat-sheet.md)

**Youtube videos**

* [PCF Academy](https://www.youtube.com/playlist?list=PL0WiRFWRFGlQr5tGZdUGUlyTl7Gi1Wb_K)

**Other resources**

* [PCF Yeoman generator](https://github.com/DynamicsNinja/generator-pcf)
* [Package a component](https://learn.microsoft.com/powerapps/developer/component-framework/import-custom-controls)
* [PCF properties](https://learn.microsoft.com/powerapps/developer/component-framework/manifest-schema-reference/property) (Overview of different properties that are allowed)

<p></p>

---

### Do you know of any other resources that should be on this list?

Leave a comment below, or fork this blogs gitbub repo and add them yourself (Here is the [guidance on how to contribute](https://pnp.github.io/blog/post/contribute-blog/))
