---
title: CLI for Microsoft 365 v7.6
date: 2024-03-31T08:00:00.000Z
author: Adam Wójcik
githubname: Adam-it
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Outlook
  - Purview
  - SharePoint
  - SharePoint Framework
type: popular
---

Introducing the latest release of CLI for Microsoft 365. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This minor release introduces several new commands that will enhance the quality of your Microsoft 365 experience.

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover an array of exciting features and improvements that will revolutionize your Microsoft 365 journey. 
 
## What's new

### New purview threatassessment commands

The release includes additional management features for purview. We added two new commands that will allow you to list and remove threat assessments. Let's see it in action. 

To list all threatassessment simply run:

```sh
m365 purview threatassessment list
```

You may also filter them by type, for example, to list threat assessments of type mail you may run:

```sh
m365 purview threatassessment list --type mail
```

To create a file threat assessment:

```sh
m365 purview threatassessment add --type file --expectedAssessment block --category malware --fileName 'test.txt' --path 'C:\Path\To\File.txt'
```

Or to Create a url threat assessment run:

```sh
m365 purview threatassessment add --type url --expectedAssessment block --category phishing --url 'http://contoso.com'
```

For more information check the following resources:
- [m365 purview threatassessment list](https://pnp.github.io/cli-microsoft365/cmd/purview/threatassessment/threatassessment-list/)
- [m365 purview threatassessment add](https://pnp.github.io/cli-microsoft365/cmd/purview/threatassessment/threatassessment-add/)

### Generate Azure DevOps Pipeline for a SharePoint Framework project

Till now CLI for Microsoft 365 allowed you to generate a CI/CD workflow for your SharePoint Framework project using the [m365 spfx project github workflow add](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-github-workflow-add/) command. In this release, we extended this capability and added the support for Azure DevOps Pipelines. It's important to understand that the command will not create the Azure DevOps pipeline. You will need to manually create it in Azure DevOps. The command will only create the workflow file which you can then push to your repo and create a new YAML pipeline based on it. The command needs to be run in the context of your SharePoint Framework project. The created .yml file will be present in the `.azuredevops/pipelines` directory in your project.

To add an Azure DevOps Pipeline for a SharePoint Framework project triggered on push to `main`, simply run: 

```sh
m365 spfx project azuredevops pipeline add
```

To add an Azure DevOps Pipeline for a SharePoint Framework project with `user` login method triggered on push to `dev` branch:

```sh
m365 spfx project azuredevops pipeline add --loginMethod "user" --branchName "dev"
```

To add an Azure DevOps Pipeline for a SharePoint Framework project with deployment to a site collection app catalog:

```sh
m365 spfx project azuredevops pipeline add --scope "sitecollection" --siteUrl "https://some.sharepoint.com/sites/someSite"
```

For more information check the following resources:
- [m365 spfx project azuredevops pipeline add](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-azuredevops-pipeline-add/)

### More features to manage your Outlook messages

CLI for Microsoft 365 already has several commands that allow you to manage Outlook messages. In this release, we added a new command that allows you to permanently remove a specific message from a mailbox.

To remove a specific message for the currently signed-in user:

```sh
m365 outlook message remove --id AAMkAGVmMDEzMTM4LTZmYWUtNDdkNC1hMDZiLTU1OGY5OTZhYmY4OABGAAAAAAAiQ8W967B7TKBjgx9rVEURBwAiIsqMbYjsT5e-T7KzowPTAAAAAAEMAAAiIsqMbYjsT5e-T7KzowPTAALvuv07AAA=
```

To remove a specific message from a specific mailbox specified by user ID using application permissions:

```sh
m365 outlook message remove --id AAMkAGVmMDEzMTM4LTZmYWUtNDdkNC1hMDZiLTU1OGY5OTZhYmY4OABGAAAAAAAiQ8W967B7TKBjgx9rVEURBwAiIsqMbYjsT5e-T7KzowPTAAAAAAEMAAAiIsqMbYjsT5e-T7KzowPTAALvuv07AAA= --userId 6799fd1a-723b-4eb7-8e52-41ae530274ca
```

To remove a specific message in a shared mailbox:

```sh
m365 outlook message remove --id AAMkAGVmMDEzMTM4LTZmYWUtNDdkNC1hMDZiLTU1OGY5OTZhYmY4OABGAAAAAAAiQ8W967B7TKBjgx9rVEURBwAiIsqMbYjsT5e-T7KzowPTAAAAAAEMAAAiIsqMbYjsT5e-T7KzowPTAALvuv07AAA= --userName sharedmailbox@contoso.com
```

For more information check the following resources:
- [m365 outlook message remove](https://pnp.github.io/cli-microsoft365/cmd/outlook/message/message-remove/)

### Retrieve retirement report of SharePoint Add-Ins and Azure ACS

Microsoft has announced that SharePoint Add-Ins and Azure ACS will be retired and as a result will stop working for new tenants as of November 1st, 2024 and they will stop working for existing tenants as of April 2nd, 2026. It's important to remember those dates and migrate your existing Add-in projects to SharePoint Framework-based solutions. In a large tenant that has many customizations, it may be hard to find all the places that require your attention. Thankfully CLI for Microsoft 365 may be the answer to that problem.

One of our contributors added a new script that allows us to get information about retirement-related components from a selected tenant. It covers key elements such as event receivers, SharePoint Add-Ins, and Azure Access Control Service (ACS). If you are eager to find out more check out the [script in our docs](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/sp-add-ins-and-azure-acs-retirement-report/).

## What's changed

Besides all these new commands, we've also made some changes to the existing commands. A few bugs have been fixed and the codebase has been polished. Some of our existing commands also got improved like the `spo folder add/set` commands that now have the possibility to set the folder color. Another great example is the `spo site recyclebinitem restore` that now has two new options that allow you to restore all items from the first and/or second-stage recycle bin.

If you are eager to go over all of the details and improvements added in this release, do not hesitate to check out the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v760) to find out more.

Also for more information check out the docs of the updated commands:
- [m365 spo folder add](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-add/)
- [m365 spo folder set](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-set/)
- [m365 spo site recyclebinitem restore](https://pnp.github.io/cli-microsoft365/cmd/spo/site/site-recyclebinitem-restore/)
- [m365 teams tab get](https://pnp.github.io/cli-microsoft365/cmd/teams/tab/tab-get/)
- [m365 teams team add](https://pnp.github.io/cli-microsoft365/cmd/teams/team/team-add/)
- [m365 spfx project github workflow add](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-github-workflow-add/)

## Upcoming changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

Right now, there are over 44 opened PRs with new awesome features that will be soon added to CLI for Microsoft 365, and 57 issues that are up for grabs. We're working hard to bring you even more exciting features and improvements in the next release. 

But we don't stop there. We value your input and ideas. If you have any suggestions for new commands, don't hesitate to share them with us. Create a [new issue](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=new-command.yml&title=New+command%3A+%3Cshort+description%3E) on our GitHub Issues list or join our vibrant [community Discord server](https://aka.ms/cli-m365/discord) to engage in discussions.

Sharing is Caring!

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Arjun Menon](https://github.com/arjunumenon)
- [János Dojcsák](https://github.com/dojcsakj)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Michał Kornet](https://github.com/mkm17)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Reshmee Auckloo](https://github.com/reshmee011)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Vedant Lakshminarayanan](https://github.com/Vedu1996)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shoutout and high fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to provide us with their insights:

- [Bart-Jan Dekker](https://github.com/bjdekker)
- [Jiahao Ji Zhou](https://github.com/JiahaoJiZhou)
- [LinChen](https://github.com/linchen2chris)
- [Nello D'Andrea](https://github.com/ferrarirosso)

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

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord), or [X](https://x.com/climicrosoft365). Don't hesitate to connect with us. Your input plays a vital role in shaping the future of CLI for Microsoft 365.
