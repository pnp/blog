---
title: "Which JavaScript framework can I use with SharePoint Framework"
date: 2021-06-23T11:55:00-04:00
author: "Waldek Mastykarz"
githubname: WaldekMastykarz
categories: ["Community post"]
images: []
tags: []
type: "regular"
---

You want to build an app using SharePoint Framework and wonder which
framework you should use? Here's my personal advice.

## Extend conversations and portals on Microsoft 365

Using [SharePoint
Framework](https://learn.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview?WT.mc_id=m365-16871-wmastyka)
you can extend conversations and portals on Microsoft 365. With
SharePoint Framework, you can build widgets, called [web
parts](https://learn.microsoft.com/sharepoint/dev/spfx/web-parts/overview-client-side-web-parts?WT.mc_id=m365-16871-wmastyka),
which users can put on pages or open as tabs in Teams. You can also use
SharePoint Framework to [add code to existing
pages](https://learn.microsoft.com/sharepoint/dev/spfx/extensions/get-started/build-a-hello-world-extension?WT.mc_id=m365-16871-wmastyka)
or [change how data in lists is
displayed](https://learn.microsoft.com/sharepoint/dev/spfx/extensions/get-started/building-simple-field-customizer?WT.mc_id=m365-16871-wmastyka).

If you have experience building web apps using JavaScript, you can build
apps using SharePoint Framework. SharePoint Framework is based on open
source tools that you already know, like npm, TypeScript, Yeoman,
webpack, and gulp, and there is very little that you have to learn to
build your first app.

## Can I use \[your-framework-here\] with SharePoint Framework?

There are many JavaScript frameworks that you can use to build web apps.
But can you use any one of them when building apps with SharePoint
Framework?


### Use any JavaScript framework

When building apps using SharePoint Framework, you can use any
JavaScript framework. If you're comfortable working with Vue or
Handlebars, or any other framework, you don't need to learn any other
framework. You can be productive from the start and focus on building
your app. That said, there is a caveat\...

While you can use any JavaScript framework when building apps with
SharePoint Framework, you will have the best development experience when
using React. Here is why.

### Integrated dev experience

From the development experience point of view, React is integrated with
SharePoint Framework. Using the SharePoint Framework Yeoman generator
you can create a project that uses React. The necessary configuration,
and build and packaging tasks are already configured and ready for you
to use. In comparison, if you choose to use another framework, you will
need to find a way to integrate its tooling, like the ng CLI, into
SharePoint Framework so that you can work efficiently.

### Seamless UX integration

Next to the SharePoint Framework, Microsoft offers [Fluent UI
React](https://developer.microsoft.com/fluentui?WT.mc_id=m365-16871-wmastyka#/controls/web):
a set of ready-to-use components that help you make your app look like
Microsoft 365. Rather than spending time on building CSS and ensuring
that your app looks as intended in the different browsers, you can save
a ton of time and use Fluent UI components instead. But only if you use
React. If you use a different framework, you will need to take care of
presenting the data yourself.

### First-load performance

Finally, from the performance point of view, React is already loaded on
SharePoint pages. If you build your app on React, your app will load
faster. That said, the difference of using React instead of any other
framework will be visible only on the initial load. Because once users
download your app, it will load from their cache the next time they use
it, making the difference imperceptible.

## The verdict

You can use any JavaScript framework to build apps using SharePoint
Framework. SharePoint Framework allows you to benefit from your existing
knowledge and use the tools that you already know to build apps for the
250 million people using Microsoft 365.


If you're just starting with web development, I'd recommend you to
learn React. It will give you the smoothest experience when building
apps for Microsoft 365. There are many tools and samples built for React
both by Microsoft and the community which you can use to learn and speed
up building your apps.
