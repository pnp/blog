---
title: "Save an email attachment to a custom path with Power Automate"
date: 2021-06-20T11:11:00-04:00
author: "Damien Bird"
githubname: DamoBird365
categories: ["Community post"]
images:
- images/DamoBird365_0-1624209543175.png
tags: ["Power Automate"]
type: "regular"

---

This use case was generated from an idea involving Xerox Docucentres,
which enables end-users to email themselves a scanned document. Equally,
this applies to regular emails with attachments that you would like
Power Automate to automatically save the attachment(s) to a specific
(*custom/bespoke/unique*) folder and/or SharePoint site and therefore
Document Library.   The dynamically chosen path is based on the Subject
Line OR File Name. This can be achieved relatively easily and would save
you a lot of routine administration time.

## The Solution

Using Power Automate, **When a new email arrives (v3)** trigger, we can
be quite specific about the sender of the email and for this, I have
assumed all emails will come from xerox@mydomain.com and the email must
contain an attachment! Ideally, you want to limit the emails that this
Flow will trigger by using the available parameters for that action.

![](images/DamoBird365_0-1624209543175.png)

To define the locations for saving files, I have used an **array** in
a **compose action** (but don't panic!). You might want to use
a **SharePoint list** as somewhere to save the specific subject or file
name keywords, alongside the folder or SharePoint site path. The
advantage of using an array is that only the owner(s) of the flow can
define these and all of the parameters are in one place. Creating a list
in SharePoint might give you and/or other colleagues the ability to
easily define and visualise the locations.

![](images/DamoBird365_1-1624209543161.png)

The parameters for this flow are basic, a keyword for searching the
Subject or Filename containing, which I have called **Dept**; and
the **Path**, which can either be a folder or a Site Name. If you are
looking to have a dynamic Folder and Site, you can define a third
parament or **key:value** pair.


## Finding our path 

We must now use the filter array action, which will allow us to search
the Subject or Attachment name to see if it **contains** one of the
keywords from the Dept key. If we get a match, the array will return a
value for the Path. Here I use a compose action to return the first
object from the array result. Why do I use the first expression? Because
the result is returned as an array, it expects multiple elements. 
Calling the path without either using the first expression
or **body('FilterFindPath')?\[0\]?\['Path'\]** to select the first
element, you will receive an error "**Array elements can only be
selected using an integer index**". Using First() or calling the element
by using an integer will allow you to simplify your Flow if you know the
result will always be the first element.

![](images/DamoBird365_2-1624209543294.png)


## Saving the File(s) to a Custom Path

Using the **Create File** action for SharePoint, I am using
the **Attachments Name** and **Attachments Content** dynamic expressions
from the email trigger. By default, when you select these dynamic
values, Power Automate will put your actions into an Apply to Each. Why?
This is because the results for the attachment name and content are
returned as an array. You can accept this and your solution will handle
multiple attachments. For my solution, I am a stickler for efficiency
and have used the first() expression described previously as my Xerox
will only ever include one file. You can accept the default Power
Automate build if you would prefer.
I've two actions here, one to demonstrate how to save to a custom
dynamic path, the other to a custom dynamic site. When manually
supplying a custom path for the site or folder, you will have to
select **Enter Custom Value** or Power Automate will try and resolve the
address and error **'Site Address' is required** or the folder path with
try and delete any additional text that you supply.

![](images/DamoBird365_3-1624209543448.png)
The expressions I have used both using the integer selection for the
first array element and the first expression are as follows:

**File Name**: triggerOutputs()?\['body/attachments'\]?\[0\]?\['name'\]

**File Content**:
first(triggerOutputs()?\['body/attachments'\])?\['contentBytes'\]

To finish off my flow and this is personal preference, I have deleted
the incoming email. Why keep it? The file attachment has been saved for
me.

![](images/DamoBird365_4-1624209543193.png)

## See it in Action


Here I have an incoming email from the Xerox mailbox. I've been sent me
an attachment from the Xerox Mailbox. This will trigger my flow.

![DamoBird365_8-1624210593508.png](images/DamoBird365_8-1624210593508.png)
 

The filter action will look for each of the Dept values in the subject
line and return a filtered array. In the example below, we output the
ICT Path based on the subject line "This file is for ICT thanks".

![](images/DamoBird365_6-1624209543237.png)

What do the two Create File Actions look like? Here you can see the
custom dynamic paths for both the Folder Path or Site Address. I am
obviously saving the file twice here in order to demonstrate the two
options. You might want to combine the custom site and folder with an
additional parameter in your Array or SharePoint List.

![DamoBird365_7-1624209543373.png](images/DamoBird365_7-1624209543373.png)

## Summary

Quickly file away those routine attached documents received via email.
Maybe this would simplify uploading documents into SharePoint? Work on a
file and email it to a shared mailbox and have the Flow decide where to
file the attachment based on keywords? Please let me know how you could
use this.
Make sure you check out my [YouTube
channel](https://www.youtube.com/c/DamoBird365?sub_confirmation=1) for
other ideas and proof of concepts.
