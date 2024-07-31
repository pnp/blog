---
title: CLI for Microsoft 365 v8
date: 2024-07-31T06:00:00.000Z
author: Arjun Menon
githubname: arjunumenon
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - SharePoint
  - Microsoft Teams
  - Microsoft Viva
  - Microsoft Entra
type: popular
lastmod: 2024-07-30T16:47:38.558Z
---

We've just published a new major version of the CLI for Microsoft 365 with new commands for working with and managing Microsoft 365 and SharePoint Framework projects on any platform.

## Manage Microsoft 365 and SharePoint Framework projects on any platform

[CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command line tool based on Node.js that helps you manage many things around Microsoft 365 and your SPFx project. You may manage OneDrive, Planner, Power Apps and Automate, Teams, Viva Engage (Yammer), SharePoint (of course), and many many more. The list keeps on growing and growing.

## The new major version of CLI for Microsoft 365 – v8

As we keep adding new commands to CLI for Microsoft 365, we noticed several areas that we should improve, to make using the CLI more intuitive and consistent. While our major releases are evolutionary in nature, we've also added some new commands and improvements to the CLI.

> To help you upgrade to v8, we prepared a summary of breaking changes and the recommended actions. For more information see the [v8 Upgrade Guidance](https://pnp.github.io/cli-microsoft365/v8-upgrade-guidance/) in our docs.

Following is an overview of the most noteworthy changes in v8.

> For the complete list of what's new and changed, see the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v800).

### Configure CI/CD pipelines for SPFx projects

We released a new command for adding CI/CD configurations to your existing SPFx projects in our previous versions for [Azure DevOps](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-azuredevops-pipeline-add/) and [GitHub Workflow](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-github-workflow-add/). In this version, we also have added a readymade script in our docs so that the users can easily invoke the script which will generate the needed YAML file based on your parameter value, be it GitHub Workflows or Azure DevOps. This would help the users minimize their effort to create the YAML file from scratch if they want to have a CI/CD pipeline enabled for their SPFx projects. You can get more details from [here](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/add-ci-cd-pipeline/).

### Content type field list command in SharePoint

Content types are a key feature in SharePoint that helps you to organize and manage your content in a more structured way. We already have a lot of commands for managing the content types, be it site content type or list content type. 
Now we have added a new command for listing the columns/fields associated with the site and the list content types

For retrieving the fields associated with a site content type, run: 

```sh
m365 spo contenttype field list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --contentTypeId "0x01"
```

For retrieving the fields associated with a list content type in the Documents library, run: 

```sh
m365 spo contenttype field list --webUrl https://contoso.sharepoint.com/sites/contoso-sales --contentTypeName "Document" --listTitle "Documents"
```

For more information, check the following resources:
- [m365 spo contenttype field list](https://pnp.github.io/cli-microsoft365/cmd/spo/contenttype/contenttype-field-list/)

### Microsoft Teams

CLI for Microsoft 365 already has a lot of commands for managing Microsoft Teams. In this feature, we have added 2 more new commands to the existing inventory of commands. 

#### Getting attendance reports for meetings

We have added a command for [getting the attendance report](https://pnp.github.io/cli-microsoft365/cmd/teams/meeting/meeting-attendancereport-get/) of your meetings easily using a command. This is going to be super useful if you want to generate the attendance reports for your completed meetings.

For getting the specified attendance report made for the currently signed-in user and Microsoft Teams meeting with the given ID, run: 

```sh
m365 teams meeting attendancereport get --meetingId MSo1N2Y5ZGFjYy03MWJmLTQ3NDMtYjQxMy01M2EdFGkdRWHJlQ --id a8634e64-3147-4a56-9b19-cc822e9c7972
```

For getting the specified attendance report made for another user and Microsoft Teams meeting with the given ID, run: 

```sh
m365 teams meeting attendancereport list --userName garthf@contoso.com --meetingId MSo1N2Y5ZGFjYy03MWJmLTQ3NDMtYjQxMy01M2EdFGkdRWHJlQ --id a8634e64-3147-4a56-9b19-cc822e9c7972
```

For more information, check the following resources:
- [m365 teams meeting attendancereport get](https://pnp.github.io/cli-microsoft365/cmd/teams/meeting/meeting-attendancereport-get/)

#### Removing a message from a Microsoft Teams team channel

We also have added a new command for [removing the message](https://pnp.github.io/cli-microsoft365/cmd/teams/message/message-remove/) from a Microsoft Teams team channel with a single command.

For removing a message by using channel ID, run: 

```sh
m365 teams message remove --teamId 5f5d7b71-1161-44d8-bcc1-3da710eb4171 --channelId 19:4a95f7d8db4c4e7fae857bcebe0623e6@thread.tacv2 --id 1540747442203
```

For removing a message using channel display names, run:

 ```sh
m365 teams message remove --teamName Marketing --channelName Branding --id 1540747442203
```

For more information, check the following resources:
- [m365 teams message remove](https://pnp.github.io/cli-microsoft365/cmd/teams/message/message-remove/)

### Other significant changes and bug fixes

#### Fixed bug for CLI in Azure Cloud shell

CLI for Microsoft 365 has been installed by default in Azure Cloud Shell for a couple of years. For the past weeks, there was an issue when we tried to run the CLI for Microsoft 365 from Azure Cloud shell. In this version, we have fixed the issue and now you can run the CLI for Microsoft 365 from Azure Cloud shell without any issues.

#### Fixed bug when listing the flows using Admin

There was a bug when we tried to list the flows using the admin account. Now this issue is fixed and you can list the flows using the admin account without any issues. The issue was because the API that we were using was deprecated and now we have updated the command to use the new API (v2). The change also has brought in a breaking change whose details can be read from [here](https://pnp.github.io/cli-microsoft365/v8-upgrade-guidance#adjusted-output-of-flow-list-command).

#### Enhancement to Entra Group and Entra App commands

In this version, we have added the ability to set many more properties related to the notifications to the Microsoft Entra group so that owners can easily manage while using the scripts for provisioning or managing the Microsoft Entra Groups.

We have added the ability to remove the app permission from your Microsoft Entra app even if you mention it in the scope in an unqualified way (like `Sites.Read.All` instead of `https://graph.microsoft.com/Sites.Read.All`). This will help users easily remove app permissions from the Entra app.

### What's next

Here are some things that we are currently working on. We have plans to release v9 version of CLI with lot of improvements and new features. Here are some of the signifant features that we are working on.

#### Commands for SharePoint Embedded

SharePoint Embedded is a cloud-based file management service that helps you build applications that can interact with SharePoint files. We are working on adding a set of commands to help you manage your SharePoint Embedded containers. If you are working with SharePoint embedded or are planning to work, we'd love to hear from you about what you'd like to see in the CLI. You can share your thoughts in the epic we have created for all the commands related to SharePoint Embedded [here](https://github.com/pnp/cli-microsoft365/issues/5731)

#### Version and storage management commands

We are planning to bring in a set of commands to help you manage the versions and storage of your files in SharePoint. This involves various commands through which you can manage your versions, storages, archival, etc. of your tenant using CLI for Microsoft 365. We would love to hear from you if you have any suggestions. You can share your thoughts in the epic we have created for all the commands related to version and storage management [here](https://github.com/pnp/cli-microsoft365/issues/5982)

#### Enhancement in the validation approach used in Codebase

We are planning to enhance the validation approach used in the codebase. Although we have a centralized validation in place, introduction to Zod would ensure the development of the commands and the validation of the inputs are more consistent and easy to maintain. We would love to hear from you if you have any suggestions. Please feel free to pitch in with your suggestions [here](https://github.com/pnp/cli-microsoft365/issues/5639).

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [János Dojcsák](https://github.com/dojcsakj)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Machacek](https://github.com/MartinM85)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)
- [Nello D'Andrea](https://github.com/ferrarirosso)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

CLI for Microsoft 365 wouldn't be where it is today if it weren't for our users who provided us with feedback. High fives to the following people who took the time to share their feedback and ideas for improvement with us (in alphabetical order):

- [Julian Pawlowski](https://github.com/jpawlowski)
- [louderthanloud123](https://github.com/louderthanloud123)
- [Michał Kornet](https://github.com/mkm17)

### Discussions

CLI for Microsoft 365 is constantly growing and evolving. We're always looking for ways to improve. There are still many areas not covered by the CLI as well as many amazing ideas for unique features the tool might provide. Your feedback will help us make the right decisions in which areas we should focus on. If you want to help out please do join the currently open [discussions](https://github.com/pnp/cli-microsoft365/discussions)

What else could we simplify? Let us know what you think by helping out with one of our [open issues](https://github.com/pnp/cli-microsoft365/issues) or chiming in on our [discussions](https://github.com/pnp/cli-microsoft365/discussions)!

## Try it today

Get the latest release of CLI for Microsoft 365 from npm by executing:

```bash
npm i -g @pnp/cli-microsoft365
```

Alternatively, you can get the latest release from Docker by executing:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

If you need more help getting started or want more details about the commands, architecture, or project, go to [aka.ms/cli-m365](https://aka.ms/cli-m365). If you see any room for improvement, please, don't hesitate to reach out to us either on [Discord](https://discord.com/invite/7rfW4kg6B5), [GitHub](https://github.com/pnp/cli-microsoft365/discussions), or [X](https://twitter.com/climicrosoft365).

