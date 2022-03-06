---
title: "Create Report Of Assigned Licenses To Users From Microsoft 365"
date: 2021-09-02T12:08:00-04:00
author: "Dipen Shah"
githubname: dips365
categories: ["Power Automate", "SharePoint", "Microsoft Graph"]
images:
- images/blog/create-report-of-assigned-licenses-to-users-from-microsoft-365/Reports2.png
tags: []
type: "regular"


---

### Introduction 

Power automate is a tool that enables you to implement queries without
knowing hardcore coding patterns. Microsoft Graph API is the universal
endpoint for Microsoft 365 which give you the flexibility to access
azure active directory resource through single endpoint using power
automate.

I am writing this article to share how we can implement Graph API with
Power automate to generate reports and this implementation would be
useful to IT Admin who is responsible for AD resources and related
reports.

Today, I am going to write steps to generate reports for users along
with the list of licenses are assigned.
**Definition**
Generate an excel report on 1st day of each month for users, a list of
assigned licenses to each user along with the metadata of users, and
store excel report in the SharePoint document library.

**Learning Objectives**

1.  Register Application and Grant Permission in Azure Active Directory
2.  Create Scheduler in Power Automate
3.  Access SharePoint list in Power Automate
4.  Array Filter in Power Automate
5.  Connect to Graph API
6.  Excel Online Connectors in Power Automate
7.  Add row to Excel Worksheet.
   
**Prerequisites**

1.  Microsoft 365 Account
2.  License to access Power Automate
3.  SharePoint Site with Site Collection Administrator
4.  Create Excel Template including worksheets and tables and upload it
    to the SharePoint document library. The sample Template file is
    added to the attachment.
Let's get started !!

## Step 1 - Create a new SharePoint List to stores licenses Product Name

and SKU IDs**
When we get the user's assigned licenses from Graph API then it returns
SKU ID only. So, we can use this list to filter Product Names from SKU
ID. [Click
here](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-service-plan-reference) to
get a list of licenses product names and SKU IDs.

Create a new list called "licenses" in SharePoint Site and add a column
called GUID. Add Product Name and GUID from above Microsoft Documents.
{{< image alt="Reports 13.jpg" src="images/blog/create-report-of-assigned-licenses-to-users-from-microsoft-365/Reports 13.jpg" >}}

## Step 2 - Register Application and Azure Active Directory

### Application Creation

-   Open [Azure portal](http://portal.azure.com/)
-   Click on azure active directory
-   Click on App registration
-   Click on New Registration
-   Enter the Name of the application
-   Select 'Accounts in this organizational directory only '
-   Click on register
-   Copy Application ID and Tenant ID and put it aside, we will use it
    in power automate.

### Generate Secret Key

-   Click on 'Certificates & secrets' in the newly created application.
-   Click on New client secret
-   Add description
-   Select Expires to 24 months.
-   Click on Add
-   Copy the value of the Secret key and put it aside, we will use it in
    power automate.

### Grant API Permission

-   Click on API Permission
-   Click on 'Add a permission'
-   Select Microsoft Graph
-   Select Application Permission
-   Find and Select '**User.Read.All**'
-   Click on Add Permission
-   Click on **Grant Admin consent** for `<Tenant Name>`

## Step 3 - Create Power Automate from Recurrence trigger

Open power automates from App list in Microsoft 365.
Create new flow -> Select Recurrence -> Select month -> Create.
{{< image alt="Create report of assigned licenses for users from Microsoft 36502.gif" src="images/blog/create-report-of-assigned-licenses-to-users-from-microsoft-365/Create report of assigned licenses for users from Microsoft 36502.gif" >}}

## Step 4 - Initialize variables in Power Automate

We need 7 variables that will store multiple values and use them to
generate reports.
{{< image alt="Reports2.png" src="images/blog/create-report-of-assigned-licenses-to-users-from-microsoft-365/Reports2.png" >}}
Paste Tenant ID, Client Secret and Client ID which we had from the azure
active directory.

## Step 5 - Get Licenses from SharePoint list in Power Automate

We will use 'Get Items' and 'Append to array object' connectors in
power to automate.
{{< image alt="Reports 3.png" src="images/blog/create-report-of-assigned-licenses-to-users-from-microsoft-365/Reports 3.png" >}}

## Step 6 - Create report file from excel template

We will get file content from a template file that is store in the
SharePoint document library and create a new file that will be used to
store users' details in it.
We will use "Get File Content" to get content from the existing excel
file template and "Create File" to create a new file in the desire
location in SharePoint.
{{< image alt="Report4.1.png" src="images/blog/create-report-of-assigned-licenses-to-users-from-microsoft-365/Report4.1.png" >}}-align-inline image-alt="Report4.1.png" style="width: 625px;"}
 
## Step 7 - Access Excel worksheet in Power Automate

We will get worksheets from excel sheet using Excel Online connector in
Power automate.
Get all sheets from excel file using "get Worksheet: connector.
"Parse JSON" connector is used to access response from getting Worksheet
connector.
{{< image alt="Report5.png" src="images/blog/create-report-of-assigned-licenses-to-users-from-microsoft-365/Report5.png" >}}
JSON Schema for Parse JSON should be the same as below.
 
 
 
```json
{
    "type": "object",
    "properties": {
        "@@odata.context": {
            "type": "string"
        },
        "value": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "@@odata.id": {
                        "type": "string"
                    },
                    "id": {
                        "type": "string"
                    },
                    "name": {
                        "type": "string"
                    },
                    "position": {
                        "type": "integer"
                    },
                    "visibility": {
                        "type": "string"
                    }
                },
                "required": [
                    "@@odata.id",
                    "id",
                    "name",
                    "position",
                    "visibility"
                ]
            }
        }
    }
}
```
 
 
## Step 8 - Get Users using Graph API

"Http" Connector will be used to execute rest API in power automate.
End Point URL
: [https://graph.microsoft.com/beta/users?$filter=userType%20eq%20%27Member%27&$select=displayName,crea...](https://graph.microsoft.com/beta/users?$filter=userType%20eq%20%27Member%27&$select=displayName,createdDateTime,accountEnabled,userPrincipalName,givenName,surname,externalUserState,assignedLicenses)
Method: get
Authentication: Azure Active Directory
Tenant: Add Reference of TenantId variable 
Client Id: Add Reference of Client ID Variable 
Secret: Add Reference of Client Secret Variable
Audience: Add Reference of AudienceURL variable
 {{< image alt="reports7.png" src="images/blog/create-report-of-assigned-licenses-to-users-from-microsoft-365/reports7.png" >}}

Pass JSON schema in Parse JSON Connector.
 
 
```json
{
    "type": "object",
    "properties": {
        "@@odata.context": {
            "type": "string"
        },
        "value": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "@@odata.id": {
                        "type": "string"
                    },
                    "displayName": {
                        "type": "string"
                    },
                    "createdDateTime": {
                        "type": "string"
                    },
                    "accountEnabled": {
                        "type": [
                            "boolean",
                            "null"
                        ]
                    },
                    "userPrincipalName": {
                        "type": [
                            "string",
                            "null"
                        ]
                    },
                    "givenName": {
                        "type": [
                            "string",
                            "null"
                        ]
                    },
                    "surname": {
                        "type": [
                            "string",
                            "null"
                        ]
                    },
                    "externalUserState": {
                        "type": [
                            "string",
                            "null"
                        ]
                    }
                },
                "required": [
                    "@@odata.id",
                    "displayName",
                    "createdDateTime",
                    "accountEnabled",
                    "userPrincipalName",
                    "givenName",
                    "surname",
                    "externalUserState"
                ]
            }
        }
    }
}
```
 
 
 
## Step 9 - Get Assigned Licenses Product Name

We have an array of Product name list which we had created on starting
of the automation.
Let's Access the assigned Licenses object from the user's object which
is getting on the response of HTTP request.

{{< image alt="Create report of assigned licenses for users from Microsoft 36508.jpg" src="images/blog/create-report-of-assigned-licenses-to-users-from-microsoft-365/Create report of assigned licenses for users from Microsoft 36508.jpg" >}}

Let's filter the array if we found licenses are assigned to the user.
We can get SKU ID from the response and we do filter from licenses array
based on SKU IDs.
"Filter Array" action is used to filter items from an existing array
in power automate.

{{< image alt="Reports9.png" src="images/blog/create-report-of-assigned-licenses-to-users-from-microsoft-365/Reports9.png" >}}

## Step 10

Add a new row in the table is created excel file.
{{< image alt="reports10.png" src="images/blog/create-report-of-assigned-licenses-to-users-from-microsoft-365/reports10.png" >}}
Full Power automate will look like as below.
{{< image alt="Create report of assigned licenses for users from Microsoft 36511.gif" src="images/blog/create-report-of-assigned-licenses-to-users-from-microsoft-365/Create report of assigned licenses for users from Microsoft 36511.gif" >}}
The output will be as below.
{{< image alt="Create report of assigned licenses for users from Microsoft 36512.png" src="images/blog/create-report-of-assigned-licenses-to-users-from-microsoft-365/Create report of assigned licenses for users from Microsoft 36512.png" >}}

### Conclusion 

We learned how to connect the SharePoint site and list to Power
automate, Create and append array, Call graph End point, Register
application and Access and Add new Records in Excel worksheet.

Happy
Learning!
