---
title: "CLI for Microsoft 365 - how cool is that? - Permission commands"
date: 2022-11-01T02:44:24+06:00
# post thumb
images:
  - images/main.png
#author
author: "Adam Wójcik"
githubname: Adam-it
# description
description: "CLI for Microsoft 365 is a cross platform command line tool based on Node.js that helps you manage many things around Microsoft 365 and your SPFx project (yes, that as well 🤩. rename, upgrade ... you name it). You may manage OneDrive, Planner, Power Apps and Automate, Teams, Yammer, SharePoint (of course). The list keeps on growing and growing. Lets check some new commands added to CLI which allow us manage permissions on many different levels in SharePoint Online."
summary: "CLI for Microsoft 365 is a cross platform command line tool based on Node.js that helps you manage many things around Microsoft 365 and your SPFx project (yes, that as well 🤩. rename, upgrade ... you name it). You may manage OneDrive, Planner, Power Apps and Automate, Teams, Yammer, SharePoint (of course). The list keeps on growing and growing. Lets check some new commands added to CLI which allow us manage permissions on many different levels in SharePoint Online."
# Taxonomies
categories: ["Community post"]
tags: ["CLI for Microsoft 365"]
type: "regular" 
---

SharePoint Online gives you the possibility to manage permissions on many different levels: webs, lists, folders, files, and items. Breaking role inheritance may not always be the best idea to do and should rather be considered as last resort, but it is not always possible to create an enterprise, tailor-made, solution without it. Thanks to the awesome work done by the community, the CLI for Microsoft 365 now has new commands that will allow us to accomplish that.


## 🤔 But first of all what is CLI for Microsoft 365? Quick intro


If you already know what the CLI for M365 is, then I suppose you may skip this part😀. CLI for Microsoft 365 is a cross platform command line tool based on Node.js that helps you manage many things around Microsoft 365 and your SPFx projects (yes, that as well 🤩. rename, upgrade ... you name it). To name a few, you may manage OneDrive, Planner, Power Apps and Automate, Teams, Yammer, SharePoint (of course). The list keeps on growing and growing, [check out the CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/). But it's not only about managing Microsoft 365. The CLI helps you also manage your own SPFx environment (check out the [doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor/)) or projects (rename, upgrade etc.). This is a very unique feature that many similar command line tools don't have. Some commands do simple things, but some are actually ready to use scenarios all done under a single command. Check out the full list of [commands](https://pnp.github.io/cli-microsoft365/cmd/login/#usage)


## 🎚️ Permission Levels


It all starts with defining what roles (permission levels) you will want to use. Each SharePoint site starts with a set of default role definitions, like: Full Control, Design, Edit, Contribute, Read. Those are the basic role definitions needed for most use cases we may think of, but if something is missing, then SharePoint gives us the possibility to extend permission levels with our custom made role definitions with different sets of permissions we may give, grouped in list, site, personal permissions. Exactly this scenario is covered by the first set of commands now available in the CLI for Microsoft 365. We may use


```powershell
spo roledefinition list/get/add/remove
```


commands to do everything we need in this area. When adding a new role definition, we may pick any set of permissions from the following list:


```json
EmptyMask, ViewListItems, AddListItems, EditListItems, DeleteListItems, ApproveItems, OpenItems, ViewVersions, DeleteVersions, CancelCheckout, ManagePersonalViews, ManageLists, ViewFormPages, AnonymousSearchAccessList, Open, ViewPages, AddAndCustomizePages, ApplyThemeAndBorder, ApplyStyleSheets, ViewUsageData, CreateSSCSite, ManageSubwebs, CreateGroups, ManagePermissions, BrowseDirectories, BrowseUserInfo, AddDelPrivateWebParts, UpdatePersonalWebParts, ManageWeb, AnonymousSearchAccessWebLists, UseClientIntegration, UseRemoteAPIs, ManageAlerts, CreateAlerts, EditMyUserInfo, EnumeratePermissions, FullMask
```


in the `rights` option.


What's worth mentioning is also the additional information (value) added when retrieving role definitions. CLI for Microsoft 365 when retrieving data usually outputs the response of the used API endpoint. For the role definition, the output is unfortunately not that user friendly.
Let's check what the SharePoint REST API gives when retrieving a custom created role definition:


```json
{
  "BasePermissions": {
    "High": "0",
    "Low": "67567639"
  },
  "Description": "",
  "Hidden": false,
  "Id": 1073741934,
  "Name": "test",
  "Order": 2147483647,
  "RoleTypeKind": 0,
}
```


Wait, what? So what exactly are the permissions given for that role definition? What does `67567639` mean 🤔? Luckily for us, CLI does the additional translation and adds this information. For the above response when running


```powershell
m365 spo roledefinition get --webUrl https://someTenant.sharepoint.com/sites/someSite --id 1073741934
```


we will get


```json
{
  "BasePermissions": {
    "High": "0",
    "Low": "67567639"
  },
  "Description": "",
  "Hidden": false,
  "Id": 1073741934,
  "Name": "test",
  "Order": 2147483647,
  "RoleTypeKind": 0,
  "BasePermissionsValue": [
    "ViewListItems",
    "AddListItems",
    "EditListItems",
    "ApproveItems",
    "Open",
    "ViewPages",
    "AddAndCustomizePages",
    "BrowseDirectories"
  ],
  "RoleTypeKindValue": "None"
}
```


Now, ok, now I get it 😉.


For more information, check out the following commands:


- [`spo roledefinition get`](https://pnp.github.io/cli-microsoft365/cmd/spo/roledefinition/roledefinition-get/) - Gets specified role definition from web
- [`spo roledefinition list`](https://pnp.github.io/cli-microsoft365/cmd/spo/roledefinition/roledefinition-list/) - Gets list of role definitions for the specified site
- [`spo roledefinition add`](https://pnp.github.io/cli-microsoft365/cmd/spo/roledefinition/roledefinition-add/) - Adds a new roledefinition to web
- [`spo roledefinition remove`](https://pnp.github.io/cli-microsoft365/cmd/spo/roledefinition/roledefinition-remove/) - Removes the role definition from the specified site


## 🔓🔒 Roleinheritance break/reset


After defining custom role definitions, the next step is breaking role inheritance on an item, list, or web. The most advanced secure scenarios sooner or later will require providing some unique permissions on list, folder, item or file level. It's best to always inherit permissions for as long as possible, and when breaking the inheritance, be aware of the [limitations](https://learn.microsoft.com/en-us/sharepoint/troubleshoot/lists-and-libraries/error-share-break-inheritance). The CLI for Microsoft 365 now has a set of commands you may use on any level that will allow you to either break or reset role inheritance. When breaking role inheritance, the currently defined permissions will be kept. In order to clear all existing permissions, we may use `clearExistingPermissions` option.


For more information, check the docs for the following commands:


- [`spo file roleinheritance break`](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-roleinheritance-break/)
- [`spo file roleinheritance reset`](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-roleinheritance-reset/)
- [`spo folder roleinheritance break`](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-roleinheritance-break/)
- [`spo folder roleinheritance reset`](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-roleinheritance-reset/)
- [`spo list roleinheritance break`](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-roleinheritance-break/)
- [`spo list roleinheritance reset`](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-roleinheritance-reset/)
- [`spo listitem roleinheritance break`](https://pnp.github.io/cli-microsoft365/cmd/spo/listitem/listitem-roleinheritance-break/)
- [`spo listitem roleinheritance reset`](https://pnp.github.io/cli-microsoft365/cmd/spo/listitem/listitem-roleinheritance-reset/)
- [`spo web roleinheritance break`](https://pnp.github.io/cli-microsoft365/cmd/spo/web/web-roleinheritance-break/)
- [`spo web roleinheritance reset`](https://pnp.github.io/cli-microsoft365/cmd/spo/web/web-roleinheritance-reset/)


## 🪪 roleassignment add/remove


Now that we have unique permissions set on item (file, folder), list or web we may start modifying them by adding or removing role assignments to a group or user. The CLI for Microsoft 365 makes this process very convenient, as we may specify the user or group by name. For example, if we would like to grant `Editor` role to a user with mail `someaccount@tenant.onmicrosoft.com` on a list, we may just run:


```powershell
m365 spo list roleassignment add --webUrl "https://contoso.sharepoint.com/sites/project-x" --listTitle "someList" --upn "someaccount@tenant.onmicrosoft.com" --roleDefinitionName "Editor"
```


It's that simple 😎.


For more information check the docs for the following commands:


- [`spo file roleassignment add`](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-roleassignment-add/)
- [`spo file roleassignment remove`](https://pnp.github.io/cli-microsoft365/cmd/spo/file/file-roleassignment-remove/)
- [`spo folder roleassignment add`](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-roleassignment-add/)
- [`spo folder roleassignment remove`](https://pnp.github.io/cli-microsoft365/cmd/spo/folder/folder-roleassignment-remove/)
- [`spo list roleassignment add`](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-roleassignment-add/)
- [`spo list roleassignment remove`](https://pnp.github.io/cli-microsoft365/cmd/spo/list/list-roleassignment-remove/)
- [`spo listitem roleassignment add`](https://pnp.github.io/cli-microsoft365/cmd/spo/listitem/listitem-roleassignment-add/)
- [`spo listitem roleassignment remove`](https://pnp.github.io/cli-microsoft365/cmd/spo/listitem/listitem-roleassignment-remove/)
- [`spo web roleassignment add`](https://pnp.github.io/cli-microsoft365/cmd/spo/web/web-roleassignment-add/)
- [`spo web roleassignment remove`](https://pnp.github.io/cli-microsoft365/cmd/spo/web/web-roleassignment-remove/)



## 🙏 THANK YOU


The commands described in this article were mostly developed thanks to the great help CLI for Microsoft 365 has received from the community. The provided functionality and improvements that were added along the way are truly awesome, and as one of the maintainers, I would like to express my gratitude to all the contributors engaged in the CLI repo. You ROCK 🤩.

## 🙋 Wanna help out?

CLI for Microsoft 365 is a great tool to use and also great place to learn GIT best practices, how to use SharePoint, Graph or other APIs. This tool is constantly improving and we are always open for contributors like you to make this tool even better 💪. Don't worry if you don't know how to start or what you could do. Just check out the [contributing guide](https://github.com/pnp/cli-microsoft365/blob/main/CONTRIBUTING.md) and [issues list](https://github.com/pnp/cli-microsoft365/issues) and give it a shot. If I still didn't convince you, check out the [7 reasons to contribute to the community](https://pnp.github.io/blog/post/7-reasons-to-contribute-to-the-community/) by [Martin Lingstuyl](https://github.com/martinlingstuyl/). I will be waiting for your PRs. Let me know if you need any help to get started 👍.
