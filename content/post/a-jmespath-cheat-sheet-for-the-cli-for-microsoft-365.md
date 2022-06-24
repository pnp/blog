---
title: "A JMESPath cheat sheet for the CLI for Microsoft 365"
date: 2021-12-10T04:23:00-05:00
author: "Albert-Jan Schot"
githubname: appieschot
categories: ["Community post"]
tags: ["CLI for Microsoft 365"]
type: "regular"
---

## JMESPath

The [CLI
documentation](https://pnp.github.io/cli-microsoft365/user-guide/cli-output-mode/) explains
some of the basics of filtering. So for the common scenario's like
filtering on a Title it still I found the cases pretty straight forward.
You can filter on any properties that are returned.

Yet for some other options I found it harder to find samples, especially
if the CLI does return nested objects.

## CLI for Microsoft 365 data 

If you are working with CLI you get your data returned as JSON by
default. So you can test your queries live
at [JMESPath.org ](https://jmespath.org/)using a response from the
CLI.  Some simplified JSON for listing all sites using
the `m365 spo site classic list --output json` would look as follows.

``` json
 [{
    "_ObjectType_": "Microsoft.Online.SharePoint.TenantAdministration.SiteProperties",
    "AllowDownloadingNonWebViewableFiles": true,
    "AllowEditing": false,
    "Title": "Demo 1"
 },
 {
    "_ObjectType_": "Microsoft.Online.SharePoint.TenantAdministration.SiteProperties",
    "AllowDownloadingNonWebViewableFiles": false,
    "AllowEditing": false,
    "Title": "A Demo 2"
 },
 {
    "_ObjectType_": "Microsoft.Online.SharePoint.TenantAdministration.SiteProperties",
    "AllowDownloadingNonWebViewableFiles": true,
    "AllowEditing": false,
    "Title": "Sample 1"
 }]

```

The most common queries are either to filter based on a specific
property, or use a `contains, starts_with or ends_with` on a specific
property. The final scenario is to limit the return values to have a
smaller data set: 

-   `[?Title == 'Demo 1']` would return **only the first item** as it
    matches on the title *Demo 1*
-   `[?contains(Title, 'Demo')]` would return **the first two items** as
    it matches the Title on the word *Demo*
-   `[?contains(*, 'Demo 1')]` would return **any item in the array
    where the value of any property** would be *Demo 1*, currently only
    the first item.
-   `[?starts_with(Title, 'Demo')]` would only return **the first
    item** as it filters the title to start with *Demo*
-   `[?ends_with(Title, '1')]` returns **the first and last item**, as
    the title ends with a *1*
-   `[?contains(Title, 'Demo') && AllowDownloadingNonWebViewableFiles]` returns **only
    the first item** as it combines two filters.
-   `[*].Title` returns **only the Titles** for all items.
-   `[*].{Title: Title}` returns **all items as array with a Title
    property**.

You can also use filters on sizing using comparison
operators `[?value < 100]`. This can come in handy if you want to filter
out based on sizes. 

For more complex scenario JMESPath can also help out. Besides filtering
you can use sorting options. Obviously you can sort your data set using
PowerShell or Bash. However in in some cases  you might want to apply
the logic with JMESPath so it would work cross platform. As with the
previous sample, some dummy `json` and you can test your queries. 

``` {.json data-lang="json"}
[
  {
    "Report Refresh Date": "2021-06-15",
    "User Principal Name": "garthf@contoso.com",
    "Is Deleted": "False",
    "Deleted Date": "",
    "Last Activity Date": "2020-07-07",
    "Viewed Or Edited File Count": "0",
    "Synced File Count": "0",
    "Shared Internally File Count": "0",
    "Shared Externally File Count": "0",
    "Visited Page Count": "0",
    "Assigned Products": "OFFICE 365 E3",
    "Report Period": "7"
  },
  {
    "Report Refresh Date": "2021-06-15",
    "User Principal Name": "sands@contoso.com",
    "Is Deleted": "False",
    "Deleted Date": "",
    "Last Activity Date": "",
    "Viewed Or Edited File Count": "152",
    "Synced File Count": "0",
    "Shared Internally File Count": "0",
    "Shared Externally File Count": "0",
    "Visited Page Count": "0",
    "Assigned Products": "OFFICE 365 E3",
    "Report Period": "7"
  },
  {
    "Report Refresh Date": "2021-06-15",
    "User Principal Name": "janets@contoso.com",
    "Is Deleted": "True",
    "Deleted Date": "2021-05-15",
    "Last Activity Date": "",
    "Viewed Or Edited File Count": "0",
    "Synced File Count": "0",
    "Shared Internally File Count": "0",
    "Shared Externally File Count": "0",
    "Visited Page Count": "0",
    "Assigned Products": "OFFICE 365 E3",
    "Report Period": "7"
  }
]
```

-   `sort_by(@, &"Last Activity Date")` would return the result set with
    the oldest **Last Activity Date** on top. That means empty dates
    first.
-   `reverse(sort_by(@, &"Last Activity Date"))` would reverse the
    order, shows the newest last activity date on top.
-   `reverse(sort_by(@, &"Viewed Or Edited File Count"))` would return
    the user with the most edited items on top.
-   `reverse(sort_by(@, &"Viewed Or Edited File Count"))[*]."User Principal Name` would
    sort and only return the **User Principal Name** sorted by the most
    edited files on top.
-   `reverse(sort_by(@, &"Viewed Or Edited File Count")) | [0]."User Principal Name"` would
    sort and return the **User Principal Name** for the user with the
    most edited files.
-   `reverse(sort_by(@, &"Viewed Or Edited File Count")) | [?"Is Deleted" == 'False']."User Principal Name"` sorts
    by then **Viewed Or Edited File Count**, then filters out deleted
    users and finally returns the **User Principal Name**

The last two commands show in the previous sample use a `|` to pipe the
command. This allows you to further filter or tweak your set. Besides
using `| [*]` to retrieve all results, or using `| [0]` to get the first
item from the array you can also specify `| [0:3]` to get the top 3
items.

You can also combine different options as sorting and selecting. So
given the previous data sample you can thus
use `reverse(sort_by(@, &"Viewed Or Edited File Count")) | [0:3]."User Principal Name"`.
The query would sort and return the **User Principal Name** for top
three users with the most edited files. 

Hope this cheat sheet helps you in case you are working with JMESPath
queries and don't hesitate to share your common scenario's as well!

**#SharingIsCaring**
