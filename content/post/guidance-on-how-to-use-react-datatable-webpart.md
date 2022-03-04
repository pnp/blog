---
title: "Guidance On How To Use React DataTable Webpart"
date: 2021-09-29T11:59:00-04:00
author: "Chandani Prajapati"
categories: []
images:
- images/blog/guidance-on-how-to-use-react-datatable-webpart/ChandaniPrajapati.png
- images/blog/guidance-on-how-to-use-react-datatable-webpart/ChandaniPrajapati.png
- images/blog/guidance-on-how-to-use-react-datatable-webpart/Output1.png
- images/blog/guidance-on-how-to-use-react-datatable-webpart/Add_An_App.png
- images/blog/guidance-on-how-to-use-react-datatable-webpart/Add-Webpart.png
- images/blog/guidance-on-how-to-use-react-datatable-webpart/Search_Sort_Config.png
- images/blog/guidance-on-how-to-use-react-datatable-webpart/Advanced_Features.png
- images/blog/guidance-on-how-to-use-react-datatable-webpart/Output1.png
- images/blog/guidance-on-how-to-use-react-datatable-webpart/ChandaniPrajapati.png
tags: []
type: "regular"
draft: false

---

## Introduction

 

In this article, we will see how to configure and
use **react-spfx-datatable** web part which I have contributed to PnP
SPFx Web part galleries. 

 

To find the full source code refer to
[this](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-datatable).

 

As per all the configurations and features, our web part will be look
like this.

 

{{< image alt="Output1.png" src="images/blog/guidance-on-how-to-use-react-datatable-webpart/Output1.png" >}}

 

Let\'s see step by step configuration.

 

**1. Download a package**

 

To download the package refer to
[this](https://github.com/chandaniprajapati/react-datatable/blob/main/sharepoint/solution/react-datatable.sppkg).

 

**2. Add solution to SharePoint Page**

 

After downloading a package add it to the **App Catalog** site.

 

Move to the site where we want to add the web part to the page.

 

Now **Add** and **install** the web part.

 

Click on **App**.

 

{{< image alt="Add_An_App.png" src="images/blog/guidance-on-how-to-use-react-datatable-webpart/Add_An_App.png" >}}

 
It will open a page for the **SharePoint apps** store. At here find
**datatable** app and add it.

 

 [![App Store.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/311990i542D6093E1FD34DB/image-size/large?v=v2&px=999 "App Store.png")

 

Now create a **page** and add web part.

 

{{< image alt="Add-Webpart.png" src="images/blog/guidance-on-how-to-use-react-datatable-webpart/Add-Webpart.png" >}}
 

 

### **3 Configure properties from property pane configuration** 

 

Now we will configure a web part as below,

 

#### 1. First we will configure the List Configuration section 

-   Change the web part title that you want to show as a header/title.
-   Select a list that you want to show in data table format
-   Then select fields that you want to show in the data table.

 

![List Config.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/311992i8D838FA13D539F22/image-size/large?v=v2&px=999 "List Config.png")

 

#### **2. Now configure the Search and Sort Section.** 

-   **Search**
    -   If you will enable search then it will ask the user for which
        fields you want to apply search functionality. so you have to
        select fields from the dropdown. Search dropdown will be
        disabled when and only when the Search toggle button will be
        enabled. 
-   **Sort**
    -   If you will enable sort then it will ask the user for which
        fields you want to apply sort functionality. so you have to
        select fields from the dropdown. Sort dropdown will be disabled
        when and only when the Sort toggle button will be enabled. 

 

{{< image alt="Search_Sort_Config.png" src="images/blog/guidance-on-how-to-use-react-datatable-webpart/Search_Sort_Config.png" >}}

####  3. Now we will configure Advanced features. 

 

-   In this section, we will configure the below features,
    -   Pagination
        -   If we will enable the **Pagination** toggle button then the
            table will be rendered with pagination.
    -   Export to CSV
        -   If we will enable this option then it will show the **Export
            to CSV** button on the top of the data table and we can
            easily export it to CSV.
    -   Export to PDF
        -   If we will enable this option then it will show the **Export
            to Pdf **button on the top of the data table and we can
            easily export it to Pdf.
    -   Order columns in DataTable
        -   It will show all the columns which we are rendering in the
            data table and from here we can **reorder the columns** in
            the data table.
    -   Set even and odd row color
        -   Using this color picker option we can set **odd/even row
            color** in the table dynamically.

{{< image alt="Advanced_Features.png" src="images/blog/guidance-on-how-to-use-react-datatable-webpart/Advanced_Features.png" >}}

 

##  Output

 

{{< image alt="Output1.png" src="images/blog/guidance-on-how-to-use-react-datatable-webpart/Output1.png" >}}
 

## Summary

 

In this article, we have seen how to configure react data table web part
and we can easily use it for any SharePoint custom list.

 

I hope it will help you!

 

Sharing is caring!

 