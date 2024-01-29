---
title: "Add multiple users to a SharePoint Group using single API Call"
date: 2021-08-18T12:10:00-04:00
author: "Arjun Menon"
githubname: arjunumenon
categories: ["Community post"]
tags: []
type: "regular"
---

Adding a user to a SharePoint group from custom solutions via REST API
in SharePoint Framework (SPFx) solutions or Power Automate or any other
custom solutions is a very common scenario. In those scenarios, we rely
on the site groups
api `_api/web/sitegroups({GROUPID})` and add the `LoginName`
 in the Body. This will be a perfect solution if you
just need to add only 1 user to the group.

Imagine scenarios where you have more than 1 user to be added to the
group. Unfortunately, the above API does not support adding more than 1
user in the Payload. That being the case, for achieving the same result,
you may have to call the API in a recursive fashion which is not a very
efficient way of execution if you have quite a large number of users to
be added and repeated API calls would not be an optimal solution when
you design your application.

## Alternate API endpoint to the rescue

Don't worry, there is another endpoint that you can rely upon which will
achieve the same result which
is [`/_api/SP.Web.ShareObject`](https://learn.microsoft.com/dotnet/api/microsoft.sharepoint.client.web.shareobject?view=sharepoint-csom).
This is the same endpoint that is used when you add users to the Owners
/ Members / Visitors from the user interface of the Modern SharePoint
site. This endpoint is used primarily for sharing the Site, Folder,
Document, etc. This is the same endpoint that is used when you want to
share with external users as well. It also has a property which
is `roleValue` through which you
can specify Id of the SharePoint Group. So the entire API call may look
something like below.


`POST https://TenantName.sharepoint.com/SiteName/_api/SP.Web.ShareObject`

BODY:

```JSON
{
    "url": "https://tenantname.sharepoint.com/sites/SiteName",
    "peoplePickerInput": "[{"Key":"user1@tenantname.onmicrosoft.com"},{"Key":"user2@tenantname.onmicrosoft.com"}]",
    "roleValue": "group:32"
}
```

**Notice.** This REST API is not officially documented by Microsoft, so
it's not officially supported to be used externally by partners and
customers. This means that the signature can be changed without further
notice.

### Details

As you can see the major property which is relevant for us
is `peoplePickerInput`


`peoplePickerInput`: Used to
give the list of Usernames that needs to be added the SharePoint Group.
Its value is a JSON array of Key Value Pair
(`{"Key":"user1@tenantname.onmicrosoft.com"}` where the Username is given the Value.

`roleValue` : We will give the
Id of the SharePoint Group to this value in the
format `group:{GROUPID}`. This
will be the Id of the SharePoint group to which the above-mentioned
users will be added.

Since this API has a feature to share the site or document with external
users also, it has [many
properties](https://learn.microsoft.com/dotnet/api/microsoft.sharepoint.client.web.shareobject?view=sharepoint-csom#parameters) which
will be relevant in those scenarios. But for us, since we are just
adding the user to the SharePoint group, all we need is the above list
of objects in the JSON body.

### Caveats

> With Power comes ~~Responsility~~ Caveats (Some)

Since we are using the API which is used for [Sharing the
Site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658),
the API even supports adding the permission to the users albeit users
are not part of your Active Directory. That being the case when you try
to add the users who are not part of your AD, there will be 2 outcomes.

### [Sharing Options is "Anyone"](https://learn.microsoft.com/sharepoint/change-external-sharing-site#which-option-to-select)

When you have external sharing enabled and are trying to add a user who
is not part of your site there wouldn't be any error thrown by the API,
but instead, a Sharing Link will be generated. So if you want to ensure
that there are no inadvertent sharing links, ensure that you are
checking the presence of the user before you execute the endpoint.
Otherwise, over time there will be a large number of sharing links
cluttering in your web

In the other cases of sharing, when the user does not exist, you will
get an error that will be thrown by the endpoint.

## CLI for Microsoft 365

If you need to automate the same scenario or execute via scripts, you
can use a command from [CLI for Microsoft
365](https://pnp.github.io/cli-microsoft365/) which
is `m365 spo group user add`. [This
command](https://pnp.github.io/cli-microsoft365/cmd/spo/group/group-member-add) will
allow you to add multiple users to SharePoint group. If you have an
automation or provisioning solution which has this scenario, it is going
to be super helpful.

Photo by [Alex Suprun](https://unsplash.com/@sooprun) on Unsplash
