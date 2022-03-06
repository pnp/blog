---
title: "How to Convert Word Document to PDF in SharePoint Document Library using Power Automate?"
date: 2021-11-16T07:06:00-05:00
author: "Chandani Prajapati"
githubname: chandaniprajapati
categories: ["Power Automate", "SharePoint"]
images:
- images/blog/how-to-convert-word-document-to-pdf-in-sharepoint-document/ChandaniPrajapati_0-1636792320998.png
tags: []
type: "regular"


---

## Introduction

In this article, we will see how to convert a **Word Document to PDF**
in SharePoint Document Library using **Power Automate** without using
any license version.
Using this method will be a bit lengthy but if we don't have the power
to automate premium licenses then we can also achieve a solution.
{{< image alt="Group 1.png" src="images/blog/how-to-convert-word-document-to-pdf-in-sharepoint-document/Group 1.png" >}}

## Implementation
 
1\. Go to **Power Automate** \> **My flows** \> Select  **New flow** \>
Select **Automated Cloud Flow**
{{< image alt="ChandaniPrajapati_0-1636792320998.png" src="images/blog/how-to-convert-word-document-to-pdf-in-sharepoint-document/ChandaniPrajapati_0-1636792320998.png" >}}
 

2\. It will ask for the flow name and trigger.
Add flow name and choose a trigger **when a file is created (properties
only).** A trigger is depending on our business requirement you can also
choose when a file is created or modified too.
{{< image alt="ChandaniPrajapati_1-1636792461300.png" src="images/blog/how-to-convert-word-document-to-pdf-in-sharepoint-document/ChandaniPrajapati_1-1636792461300.png" >}}

3\. Select  **Create.

  Basically, we don't have direct action to convert to PDF for SharePoint so first, we will create a library item/file in OneDrive and in one drive has an action to conversion so we will use one drive converter to convert to pdf format, and then we will move it to the library and delete it from one drive.*

At the end, our flow will be as below,

{{< image alt="ChandaniPrajapati_0-1636793559861.png" src="images/blog/how-to-convert-word-document-to-pdf-in-sharepoint-document/ChandaniPrajapati_0-1636793559861.png" >}}
 

Now let's see an implementation.

-   ### When a file is created (properties only) 

  **Properties**     **Value**
  **Site Address**   Select Site URL or Add Custom Site URL on which you want to run this flow
  **Library Name**   Select Library Name
  ------------------ ---------------------------------------------------------------------------
{{< image alt="ChandaniPrajapati_0-1636864104189.png" src="images/blog/how-to-convert-word-document-to-pdf-in-sharepoint-document/ChandaniPrajapati_0-1636864104189.png" >}}

### Get File content 

- Action:  Select SharePoint Get file content

    - **Site Address**
   Select Site URL or Add Custom Site URL on which you want to run this flow
    - **File Identifier** 
  [Select ]

{{< image alt="ChandaniPrajapati_1-1636864275047.png" src="images/blog/how-to-convert-word-document-to-pdf-in-sharepoint-document/ChandaniPrajapati_1-1636864275047.png" >}}

### Create a file to OneDrive 

- Action:  Create a file for OneDrive for business
    - **Folder Path** 
  Select folder path of one drive where you want or create a file
    - **File Name** 
    - [Select ][File Name with extension]
    - **File Content**
    - [Select File Content - which we have created in the previous action]

{{< image alt="ChandaniPrajapati_7-1636864944228.png" src="images/blog/how-to-convert-word-document-to-pdf-in-sharepoint-document/ChandaniPrajapati_7-1636864944228.png" >}}

#### Convert file to PDF 

    -   Action:  Convert a file for OneDrive for business

  **Properties**    **Value**
  **File**          Select Id [which we have created in the previous action]
  **Target Type**   [Select ]

{{< image alt="ChandaniPrajapati_6-1636864910697.png" src="images/blog/how-to-convert-word-document-to-pdf-in-sharepoint-document/ChandaniPrajapati_6-1636864910697.png" >}}

#### Create PDF File to OneDrive 

-   Action:  Create a file for OneDrive for business

    - **Folder Path**    
    - Select folder path of one drive where you want or create a file
    - **File Name**
  [Select ][File Name with extension]
    - **File Content**
  [Select File Content - which we have created in the previous action]

{{< image alt="ChandaniPrajapati_5-1636864879248.png" src="images/blog/how-to-convert-word-document-to-pdf-in-sharepoint-document/ChandaniPrajapati_5-1636864879248.png" >}}

### Create PDF file to Document Library 

- Action:  Create a file for SharePoint
    - **Site Address**
  Select Site URL
    - **Folder Path**
   Select folder path of one drive where you want or create a file
    - **File Name** 
  [Select ][File Name with extension]
    - **File Content**
  [Select File Content - which we have created in the previous action]

{{< image alt="ChandaniPrajapati_4-1636864839927.png" src="images/blog/how-to-convert-word-document-to-pdf-in-sharepoint-document/ChandaniPrajapati_4-1636864839927.png" >}}

#### Delete word file from OneDrive 

- Action:  Delete a file for OneDrive for business

  ---------------- ------------------------------
  **Properties**   **Value**
  **Id**           Select eDrive word file ID
  ---------------- ------------------------------

{{< image alt="ChandaniPrajapati_3-1636864760614.png" src="images/blog/how-to-convert-word-document-to-pdf-in-sharepoint-document/ChandaniPrajapati_3-1636864760614.png" >}}

### Delete PDF file from OneDrive 

- Action:  Delete a file for OneDrive for business

  ---------------- -----------------------------
  **Properties**   **Value**
  **Id**           Select eDrive PDF file ID
  ---------------- -----------------------------

{{< image alt="ChandaniPrajapati_2-1636864751972.png" src="images/blog/how-to-convert-word-document-to-pdf-in-sharepoint-document/ChandaniPrajapati_2-1636864751972.png" >}}


## Output 

{{< image alt="ChandaniPrajapati_0-1637069155125.png" src="images/blog/how-to-convert-word-document-to-pdf-in-sharepoint-document/ChandaniPrajapati_0-1637069155125.png" >}}
 

## Summary 

In this article, we have seen how to convert **Word Document to PDF** in
**SharePoint Document Library** using Power Automate.
Hope this helps!
Sharing is caring!
