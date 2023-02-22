---
title: "Break And Change List Item Permission Using PnP JS In SPFx"
date: 2021-03-17T07:38:00-04:00
author: "Chandani Prajapati"
githubname: chandaniprajapati
categories: ["Community post"]
images:
- images/FirstOP.png
tags: ["PnPjs", "SharePoint framework (SPFx)"]
type: "regular"
---

## Introduction

In SPFx many times we have a requirement like break permissions for the
list, list items and etc for the particular users. for eg., we want to
break permission of the list item for XYZ user.so in this article, we will see how to implement break permission of the
list items using PnP js so we can use this in SPFx.

## Implementation

For the testing purpose of our PnP js query, we can use the [SP Editor
extension for
chrome](https://chrome.google.com/webstore/detail/sp-editor/ecblfcmjnbbgaojblcpmjoamegpbodhd?hl=en).
After installation, you can check it in the developer tool. \
So open developer tool(F12) \> SharePoint Tab \> PnP Js Console \> At
here you can write PnP queries and using ctrl + D we can test it.

Now we will implement the logic for break permission as below,

1.  For eg. I want to set "Contribute" permission so we have to get a
    Role definition Id. you can set it as per your requirement. for more
    details to refer
    to [this article. ](https://pnp.github.io/pnpjs/sp/security/#role-definitions)
2.  Then get list by title and break list permission. 
3.  Get list item by id. 
4.  Break list item permission and then set permission. To add
    permission we require two parameters UserId and Role definition ID.
    The meaning of this method is to give permission to a specific user.

### Setting list item permission to one user

![Single user.png](images/Single user.png)

## Setting list item permission to multiple users

![Multiple users.png](images/Multiple users.png)

Here logic will be the same as above. just have to add one array with
required user IDs and then will iterate this array and set the
permissions.

**Output**

After successfully running the query now we will check the permission.
so first select the list item and select  the details panel from the
right corner second last icon (above the list title). you can see the
panel as below,

![FirstOP.png](images/FirstOP.png)

Select  **manage access** and then select  Advanced as below,


![SecondCropped.png](images/SecondCropped.png)

It will open another tab and in this, you can see all the list item
level permission as below,

![Third.png](images/Third.png)

## Summary

In this article, we have seen how to break and add permission to list
items using PnP JS.

Hope this helps! If it is helpful to you then share it with others. Give
your valuable feedback and suggestions in the comments section below.

Sharing is caring!
