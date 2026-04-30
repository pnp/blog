---
title: CLI for Microsoft 365 v11.7
date: 2026-04-30T01:00:00.000Z
author: Milan Holemans
githubname: milanholemans
categories:
  - CLI for Microsoft 365
images:
  - images/banner-cli-m365.png
tags:
  - CLI for Microsoft 365
  - SharePoint
  - Microsoft Outlook
  - SPFx
  - Microsoft Teams
type: popular
---

CLI for Microsoft 365 v11.7 is a feature-rich release centered on Outlook calendar automation, adding a full suite of commands for calendars, events, and calendar groups, alongside new SharePoint capabilities and meaningful quality improvements across the tool. [CLI for Microsoft 365](https://aka.ms/cli-m365) remains the cross-platform tool you rely on to manage your Microsoft 365 tenant and SharePoint Framework projects, and this release continues to expand coverage across the platform.

> Explore the [release notes](https://pnp.github.io/cli-microsoft365/about/release-notes#v1170) to see every detail that landed in v11.7.

## What's new

### Outlook calendar management

This release delivers a complete set of calendar management commands, giving you end-to-end control over user calendars from the command line.

The new `outlook calendar get` command retrieves a specific calendar for a user or group. This is useful when you need to inspect calendar metadata or confirm settings before making changes.

To retrieve a calendar for the signed-in user by its ID, run:

```sh
m365 outlook calendar get --userId "@meId" --id "AAMkAGI2TGuLAAA="
```

To retrieve a calendar by name within a specific calendar group, run:

```sh
m365 outlook calendar get --userId "@meId" --calendarGroupName "Colleague calendars" --name "Calendar"
```

The new `outlook calendar add` command creates a new calendar for a user. You can assign a name, color, and optionally place it in a specific calendar group.

To create a new calendar for the signed-in user, run:

```sh
m365 outlook calendar add --userId '@meId' --name 'Holidays'
```

To create a calendar in a specific group with a color, run:

```sh
m365 outlook calendar add --userName 'john.doe@contoso.com' --name 'Interviews' --calendarGroupId 'AAMkADY1YmE3N2FhLWEwMz' --color 'lightBlue'
```

The new `outlook calendar remove` command removes a calendar from a user's mailbox. An optional `--permanent` flag bypasses the deleted items folder.

To remove a calendar by ID, run:

```sh
m365 outlook calendar remove --userId "@meId" --id "AAMkAGI2TGuLAAA="
```

The new `outlook calendar set` command updates properties of an existing calendar such as its name, color, or default status.

To rename a calendar, run:

```sh
m365 outlook calendar set --id 'AAMkAGI2TQpZAAA=' --name 'Team planning'
```

To set a calendar as the default for a specific user, run:

```sh
m365 outlook calendar set --id 'AAMkAGI2TQpZAAA=' --userId 'b743445a-112c-4fda-9afd-05943f9c7b36' --isDefault true
```

For additional options and response details, visit the command documentation:

- [calendar add](https://pnp.github.io/cli-microsoft365/cmd/outlook/calendar/calendar-add/)
- [calendar get](https://pnp.github.io/cli-microsoft365/cmd/outlook/calendar/calendar-get/)
- [calendar remove](https://pnp.github.io/cli-microsoft365/cmd/outlook/calendar/calendar-remove/)
- [calendar set](https://pnp.github.io/cli-microsoft365/cmd/outlook/calendar/calendar-set/)

### Outlook calendar events

Three new event management commands let you list, cancel, and remove calendar events, making end-to-end calendar automation possible from a single tool.

The new `outlook event list` command retrieves events from a specific calendar. You can filter by date range, time zone, or OData filter expressions to narrow results.

To list events in a calendar, run:

```sh
m365 outlook event list --userId "@meId" --calendarId "AAMkAGRkZ"
```

To list events within a specific date range, run:

```sh
m365 outlook event list --userId "@meId" --calendarId "AAMkAGRkZ" --startDateTime '2026-01-01' --endDateTime '2026-01-31'
```

The new `outlook event cancel` command cancels a calendar event and notifies attendees. You can include an optional cancellation comment to provide context.

To cancel an event with a message, run:

```sh
m365 outlook event cancel --userName "john.doe@contoso.com" --comment "Cancelling for this week due to all hands" --id "AAMkAGVmMDEzMTM4LTZmYWUtNDdkNC1hMDZiLTU1OGY5OTZhYmY4OABGAAAAAAAiQ8W967B7TKBjgx9rVEURBwAiIsqMbYjsT5e"
```

The new `outlook event remove` command removes an event from a calendar. By default it moves it to the deleted items folder; the `--permanent` flag skips that step.

To permanently remove an event, run:

```sh
m365 outlook event remove --userName "john.doe@contoso.com" --permanent --id "AAMkAGVmMDEzMTM4LTZmYWUtNDdkNC1hMDZiLTU1OGY5OTZhYmY4OABGAAAAAAAiQ8W967B7TKBjgx9rVEURBwAiIsqMbYjsT5e"
```

For additional options and response details, visit the command documentation:

- [event cancel](https://pnp.github.io/cli-microsoft365/cmd/outlook/event/event-cancel/)
- [event list](https://pnp.github.io/cli-microsoft365/cmd/outlook/event/event-list/)
- [event remove](https://pnp.github.io/cli-microsoft365/cmd/outlook/event/event-remove/)

### Outlook calendar group get and set

Two new commands extend the calendar group support introduced in v11.6.

The new `outlook calendargroup get` command retrieves a specific calendar group for a user, by name or by ID. This is helpful when you need to look up group metadata or resolve a group before working with its calendars.

To retrieve a calendar group by name, run:

```sh
m365 outlook calendargroup get --name "Personal Events"
```

To retrieve a calendar group for a specific user, run:

```sh
m365 outlook calendargroup get --name "Personal Events" --userId "44288f7d-7710-4293-8c8e-36f310ed2e6a"
```

The new `outlook calendargroup set` command updates the name of an existing calendar group.

To rename a calendar group for the signed-in user, run:

```sh
m365 outlook calendargroup set --name "Personal Evts" --newName "Personal Events"
```

To rename a calendar group for a specific user, run:

```sh
m365 outlook calendargroup set --id "AAMkADIxYjJiYm" --newName "Personal Events" --userId "44288f7d-7710-4293-8c8e-36f310ed2e6a"
```

For additional options and response details, visit the command documentation:

- [calendargroup get](https://pnp.github.io/cli-microsoft365/cmd/outlook/calendargroup/calendargroup-get/)
- [calendargroup set](https://pnp.github.io/cli-microsoft365/cmd/outlook/calendargroup/calendargroup-set/)

### SharePoint Brand Center colors

The new `spo brandcenter colors list` command retrieves the color palettes configured in your SharePoint Brand Center. This is useful for admins who want to audit branding settings or export color configurations as part of a governance or documentation workflow.

To list Brand Center colors, run:

```sh
m365 spo brandcenter colors list
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/brandcenter/brandcenter-colors-list/).

### SharePoint file archiving

The new `spo file archive` command archives a file in SharePoint. This is useful for storage management scenarios where you want to move files to an archived state without permanently deleting them.

To archive a file by its ID, run:

```sh
m365 spo file archive --webUrl https://contoso.sharepoint.com/sites/Marketing --id 7a8c9207-7745-4cda-b0e2-be2618ee3030 --force
```

To archive a file by its server-relative URL, run:

```sh
m365 spo file archive --webUrl https://contoso.sharepoint.com/sites/Marketing --url '/sites/Marketing/shared documents/document.docx'
```

For additional options and response details, visit the [command documentation](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-archive/).

## What's changed

### SPFx CI/CD commands set Node version based on project

The SPFx CI/CD pipeline commands now automatically determine the appropriate Node.js version based on the SPFx version of the project being built. This removes the need to manually configure the Node version in generated pipeline files and ensures runtime compatibility across different project versions.

Related commands:

- [spfx project azuredevops pipeline add](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-azuredevops-pipeline-add)
- [spfx project github workflow add](https://pnp.github.io/cli-microsoft365/cmd/spfx/project/project-github-workflow-add)

### Enhanced `spo tenant settings set` with new property

The `spo tenant settings set` command now supports the `AllowWebPropertyBagUpdateWhenDenyAddAndCustomizePagesIsEnabled` property. This gives admins finer control over property bag update behavior on sites where custom scripting is restricted.

### Enhanced `applicationcustomizer` commands with `hostProperties`

The application customizer commands now accept a `hostProperties` option. This lets you pass host properties directly when deploying or updating an application customizer, reducing the need for extra scripting steps.

### Enhanced `teams chat message list`

The `teams chat message list` command has been enhanced with additional filtering and output capabilities, making it more useful for auditing and reporting on Teams chat history.

## Keep the momentum going

Every improvement in this release is driven by real-world usage and community input. If you want to help shape the next version, browse the open ["help wanted" issues](https://github.com/pnp/cli-microsoft365/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22) or share your ideas on Discord.

## Contributors

We want to extend our heartfelt appreciation to the incredible individuals who have made this release possible. Without their valuable contributions and dedication, CLI for Microsoft 365 wouldn't be where it is today. Let's give a round of applause to the following contributors (in alphabetical order):

- [Adam Wójcik](https://github.com/Adam-it)
- [Alejandro Gispert](https://github.com/AlejandroGispert)
- [Martin Machacek](https://github.com/MartinM85)
- [Mathijs Verbeeck](https://github.com/MathijsVerbeeck)
- [Matt Van Horn](https://github.com/mvanhorn)
- [Milan Holemans](https://github.com/milanholemans)
- [Nanddeep Nachan](https://github.com/nanddeepn)
- [Saurabh Tripathi](https://github.com/Saurabh7019)
- [Smita Nachan](https://github.com/SmitaNachan)
- [Zekai (Kai) Zhao](https://github.com/Zekai-Zhao-321)

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

We value your feedback and are eager to hear from you. If you have any suggestions for improvement or want to engage with our community, you can reach out to us on [GitHub](https://github.com/pnp/cli-microsoft365/issues), [Discord](https://aka.ms/cli-m365/discord) or [Bluesky](https://bsky.app/profile/climicrosoft365.bsky.social). Your input plays a vital role in shaping the future of CLI for Microsoft 365.
