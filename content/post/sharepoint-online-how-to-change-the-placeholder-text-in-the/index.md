---
title: "SharePoint Online: How to change the placeholder text in the search box"
date: 2021-07-13T04:52:00-04:00
author: "Ganesh Sanap"
githubname: ganesh-sanap
categories: ["Community post"]
images:
- images/sharepoint-online-how-to-change-the-placeholder-text-in-the-search-box.png
tags: ["SharePoint"]
type: "regular"
---

Placeholder text is the text that appears in the search box before user
starts typing into it. The placeholder text may help your users about
what to expect from search if you've configured a custom results page or
changed behavior of search in other ways.
By default SharePoint online site has ***Search this site*** as default
placeholder text in the search box at the top of your page. This is a
very generic placeholder text & sometimes you may want to change this
placeholder text to something more specific or relevant to current site
or site collection.
You can change the placeholder text in the search box for a specific
(sub) site or an entire site collection using PnP PowerShell. Follow
below steps to change the placeholder text in the search box:

## Install/Update PnP PowerShell module

You can run the following command to install the PnP PowerShell cmdlets:
 

```powershell
Install-Module -Name "PnP.PowerShell"
```
 
If you have previously installed the PnP PowerShell module, you can run
the following command to update it:
 

```powershell
Update-Module -Name "PnP.PowerShell"
```
 

### Connect to SharePoint site

You can connect to a SharePoint site using below PnP PowerShell command
(use administrative account):
 

```powershell
Connect-PnPOnline -Url https://tenant.sharepoint.com/sites/siteName -UseWebLogin
```

### Change the placeholder text

To change the placeholder text in search box for a given (sub) site run
the following command:
 

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "Search Work @ SPExplorer Site"
```
 
Alternately, if you want to change the placeholder text for all the
sites in a site collection, you can use below command:
 

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "Search Work @ SPExplorer Site"
```
 

#### ![sharepoint-online-how-to-change-the-placeholder-text-in-the-search-box.png](images/sharepoint-online-how-to-change-the-placeholder-text-in-the-search-box.png)

### Reset to default placeholder text

If you have changed the placeholder text in search box previously & now
you want to reset it to the default placeholder text, you can run the
following command after connecting to a SharePoint site:
 

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText ""
```
 
![sharepoint-online-how-to-reset-the-placeholder-text-in-the-search-box.png](images/sharepoint-online-how-to-reset-the-placeholder-text-in-the-search-box.png)

------------------------------------------------------------------------

This article is originally posted at: [SharePoint Online: How to change
the placeholder text in the search
box](https://ganeshsanapblogs.wordpress.com/2021/06/20/sharepoint-online-how-to-change-the-placeholder-text-in-the-search-box/ "SharePoint Online: How to change the placeholder text in the search box") 
