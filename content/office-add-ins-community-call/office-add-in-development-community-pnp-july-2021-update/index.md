---
title: "Office Add-in Development Community (PnP) -- July 2021 update"
date: 2021-07-22T01:24:00-04:00
author: "David Chesnut"
githubname: davidchesnut

categories: ["Office add-in developer community call"]
images:
- images/pnp-outlook-tag-external.png
tags: []
type: "regular"
---

The Office Add-ins developer platform team has new updates to share this
month on Office Add-ins Patterns and Practices. PnP is a community
effort, so if you're interested in contributing, see our [good first
issue
list](https://github.com/OfficeDev/PnP-OfficeAddins/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22).

## Use Outlook event-based activation to tag external recipients (preview)

![Diagram showing new email with added external recipient. OnMessageRecipientsChange event is sent to Outlook add-in. Add-in prepends the text external to the subject line](images/pnp-outlook-tag-external.png) [Diagram showing new email with added
external recipient. OnMessageRecipientsChange event is sent to Outlook
add-in. Add-in prepends the text external to the subject
line]
"Diagram showing new email with added external recipient. OnMessageRecipientsChange event is sent to Outlook add-in. Add-in prepends the text external to the subject line"

This sample uses event-based activation to run an Outlook add-in when
the user creates a new message or appointment. The add-in can respond to
events, even when the task pane is not open. It registers for the
OnMessageRecipientsChanged event. If the message has external
recipients, the add-in prepends "\[External\]" to the message subject.
When the user sends an email message that includes external recipients,
the add-in appends a disclaimer to the message.

-   Check out the code sample: [Use Outlook event-based activation to
    tag external recipients
    (preview)](https://github.com/OfficeDev/PnP-OfficeAddins/tree/main/Samples/outlook-tag-external)
-   Check out the docs: [Configure your Outlook add-in for event-based
    activation
    (preview)](https://learn.microsoft.com/office/dev/add-ins/outlook/autolaunch)

## Insert an external Excel file and populate it with JSON data

![Diagram showing a worksheet inserted into the current workbook from an external Excel file](images/pnp-outlook-set-signature.png)
This sample shows how to insert an existing template from an external
Excel file into the currently open Excel file. Then it retrieves data
from a JSON web service and populates the template for the customer.

-   Check out the code sample: [Insert an external Excel file and
    populate it with JSON
    data](https://github.com/OfficeDev/PnP-OfficeAddins/tree/main/Samples/excel-insert-file)
-   Check out the docs: [insertWorksheetsFromBase64
    method](https://learn.microsoft.com/javascript/api/excel/excel.workbook?view=excel-js-preview#insertWorksheetsFromBase64_base64File__options_)

## SSO samples updated

We moved the SSO samples to the PnP repo. We also updated them to the
latest packages and libraries. You can find them here:

-   [Single Sign-on (SSO) sample Outlook
    add-in](https://github.com/OfficeDev/PnP-OfficeAddins/tree/main/Samples/auth/Outlook-Add-in-SSO)
-   [Office Add-in that supports Single Sign-on (SSO) using
    Node.js](https://github.com/OfficeDev/PnP-OfficeAddins/tree/main/Samples/auth/Office-Add-in-NodeJS-SSO)
-   [Office Add-in that supports Single Sign-on (SSO) using
    ASP.NET](https://github.com/OfficeDev/PnP-OfficeAddins/tree/main/Samples/auth/Office-Add-in-ASPNET-SSO)

## Want to contribute?

PnP is a community effort by developers like you. Check out our [good
first issue
list](https://github.com/OfficeDev/PnP-OfficeAddins/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22)
as a great place to help with some samples. Feel free to contribute to
existing samples or create new ones.

## About Office Add-ins Patterns & Practices (PnP)

Office Add-ins PnP is a Microsoft-led, community driven effort that
helps developers extend, build, and provision customizations on the
Office platform the right way by providing guidance and help through
official documentation and open-source initiatives. The source is
maintained in GitHub where anyone can participate and provide
contributions to the samples, reusable components, and documentation.
Office Add-ins PnP is owned and coordinated by Office engineering teams,
but the work is done by the community for the community.
Find code samples for Office Add-in development in the [Office Add-ins
PnP repo](https://github.com/OfficeDev/PnP-OfficeAddins). Some samples
are also documented in the [Office Add-ins
docs](https://learn.microsoft.com/office/dev/add-ins/), such as [Open in
Excel](https://learn.microsoft.com/office/dev/add-ins/excel/pnp-open-in-excel).

## Additional resources

-   Get started with Office development by joining the [Microsoft 365
    developer
    program](https://developer.microsoft.com/office/dev-program).
-   Try out some samples and get coding quickly with Office add-ins by
    downloading [Script
    Lab](https://www.microsoft.com/garage/profiles/script-lab/).
-   Automate your solutions with [Office
    Scripts](https://learn.microsoft.com/office/dev/scripts/).

\
Learn more by joining the monthly [Office Add-ins community
call](https://aka.ms/officeaddinscommunitycall).
