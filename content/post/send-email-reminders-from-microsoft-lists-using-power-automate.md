---
title: "Send email reminders from Microsoft Lists using Power Automate"
date: 2021-02-24T09:33:00-05:00
author: "Norm Young"
githubname: nyoung30
categories: ["Community post"]
images:
- images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/issuetracker01.png
tags: []
type: "regular"
summary: "In this blog post, I will show how to send email reminders for Microsoft Lists items based on a date column using Power Automate. "
---

In this blog post, I will show how to send email reminders for Microsoft Lists items based on a date column using Power Automate. I am using the Microsoft Lists **Issue Tracker** template for this blog.  Automated email reminders give users time and opportunity to intervene in the business process prior to expiration or end dates. In this demo, we will base our Power Automate Flow on the "Due Date" column and will send reminders 30 days in advance of the date.

## Issue Tracker setup 

You can get started with the **Issue Tracker** by navigating to Microsoft Lists, select **New list** and then select **Issue tracker**.

{{< image alt="The issue tracker template" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/issuetracker01.png" >}}

Review the sample and select **Use template**.

{{< image alt="The template preview with use template button on the lower right corner" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/issuetracker02.png" >}}

Provide a **Name**, **Color**, **Icon** and storage location (i.e. **Save to**) (OneDrive aka **My lists** or **SharePoint**) and then select **Create**. I am using **My lists** in this example.

{{< image alt="The new list creation dialog" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/issuetracker03.png" >}}


We will add a `Due Date` column to connect our reminders to. From **Issue Tracker** to the right of the `Date reported` column select **+ Add column** or **+** and select **Date and Time** from the dropdown list of column types. 

{{< image alt="Dropdown list of column types" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/stormin_30_4-1613402858860.png" >}}

Set **Name** to `Due Date` and select **Save**.

{{< image alt="The create a column dialog" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/stormin_30_5-1613403503451.png" >}}

## Flow build 

Create a new Flow by selecting **Automate** \> **Power Automate** \> **See your flows**.

{{< image alt="The automate menu" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/image-23.png" >}}

Select **New** \> **Scheduled--from blank**.

{{< image alt="New -- scheduled from blank dialog" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/image-24.png" >}}

Provide a **Flow name**, I.e. `Issue Tracker -- Daily`, set **Starting** to `10:00 AM`, **Repeat every** to `1`, **Day** and select **Create**.

{{< image alt="Build a scheduled flow dialog" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/image-25.png" >}}

{{< notice tip>}}
Use the advanced options to set your target time zone.
{{< /notice >}}


{{< image alt="The recurrence step" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/image-26.png" >}}

Select **New step**, search for **Variable** and select the **Initialize variable** action. 

Set the **Name** to `varNumDays`; **Type** to **Integer** and **Value** to `30`.

{{< image alt="Initialize variable step" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/image-27.png" >}}

Select **New step**, search for **Variable** and select the **Initialize variable** action.  

Set the **Name** to `varReminderDate`; **Type** to **String** and **Value** to the following expression:

```powerappsfl
addDays(utcNow(), variables('varNumDays'), 'yyyy-MM-dd')
```

{{< notice note>}}
Select **Add dynamic content** \> **Expression** to access the expression editor.
{{< /notice >}}

{{< image alt="Initialize variable step" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/image-28.png" >}}

Select **New step**, search for **SharePoint** and select the **Get items** action. 

{{< notice note>}}
Microsoft Lists is really SharePoint, so that is why we are using the Power Automate SharePoint actions. 
{{< /notice >}}

Set the **Site Address** and **List Name** to your **Issue Tracker** site and list.  Use the **Advanced options** to set **Filter query** to the following ODATA filter query:

```powerappsfl
DueDate eq '@{variables('varReminderDate')}'
```

Where `@{variables('varReminderDate')}` is the `varReminderDate` variable. 

{{< notice note>}}
Pay attention to the single quotes used in the ODATA filter query.
{{< /notice >}}

{{< image alt="Get items step" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/image-30.png" >}}

Select **New step**, search for **Office 365 Outlook** and select the **Send an email (V2)** action.

Set **To** to **Person or group the issue is assigned to Email** (from the **SharePoint Get items** action). Power Automate will put this into a **Apply to each** loop so it can send multiple emails based on the previous **Get items** action.

Set **Subject** and **Body** to something similar to the image below.

{{< image alt="Reminder: title due in varNumDays" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/image-31.png" >}}

My completed Flow looks like the image below.

{{< image alt="The completed flow" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/image-33.png" >}}

Save and test the Flow. If you have items due in 30 days the owner will receive a reminder email.

{{< image alt="Sample reminder email" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/image-32.png" >}}


This Flow is relatively simplistic in design and function but illustrates how value can be added to existing business processes by automating tasks and giving users an opportunity to act prior to a due date.

Thanks for reading.

NY

Adapted from **[normyoung.ca](https://normyoung.ca/2020/09/18/send-email-reminders-from-microsoft-lists-using-power-automate/)**
