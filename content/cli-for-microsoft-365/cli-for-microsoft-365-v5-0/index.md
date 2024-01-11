---
title: "CLI for Microsoft 365 v5.0"
date: 2022-02-28T12:45:00-04:00
author: "Waldek Mastykarz"
githubname: waldekmastykarz
categories: ["CLI for Microsoft 365"]
images:
- images/banner-cli-m365.png
tags: ["CLI for Microsoft 365","SharePoint", "SharePoint Framework (SPFx)"]
type: "regular"
---

We've just published a new major version of the CLI for Microsoft 365 with new commands for working with and managing Microsoft 365 and SharePoint Framework projects on any platform.

## Manage Microsoft 365 and SharePoint Framework projects on any platform

CLI for Microsoft 365 is a cross-platform CLI that allows you to manage various configuration settings of Microsoft 365 and SharePoint Framework projects no matter which operating system or shell you use.

While building solutions for Microsoft 365 expands beyond the Windows operating system, managing many of the platform settings is possible only through PowerShell on Windows. As more and more users work on non-Windows machines, it’s inconvenient for them to have to use a Windows virtual machine to configure their tenants. With the CLI for Microsoft 365, you can configure your tenant no matter which operating system you use. Additionally, using CLI for Microsoft 365, you can manage your SharePoint Framework projects.

## New version of CLI for Microsoft 365 – v5

Breaking out from our regular release cycle, we've just released a new major version of CLI for Microsoft 365. Typically, our major releases are evolutionary, but this time around, next to the few necessary changes, together with our awesome community we've released many new commands and improvements! Here are a few of the most noteworthy additions.

> For the full list of what's new and changed, see the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes/#v500).

### New major version

Typically, we release a major version once a year. While we strive for all commands to be consistent, there are cases where in hindsight, we need to add changes. If they require us to break the contract, we properly communicate it by including them in a major version.

This time around, we're affected by the deprecation of the Azure AD Graph API, which has been announced in June 2020. The API will stop working in June 2022. To ensure that you can keep using CLI for Microsoft 365 without any interruptions, we decided to update the few commands that were using it. While the change is relatively small, it could be backwards incompatible for your scripts.

To help you understand that impact of the change, we prepared [guidance for upgrading to using CLI for Microsoft 365 v5](https://pnp.github.io/cli-microsoft365/v5-upgrade-guidance/).

### Upgrade SharePoint Framework projects to v1.14

Mid-February 2022, Microsoft released a new version of SharePoint Framework - the development model for extending Microsoft Viva Connections, Microsoft Teams and SharePoint. To help you upgrade your projects we've updated CLI for Microsoft 365 with the support for this new version.

To upgrade your SPFx project to this version, change the working directory to your project and execute:

```bash
m365 spfx project upgrade --output md > report.md
```

We'd also recommend that you try a richer upgrade report based on the Visual Studio Code CodeTour extension:

```bash
m365 spfx project upgrade --preview --output tour
```

To help you verify that your machine has the necessary prerequisites to start building on SPFx v1.14, we've also updated the `spfx doctor` command.

To verify that your environment meets the requirements to work with the SharePoint Framework, run:

```bash
m365 spfx doctor
```

For more information about upgrading SharePoint Framework projects, see the [CLI documentation](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade/).

### Integrate CLI for Microsoft 365 in your app

Recently we've seen an increasing demand to integrate CLI for Microsoft 365 in other solutions. CLI offers advanced capabilities for managing resources in the Microsoft cloud that are a great addition to other solutions. Instead of reinventing the wheel, why not use the CLI for Microsoft 365?

Originally, if you wanted to integrate CLI for Microsoft 365, you had to interface with it through the shell, basically treating it as any other executable. In CLI for Microsoft 365 v5, we introduced an API that you can call to execute any CLI command from your Node.js-based application.

For more information about using CLI for Microsoft 365 programmatically, check out our [integration documentation](https://pnp.github.io/cli-microsoft365/user-guide/use-cli-api/). This is the first version of our API and we'd love to hear from you [how we could improve it](https://github.com/pnp/cli-microsoft365/discussions).

### Monitor tenant health

As more and more organizations embrace remote and hybrid work and Microsoft 365 becomes a critical part of their collaboration infrastructure, they need to be able to monitor its status and respond to any changes.

To help you keep track of your Microsoft 365 tenant's health, in this version we introduced a set of commands for retrieving [service update messages](https://pnp.github.io/cli-microsoft365/cmd/tenant/serviceannouncement/serviceannouncement-message-list/), [service health issues](https://pnp.github.io/cli-microsoft365/cmd/tenant/serviceannouncement/serviceannouncement-healthissue-list/) and [tenant health](https://pnp.github.io/cli-microsoft365/cmd/tenant/serviceannouncement/serviceannouncement-health-list/) information.

We hope these commands will help you monitor the status of your tenant. For more information about how they work and what type of information you can retrieve, check out the documentation.

### Clean up Azure AD app registrations

One of the main building blocks for Microsoft 365 apps are Azure AD app registrations. With the advancement in tooling, creating new apps comes often down to a couple of clicks and sometimes it's even totally abstracted away from you.

To help you keep your tenant clean, we release a command that allows you to easily remove Azure AD app registrations that you no longer need.

To remove an Azure AD app registration, run:

```bash
m365 aad app delete --appId d75be2e1-0204-4f95-857d-51a37cf40be8
```

For more information about managing Azure AD apps using CLI for Microsoft 365, see the [documentation](https://pnp.github.io/cli-microsoft365/cmd/aad/app/app-remove/).

### Get Planner tasks

We continue to extend our support for Planner and in this version we added commands that allow you to retrieve information about tasks.

To get a task, run:

```bash
m365 planner task get --id 'vzCcZoOv-U27PwydxHB8opcADJo-'
```

For each task, you can retrieve additional information using:

```bash
m365 planner task details get --taskId 'vzCcZoOv-U27PwydxHB8opcADJo-'
```

For more information about working with Planner see our [documentation](https://pnp.github.io/cli-microsoft365/cmd/planner/plan/plan-list/).

### New script samples

CLI for Microsoft 365 is a great tool both for quick adjustments to the configuration of your Microsoft 365 tenant as well as automating more complex tasks. Because CLI for Microsoft 365 is cross-platform you can use it on any OS and in any shell. To help you get started using the CLI for Microsoft 365 for automation scenarios, we started gathering some [sample scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/introduction).

> If you have any scripts that you use frequently, please [share them with us](https://github.com/pnp/cli-microsoft365/issues) so that we can learn more about your common automation scenarios.

#### Get attachment names from SPO lists

Veronique Lengelle contributes a sample that shows how to [get names of attachments for items stored in a SharePoint list](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/list-attachment-names-from-spo-lists/).

#### List all documents with a specific name within a SharePoint site

Another sample script that Veronique published is how to [get all documents from a specific site with a specific name](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/list-all-files-specific-name/), for example search all documents where the word "CLI" is part of the file name.

#### Check all users for known breaches with HIBP

As hacks and data breaches become more prevalent, you should regularly track if any of your credentials have been leaked in the open.

Albert-Jan Schot contributed a script that shows how you can [use the Have I Been Pwned service, to check if any accounts from your Azure Active Directory have be...](https://pnp.github.io/cli-microsoft365/sample-scripts/aad/analyze-users-haveibeenpwnd/).

#### List items with unique permissions

Veronique Lengelle submitted another script, inspired by Salaudeen Rajack, that shows how to [get list items with unique permissions](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/list-all-items-with-unique-permissions/). Using this script you can understand the security configuration of your data and verify that it's correctly configured.

#### Detecting PII exist in SharePoint List using AWS Comprehend

Joseph Velliah contributed a script that shows how to [use AWS Comprehend to detect personally identifiable information (PII) stored in SharePoint lists](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/detecting-pii-exists-in-sharepointlist-column/). Different organization have different regulations when it comes to handling PII and this script is the first step of the governance, allowing you to find where PII is stored in your tenant.

## Contributors

This release wouldn't be possible without the help of (in alphabetical order):

*   [Reshmee Auckloo](https://github.com/reshmee011)
*   [Robert Dyjas](https://github.com/robdy)
*   [Akash Karda](https://github.com/akashkarda)
*   [Patrick Lamber](https://github.com/plamber)
*   [Veronique Lengelle](https://github.com/veronicageek)
*   [Martin Lingstuyl](https://github.com/martinlingstuyl)
*   [Michaël Maillot](https://github.com/michaelmaillot)
*   [Waldek Mastykarz](https://github.com/waldekmastykarz)
*   [Kevin McDonnell](https://github.com/kevmcdonk)
*   [Arjun Menon](https://github.com/arjunumenon)
*   [Abderahman Moujahid](https://github.com/Abderahman88)
*   [Nanddeep Nachan](https://github.com/nanddeepn)
*   [Smita Nachan](https://github.com/SmitaNachan)
*   [pramod74](https://github.com/pramod74)
*   [Albert-Jan Schot](https://github.com/appieschot)
*   [Garry Trinder](https://github.com/garrytrinder/)
*   [Joseph Velliah](https://github.com/sprider)
*   [Jasey Waegebaert](https://github.com/Jwaegebaert)
*   [Rabia Williams](https://github.com/rabwill)

Thank you all for the time you chose to spend on CLI for Microsoft 365 and your help to advance it!

## Work in progress

Here are some things that we're currently working on.

### Validate your SharePoint Framework project's integrity

SharePoint Framework is one of the most popular development models for building enterprise apps for Microsoft 365. It's highly flexible and allows you to build solutions for many different scenarios. But as you build your apps, install additional packages and change your project's configuration, you might run into errors.

Together with Alex Terentiev from SharePoint Framework engineering, we're working on a [command that will allow you to verify your project's configuration](https://github.com/pnp/cli-microsoft365/issues/3057) before you submit an issue to the sp-dev-docs repo.

### `@me` user tokens to simplify working with the current user

We're constantly seeking for ways to let you work with CLI for Microsoft 365 more efficiently. In the past, we've shipped support for [passing contents from files into options using the `@` token](https://pnp.github.io/cli-microsoft365/user-guide/using-cli/#passing-complex-content-into-cli-options) and [using server-relative URLs with SharePoint commands](https://pnp.github.io/cli-microsoft365/user-guide/using-cli/#working-with-sharepoint-urls-in-spo-commands). We're continuing the improvement by introducing [`@me` tokens](https://github.com/pnp/cli-microsoft365/issues/3056) to let you pass information about the current user into options.

### Microsoft 365 app commands

When building apps for Microsoft 365, next to your code, you also need to manage how your app is exposed to Microsoft 365. You need to register your application in Azure Active Directory, and depending what type of app you build, you might need to deploy it to an app catalog as well. All these properties are managed in different locations and we're thinking of ways that we could simplify it for you.

What else could we simplify? Let us know what you think by helping out with one of our [open issues](https://github.com/pnp/cli-microsoft365/issues) or chime in on our [discussions](https://github.com/pnp/cli-microsoft365/discussions)!

## Try it today

Get the latest release of CLI for Microsoft 365 from npm by executing:

```bash
npm i -g @pnp/cli-microsoft365
```

Alternatively, you can get the latest release from Docker by executing:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

If you need more help getting started or want more details about the commands or the architecture or the project, go to [aka.ms/cli-m365](https://aka.ms/cli-m365). And if you see any room for improvement, please, don't hesitate to reach out to us either on [GitHub](https://github.com/pnp/cli-microsoft365/discussions) or [twitter](https://twitter.com/climicrosoft365).
