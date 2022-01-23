# How to Convert Word Document to PDF in SharePoint Document Library using Power Automate?

## Introduction

In this article, we will see how to convert a **Word Document to PDF**
in SharePoint Document Library using **Power Automate** without using
any licence version.
Using this method will be a bit lengthy but if we don\'t have the power
to automate premium licenses then we can also achieve a solution.
![Group
1.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/326574i3FEC557E437AC323/image-size/large?v=v2&px=999 "Group 1.png")

## Implementation 
1\. Go to **Power Automate** \> **My flows** \> Click on **New flow** \>
Select **Automated Cloud Flow**
![ChandaniPrajapati_0-1636792320998.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/326840i68A176C1475E2211/image-size/large?v=v2&px=999 "ChandaniPrajapati_0-1636792320998.png")
 

2\. It will ask for the flow name and trigger.
Add flow name and choose a trigger **when a file is created (properties
only).** A trigger is depending on our business requirement you can also
choose when a file is created or modified too.
![ChandaniPrajapati_1-1636792461300.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/326841iD1572E113B2456E6/image-size/large?v=v2&px=999 "ChandaniPrajapati_1-1636792461300.png")

3\. Click on **Create.

  Basically, we don\'t have direct action to convert to PDF for SharePoint so first, we will create a library item/file in Onedrive and in one drive has an action to conversion so we will use one drive converter to convert to pdf format, and then we will move it to the library and delete it from one drive.*

At the end, our flow will be as below,

![ChandaniPrajapati_0-1636793559861.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/326843i46C4E19F8F6BBEAF/image-size/large?v=v2&px=999 "ChandaniPrajapati_0-1636793559861.png")
 

Now let\'s see an implementation.

-   ### When a file is created (properties only) 

  **Properties**     **Value**
  **Site Address**   Select Site URL or Add Custom SIte URL on which you want to run this flow
  **Library Name**   Select Library Name
  ------------------ ---------------------------------------------------------------------------
![ChandaniPrajapati_0-1636864104189.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/326893i2BA11008512CD7C4/image-size/large?v=v2&px=999 "ChandaniPrajapati_0-1636864104189.png")

### Get File content 

    -   Action:  Select SharePoint Get file content


  - **Site Address**
   Select Site URL or Add Custom Site URL on which you want to run this flow
  - **File Identifier** 
  [Select ]
![ChandaniPrajapati_1-1636864275047.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/326894iBD5BA2B2DBB04BF6/image-size/large?v=v2&px=999 "ChandaniPrajapati_1-1636864275047.png")

-   ### Create a file to Onedrive 

    -   Action:  Create a file for Onedrive for business
 
  - **Folder Path** 
  Select folder path of one drive where you want or create a file
  - **File Name** 
  [Select ][File Name with extension]
  - **File Content**
- [Select File Content - which we have created in the previous action]

![ChandaniPrajapati_7-1636864944228.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/326900i0773D79FAA4746F9/image-size/large?v=v2&px=999 "ChandaniPrajapati_7-1636864944228.png")

-   #### Convert file to PDF 

    -   Action:  Convert a file for Onedrive for business

  **Properties**    **Value**
  **File**          Select Id [which we have created in the previous action]
  **Target Type**   [Select ]

![ChandaniPrajapati_6-1636864910697.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/326899i294BF6F005F16561/image-size/large?v=v2&px=999 "ChandaniPrajapati_6-1636864910697.png")
-   #### Create PDF File to Onedrive 

    -   Action:  Create a file for Onedrive for business


  - **Folder Path**    
- Select folder path of one drive where you want or create a file
  - **File Name**
  [Select ][File Name with extension]
  - **File Content**
  [Select File Content - which we have created in the previous action]

![ChandaniPrajapati_5-1636864879248.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/326898i339CE0360AFA602F/image-size/large?v=v2&px=999 "ChandaniPrajapati_5-1636864879248.png")

-   ### Create PDF file to Document Library 

    -   Action:  Create a file for SharePoint
  - **Site Address**
  Select Site URL
  - **Folder Path**
   Select folder path of one drive where you want or create a file
  - **File Name** 
  [Select ][File Name with extension]
  - **File Content**
  [Select File Content - which we have created in the previous action]
![ChandaniPrajapati_4-1636864839927.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/326897i8564830E2B45DD25/image-size/large?v=v2&px=999 "ChandaniPrajapati_4-1636864839927.png")

-   #### Delete word file from OneDrive 

    -   Action:  Delete a file for Onedrive for business

  ---------------- ------------------------------
  **Properties**   **Value**
  **Id**           Select Onedrive word file ID
  ---------------- ------------------------------
![ChandaniPrajapati_3-1636864760614.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/326896iB8CBA402E13163FB/image-size/large?v=v2&px=999 "ChandaniPrajapati_3-1636864760614.png")

-   ### Delete PDF file from OneDrive 

    -   Action:  Delete a file for Onedrive for business

  ---------------- -----------------------------
  **Properties**   **Value**
  **Id**           Select Onedrive PDF file ID
  ---------------- -----------------------------
![ChandaniPrajapati_2-1636864751972.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/326895i0B8F91B9FBD8B21A/image-size/large?v=v2&px=999 "ChandaniPrajapati_2-1636864751972.png")

## Output 

![ChandaniPrajapati_0-1637069155125.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/327283iB7A286C44B3C2D74/image-size/large?v=v2&px=999 "ChandaniPrajapati_0-1637069155125.png")
 

## Summary 

In this article, we have seen how to convert **Word Document to PDF** in
**SharePoint Document Library** using Power Automate.
Hope this helps!
Sharing is caring!
