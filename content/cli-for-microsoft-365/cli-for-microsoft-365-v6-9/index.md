---
title: CLI for Microsoft 365 v6.9
date: 2023-06-30T08:00:00.000Z
author: Jasey Waegebaert
githubname: jwaegebaert
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - SharePoint
  - SharePoint Framework (SPFx)
type: popular
---

Introducing the latest release of CLI for Microsoft 365

[CLI for Microsoft 365](https://aka.ms/cli-m365): a cross-platform command-line tool that empowers you to manage your Microsoft 365 tenant and SharePoint Framework projects. This release comes packed with an impressive arsenal of **8 new commands**, along with a staggering **90+ enhancements** to existing commands. 

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover an array of exciting features and improvements that will revolutionize your Microsoft 365 journey. 
 
## What's new

Our CLI for Microsoft 365 now features **8 new commands**, giving you control over various Microsoft 365 services. From SharePoint Application Customizers to sensitivity labels and Azure Active Directory. Get ready to elevate your productivity and dive into a world of possibilities!

### SharePoint Management

We've introduced new commands to enhance your SharePoint management experience. Now, it's easier than ever to handle Application Customizers, discard checked-out files, and manage tenant-wide ListView Command Sets. Check out the details below:

Update the title of an application customizer on the sales site:

```sh
m365 spo applicationcustomizer set --id 058140e3-0e37-44fc-a1d3-79c487d371a3 --newTitle "Some customizer" --webUrl https://contoso.sharepoint.com/sites/sales
```

Discard a checked-out file with a specific ID:

```sh
m365 spo file checkout undo --webUrl https://contoso.sharepoint.com/sites/project-x --fileId 'b2307a39-e878-458b-bc90-03bc578531d6'
```

Applies a sensitivity label by ID to a document library using the list title:

```sh
m365 spo list sensitivitylabel ensure --webUrl 'https://contoso.sharepoint.com' --listTitle 'Shared Documents' --id '0d39dc11-75ff-4309-8b32-ff94f0e41607'
```

Update the title of a tenant-wide deployed Application Customizer by its ID:

```sh
m365 spo tenant applicationcustomizer set --id 3 --newTitle "Some customizer"
```

Add a tenant-wide deployed ListView Command Set to CommandBars of Lists:

```sh
m365 spo tenant commandset add --title "Some customizer" --clientSideComponentId 799883f5-7962-4384-a10a-105adaec6ffc --listType List
```

Retrieve a ListView Command Set by its title:

```sh
m365 spo tenant commandset get --title "Some customizer"
```

Retrieve a list of tenant-wide deployed ListView Command Sets:

```sh
m365 spo tenant commandset list
```

- [m365 spo applicationcustomizer set](https://pnp.github.io/cli-microsoft365/cmd/spo/applicationcustomizer/applicationcustomizer-set/)
- [m365 spo file checkout undo](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-checkout-undo/)
- [m365 spo list sensitivitylabel ensure](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-sensitivitylabel-ensure/)
- [m365 spo tenant applicationcustomizer set](https://pnp.github.io/cli-microsoft365/cmd/spo/tenant/tenant-applicationcustomizer-set/)
- [m365 spo tenant commandset add](https://pnp.github.io/cli-microsoft365/cmd/spo/tenant/tenant-commandset-add/)
- [m365 spo tenant commandset get](https://pnp.github.io/cli-microsoft365/cmd/spo/tenant/tenant-commandset-get/)
- [m365 spo tenant commandset list](https://pnp.github.io/cli-microsoft365/cmd/spo/tenant/tenant-commandset-list/)

### Azure Active Directory Management

As part of this release, we've added a handy new command for listing service principals in your Azure Active Directory. Take a look at the example below to see how it works:

Retrieve a list of service principals based on display name and tag parameters:

```sh
m365 aad sp list --displayName "My custom service principal" --tag "WindowsAzureActiveDirectoryIntegratedApp"
```

- [m365 aad sp list](https://pnp.github.io/cli-microsoft365/cmd/aad/sp/sp-list/)

## What's changed

Hold on tight because we've got even more in store for you! Brace yourself for over **90 enhancements** that have been added to the very fabric of our existing commands. These upgrades have been carefully tailored to deliver a seamless experience, whether you're a seasoned CLI user or a fresh adopter. Get ready to dive into a world of improved navigation, enhanced error handling, and an abundance of refactoring goodness. 

With these tweaks at your disposal, your workflow will be streamlined and your productivity will soar to unimaginable heights.

### Introducing our New Website with Docusaurus 🦖

We're thrilled to announce that we've given our website a long-awaited makeover! After much deliberation and development efforts, we've migrated to a new static site generator called [Docusaurus](https://docusaurus.io/). This transition has been a significant undertaking, involving extensive discussions and dedicated development time. The result? A refreshed and enhanced website experience that includes a sophisticated search engine powered by [Algolia](https://www.algolia.com/).

We can't wait to hear your thoughts and feedback on our new website! Feel free to share your experience and leave us a comment on [Discord](https://aka.ms/cli-m365/discord). We value your input and look forward to continuously improving our online presence based on your valuable insights.

### **MAJOR**: SharePoint Framework Projects v1.17.3 & v1.17.4 Support

Calling all SharePoint Framework enthusiasts! We're thrilled to share some exciting news that will brighten your day. Our latest update brings support for not only SPFx `v1.17.3` but also `v1.17.4` to three of our most popular commands: `spfx project upgrade`, `spfx project doctor`, and `spfx doctor`.

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

Don't miss out on this opportunity to leverage the capabilities of SPFx `v1.17.3` & `v1.17.4`. Upgrade your projects now and experience the remarkable advancements firsthand.

For more information, check out the documentation for each command:

- [spfx project upgrade](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade/)
- [spfx doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor/)
- [spfx project doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-doctor/)

### Embracing the Power of async/await in our Codebase

We're excited to unveil a major undertaking that has consumed our efforts for quite some time: the refactoring of our codebase to embrace the asynchronous programming model using **async/await**. This change marks a milestone in our journey, as it makes our code more readable and easier to work with.

With the groundwork already laid by refactoring the core aspects of our commands, we are now changing all remaining promises to achieve a fully async/await codebase. This process ensures that our commands operate seamlessly, taking full advantage of the benefits offered by async/await. This refactoring demonstrates the remarkable power of community and the cherished principle of `sharing is caring`, as it has involved an immense amount of work accomplished within a relatively short span of time.

We're thrilled to present you with an improved experience that harnesses the power of asynchronous programming. [Stay tuned](https://github.com/pnp/cli-microsoft365/issues/3618) as we continue to refine and optimize our codebase, delivering even greater efficiency and readability to our valued users.

### Filter Flows by Sharing Status with 'flow list' Command

We're thrilled to introduce a significant enhancement to our widely used `m365 flow list` command. Now, you have the ability to filter the list of flows based on their sharing status, providing you with greater control and flexibility. You can now refine your flow list using the following sharing statuses:

- `ownedByMe`: Retrieves all flows created by you, regardless of whether they are shared or not.
- `personal`: Displays flows created by you that are not shared with others.
- `sharedWithMe`: Presents flows that are shared with you or those created by you and shared with someone else.
- `all`: Combines both personal and sharedWithMe categories to provide a comprehensive list of flows.

To utilize this powerful feature, simply include the `--sharingStatus` option followed by the desired sharing status value when executing the `m365 flow list` command. For example:

```sh
m365 flow list --environmentName Default-d87a7535-dd31-4437-bfe1-95340acd55c5 --sharingStatus personal --includeSolutions
```

- [m365 flow list](https://pnp.github.io/cli-microsoft365/cmd/flow/flow-list/)

### Explore the Extensive Enhancements

We've poured our heart and soul into this release, and the results are truly remarkable.

For a comprehensive overview of everything we've accomplished, dive into our release notes below. It's an exciting read that showcases the extent of our hard work. We're eager to hear about your experiences and insights, so don't hesitate to share them with us.

- [Changelog v6.9.0](https://pnp.github.io/cli-microsoft365/about/release-notes/#v690)

Prepare to be amazed as you discover the multitude of enhancements we've made!

## Upcoming Changes

Curious about what lies ahead? We're excited to share some of our ongoing projects and initiatives.

### Expanding Command Arsenal

Our relentless pursuit of empowering your Microsoft 365 experience continues. We're actively working on introducing more commands to CLI for Microsoft 365. From Power Platform to SharePoint Online, we're exploring various services to enhance your command-line capabilities. Additionally, we're dedicated to refactoring our codebase to embrace the power of async/await, further improving performance and readability.

But we don't stop there. We value your input and ideas. If you have any suggestions for new commands, don't hesitate to share them with us. Create a [new issue](https://github.com/pnp/cli-microsoft365/issues/new?assignees=&labels=&template=new-command.yml&title=New+command%3A+%3Cshort+description%3E) on our GitHub Issues list or join our vibrant [community Discord server](https://aka.ms/cli-m365/discord) to engage in discussions.

Together, let's shape the future of CLI for Microsoft 365 and unlock even greater possibilities.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Ganesh Sanap](https://github.com/ganesh-sanap)
- [Garry Trinder](https://github.com/garrytrinder)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [János Dojcsák](https://github.com/dojcsakj)
- [Manan Shah](https://github.com/manan-m-shah)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Matthijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Nico De Cleyre](https://github.com/nicodecleyre)
- [Patrick Lamber](https://github.com/plamber)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

We express our deepest gratitude for the time and effort you have invested in CLI for Microsoft 365, improving its progress and enriching its capabilities. Your contributions have played a significant role in advancing this project and empowering users worldwide. Thank you for your commitment and valuable assistance!

### High fives

We would like to give a big shoutout and high fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to provide us with their insights:

- [Adam](https://github.com/adam13hylo)
- [Alex Terentiev](https://github.com/AJIXuMuK)
- [Simon Cumming](https://github.com/simoncumming)

Your feedback has been instrumental in shaping the direction of CLI for Microsoft 365, and we are grateful for your involvement in making our platform even better. Your active participation and valuable insights continue to drive innovation and enhance the user experience for all. Thank you for being an essential part of our community!

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

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord), or [Twitter](https://twitter.com/climicrosoft365). Don't hesitate to connect with us; your input plays a vital role in shaping the future of CLI for Microsoft 365.