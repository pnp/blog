---
title: CLI for Microsoft 365 v11.0
date: 2025-09-30T01:00:00.000Z
author: Jasey Waegebaert
githubname: jwaegebaert
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - Outlook
  - Entra ID
  - SharePoint
  - SharePoint Embedded
  - Teams
type: popular
---

We're excited to announce CLI for Microsoft 365 v11.0, featuring new commands and improvements that enhance your Microsoft 365 workflow. [CLI for Microsoft 365](https://aka.ms/cli-m365) is a cross-platform command-line tool that allows you to manage your Microsoft 365 tenant and SharePoint Framework projects. This major release introduces several new commands alongside important breaking changes designed to improve functionality and align with the latest Microsoft 365 innovations.

> Explore the [release notes](https://aka.ms/cli-m365/notes) to discover all the new features and improvements in this release. 
 
## CLI for Microsoft 365 v11.0 – Major release overview

CLI for Microsoft 365 v11.0 represents a significant step forward in our ongoing effort to provide powerful, reliable automation tools for Microsoft 365. This major release introduces substantial improvements and new capabilities while implementing important breaking changes that align with the latest Microsoft 365 platform updates.

The [breaking changes](https://pnp.github.io/cli-microsoft365/about/release-notes#%EF%B8%8F-breaking-changes) in this release are designed to enhance functionality, improve reliability, and ensure compatibility with current Microsoft 365 services and terminology.

### Key improvements in v11.0

**SharePoint Embedded Enhancements**: We've [upgraded SharePoint Embedded container commands](https://pnp.github.io/cli-microsoft365/v11-upgrade-guidance#updated-container-type-commands) to use new preview endpoints, providing enhanced capabilities and configuration options.

**Multi-Home Site Support**: [SharePoint homesite commands](https://pnp.github.io/cli-microsoft365/v11-upgrade-guidance#updated-behavior-for-spo-homesite-commands) now support multiple home sites per tenant, reflecting the current capabilities of SharePoint Online.

**Improved Output Consistency**: [Teams report commands](https://pnp.github.io/cli-microsoft365/v11-upgrade-guidance#consistent-list-output-for-teams-report-commands) now return consistent array formats, making script automation more predictable and reliable.

**Command Alignment**: We've [updated command and option names](https://pnp.github.io/cli-microsoft365/v11-upgrade-guidance#renamed-commands-for-alignment) to align with current Microsoft 365 terminology and [removed deprecated functionality](https://pnp.github.io/cli-microsoft365/v11-upgrade-guidance#renamed-options-for-clarity).

**Enhanced Defaults**:
- [List views](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-view-add) now default to paged mode, reflecting common usage patterns
- [SPFx upgrades](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-upgrade) default to PowerShell, matching current development preferences

> For detailed migration guidance, see our comprehensive [v11 Upgrade Guidance](https://pnp.github.io/cli-microsoft365/v11-upgrade-guidance) documentation.

## New commands in v11.0

### Outlook folder search

We've added a new command to help you manage Outlook mail search folders more effectively. This command allows you to create mail search folders in the user's mailbox, providing better organization for your email management workflows.

To create a mail search folder in the user's mailbox , run:

```sh
m365 outlook mail searchfolder add --userId 1caf7dcd-7e83-4c3a-94f7-932a1299c844 --folderName 'CLI m365' --sourceFolderIds 'AQMkADYAAAIBDAAAAA==' --messageFilter "contains(subject, 'CLI for Microsoft 365')"
```

This command is particularly useful for automated email management, filtering important messages, and setting up dynamic folders based on specific criteria.

For more information, see: [outlook mail searchfolder add](https://pnp.github.io/cli-microsoft365/cmd/outlook/mail/mail-searchfolder-add/)

### SharePoint version control

This release introduces a new command to help you manage SharePoint file versions more effectively. You can now ensure that a specific file version will never expire, providing better control over your document versioning strategy.

To mark a file version as never expiring by file URL, run:

```sh
m365 spo file version keep --webUrl "https://contoso.sharepoint.com/sites/marketing" --fileUrl "/sites/marketing/Documents/report.docx" --label "6.0"
```

This command is ideal for document management, compliance requirements, and preserving critical file versions that need to remain accessible indefinitely.

For more information, see: [spo file version keep](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-version-keep/)

### Entra ID role management

We've enhanced our Entra ID management capabilities with a new command that allows you to assign Entra ID roles to users and specify the scope for which the user has been granted access. This provides more granular control over role assignments in your Entra ID environment.

To assign a role to a user, run:

```sh
m365 entra roleassignment add --roleDefinitionName 'SharePoint Administrator' --principal 7a2ca997-9461-402e-9882-58088a370889
```

This command is particularly useful for automated user provisioning, role-based access control, and security automation scenarios.

For more information, see: [entra roleassignment add](https://pnp.github.io/cli-microsoft365/cmd/entra/roleassignment/roleassignment-add/)

## Additional improvements

Beyond the new commands, we've made several important improvements to existing functionality:

### SharePoint Embedded enhancements

We've enhanced our SharePoint Embedded support with significant improvements to container type commands. These commands now use new preview endpoints that offer enhanced capabilities and configuration options, enabling us to introduce additional SharePoint Embedded commands in the future.

The updated commands include:
- Enhanced [spe containertype add](https://pnp.github.io/cli-microsoft365/cmd/spe/containertype/containertype-add) with new options for better container-type configuration
- Updated permission scopes for improved security and functionality
- Improved API reliability and performance

These SharePoint Embedded improvements make it easier to manage and configure your SharePoint Embedded environments with more granular control and better reliability.

### SharePoint Online improvements

We've improved how SharePoint Online commands work with modern features and capabilities. The SharePoint homesite commands now properly support multiple home sites per tenant, reflecting the current state of SharePoint Online where organizations can configure more than one home site.

We also updated the default behavior of the [spo list view add](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-view-add) command to default the `paged` option to `true`, reflecting common usage patterns where most views support paging and fetch new items while scrolling.

### Teams report command consistency

We've enhanced the consistency of Teams report commands by updating their output format. Previously, some commands returned an object with a `value` property, but now they return a proper array for consistency. This makes it much more predictable when working with Teams reporting data in your scripts and automation.

### Command migration and validation

We've migrated several Entra ID administrative unit commands to use Zod for better validation and error handling. This includes commands like `entra administrativeunit list`, `entra administrativeunit get`, `entra administrativeunit remove`, and `entra administrativeunit add`. These improvements ensure better data validation and more reliable command execution.

## Upcoming changes

We continue to work on exciting new features and improvements for future releases.

**In development:**
- Over 20 pull requests in progress with new features
- [136 issues available for community contribution](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22)

### Hacktoberfest 2025

We're excited to participate in Hacktoberfest 2025! This is a perfect opportunity for developers of all skill levels to contribute to CLI for Microsoft 365 and make a real impact on the Microsoft 365 automation ecosystem.

We've prepared a curated list of issues that are perfect for Hacktoberfest contributions:

- **Zod Migration** - Help us migrate commands to use Zod for better validation and error handling
- **Minimal Permissions Documentation** - Add comprehensive permission requirements to our command documentation

These issues are ideal for contributors looking to understand how CLI for Microsoft 365 works internally, learn about modern TypeScript validation patterns, and contribute to documentation that helps thousands of developers worldwide.

All Hacktoberfest contributions count toward the official Hacktoberfest goals, and you'll be helping improve the reliability and usability of CLI for Microsoft 365.

Ready to get started? Check out our [Hacktoberfest issues](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3Ahacktoberfest) or browse all [community contribution opportunities](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22).

**Community input welcome:**
- Submit suggestions via [GitHub Issues](https://github.com/pnp/cli-microsoft365/issues/new/choose)
- Join discussions on our [Discord server](https://aka.ms/cli-m365/discord)
- Share your ideas for new commands and improvements

We value community feedback and many of our best features have come from user suggestions. Your input helps shape the future of CLI for Microsoft 365.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Jasey Waegebaert](https://github.com/Jwaegebaert)
- [Martin Lingstuyl](https://github.com/martinlingstuyl)
- [Martin Machacek](https://github.com/MartinM85)
- [Milan Holemans](https://github.com/milanholemans)
- [Reshmee Auckloo](https://github.com/reshmee011)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Waldek Mastykarz](https://github.com/waldekmastykarz)

### High fives

We would like to give a big shout-out and high-fives to the amazing individuals who have shared their invaluable feedback and ideas for improving CLI for Microsoft 365. We greatly appreciate your engagement and contribution to the growth of our platform. Let's celebrate the following users (in alphabetical order) for taking the time to share their insights:

- [BigGGG777](https://github.com/BigGGG777)
- [Tyas Lambrechts](https://github.com/eltyBelgium)

Thank you for making CLI for Microsoft 365 better for everyone!

## Get started today!

Experience the power of CLI for Microsoft 365 by getting the latest release from npm:

```bash
npm i -g @pnp/cli-microsoft365
```

Alternatively, you can access the latest release from Docker:

```bash
docker run --rm -it m365pnp/cli-microsoft365:latest
```

## Need more information?

For additional guidance on getting started or to explore detailed information about commands, architecture, or the project itself, visit [aka.ms/cli-m365](https://aka.ms/cli-m365).

## Stay connected!

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord) or [Bluesky](https://bsky.app/profile/climicrosoft365.bsky.social). Don't hesitate to connect with us. Your input plays a vital role in shaping the future of CLI for Microsoft 365.
