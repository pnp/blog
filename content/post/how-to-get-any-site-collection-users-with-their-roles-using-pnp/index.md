---
title: "How to get any site collection users with their roles using PnP PowerShell?"
date: 2021-04-12T12:48:00-04:00
author: "Chandani Prajapati"
githubname: chandaniprajapati
categories: ["Community post"]
images:
- images/UserRolesOP.png
tags: ["SharePoint", "PnP PowerShell"]
type: "regular"
---

## Introduction 

Sometimes we have a requirement to get reports of users and their roles
on the SharePoint site and we have to export to CSV/Excel format. To
achieve this solution we will use **PnP PowerShell**. 
Let's see step-by-step implementation:
 

## Implementation 

-   Open **Windows PowerShell ISE**
-   Create a new file and write a script
Now we will see all the steps which we required to achieve the solution:
1.  We will read the site URL from the user

2.  Then we will connect to the O365 admin site and then we will connect
to the site which the user has entered
3. Create a function to get user and their roles and store it in an
array
4.  And we will export the array to CSV format

So in the end, our script will be like this,
 
```powershell
$basePath = "E:\Chandani\Blogs\UserRolesPS\"
$dateTime = "{0:MM_dd_yy}_{0:HH_mm_ss}" -f (Get-Date)
$csvPath = $basePath + "\userdetails" + $dateTime + ".csv"
$adminSiteURL = "https://*****-admin.sharepoint.com/" #O365 admin site URL
$username = #Email ID
$password = "********"
$secureStringPwd = $password | ConvertTo-SecureString -AsPlainText -Force 
$Creds = New-Object System.Management.Automation.PSCredential -ArgumentList $username, $secureStringPwd
$global:userRoles = @()


Function Login() {
    [cmdletbinding()]
    param([parameter(Mandatory = $true, ValueFromPipeline = $true)] $Creds)
 
    #connect to the O365 admin site
    Write-Host "Connecting to Tenant Admin Site '$($adminSiteURL)'" -f Yellow
  
    Connect-PnPOnline -Url $adminSiteURL -Credentials $Creds
    Write-Host "Connection Successfull" -f Yellow 
   
}
Function StartProcessing {
    Login($Creds);
    GetUserRoles
}

Function GetUserRoles {
    try {
        $siteURL = Read-Host "Please enter site collection URL"
        Write-Host "Connecting to Site '$($siteURL)'" -f Yellow          
     
        Connect-PnPOnline -Url $siteURL -Credentials $Creds
    
        $web = Get-PnPWeb -Includes RoleAssignments
    
        foreach ($roles in $web.RoleAssignments) {
            $member = $roles.Member
            $loginName = get-pnpproperty -ClientObject $member -Property LoginName
            $title = get-pnpproperty -ClientObject $member -Property Title
            $rolebindings = get-pnpproperty -ClientObject $roles -Property RoleDefinitionBindings
            $roleName = $($rolebindings.Name)            
    
            $global:userRoles += New-Object PSObject -Property ([ordered]@{                   
                    UserName  = $title
                    LoginName = $loginName
                    Roles     = $roleName
                })            
        }       
    }
    catch {
        Write-Host -f Red "Error in connecting to Site '$($TenantSite)'"     
    } 
    Write-Host "Exporting to CSV" -ForegroundColor Yellow      
    $global:userRoles | Export-CSV $csvPath -NoTypeInformation
    Write-Host "Export to CSV successfully!" -ForegroundColor Yellow
}

StartProcessing
```
 
 

## Output 

![UserRolesOP.png](images/UserRolesOP.png)

## Summary 

So in this article, we have seen how to get users and their roles from
any SharePoint site collection and convert it in CSV format.
Hope this helps! If it is helpful to you then share it with others.
Sharing is caring!
