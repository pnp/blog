---
title: "How to Fix the SPFx Error: 'Cannot find module node:os'"

# Add a summary to convince readers to read your article (recommended). It will display on the homepage.
summary: "Learn to fix the SharePoint Framework error 'Cannot find module node:os'. Understand the root cause and the simple solution: running npm install."
date: 2024-06-19T16:42:45-04:00

# Author. Your own name
author: "Andrew Connell"

# GitHub username.
githubname: "andrewconnell"

# Featured image
# To use, add an image named `thumbnail.jpg/png` to your page's images folder. Make sure to replace the placeholder image
images:
- images/feature.png

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
# Community posts should always use "Community post" as the categories
tags: ["SharePoint Framework (SPFx)"]
categories: ["Community post"]
canonicalURL: https://www.voitanos.io/blog/fix-spfx-eror-cannot-find-module/
---
> This article originally appeared on Andrew Connell's site, **[How to Fix the SPFx Error: 'Cannot find module node:os'](https://www.voitanos.io/blog/fix-spfx-eror-cannot-find-module/?utm_medium=website&utm_source=pnpblog&utm_campaign=How+to+Fix+the+SPFx+Error%3A+%27Cannot+find+module+node%3Aos%27)**.

From time to time, I see similar questions come up from students in my [SharePoint Framework courses](https://www.voitanos.io/courses-sharepoint-framework/). One that's come up a bunch recently is the first-run experience with a new project or one that you've recently acquired.

When you run any of the gulp tasks, like **gulp serve**, you get the following error: `Error: Cannot find module 'node:os'`, or something similar to it.

The full error looks something like this.

```console
Error: Cannot find module 'node:os'
Require stack:
- C:\dev\HelloWorld\node_modules\@azure\logger\dist\commonjs\log.js
- C:\dev\HelloWorld\node_modules\@azure\logger\dist\commonjs\debug.js
- C:\dev\HelloWorld\node_modules\@azure\logger\dist\commonjs\index.js
- C:\dev\HelloWorld\node_modules\@azure\core-http\dist\index.js
- C:\dev\HelloWorld\node_modules\@azure\storage-blob\dist\index.js
// omitted for brevity
- C:\Users\superman\AppData\Roaming\npm\node_modules\gulp\node_modules\gulp-cli\index.js
- C:\Users\superman\AppData\Roaming\npm\node_modules\gulp\bin\gulp.js
    at Function.Module._resolveFilename (internal/modules/cjs/loader.js:880:15)
    at Function.Module._load (internal/modules/cjs/loader.js:725:27)
    at Module.require (internal/modules/cjs/loader.js:952:19)
    at require (internal/modules/cjs/helpers.js:88:18)
    at Object.<anonymous> (C:\dev\HelloWorld\node_modules\@azure\logger\dist\commonjs\log.js:7:19)
    at Module._compile (internal/modules/cjs/loader.js:1063:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:1092:10)
    at Module.load (internal/modules/cjs/loader.js:928:32)
    at Function.Module._load (internal/modules/cjs/loader.js:769:14)
    at Module.require (internal/modules/cjs/loader.js:952:19) {
  code: 'MODULE_NOT_FOUND',
  requireStack: [ // omitted for brevity ]
}
```

Look towards the middle of that stack trace where it says `at Object.<anonymous>...`. This is a hint that the gulp CLI, running from within your global package registry (in this case it's running from the user's roaming profile). gulp is failing trying to load a package installed locally within the project.

See the problem now?

**It can't find the package that should be installed in the project**, which would be in the project's **./node_modules/@azure/logger** folder.

**OK, but why?**

## Root cause of the error

The most likely root cause of this error is that you haven't installed the project's dependencies or you haven't run **npm install** on your project.

Node.js projects, which is what a SharePoint Framework (SPFx) project is, almost never include their dependencies when we share them with others. This is a common practice among platforms that leverage package managers.

In the Microsoft world, even dotnet projects are subject to the same, having to install their dependencies using the nuget package manager.

## When does this happen?

Great question!

This obviously is the case when you create a brand new project.

But it's also applies when you acquire a project by cloning it from a repository such as one in Azure DevOps, GitHub, or other source code repository hosters.

Lacking the project's dependencies also applies when you download the project from some other resource, for example, like the [PnP SPFx sample repos](https://pnp.github.io/#samples) or as one of the samples from my [SharePoint Framework courses](https://www.voitanos.io/courses-sharepoint-framework/) that students have access to.

## What's triggering the error?

When you execute a gulp task, you use the globally installed gulp CLI. The CLI looks in your project for defined tasks. These tasks are specified within your project, particularly within some dependency packages that Microsoft includes with all new SPFx projects. If those tasks or dependencies are absent from the project, the process will fail, as depicted in the aforementioned error.

## So how do you fix it?

It's simple.

You just run **npm install** from the root of your project to download the project's dependencies.

This process downloads all of the project's dependencies into the **node_modules** folder. Afterwards, when you run any gulp tasks, gulp can locate the tasks defined within the project's dependencies and execute them as expected.

The dependencies are not included in the project because they are installed in the **node_modules** folder, which can become quite large. Generally, files within the **node_modules** folder are not included when checking into source code repositories to avoid duplication. There is no need to store this code in different repositories, which would only increase download sizes when local installations suffice. It's important to note that this is unrelated to SPFx.

Typically in Node.js projects, dependencies become apparent when you build or start the project. However, since the SharePoint Framework (SPFx) depends on gulp, and gulp relies on tasks defined within the project or its dependencies, you need to resolve these dependencies before running any gulp tasks.
