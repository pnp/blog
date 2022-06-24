---
title: "Fetch User Profile Properties From Site Collection And Export To CSV Using PNP PowerShell"
date: 2021-03-24T06:13:00-04:00
author: "Chandani Prajapati"
githubname: chandaniprajapati
categories: ["Community post"]
images:
- images/OP.png
tags: ["PnP PowerShell", "SharePoint"]
type: "regular"
---

## Introduction 
 
Many times we have a requirement like to get users or user profile
properties from any SharePoint site collection and we need it in CSV or
Excel format. so to achieve this solution we will use PnP PowerShell. 
 
Let's see step-by-step implementation.
 
## Prerequisites 

If we are using Window 10 or we have PowerShellGet then we can run the
below commands to install PnP PowerShell and AzureAD Modules\

Install PnP PowerShell Module,
 
 
```powershell
Install-Module SharePointPnPPowerShellOnline -Scope CurrentUser  
```
 
 
## Implementation 
 
-   Open Windows PowerShell ISE
-   Create a new file and write a script
 
Now we will see all the steps which we required to achieve the solution:

1.  We will read the site URL from the user
2.  then we will connect to the O365 admin site and then we will connect to the site which the user has entered
3.  Create a function to bind a CSV
4.  Create a function to get user profile properties by email
5.  In the main function we will write a logic to get web and users of
site collection URL and then get all the properties and bind it to CSV
 
So at the end, our script will be like this,
 
 
 
```powershell
$basePath = #base path where you want to save CSV file("D:\Chandani\...\")
$dateTime = "{0:MM_dd_yy}_{0:HH_mm_ss}" -f (Get-Date)
$csvPath = $basePath + "\userdetails" + $dateTime + ".csv"
$adminSiteURL = "https://****-admin.sharepoint.com/" #O365 admin site URL
$username = #user email id
$password = "********"
$secureStringPwd = $password | ConvertTo-SecureString -AsPlainText -Force 
$Creds = New-Object System.Management.Automation.PSCredential -ArgumentList $username, $secureStringPwd
$global:userDetails = @()
$index = 1;
$userInfo;
  
Function Login() {
    [cmdletbinding()]
    param([parameter(Mandatory = $true, ValueFromPipeline = $true)] $Creds)
 
    #connect to O365 admin site
    Write-Host "Connecting to Tenant Admin Site '$($adminSiteURL)'" -f Yellow | Out-File $LogFile -Append -Force
  
    Connect-PnPOnline -Url $adminSiteURL -Credentials $Creds
    Write-Host "Connection Successfull" -f Yellow | Out-File $LogFile -Append -Force
   
}
Function StartProcessing {
    Login($Creds);
    ConnectionToSite($Creds)
}
Function ConnectionToSite() {
    $siteURL = Read-Host "Please enter site collcetion URL" 
  
    try {            
        Write-Host "Connecting to Site '$($siteURL)'" -f Yellow          
                              
        $SCWeb = Get-PnPWeb -Identity ""              
                                                     
        $getusers = Get-PnPUser -Web $SCWeb
        ForEach ($user in $getusers) { 
            $email = $user.Email
            If ($email) {
                $userInfo = GetUserProfileProperties $email        
                #creating object fro CSV
                $global:userDetails += New-Object PSObject -Property ([ordered]@{                   
                        Id            = $index
                        GUID          = $userInfo.'UserProfile_GUID'
                        FirstName     = $userInfo.FirstName
                        LastName      = $userInfo.LastName
                        WorkEmail     = $userInfo.WorkEmail 
                        PictureURL    = $userInfo.PictureURL    
                        Department    = $userInfo.Department
                        PreferredName = $userInfo.PreferredName                        
                    })
                $index++ 
            } 
        }                                                                
    }
    catch {
        Write-Host -f Red "Error in connecting to Site '$($TenantSite)'"                        
    }                                     
    BindingtoCSV($global:userDetails) 
}
Function BindingtoCSV {
    [cmdletbinding()]
    param([parameter(Mandatory = $true, ValueFromPipeline = $true)] $Global)   
    Write-Host -f Yellow "Exporting to CSV..."
    $userDetails | Export-Csv $csvPath -NoTypeInformation -Append
    Write-Host -f Yellow "Exported Successfully..."
}
Function GetUserProfileProperties($username) {
    $Properties = Get-PnPUserProfileProperty -Account $username
    $Properties = $Properties.UserProfileProperties
   
    If ($Properties) {
        $Properties = $Properties
    }
    else {
        $Properties = $null
    }
    return $Properties
}
StartProcessing
```
 
 
 
In the above script do the following changes:
 
1. Change O365 Site URL, base path, username, and password
2. To check all the properties you can print **\$userInfo** and then
change **\$global:userDetails** object as per your requirement at where
I have used **\$userInfo.FirstName,LastName** etc.
 
Then run the script with the **F5** command.
 
## Output 
 
![OP.png](images/OP.png)
 
 
After this check the CSV file at your base location.
 
## Summary 
 
So in this article, we have seen how to get user and user profile
properties and as well as how to export them to CSV.
 
Hope this helps! If it is helpful to you then share it with others.
 
Sharing is caring!
