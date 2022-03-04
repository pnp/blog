---
title: "Send email reminders from Microsoft Lists using Power Automate"
date: 2021-02-24T09:33:00-05:00
author: "Norm Young"
categories: ["Power Automate"]
images:
- images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/issuetracker01.png
tags: []
type: "regular"
draft: false

---

In this blog post, I will show how to send email reminders for Microsoft
Lists items based on a date column using Power Automate. I am using the
Microsoft Lists **Issue Tracker** template for this blog. 
Automated email reminders give users time and opportunity to intervene
in the business process prior to expiration or end dates. In this demo,
we will base our Power Automate Flow on the \"Due Date\" column and will
send reminders 30 days in advance of the date.

## Issue Tracker setup 

You can get started with the **Issue Tracker** by navigating to
Microsoft Lists, click \"New list\" and then select \"Issue tracker\".

{{< image alt="issuetracker01" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/issuetracker01.png" >}}

Review the sample and click \"Use template\".

{{< image alt="issuetracker02" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/issuetracker02.png" >}}

Provide a name, color, icon and storage location (OneDrive aka \"My
lists\" or SharePoint) and then click \"Create\". I am using \"My
lists\" in this example.

{{< image alt="issuetracker03" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/issuetracker03.png" >}}


We will add a *Due Date* column to connect our reminders to. From
**Issue Tracker** to the right of the *Date reported* column select **+
Add column** or **+** and select \"Date and Time\". 

{{< image alt="stormin_30_4-1613402858860.png" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/stormin_30_4-1613402858860.png" >}}
Set Name to *Due Date* and click \"Save\".

{{< image alt="stormin_30_5-1613403503451.png" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/stormin_30_5-1613403503451.png" >}}

## Flow build 

Create a new Flow by clicking \"Automate\" \> \"Power Automate\" \>
\"See your flows\".

{{< image alt="image-23" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/image-23.png" >}}

Click \"New\" \> \"Scheduled-from blank\".

{{< image alt="image-24" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/image-24.png" >}}
Provide a Flow name, I.e. *Issue Tracker -- Daily*, set \"Starting\" to
\"10:00 AM\", \"Repeat every\" to \"1\", \"Day\" and click \"Create\".

{{< image alt="image-25" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/image-25.png" >}}
**Tip:** Use the advanced options to set your target time zone.

{{< image alt="image-26" src="images/blog/send-email-reminders-from-microsoft-lists-using-power-automate/image-26.png" >}}

Click \"New step\", search for \"Variable\" and select the \"Initialize
variable\" action. 

Set the \"Name\" to *varNumDays*; \"Type\" to \"Integer\" and \"Value\"
to \"30\".

![](https://normanyoungblog.files.wordpress.com/2020/09/image-27.png)
Click \"New step\", search for \"Variable\" and select the \"Initialize
variable\" action.  

Set the \"Name\" to *varReminderDate*; \"Type\" to \"String\" and
\"Value\" to the following expression:

    addDays(utcNow(), variables('varNumDays'), 'yyyy-MM-dd')

**Note:** Click \"Add dynamic content\" \> \"Expression\" to access the
expression editor.

![](https://normanyoungblog.files.wordpress.com/2020/09/image-28.png)
Click \"New step\", search for \"SharePoint\" and select the \"Get
items\" action. **Note:** Microsoft Lists is really SharePoint, so that
is why we are using the Power Automate SharePoint actions. 
Set the \"Site Address\" and \"List Name\" to your **Issue
Tracker** site and list. 
Use the "Advanced options" to set "Filter query" to the following ODATA
filter query:

    DueDate eq '@{variables('varReminderDate')}'

Where \"\@{variables(\'varReminderDate\')}\" is the *varReminderDate*
variable. 

**Note:** pay attention to the single quotes used in the ODATA filter
query.

![](https://normanyoungblog.files.wordpress.com/2020/09/image-30.png)
Click \"New step\", search for \"Office 365 Outlook\" and select the
\"Send an email (V2)\" action.
Set \"To\" to *Person or group the issue is assigned to Email* (from the
SharePoint Get items action). Power Automate will put this into a
\"Apply to each\" loop so it can send multiple emails based on the
previous \"Get items\" action.
Set \"Subject\" and \"Body\" to something similar to the image below.

![](https://normanyoungblog.files.wordpress.com/2020/09/image-31.png)
My completed Flow looks like the image below.

![](https://normanyoungblog.files.wordpress.com/2020/09/image-33.png)
Save and test the Flow. If you have items due in 30 days the owner will
receive a reminder email.

![](https://normanyoungblog.files.wordpress.com/2020/09/image-32.png)
This Flow is relatively simplistic in design and function but
illustrates how value can be added to existing business processes by
automating tasks and giving users an opportunity to act prior to a due
date.
Thanks for reading.
NY
*Adapted
from *[normyoung.ca](https://normyoung.ca/2020/09/18/send-email-reminders-from-microsoft-lists-using-power-automate/) 
