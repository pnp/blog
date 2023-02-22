---
title: "Create Site Script and Site Template Using Power Automate in SharePoint"
date: 2021-09-07T03:46:00-04:00
author: "Dipen Shah"
githubname: dips365
categories: ["Community post"]
images:
- images/Flow2.jpg
tags: ["Power Automate", "SharePoint"]
type: "regular"
---

## Introduction

Many times, the Site is already created, and we need to apply
configuration in the existing site to achieve some level of consistency.
How can we achieve it?\
\
To achieve, this kind of implementation, use site template and site
scripts to automate provisioning to the existing modern site or create a
new site using site templates which is available in your organization
tenant.
\
In the previous version of SharePoint, Site templates were known as site
designs.
Site templates are a set of configurations that need to apply on a
particular site and Site Scripts are JSON files that include an order
list that needs to be executed while we apply it on a Specific
SharePoint Site.


## Learning Objectives

1.  Create JSON file for Site Scripts
2.  Create Power automate
3.  Create Site Script using REST Call in Power Automate
4.  Create Site Template using REST Call in Power Automate
5.  Output

## Prerequisite

1.  M365 environment
2.  Power automate access requires a license
3.  SharePoint Admin Access
4.  Permission
    1.  SharePoint Administrator
    2.  Site Collection Administrator
Let's get started.


## Create JSON file for Site Scripts 

You need to create JSON files in specific formats to implement
SharePoint artifacts in SharePoint Site.
Available Action includes.
![Site Script and Site Template In Power Automate.png](images/Site Script and Site Template In Power Automate.png)
 
```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/sp/site-design-script-actions.schema.json",
  "actions": [
    {
      "verb": "applyTheme",
      "themeName": "Contoso Explorers"
    },
    {
      "verb": "createSPList",
      "listName": "Customer Tracking",
      "templateType": 100,
      "subactions": [
        {
          "verb": "setDescription",
          "description": "List of Customers and Orders"
        }
      ]
    },
    {
        "verb": "setRegionalSettings",
        "timeZone": 2,
        "locale": 1050,
        "sortOrder": 0,
        "hourFormat": "12"
    }
  ],
  "version": 1
}
```
 
Each action identifies by its "verbName" property and inside auction
property, you need to configure the things that you want to apply while
creating the site or on an existing site.
 
## Create Power automate 


Go to [https://portal.office.com](https://portal.office.com/) and click
on Power automate.
Select  "New Flow" and Select "Instant Cloud Flow"
Select "Manually Trigger Flow" and Add Name "Create-SiteTemplate-Flow"
Select  Create Button.
![Site Script and Site Template In Power Automate11.jpg](images/Site Script and Site Template In Power Automate11.jpg)
 
### Create Site Script using REST Call in Power Automate

Initialize variable in power automat to store JSON config.
![Flow2.jpg](images/Flow2.jpg)

Select "Send an HTTP request to SharePoint" from the list of actions.

![Flow3.jpg](images/Flow3.jpg)
 
**Parameters**
Site Address - You can select any site Address either it's root or not\
Method - post\
Url
- /\_api/Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptUtility.CreateSiteScript(Title='\<Site
Script Title Name>')

**Headers**
 
```json
{
  "Content-Type\n": "application/json;charset=utf-8",
  "accept": "application/json;odata.metadata=minimal",
  "odata-version": "4.0"
}
```
 
 
**Body**

@{variables('SiteScript')} // Reference of variable that we
Initialized before this action.
Get Create Script ID and store it in Variable\
\
![Dips365_1-1630571668730.png](images/Dips365_1-1630571668730.png)


### Create Site Template using REST Call in Power Automate

![Dips365_0-1630571387332.png](images/Dips365_0-1630571387332.png)

**Parameters**
Site Address - You can select any site Address either it's root or not\
Method - post\
Url -
/\_api/Microsoft.SharePoint.Utilities.WebTemplateExtensions.SiteScriptUtility.CreateSiteDesign
 

**Headers**

```json
{
  "Content-Type\n": "application/json;charset=utf-8",
  "accept": "application/json;odata.metadata=minimal",
  "odata-version": "4.0"
}
```

**Body**

```json
{
    "info": {
        "Title": "<Site Template Title>",
        "Description": "<Site Template Description>",
        "SiteScriptIds": ["@{variables('ScriptID')}"],
        "WebTemplate": "64"
    }
}
```

The flow looks like as below\
![Flow6.jpg](images/Flow6.jpg)
**Output**
Select  the "gear" Icon in SharePoint Site.
Select  "Apply a site template".
![Site Script and Site Template In Power Automate7.gif](images/Site Script and Site Template In Power Automate7.gif)
 