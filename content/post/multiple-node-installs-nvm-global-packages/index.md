---
title: Multiple Node.js Installs with NVM and Global Packages

# Add a summary to convince readers to read your article (recommended). It will display on the homepage.
summary: Explore the power of the Node Version Manager (NVM) in managing multiple Node.js installs for diverse SharePoint and Teams Toolkit projects.
date: 2024-06-27T14:27:22-04:00

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
tags: ["SharePoint Framework","SharePoint Framework (SPFx)","SPFx"]
categories: ["Community post","SPFx"]
canonicalURL: https://www.voitanos.io/blog/multiple-node-installs-nvm-global-packages/
---
> This article originally appeared on Andrew Connell's site, **[Multiple Node.js Installs with NVM and Global Packages](https://www.voitanos.io/blog/multiple-node-installs-nvm-global-packages/?utm_medium=website&utm_source=pnpblog&utm_campaign=blog&utm_content=Multiple+Node.js+Installs+with+NVM+and+Global+Packages)**.

Different SharePoint Framework (SPFx) and Microsoft Teams Toolkit (TTK) project types support various versions of Node.js. For instance, different SPFx versions require specific Node.js versions. This means you need the right version of Node.js installed on your machine to run and compile these projects.

The challenge arises when you need multiple versions of Node.js on your machine. By default, Node.js doesn't support this; it allows only one installation. However, using the popular tool [Node Version Manager (NVM)](https://www.voitanos.io/blog/better-node-js-install-management-with-node-version-manager/), available for both Mac OS and Windows, you can install multiple Node.js versions on your computer. This tool also simplifies switching between versions on the fly.

## How NVM works

When you switch to different versions of Node.js, NVM updates the `PATH` environment variable on your system. This change points to the folder containing the version of Node.js you wish to use.

The `PATH` environment variable, found on both Mac OS and Windows, serves a very important role. It specifies the directories to search when finding a command, meaning directories in the `PATH` allow you to run executables from those folders anywhere in your environment. In this case, you can execute the Node process from any location in your environment.

## NVM makes all Node.js installs 100% isolated from each other

It's important to note that each version of Node.js you install is completely isolated from the others. This isolation applies not only to the Node.js runtime executable, but also to the global package registry for each Node.js version.

For instance, if I have Node.js v16.20.2 installed with all necessary tools for the SPFx in the global registry - like Yeoman ([yo](https://www.npmjs.com/package/yo)), the Yeoman generator for SPFx ([@microsoft/generator-sharepoint](https://www.npmjs.com/package/@microsoft/generator-sharepoint)), and the Gulp CLI ([gulp-cli](https://www.npmjs.com/package/gulp-cli)) - these tools are only available for that specific Node.js version.

```console
> node -v
v16.20.2

// show contents
> npm list -g
/Users/ac/.nvm/versions/node/v16.20.2/lib
├── @microsoft/generator-sharepoint@1.19.0
├── corepack@0.17.0
├── gulp-cli@3.0.0
├── npm@8.19.4
└── yo@5.0.0
```

If I install a new version of Node.js v18.20.2 using NVM, the global registry of that installed version won't contain the three packages that I need.

```console
> node -v
v18.20.2
// show contents
> npm list -g
/Users/ac/.nvm/versions/node/v18.20.2/lib
├── corepack@0.25.0
└── npm@10.5.0
```

I'll need to reinstall those three packages into the same registry.

## NVM for Mac OS simplifies new Node.js version installs

One way to simplify the process is by using the Mac OS version of NVM. It contains the `--reinstall-packages-from` argument, which automatically installs all the same packages from another installed Node.js version to your new one. This argument can be used with the **nvm install** command.

```console
nvm install v18.20.1 --reinstall-packages-from=16.20.2
```

This will enable NVM to automate package handling after installing a new version of Node.js. It will automatically locate all packages installed in other versions of Node.js package registry and install them into the new version right away. This greatly simplifies and accelerates the process of installing a new version of Node.js.

## Learn more about NVM

Interested in learning more about NVM? Check out my other articles on NVM!

- [Manage Multiple Node.js Version Installs with NVM](https://www.voitanos.io/blog/better-node-js-install-management-with-node-version-manager/?utm_medium=website&utm_source=pnpblog&utm_campaign=blog&utm_content=Multiple+Node.js+Installs+with+NVM+and+Global+Packages)
- [Try SharePoint Framework Preview Releases with NVM](https://www.voitanos.io/blog/try-sharepoint-framework-preview-releases/?utm_medium=website&utm_source=pnpblog&utm_campaign=blog&utm_content=Multiple+Node.js+Installs+with+NVM+and+Global+Packages)
- [How to set up SPFx development environments for multiple SharePoint Server deployments](https://www.voitanos.io/blog/how-to-setup-sharepoint-framework-development-environment-for-multiple-sharepoint-server-deployments/?utm_medium=website&utm_source=pnpblog&utm_campaign=blog&utm_content=Multiple+Node.js+Installs+with+NVM+and+Global+Packages)
