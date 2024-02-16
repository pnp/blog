---
title: "Get Associated Groups (Owners, Members, Visitors) of a SharePoint Site"
date: 2021-07-19T03:14:00-04:00
author: "Arjun Menon"
categories: []
tags: []
type: "regular"
---

There will be cases where you want to know the associated Owner or a
Member or a Visitor group of a specific SharePoint site. This will be
very much needed if you want to,

1.  assign permission
2.  to get the owners from the Owner Group.
3.  Or many many other use cases


This will be super helpful if you want to get the default groups when
you get the Web properties. Especially when you are automating web
provisioning along with the Permissions.
For doing that you can use the properties
like [associatedOwnerGroup](https://learn.microsoft.com/previous-versions/office/sharepoint-visio/jj245638(v=office.15)), [associatedMemberGroup](https://learn.microsoft.com/previous-versions/office/sharepoint-visio/jj245549(v=office.15)), [associatedVisitorGroup](https://learn.microsoft.com/previous-versions/office/sharepoint-visio/jj247047(v=office.15)) in
REST API for getting the SP Web Properties REST API
- `https://contoso.sharepoint.com/sites/contososite/_api/web`.
So the entire REST call with all the associated groups
(`associatedOwnerGroup`, `associatedMemberGroup`, `associatedVisitorGroup`), your complete REST API endpoint would look
something like below
`https://contoso.sharepoint.com/sites/contososite/_api/web?`
`$expand=AssociatedOwnerGroup,AssociatedMemberGroup,AssociatedVisitorGroup`
The above REST call would fetch the associated group information of a
particular SharePoint Web. Once you execute the API, you will get the
result something like below.
 
 

 
```json
{
    "AssociatedMemberGroup": {
        "Id": 5,
        "IsHiddenInUI": false,
        "LoginName": "Contoso Site Members",
        "Title": "Contoso Site Members",
        "PrincipalType": 8,
        "AllowMembersEditMembership": true,
        "AllowRequestToJoinLeave": false,
        "AutoAcceptRequestToJoinLeave": false,
        "Description": null,
        "OnlyAllowMembersViewMembership": false,
        "OwnerTitle": "Contoso Site Owners",
        "RequestToJoinLeaveEmailSetting": ""
    },
    "AssociatedOwnerGroup": {
        "Id": 3,
        "IsHiddenInUI": false,
        "LoginName": "Contoso Site Owners",
        "Title": "Contoso Site Owners",
        "PrincipalType": 8,
        "AllowMembersEditMembership": false,
        "AllowRequestToJoinLeave": false,
        "AutoAcceptRequestToJoinLeave": false,
        "Description": null,
        "OnlyAllowMembersViewMembership": false,
        "OwnerTitle": "Contoso Site Owners",
        "RequestToJoinLeaveEmailSetting": ""
    },
    "AssociatedVisitorGroup": {
        "Id": 4,
        "IsHiddenInUI": false,
        "LoginName": "Contoso Site Visitors",
        "Title": "Contoso Site Visitors",
        "PrincipalType": 8,
        "AllowMembersEditMembership": false,
        "AllowRequestToJoinLeave": false,
        "AutoAcceptRequestToJoinLeave": false,
        "Description": null,
        "OnlyAllowMembersViewMembership": false,
        "OwnerTitle": "Contoso Site Owners",
        "RequestToJoinLeaveEmailSetting": ""
    }
}
```
 

This also would be super handy if you want to have a [Power
Automate](https://flow.microsoft.com/) which will assign users to
default SharePoint Owner or Member of Visitor Group.
 
## Get Associated Groups in scripts for automation

If you want to have the same functionality for writing automated
scripts, [CLI for Microsoft
365](https://pnp.github.io/cli-microsoft365/cmd/spo/web/web-get#options) has
a command called `m365 spo web get`. If you
execute `m365 spo web get` with
the option, `--withGroups` you
will get the complete Web Properties along with the associated groups
(`associatedOwnerGroup`, `associatedMemberGroup`, `associatedVisitorGroup`).
 
Supercool isn't it?
