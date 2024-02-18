---
title: "Power Platform? I'm a developer!"
date: 2024-02-18T08:40:00-04:00
author: "Kinga Kazala"
githubname: kkazala
categories: ["Community post"]
images:
- images/thumbnail.png
tags: []
type: "regular"
---

## Power Platform extensibility

### Contents

1. **Power Platform? I'm a developer!**
1. [Power Apps](PowerApps.md)
1. [Power Automate](./PowerAutomate.md)
1. [Dataverse](Dataverse.md)

When building Power Platform solutions, we should first evaluate Platform capabilities and use as much of low-code as possible.
This means learning which controls are available, how to use [Power Fx](https://learn.microsoft.com/en-us/power-platform/power-fx/overview) (if you ever wrote Excel formula, you will feel at home), deciding which parts of business logic should be executed client side, and when it's time to use Power Automate or other capabilities instead.

Make sure you are familiar with [Where to place logic: Canvas apps, model-driven apps, Microsoft Dataverse, or Power Automate flows?](https://learn.microsoft.com/en-us/power-apps/guidance/planning/logic) and keep an eye on the [Release plans for Dynamics 365, Power Platform, and Cloud for Industry - Dynamics 365](https://learn.microsoft.com/en-us/dynamics365/release-plans/) to learn about new features as they are prepared for release.

>As a developer, you should approach apps on Microsoft Power Platform from the perspective that **writing code […] should be** considered as an **exception** to no-code and low-code approaches. […]
Microsoft Power Platform often implements something in a particular way that benefits the platform. This may be different if you're used to doing it in custom application code. It isn't uncommon for developers that are new to building Microsoft Power Platform solutions to try to customize the platform the way they used to build custom apps previously. This should be avoided when possible and you should try to take advantage of what the platform does well, rather than try to change it to what you are used to doing.
>
>Source: [Determine when to configure or when to code](https://learn.microsoft.com/en-us/training/modules/introduction-power-platform-extend/configure-code)

But what happens if, after extensive evaluation, you see that the existing controls or declarative process don't meet your requirements? Depending on [where you want to place your logic](https://learn.microsoft.com/en-us/power-apps/guidance/planning/logic), you may start coding using either **Power Fx**, **Typescript** or **.NET**.

Yes, _"coding in Power Fx"_; it's getting better and better, and is now offering [error handling](https://learn.microsoft.com/en-us/power-platform/power-fx/error-handling) (preview feature at the time of writing), [named formulas](https://learn.microsoft.com/en-us/power-platform/power-fx/reference/object-app#formulas-property), [assertion](https://learn.microsoft.com/en-us/power-platform/power-fx/reference/function-assert), [regular expressions](https://learn.microsoft.com/en-us/power-platform/power-fx/reference/function-ismatch), etc (please always ensure the feature you want to use is already generally available, as experimental and preview features are not meant for production).

And if you are still not convinced that building [fusion team ](https://learn.microsoft.com/en-us/power-platform/developer/fusion-development) makes sense in your project, remember that professional developers bring more to the table than just the coding skills. It makes sense to include them from the start, because they:

- understand and adhere to principles of [well architected framework](https://learn.microsoft.com/en-us/industry/well-architected/overview) and apply them from early stages of solution design,
- instinctively follow security best practices, ensuring that the solution is "secure by design". That's important, because one day you may find that you have been [hacked by a Power App](https://dev.to/wyattdave/ive-just-been-hacked-by-a-power-app-1fj4).
- will accelerate the implementation and ensure best practices in terms of design, security and governance are followed from the beginning.


## Extensibility options

The image below presents a summary of currently available options for implementing business logic. It includes low-code approaches like custom canvas components or business rules, and pro-code like React components, add-ins etc.

The following sections present the available options in more detail, outlining differences and whenever applicable, the limitations.

![Extensibility options](./images/Extensibility.png)

For a detailed summary of the above options, see the following articles:

- [Power Apps](powerApps.md)
- [Power Automate](./PowerAutomate.md)
- [Dataverse](Dataverse.md)
