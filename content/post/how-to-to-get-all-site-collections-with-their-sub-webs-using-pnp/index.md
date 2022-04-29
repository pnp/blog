---
title: "How to to get all site collections with their sub webs using PnP PowerShell?"
date: 2021-05-05T01:32:00-04:00
author: "Chandani Prajapati"
githubname: chandaniprajapati
categories: ["Community post"]
images:
- images/AllSCAndSCW.png
tags: ["PnP PowerShell", "SharePoint"]
type: "regular"
---

Sometimes we have a business requirement to get site collections with
all the sub-webs so we can achieve the solution easily using PnP
PowerShell.
Let's see step-by-step implementation:

## Implementation 

Open Windows PowerShell ISE\
Create a new file and write a script

Now we will see all the steps which we required to achieve the solution:

1.  We will initialize the admin site URL, username, and password in the
global variables.

2.  Then we will create a Login function to connect the O365 SharePoint
Admin site.

3.  Create a function to get all site collections and all the sub-webs 
So in the end, our script will be like this,
 

```powershell
$SiteURL = "https://domain-admin.sharepoint.com/"
$UserName = "UserName@domain.onmicrosoft.com"
$Password = "********"
$SecureStringPwd = $Password | ConvertTo-SecureString -AsPlainText -Force 
$Creds = New-Object System.Management.Automation.PSCredential -ArgumentList $UserName, $SecureStringPwd

Function Login {
    [cmdletbinding()]
    param([parameter(Mandatory = $true, ValueFromPipeline = $true)] $Creds)
    Write-Host "Connecting to Tenant Admin Site '$($SiteURL)'" 
    Connect-PnPOnline -Url $SiteURL -Credentials $creds
    Write-Host "Connection Successfull"
}

Function AllSiteCollAndSubWebs() {
    Login($Creds)
    $TenantSites = (Get-PnPTenantSite) | Select Title, Url       
       
    ForEach ( $TenantSite in $TenantSites) { 
        Connect-PnPOnline -Url $TenantSite.Url -Credentials $Creds
        Write-Host $TenantSite.Title $TenantSite.Url
        $subwebs = Get-PnPSubWebs -Recurse | Select Title, Url
        foreach ($subweb in $subwebs) { 
            Connect-PNPonline -Url $subweb.Url -Credentials $Creds
            Write-Host $subweb.Title $subweb.Url 
        }  
    }
}

AllSiteCollAndSubWebs
```
 
## Output

![AllSCAndSCW.png](images/AllSCAndSCW.png)
 

## Summary

In this article, we have seen how to get all the site collections and
their subwebs using pnp PowerShell.
Hope this helps! If it is helpful to you then share it with others.
Sharing is caring!
