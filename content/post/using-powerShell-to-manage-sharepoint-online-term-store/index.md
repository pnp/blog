---
title: "Using PowerShell to Manage SharePoint Online Term Store"
date: 2023-02-22T08:40:00-04:00
author: "Valeras Narbutas"
githubname: ValerasNarbutas
categories: ["Community post"]
images:
- images/github.png
tags: []
type: "regular"
---

## Intro 

SharePoint Online's term store is a powerful feature that allows organizations to create and manage metadata in a centralized location. While the SharePoint Online user interface provides a way to manage the term store, using PowerShell can be more efficient and effective for managing large term stores or for automating term store management tasks. In this blog post, we'll discuss how to use PowerShell to manage SharePoint Online term store.

## Prerequisites

Before we begin, make sure you have the following prerequisites:

A SharePoint Online site collection with a term store created.
SharePoint Online Management Shell installed on your computer.

## Connecting to the SharePoint Online Site Collection

The first step to managing the term store with PowerShell is connecting to the SharePoint Online site collection. To do this, we'll use the Connect-PnPOnline cmdlet. Here's an example:

```powershell
Connect-PnPOnline -Url https://contoso.sharepoint.com/sites/sitecollection -useWebLogin
```

Replace the URL with the URL of your SharePoint Online site collection

## Managing the Term Store

Once you're connected to the SharePoint Online site collection, you can start managing the term store with PowerShell. Here are some common tasks you might need to perform:

### Creating a New Term

To create a new term in the term store, use the New-PnPTerm cmdlet. Here's an example:

```powershell
New-PnPTerm -TermSet "Locations" -TermGroup "Global" -Name "Seattle" -LCID 1033 -Description "A city in Washington state" -CustomSortOrder "1.1"
```

This example creates a new term called "Seattle" in the "Locations" term set in the "Global" term group. The -LCID parameter specifies the language for the term, and the -Description parameter provides a description of the term. The -CustomSortOrder parameter allows you to specify a custom sort order for the term.

[New-PnPTerm ](https://pnp.github.io/powershell/cmdlets/New-PnPTerm.html)

### Updating Term Properties

To update the properties of an existing term in the term store, use the Set-PnPTerm cmdlet. Here's an example:

```powershell
Set-PnPTerm -Identity "Seattle" -TermSet "Locations" -TermGroup "Global" -Name "Seattle, WA" -LCID 1033 -Description "A city in the Pacific Northwest" -CustomSortOrder "1.1"
```

This example updates the name and description of the "Seattle" term in the "Locations" term set in the "Global" term group. The other parameters work the same way as in the New-PnPTerm example.

[Set-PnPTerm ](https://pnp.github.io/powershell/cmdlets/Set-PnPTerm.html)

### Deleting a Term

To delete a term from the term store, use the Remove-PnPTerm cmdlet. Here's an example:

```powershell
    Remove-PnPTerm -Identity "Seattle" -TermSet "Locations" -TermGroup "Global" -Force
```

This example deletes the "Seattle" term from the "Locations" term set in the "Global" term group. The -Force parameter is required to confirm the deletion.

[Remove-PnPTerm ](https://pnp.github.io/powershell/cmdlets/Remove-PnPTerm.html)

## Conclusion

Using PowerShell to manage SharePoint Online term store can save time and make managing large term stores or automating term store management tasks easier. In this blog post, we've covered some common tasks for managing the term store with PowerShell, such as creating new terms, updating term properties, and deleting terms. With these tools at your disposal, you can take control of your SharePoint Online term store and make it work for your organization.
