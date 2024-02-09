---
title: "Power Platform? I'm a developer!"
date: 2024-02-08T00:00:00-04:00
author: "Kinga Kazala"
githubname: kkazala
categories: ["Community post"]
images:
- images/Extensibility.png
tags: []
type: "regular"
---

## Power Platform? I'm a developer!

Microsoft makes it clear:  when building Power Platform solutions, we should first evaluate Platform capabilities and use as much of low-code as possible.
This means learning which controls are available, how to use PowerFx (if you ever wrote Excel formula, you will feel at home), deciding which logic should be executed client side and when it's time to use Power Automate or Dataverse capabilities instead.

Make sure you are familiar with [Where to place logic: Canvas apps, model-driven apps, Microsoft Dataverse, or Power Automate flows?](https://learn.microsoft.com/en-us/power-apps/guidance/planning/logic) and keep an eye on the [Release plans for Dynamics 365, Power Platform, and Cloud for Industry - Dynamics 365](https://learn.microsoft.com/en-us/dynamics365/release-plans/) to learn about new features as they are prepared for release.

>As a developer, you should approach apps on Microsoft Power Platform from the perspective that **writing code […] should be** considered as an **exception** to no-code and low-code approaches. […]
Microsoft Power Platform often implements something in a particular way that benefits the platform. This may be different if you're used to doing it in custom application code. It isn't uncommon for developers that are new to building Microsoft Power Platform solutions to try to customize the platform the way they used to build custom apps previously. This should be avoided when possible and you should try to take advantage of what the platform does well, rather than try to change it to what you are used to doing.
>
>Source: [Determine when to configure or when to code](https://learn.microsoft.com/en-us/training/modules/introduction-power-platform-extend/configure-code)

But what happens if after extensive evaluation, you see that existing controls or declarative process doesn't meet your requirements? As a developer you have several options.

Depending on [where you want to place your logic](https://learn.microsoft.com/en-us/power-apps/guidance/planning/logic), you may start coding using either Power Fx, Typescript or .NET.

Yes, I wrote "coding in Power Fx".  It's getting better and better, offering [error handling](https://learn.microsoft.com/en-us/power-platform/power-fx/error-handling) (preview feature at the time of this writing), [assertion](https://learn.microsoft.com/en-us/power-platform/power-fx/reference/function-assert), [regular expressions](https://learn.microsoft.com/en-us/power-platform/power-fx/reference/function-ismatch) etc.

There are some other reasons why involving professional developer from a start is a good idea. They:

- understand and adhere to principles of [well architected framework](https://learn.microsoft.com/en-us/industry/well-architected/overview) design principles, applying them from early stages of solution design
- Instinctively follow security best practices, not only enabling solution monitoring, but also ensuring that the solution is indeed "secure by design" by using service principals and understanding the [difference](https://learn.microsoft.com/en-us/power-platform/admin/security/connect-data-sources#authenticating-to-data-sources) between implicit (app maker) and explicit (user) connectors. That's important, because one day you may find that you have been [hacked by a Power App](https://dev.to/wyattdave/ive-just-been-hacked-by-a-power-app-1fj4). Pro Power Platform developers are also more likely to invest time in learning what's new and reading technical documentation, like [Secure Implicit Connections](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/connections-list#shared-connections--secure-implicit-connections) for example.
- will accelerate the implementation and ensure adherence to best practices in terms of design, security and governance. In cases where the pro-developer will eventually hand over the application to the technical owner with business background, they enable the citizen developers to confidently develop and maintain the application without a need for continuous involvement of technical specialists.


### Keep in mind

The low-code tooling doesn't provide a line-by-line debug experience. To troubleshoot your app, you can use [error handling](https://learn.microsoft.com/en-us/power-platform/power-fx/error-handling), or view stream of events and [source expressions](https://learn.microsoft.com/en-us/power-apps/maker/monitor-canvasapps#setting-debug-published-app) from a user's session in [Monitor](https://learn.microsoft.com/en-us/power-apps/maker/monitor-overview).
If logic spans more than one screen or is hard to read, consider other approaches that would be more maintainable. One option is Git version control (still experimental as of time of this writing) which allows you editing the formulas in the code editor of your choice.

Apart from securely storing your code, it also enables more than one person to edit a canvas app at the same time. Use existing Git tools to see version history, create and manage pull requests, and do other version control tasks.

We still need to wait for the [VS Code extension for Power Fx](https://github.com/microsoft/Power-Fx/discussions/227), though.


![Git version control for Power Apps](./images/Git.png)

## Extensibility options

The image below presents a summary of all currently available options for implementing custom logic. This includes low-code like custom canvas components or business rules, and pro-code like React components, add-ins etc.
The following sections will walk you through the available options, outlining differences and wherever applicable, the limitations.

![Extensibility optipns](./images/Extensibility.png)

For a detailed summary of the above options, see the following articles:

|[Power Apps](powerApps.md)|[Power Automate](./PowerAutomate.md)|[Dataverse](Dataverse.md)|
|-|-|-|
