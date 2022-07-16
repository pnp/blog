title: "Creating a SharePoint site using the configuration of another site with PnP Powershell"
date: 2022-07-16T21:57:00
author: "Lewis Baybutt"
githubname: lowcodelewis
categories: ["Community Post"]
images:
-
tags: []
type: "regular"
---

# Creating a SharePoint site using the configuration of another site with PnP Powershell

So... have you ever had the need to copy the configuration of a site you've created to another SharePoint site, or make a copy of that site say? Perhaps you're implementing ALM practices and need to make duplicates of a SharePoint site with all the same lists and columns, but the content doesn't matter?
In this post, I'm going to show you how you can do this, using PnP Powershell cmdlets!

## What is PnP Powershell?

If you haven't come across PnP Powershell yet, it is a cross-platform Powershell Module which provides over 600 cmdlets that work with various Microsoft 365 platform areas. It is also a community based module and is open source.

![](https://github.com/lowcodelewis/blog/blob/Creating-a-SharePoint-site-using-the-configuration-of-another-site-with-PnP-Powershell/content/post/Creating-a-SharePoint-site-using-the-configuration-of-another-site-with-PnP-Powershell/logo.svg)

To find all of the PnP Powershell Cmdlets, you can check out the PnP PS site [here](https://pnp.github.io/powershell)

## What Cmdlet can we use to copy our site configuration?

So, to create a copy of a site using its template or configuration, but without its content such as list items, we can use a couple of template related Cmdlets. 
In order to get the template of our existing and pre-configured site, we can use the 'Get-PnpSiteTemplate', and to copy this to another created site, we can use the 'Invoke-PnpSiteTemplate' cmdlet.
