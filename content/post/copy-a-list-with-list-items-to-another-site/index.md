---
title: "Copy a list - with list items - to another site"
date: 2021-04-01T08:47:00-04:00
author: "Will Holland"
githubname: willholland
categories: ["Community post"]
images:
- images/sad-mario.png
tags: ["SharePoint", "PnP PowerShell"]
type: "regular"
---

## The Problem 

Have you ever heard this from a client or colleague?
 
> "I have a list of data on this one site that I need to move to
> another site."
> 
![sad-mario.png](images/sad-mario.png)
 
Just a simple list of data that they want moved from **Site A** to
**Site B**. For such a simple request, the solution has, historically,
always been anything but simple.
 
Until now! Thanks to [PnP
PowerShell](https://pnp.github.io/powershell/), we can handle this
request in 5 lines of PowerShell!
 
## The Setup 

Aside from the obvious set of SharePoint sites and a list, the only real
prerequisite is to make sure you have PnP PowerShell installed.
 
This blog is running the newer `PnP.PowerShell` module, which I highly
recommend you jump over to.
 
You can use the link from the introduction for the full instructions, or
you can open up PowerShell and\...
 
``` powershell
Install-Module -Name PnP.PowerShell
```
 
## The Solution 

In a previous blog post, we walked through the process of creating
custom view formats to create a pretty nifty dashboard full of cards
about members of the *Fellowship of the Ring*.
 
For the sake of this example, let's pretend I made a mistake (which
*never* happens IRL), and I put that list on the wrong site.
 
The solution is pretty straightforward. We're basically going to create
a PnP site template, add our list data to it, and then apply that
template to our target site.
 
### Step 1 - Connect to the Source Site 

The first thing we'll do is connect to the source site.
 
``` powershell
Connect-PnPOnline -Url https://constoso.sharepoint.com/sites/star-wars -Interactive
```
 
### Step 2 - Create the Template 

We actaully have two lists we need to copy. *Fellowship Members* is the
list we care about but, since it contains a lookup column, we need to
grab the *Middle Earth Locales* lookup list as well.
 
``` powershell
Get-PnPSiteTemplate -Out Lists.xml -ListsToExtract "Middle Earth Locales", "Fellowship Members" -Handlers Lists
```
 
### Step 3 - Get the List Data 

We'll use the `Add-PnPDataRowToSiteTemplate` cmdlet to populate our
list instances with actual list item. Because we have two lists, we need
to run the cmdlet twice. (So, technically, I guess we're doing 6 lines
of PowerShell. Shh!)
 
``` powershell
Add-PnPDataRowsToSiteTemplate -Path Lists.xml -List "Middle Earth Locales"
Add-PnPDataRowsToSiteTemplate -Path Lists.xml -List "Fellowship Members"
```
 
### Step 4 - Connect to Target Site 

Now we connect to the target site\...
 
``` powershell
Connect-PnPOnline -Url https://constoso.sharepoint.com/sites/lotr -Interactive
```
 
### Step 5 - Apply the Template 

\...and we apply our template using the `Invoke-PnPSiteTemplate` cmdlet.
 
``` powershell
Invoke-PnPSiteTemplate -Path Lists.xml
```

## Game Over 

Now you've got your list(s), complete with data, copied over to another
site. All that's left to do is get rid of the old one, if necessary.

![you-win.jpg](images/you-win.jpg)
