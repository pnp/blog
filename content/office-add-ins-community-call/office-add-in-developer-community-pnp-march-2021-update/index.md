---
title: "Office Add-in Developer Community (PnP) -- March 2021 update"
date: 2021-04-29T03:10:00-04:00
author: "David Chesnut"
githubname: davidchesnut

categories: ["Office add-in developer community call"]
images:
- images/pnp-set-signature.png
tags: []
type: "regular"
---

The Office Add-ins developer platform team has new updates to share this
month on Office Add-ins Patterns and Practices. PnP is a community
effort, so if you are interested in contributing, see our [good first
issue
list](https://github.com/OfficeDev/PnP-OfficeAddins/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22).

## Use Outlook event-based activation to set the signature (preview)

![Screen shot of PnP sample displaying an information bar prompting the user to set up signatures, and sample signature inserted into the email.](images/pnp-set-signature.png)

This sample uses event-based activation to run an Outlook add-in when
the user creates a new message or appointment. The add-in can respond to
events, even when the task pane is not open. It also uses the
[setSignatureAsync
API](https://learn.microsoft.com/javascript/api/outlook/office.body?view=outlook-js-preview#setSignatureAsync_data__options__callback_).
If no signature is set, the add-in prompts the user to set a signature,
and can then open the task pane for the user.

-   Check out the code sample: [Use Outlook event-based activation to
    set the signature
    (preview)](https://github.com/OfficeDev/PnP-OfficeAddins/tree/master/Samples/outlook-set-signature)
-   Check out the docs: [Configure your Outlook add-in for event-based
    activation
    (preview)](https://learn.microsoft.com/office/dev/add-ins/outlook/autolaunch)

## Contributors

Thank you to our contributors who are actively helping each month with
the [PnP-OfficeAddins](https://github.com/OfficeDev/PnP-OfficeAddins)
community effort.

-   [Maarten van
    Stam](https://mvp.microsoft.com/PublicProfile/33535) - helping
    review PRs and issues on PnP-OfficeAddins

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
maintained in GitHub where anyone can participate. You can provide
contributions to the samples, reusable components, and documentation.
Office Add-ins PnP is owned and coordinated by Office engineering teams,
but the work is done by the community for the community.

You can find code samples for Office Add-in development in the [Office
Add-ins PnP repo](https://github.com/OfficeDev/PnP-OfficeAddins). Some
samples are also documented in the [Office Add-ins
docs](https://learn.microsoft.com/office/dev/add-ins/), such as [Open in
Excel](https://learn.microsoft.com/office/dev/add-ins/excel/pnp-open-in-excel).

## Additional resources

Get started with Office development by joining the [Microsoft 365
developer program](https://developer.microsoft.com/office/dev-program).

Try out some samples and get coding quickly with Office add-ins by
[downloading Script
Lab](https://www.microsoft.com/garage/profiles/script-lab/).

Learn more by joining the monthly [Office Add-ins community
call](https://aka.ms/officeaddinscommunitycall).
