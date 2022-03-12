---
title: "Assigning a built-in role to the group at resource group scope level using PowerShell scripts"
summary: "This article is focused on the following 4 sections: Creating new resource group, Fetching User Object Id, Creating an azure AD group with the user using user’s object Id, Assigning a built in ‘Reader’ role to the group at resource group scope level"
date: 2022-03-03T01:57:00-05:00
author: "Shrusti Shah"
categories: []
images: []
tags: ["PowerShell"]
type: "regular"
---

This article is focused on the following 4 sections.

1.  Creating new resource group
2.  Fetching User Object Id
3.  Creating an azure AD group with the user using user’s object Id
4.  Assigning a built in ‘Reader’ role to the group at resource group scope level

Let’s start writing the scripts section wise as mentioned above, to achieve our intention,

## Firstly, Creating a new Resource group

```powershell
#Creating New Resource Group

#Connecting to Azure Account using your username and password

Connect - AzAccount

#To Validate if resource group already exists in the given location or not

resourcegroupname = “Test-rg”

$location = “West Europe”

Get-AzResourceGroup -Name$resourcegroupname -location $location

#If resource group not exists, Create a new resource group

$rg = New-AzResourceGroup -Name $resourcegroupname -Location $location

#Print the Resource Group Name as output in your PowerShell

Write-Output $rg.ResourceGroupName

#Save Resource group name to a variable as we will use in the upcoming steps

$nameofresourcegroup = $rg.ResourceGroupName

Write-Output $nameofresourcegroup

#This finishes 1st section of creating a Resource Group at specific location using PowerShell script
```
   

## As per the second step mentioned, we will now fetch the user object id to add it to the group in the next step

```powershell
#This finishes 1st section of creating a Resource Group at specific location using PowerShell script

#Fetching user id

#Connect to Azure if not have any existing connection

Connect-AzAccount

#Get user id using the below mentioned script by passing email id of user

$userid = Get-AzADUser -Filter "UserPrincipalName eq 'test@domain.onmicrosoft.com'"

#Print the output

Write-Output $userid

#Print and save the user id in another variable to use it in the next step

$useridfetched = $userid.id

#Print the id in your PowerShell

Write-Output $useridfetched
```

## Now, as per the third step mentioned, we will add the user to the group for that we will need users’ id which we have fetched from the above step

```powershell
#Creating group will need 2 inputs, group name and user id fetched from the above step

$azureadgroupname = "Test_AD_Group"

$useridfetched

#To validate if the same group exists or not

Get-AzADGroup | Where-Object { $_.DisplayName -eq $azureadgroupname }

#if group does not exists create a new one

$newgroup = New-AzADGroup -DisplayName $azureadgroupname -MailNickName "NotSet"

#Now is the time to add user to the newly created group where we will pass created group id value to TargetGroupObjectId parameter and useridfetched to MemberObjectId parameter

$usergroup = Add-AzADGroupMember -TargetGroupObjectId $newgroup.Id -MemberObjectId $useridfetched

#Print output with created group id and group name

$groupId = $newgroup.Id

$groupName = $newgroup.Name

Write-Output $groupId

Write-Output $groupName

#Azure AD group with user is created using PowerShell scripts
```


## Now is the time for the last step mentioned, which will assign the built-in reader role to the newly created group with users at newly created resource group scope level

```powershell
#For assigning role to the group at scope level we will need 3 inputs, resource group name which we have as an output from the first section, group object id which we have as an output from the previous section and a built-in role name

$groupId

$nameofresourcegroup

$rolename = "Reader"

#To validate if the role assignment already exists or not

Get-AzRoleAssignment -ObjectId $groupId -RoleDefinitionName $rolename -ResourceGroupName $nameofresourcegroup

#If it does not exists, we will create assign the created group the specified role at resource group scope level

# you can also change the built-in role and scope as per your usage

$roleassignment = New-AzRoleAssignment -ObjectId $groupId -RoleDefinitionName $rolename -ResourceGroupName $nameofresourcegroup

#Output the role assignment namd and Id

$roleassignementId = $roleassignment.RoleAssignmentId

$roleassignmentName = $roleassignment.RoleAssignmentName

Write-Output $roleassignementId

Write-Output $roleassignmentName

#Voila, it’s time to validate the performed operations on the Azure Portal
```

Now navigate to your **Azure Portal** > **Resource Group**,

Check for the newly created resource group, redirect to the **Access control** > **Role assignments** and check if you can see the newly created group with the `Reader` role.

I hope this article seems useful for all the automation use cases related to Azure AD

Keep Learning!

Keep Sharing!
