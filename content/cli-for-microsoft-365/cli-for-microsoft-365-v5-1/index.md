---
title: "CLI for Microsoft 365 v5.1"
date: 2022-03-31T12:45:00-04:00
author: "Patrick Lamber"
githubname: plamber
categories: ["CLI for Microsoft 365"]
images:
- images/banner-cli-m365.png
tags: ["CLI for Microsoft 365","SharePoint", "SharePoint Framework (SPFx)"]
type: "regular"
---

## Manage Microsoft 365 and SharePoint Framework projects on any platform


CLI for Microsoft 365 is a cross-platform CLI that allows you to manage various configuration settings of Microsoft 365 and SharePoint Framework projects no matter which operating system or shell you use.

While building solutions for Microsoft 365 expands beyond the Windows operating system, managing many of the platform settings is possible only through PowerShell on Windows. As more and more users work on non-Windows machines, it’s inconvenient for them to have to use a Windows virtual machine to configure their tenants. With the CLI for Microsoft 365, you can configure your tenant no matter which operating system you use. Additionally, using CLI for Microsoft 365, you can manage your SharePoint Framework projects.

## The new version of CLI for Microsoft 365 – v5.1

Following our monthly release cadence, we’ve released a new version of the CLI for Microsoft 365 with some new capabilities. Here are a few of the most noteworthy additions.

> For the full list of what's new and changed, see the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v500).

### Validate correctness of a SharePoint Framework project

When building Microsoft 365 apps using the SharePoint Framework, it could happen that you hit a snag. To help you self-diagnose your project, we've worked with the SharePoint Framework engineering team, to provide you a command that validates the configuration of your project. If there are any issue, you'll get a report with additional explanation and a script that you can run to fix these issues!

To validate your SharePoint Framework project, change the working directory to your project and execute:

`m365 spfx project doctor --output md > "doctor-report.md"`

The command will analyze your project and store the list of findings in a file named _doctor-report.md_. For more information about validating SharePoint Framework projects, see the [documentation](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-doctor/).

### Register management application for Power Platform

More and more organizations are using Power Platform to automate business processes and build line of business applications. Using Power Platform APIs, they can automate managing these solutions. To use these APIs, you need to register your app as a management application with Power Platform.

If you wanted for example to use CLI for Microsoft 365 as a Power Platform management app, execute the following command:

`m365 pp managementapp add --appId 31359c7f-bd7e-475c-86db-fdb8c937548e`

For more information about working with Power Platform using CLI for Microsoft 365, see the [documentation](https://pnp.github.io/cli-microsoft365/cmd/pp/managementapp/managementapp-add/).

### Configure Microsoft 365 groups' behavior

You might want to specify the behavior of your Microsoft 365 Groups during provisioning. You can set specific group behaviors and resources to provision when creating a Microsoft 365 group.


||  |
|-------|---------------|
|      AllowOnlyMembersToPost  |            Only group _members_ can post conversations to the group.   |
|    HideGroupInOutlook   |   This group is hidden in Outlook experiences.            |
|     SubscribeNewGroupMembers  |      Group members are subscribed to receive group conversations.         |
|   WelcomeEmailDisabled    |     Welcome emails are not sent to new members.          |


For example, to create a public Microsoft 365 group and set it to not send welcome emails to new group members, execute:

`m365 aad o365group add --displayName Finance --description "This is the Contoso Finance Group. Please come here and check out the latest news, posts, files, and more." --mailNickname finance --welcomeEmailDisabled`

To create a public Microsoft 365 group and hide it from the Outlook experiences (web and client), execute:

`m365 aad o365group add --displayName Finance --description "This is the Contoso Finance Group. Please come here and check out the latest news, posts, files, and more." --mailNickname finance --hideGroupInOutlook`

For more information about creating Microsoft 365 groups, see the [CLI documentation](https://pnp.github.io/cli-microsoft365/cmd/entra/m365group/m365group-add/).

### Interacting with Microsoft 365 conversations becomes easier

In CLI for Microsoft 365 v5.0 we introduced commands to create Microsoft 365 group conversations. This release finalized the set of commands required to interact with conversations with the command **m365 aad o365group conversation post list**.

For more information about retrieving Microsoft 365 Group conversations, see the [CLI documentation](https://pnp.github.io/cli-microsoft365/cmd/entra/m365group/m365group-conversation-post-list/).

### New script samples

CLI for Microsoft 365 is a great tool both for quick adjustments to the configuration of your Microsoft 365 tenant as well as for automating more complex tasks. Because CLI for Microsoft 365 is cross-platform you can use it on any OS and in any shell. To help you get started using the CLI for Microsoft 365 for automation scenarios, we started gathering some [sample scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/introduction).

> If you have any scripts that you use frequently, please [share them with us](https://github.com/pnp/cli-microsoft365/issues) so that we can learn more about your common automation scenarios.

#### Migrate planner plan to SharePoint Online

Albert-Jan Schot contributed a sample that shows how to [migrate a Planner Plan to a SharePoint list](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/planner-migrate-sharepoint-list/).

#### Change group membership of all SharePoint Online sites

Another sample script that Arjun Menon published is how to [downgrade the permissions of all members of an owner group to the default member group.](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/change-owner-group-membership/)

## Contributors


This release wouldn't be possible without the help of (in alphabetical order):

*   [Reshmee Auckloo](https://github.com/reshmee011) 
*   [Milan Holemans](https://github.com/milanholemans)
*   [Akash Karda](https://github.com/akashkarda)
*   [Vipul Kelkar](https://github.com/vipulkelkar)
*   [Patrick Lamber](https://github.com/plamber)
*   [Martin Lingstuyl](https://github.com/martinlingstuyl) 
*   [Waldek Mastykarz](https://github.com/waldekmastykarz)
*   [Michaël Maillot](https://github.com/michaelmaillot)
*   [Arjun Menon](https://github.com/arjunumenon)
*   [Abderahman Moujahid](https://github.com/Abderahman88) 
*   [Nanddeep Nachan](https://github.com/nanddeepn)
*   [Albert-Jan Schot](https://github.com/appieschot)
*   [Garry Trinder](https://github.com/garrytrinder/)
*   [Jasey Waegebaert](https://github.com/Jwaegebaert)
*   [Adam Wójcik](https://github.com/Adam-it)

Thank you all for the time you chose to spend on CLI for Microsoft 365 and for your help to advance it!

## Work in progress


Here are some things that we're currently working on.

### [@me](https://techcommunity.microsoft.com/t5/user/viewprofilepage/user-id/31142) user tokens to simplify working with the current user

We're constantly seeking for ways to let you work with CLI for Microsoft 365 more efficiently. In the past, we've shipped support for [passing contents from files into options using the `@` token](https://pnp.github.io/cli-microsoft365/user-guide/using-cli/#passing-complex-content-into-cli-options) and [using server-relative URLs with SharePoint commands](https://pnp.github.io/cli-microsoft365/user-guide/using-cli/#working-with-sharepoint-urls-in-spo-commands). We're continuing the improvement by introducing [`@me` tokens](https://github.com/pnp/cli-microsoft365/issues/3056) to let you pass information about the current user into options.

### Microsoft 365 app commands

When building apps for Microsoft 365, next to your code, you also need to manage how your app is exposed to Microsoft 365. You need to register your application in Azure Active Directory, and depending what type of app you build, you might need to deploy it to an app catalog as well. All these properties are managed in different locations and we're thinking of ways that we could simplify it for you.

### OneNote commands

We are extending our commands with OneNote capabilities. We will start by giving you the ability to provision and retrieve OneNote notebooks.

### Interact with the Microsoft Search schema

We are not going to stop with OneNote commands but we will also extend our command palette in the Microsoft Search ecosystem. We are going to implement a command that will allow you to add a schema to a specific external connection for use in Microsoft Search.

What else could we simplify? Let us know what you think by helping out with one of our [open issues](https://github.com/pnp/cli-microsoft365/issues) or chime in on our [discussions](https://github.com/pnp/cli-microsoft365/discussions)!

## Try it today

Get the latest release of CLI for Microsoft 365 from npm by executing:

`npm i -g @pnp/cli-microsoft365`

Alternatively, you can get the latest release from Docker by executing:

`docker run --rm -it m365pnp/cli-microsoft365:latest`

If you need more help getting started or want more details about the commands or the architecture or the project, go to [aka.ms/cli-m365](https://aka.ms/cli-m365). And if you see any room for improvement, please, don't hesitate to reach out to us either on [GitHub](https://github.com/pnp/cli-microsoft365/discussions) or [Twitter](https://twitter.com/climicrosoft365).
