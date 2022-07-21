---
title: "Creating a SharePoint site using the configuration of another site with PnP Powershell"
date: 2022-07-16T21:57:00
author: "Lewis Baybutt"
githubname: lowcodelewis
categories: ["Community Post"]
images:
- images/Untitled-2.png
tags: []
type: "regular"
---

## Creating a SharePoint site using the configuration of another site with PnP Powershell

So... have you ever had the need to copy the configuration of a site you've created to another SharePoint site, or make a copy of that site say? Perhaps you're implementing ALM practices and need to make duplicates of a SharePoint site with all the same lists and columns, but the content doesn't matter?
In this post, I'm going to show you how you can do this, using PnP Powershell cmdlets!

## What is PnP Powershell?

If you haven't come across PnP Powershell yet, it is a cross-platform Powershell Module which provides over 600 cmdlets that work with various Microsoft 365 platform areas. It is also a community based module and is open source.

![PnP PowerShell and ALM](images/logo%20(1).svg)

To find all of the PnP Powershell Cmdlets, you can check out the PnP PS site [here](https://pnp.github.io/powershell)

## Which Cmdlets can we use to copy our site configuration?

So, to create a copy of a site using its template or configuration, but without its content such as list items, we can use a couple of template related Cmdlets. 
In order to get the template of our existing and pre-configured site, we can use the 'Get-PnpSiteTemplate', and to copy this to another created site, we can use the 'Invoke-PnpSiteTemplate' cmdlet.

## Running the script

Now... the part you came here for. In order to copy a template of a SharePoint site from one site to another, we're going to first want to make sure that we have PnP Powershell installed with the latest major release. To do this, open a Powershell window which you can do using the Windows clients or VSCode. Then you simply need to execute this line:


```bash
Install-Module -Name PnP.PowerShell
```

So, now we're ready to run the script to copy a template for a SharePoint site from one site to another! Your easiest way to do this is in either VSCode or PowerShell ISE. VSCode is probably a better option though ;)

```bash
$ExistingSiteUrl = "https://yourtenant.sharepoint.com/sites/yourexistingsite"
$SiteTemplateFile = "\Template.xml"

Connect-PnPOnline -Url $ExistingSiteUrl -PnPManagementShell
Get-PnPSiteTemplate -Out $SiteTemplateFile

$TargetSiteUrl = "https://yourtenant.sharepoint.com/sites/yourtargetsite"

Connect-PnPOnline -Url $TargetSiteUrl -PnPManagementShell
Invoke-PnPSiteTemplate -Path $SiteTemplateFile
```

Make sure that when you paste this code into your PowerShell / VSCode window, that you replace the SharePoint site links. You should expect that on running this script you will get a message to complete a device login using a code. Simply go to https://microsoft.com/devicelogin and enter the code that your PowerShell window returns. Then go through the on screen instructions accepting anything necessary to give PnP PowerShell permissions to your tenant, then exit the browser window when you are asked to. It is important that you go to a browser window where you are already signed in with the account with the necessary privileges prior to going to this link.

## I only want lists!

Okay let's take a step back... you might only want to copy lists across to your target site. You'll have probably noticed that if you tried the script above, almost everything apart from content has copied. This means that you'll most likely have duplicate navigation items and lots more that you didn't want twice! So, perhaps you only want to copy your lists across. This is very easy to achieve, all we need to do is simply add the following syntax to the end of our line to extract our site template.

```bash
-Handlers Lists
```

So, we're now working with the following script instead of the one we looked at earlier...

```bash
$ExistingSiteUrl = "https://yourtenant.sharepoint.com/sites/yourexistingsite"
$SiteTemplateFile = "\Template.xml"

Connect-PnPOnline -Url $ExistingSiteUrl -PnPManagementShell
Get-PnPSiteTemplate -Out $SiteTemplateFile -Handlers Lists

$TargetSiteUrl = "https://yourtenant.sharepoint.com/sites/yourtargetsite"

Connect-PnPOnline -Url $TargetSiteUrl -PnPManagementShell
Invoke-PnPSiteTemplate -Path $SiteTemplateFile
```

Now you're only copying your lists from your existing site to your target site!

## Revisiting a use case - ALM

So, let's now revisit a use case as to why we might want to take advantage of this pretty neat Cmdlet. One of the key practices to implement when developing software including Power Platform solutions is Application Lifecycle Management practices. This involves us keeping separate environments for Development, Testing, potential UAT, and Production. This is pretty easy with Dataverse because our solutions contain our data schema, but this isn't quite the case with Canvas SharePoint based solutions. So, by using this script to copy lists across sites, we can implement Application Lifecycle Management practices where we build SharePoint based solutions in Power Platform.

## Further ALM Background

Not overly sure on what Application Lifecycle Management is yet? Don't worry, I've got you covered! You can check out [these blog posts](https://www.lowcodelewis.com/blog/category/ALM) on my site, [Low Code Lewis](https://www.lowcodelewis.com/), where I give you a bit of guidance to getting started with Application Lifecycle Management and Power Platform.

* [A simple start to Application Lifecycle Management with Power Platform](https://www.lowcodelewis.com/blog/a-simple-start-to-application-lifecycle-management-with-power-platform)
* [Environment Variables](https://www.lowcodelewis.com/blog/environment-variables)
* [Power Platform Configuration with Azure DevOps](https://www.lowcodelewis.com/blog/power-platform-configuration-with-azure-devops)
* [Push Power Platform Solutions to a Repo using Azure Pipelines](https://www.lowcodelewis.com/blog/push-power-platform-solutions-to-a-repo-using-azure-pipelines)
* [Automate Dataverse solution deployment with Azure Pipelines](https://www.lowcodelewis.com/blog/automate-dataverse-solution-deployment-with-azure-pipelines)
