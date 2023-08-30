---
title: CLI for Microsoft 365 v6.11
date: 2023-08-31T08:00:00.000Z
author: Adam Wójcik
githubname: adam-it
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - SharePoint
  - SharePoint Framework (SPFx)
  - Power Apps
type: popular
---

Introducing the latest release of CLI for Microsoft 365

[CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command line tool based on Node.js that helps you manage many things around Microsoft 365 and your SPFx project. You may manage OneDrive, Planner, Power Apps and Automate, Teams, Viva Engage (Yammer), SharePoint (of course), and many many more. The list keeps on growing and growing. In this minor release, we introduced new commands as well as a tonne of improvements.

> Explore the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v6110) to discover an array of exciting features and improvements that will revolutionize your Microsoft 365 journey.

## Last minor release before v7

Before we will have a deep dive on what's added in this release it's worth mentioning that the v7 release is just around the corner. We are planning to go live next month so be sure you prepare yourself in advance. You may check out the [upgrade guidance](https://github.com/pnp/cli-microsoft365/blob/v7/docs/docs/v7-upgrade-guidance.mdx) directly in the repo today.

You may also install the upcoming release and give it a try:

```sh
npm i -g @pnp/cli-microsoft365@seven
```

## What's new

In this minor release, we added a couple of new commands and enhancements to the existing functionality. Check out some of the awesome stuff added and be sure to try them out.

### Power Apps management

In the last release we introduced a couple of new commands that allowed you to manage Power Apps and we are not slowing down. In this release, we added two more commands to give you more control over permission management.

The first one is the `pa app permission ensure` command that will allow you to assign or update permissions to a Power Apps app. Let's check out what is possible.

For example to add a co-owner permissions for a security group to a Power Apps app simply run:

```sh
m365 pa app permission ensure --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0 --groupName Developers --roleName CanEdit
```

Or to share a Power Apps app with everyone in the tenant type:

```sh
m365 pa app permission ensure --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0 --roleName CanView --tenant
```

We also introduced a new command that allows you to remove permissions to a Power Apps app.

Thanks to that you may for example remove permissions of a specific user for a specific app by simply:

```sh
m365 pa app permission remove --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0 --userName john.doe@contoso.com 
```

Or to unshare a Power Apps app with the entire tenant

```sh
m365 pa app permission remove --appName bc9f0a7e-53df-46af-b669-5888bb2f63d0 --tenant
```

- [m365 pa app permission ensure](https://pnp.github.io/cli-microsoft365/cmd/pa/app/app-permission-ensure/)
- [m365 pa app permission remove](https://pnp.github.io/cli-microsoft365/cmd/pa/app/app-permission-remove/)

### CLI config management

You may configure CLI for Microsoft 365 to meet your personal preferences. Thanks to that you may for example configure how CLI should behave in case a URL is returned or what should be the default output mode, or configure CLI to prompt for missing values in required options, or so much much more that if you haven't, you should definitely [give it a check](https://pnp.github.io/cli-microsoft365/user-guide/configuring-cli). In this release, we added a command that allows you to have a quick overview of all self-set configurations.

To list all self-set configuration keys with their value, simply run:

```sh
m365 cli config list
```

For more information, check out:

- [m365 cli config list](https://pnp.github.io/cli-microsoft365/cmd/cli/config/config-list/)

### Add a CI/CD pipeline to your SPFx project with ease

I will be honest this is one of my personal favorites. Who wouldn't want some kind of flow that will automagically build, package, and deploy your solution after adding a new feature to your code base? In the IT world, we use workflows (pipelines) for exactly that. We added a new command that will generate a YAML GitHub workflow for a given SPFx project which will give you a huge head start in creating a good quality CI/CD flow. Let's check out what's possible.

To add a GitHub workflow for a SharePoint Framework project with an application login method triggered on push to main you only need to run:

```sh
m365 spfx project github workflow add 
```

To do the same but with user login method just run:

```sh
m365 spfx project github workflow add --manuallyTrigger --loginMethod "user"
```

And if you want to have a CI/CD pipeline to deploy your app to a Site level app catalog just run:

```sh
m365 spfx project github workflow add --scope "sitecollection" --siteUrl "https://some.sharepoint.com/sites/someSite"
```

For more information, check out the documentation for each command:

- [m365 spfx project github workflow add](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-github-workflow-add/)

### SharePoint Framework Projects v1.18.0-beta.5 support

Staying up to date is crucial if you want to be prepared for what’s coming but upgrading an SPFx solution may sometimes not be a fair fight. Luckily for you, CLI for Microsoft 365 has a couple of commands that may save you a lot of time. In this release, we added the support for SPFx `v1.18.0-beta.5` to three of our most popular commands: `spfx project upgrade`, `spfx project doctor`, and `spfx doctor`.

Here are the commands to get you started:

```sh
m365 spfx project upgrade --output md
```

```sh
m365 spfx doctor --output text
```

```sh
m365 spfx project doctor --output md
```

For more information, check out the documentation for each command:

- [spfx project upgrade](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade/)
- [spfx doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor/)
- [spfx project doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-doctor/)

### Extended the 'spo file copy' command

In this release, we also improved the `spo file copy` command with two new options. One of them is definitely worth checking as it allows to clear the author and created date. Let's check it out in action.

To copy a file by site-relative URL to a document library in another site collection and clear the author and created date simply run:

```sh
m365 spo file copy --webUrl https://contoso.sharepoint.com/sites/project --sourceUrl "/Shared Documents/Document.pdf" --targetUrl "/sites/IT/Shared Documents" --resetAuthorAndCreated
```

Check out the [related issue](https://github.com/pnp/cli-microsoft365/issues/5340) to find out more.

### New contributing guidance

Not so long ago we migrated our docs to a new static site generator adding a couple of awesome features along the way like AI search powered by [Mendable](https://www.mendable.ai/). In this release, we worked on adding more valuable content and added a new section with contributing guidance to the CLI for Microsoft 365. How to add a new command? How to add unit tests? How to add a new script sample? All that and much much more will become super clear after [checking out our docs](https://pnp.github.io/cli-microsoft365/contribute/contributing-guide).

### The fun never stops, improving our codebase

In this minor release, we continued our work on refactoring the code base to embrace the asynchronous programming model using **async/await**. All this would not have been possible without our awesome contributors and their dedication to CLI for Microsoft 365. Just have a look at the [list](https://github.com/pnp/cli-microsoft365/issues/3618) to get a feeling of the amount of work already done and what is left.

We've also taken the first steps to refactor our codebase to centralize the shared code in util functions. This refactor will bring a performance boost to the tool as well as allow easier integration and testing. Check out the [related issue](https://github.com/pnp/cli-microsoft365/issues/4531) to go over the details.

### What else

If you are eager to go over all of the details and improvements added in this release, do not hesitate to check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v6110) to find out more.

## Upcoming changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

### Expanding command arsenal

Our relentless pursuit of empowering your Microsoft 365 experience continues. We're actively working on introducing more commands to CLI for Microsoft 365. From Power Platform to SharePoint Online, we're exploring various services to enhance your command-line capabilities. Additionally, we're dedicated to refactoring our codebase to embrace the power of async/await, further improving performance and readability.

But we don't stop there. We value your input and ideas. If you have any suggestions for new commands, don't hesitate to share them with us. Create a [new issue](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=new-command.yml&title=New+command%3A+%3Cshort+description%3E) on our GitHub Issues list or join our vibrant [community Discord server](https://aka.ms/cli-m365/discord) to engage in discussions.

Together, let's shape the future of CLI for Microsoft 365 and unlock even greater possibilities.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Arjun Menon](https://github.com/arjunumenon)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Patrick Lamber](https://github.com/plamber)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

We express our deepest gratitude for the time and effort you have invested in CLI for Microsoft 365, improving its progress and enriching its capabilities. Your contributions have played a significant role in advancing this project and empowering users worldwide. Thank you for your commitment and valuable assistance!

## Get Started Today!

Experience the power of CLI for Microsoft 365 by getting the latest release from npm:

```bash
npm i -g @pnp/cli-microsoft365
```

Alternatively, you can access the latest release from Docker:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

## Need More Information?

For additional guidance on getting started or to explore detailed information about commands, architecture, or the project itself, visit [aka.ms/cli-m365](https://aka.ms/cli-m365).

## Stay Connected!

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord), or [Twit... sorry X](https://twitter.com/climicrosoft365). Don't hesitate to connect with us; your input plays a vital role in shaping the future of CLI for Microsoft 365.
