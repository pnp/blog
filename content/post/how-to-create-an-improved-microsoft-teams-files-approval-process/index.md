---
title: "How to create an improved Microsoft Teams Files approval process using Azure Logic Apps"
date: 2021-02-12T05:46:00-05:00
author: "Vesa Nopanen"
githubname: veskunopanen
categories: ["Community post"]
images:
- images/2021-02-10_22-02-47.png
tags: ["Azure", "Azure Logic Apps", "Microsoft Teams"]
type: "regular"
---

We are all there during some days: Power Automate Premium is the key to
the next level but there is no way we could justify that licensing --
the ROI is simply not enough. Have you thought that you could be
utilizing a Azure Logic App instead?

![2021-02-10_22-02-47.png](images/2021-02-10_22-02-47.png)

Following my earlier post ( [How to: initiate a document approval
directly in team files tab (using Power
Automate) ](https://myteamsday.com/2021/01/29/approve-files/)) that
required a Power Automate Premium license I recreated that with Azure
Logic Apps solution. Please do refer and compare to that blog post these
steps to see how they differ. For later mentioned parts you need to
follow steps in that post.

## What are Azure Logic Apps and do they cost?

First: what are Logic Apps? Let's take a snippet from [Microsoft Azure
Logic Apps
documentation](https://learn.microsoft.com/azure/logic-apps/logic-apps-overview?WT.mc_id=M365-MVP-5003326) here.
*Azure Logic Apps is a cloud service that helps you schedule, automate,
and orchestrate tasks, business processes, and workflows when you need
to integrate apps, data, systems, and services across enterprises or
organizations. Logic Apps simplifies how you design and build scalable
solutions for app integration, data integration, system integration,
enterprise application integration (EAI), and business-to-business (B2B)
communication, whether in the cloud, on premises, or both.*
In short: you are create something almost like a Power Automate Cloud
Flow but you do that in the Azure. The user interface is slightly
different but almost all essential parts are there: triggers, actions,
connections and of course various connector.
The big difference is that you will be paying for all Logic App runs but
the bright side is that you don't have to purchase Power Automate
Premium. Of course it pays to do some rough calculation on Logic Apps.
In my demos for a week I accumulated less than one euro on Logic Apps
costs.. If something you construct is used repeatedly and has lots of
loops costs can build up. But if you have a random need for a Premium or
custom connector requirements Logic Apps might be a perfect solution.
This also depends on number of users you would have to license Premium
Power Automates to: yearly investment counts.
Read more about [Logic Apps pricing
here](https://learn.microsoft.com/azure/logic-apps/logic-apps-pricing?WT.mc_id=M365-MVP-5003326).
I suggest to start with

-   Create a resource group for Logic Apps so you can easily keep on
    track of the costs -- and also manage your apps
-   Put a budget to Azure in place so your costs don't suddenly
    skyrocket
-   Follow costs and cost estimate

## Creating Azure Logic Apps -process for file approval requests

Now that we have that householding taken care of we can finally create
the Logic App.

Navigate to your Resource Group and select  Add.


Add a Logic App. Use search to narrow the list down.
![image-55](images/image-55.png)
 

**Note: Be careful how you name your Logic App in the next step because
you won't be able to change it later!**
![image-58](images/image-58.png)
 

Add Tags if you use them, Review and Create the App. The Logic App is
deployed rather quickly and you can then go to the Resource.
Go to Logic App Designer
 

![image-59](images/image-59.png)
 

From there you can start selecting your trigger how the Logic App is
activated. Since we are duplicating the earlier post functionality with
Azure Logic Apps we choose "When a HTTP request is received"
 

![image-60](images/image-60.png)
 

And now the UI starts to look very Power Automatish
![image-61](images/image-61.png)
 

The difference is about available parameters. You need to select  Add
new parameter to open menu that is in this (and in many other actions)
not visible unlike at Power Automate designer.
 

![image-62](images/image-62.png)
 

Check Method
![image-63](images/image-63.png)
 

And you can choose Get from the list.
 

![image-64](images/image-64.png)
And now we have the trigger part ready (waiting for a save)!
![image-65](images/image-65.png)
 

Then we add other parts. The search for actions is not as good as in
Power Automate Cloud Flows but keep on trying -- the actions are there!
 

![image-66](images/image-66.png)
 

Let's populate that with triggerOutputs()\['queries'\]\['FileID'\] just
like in the earlier blog post.
 

![image-67](images/image-67.png)
 

Add there Get File Properties from SharePoint. In this point we need to
add a connection to the SharePoint. Use credentials that you seem to be
fit.
 

![image-68](images/image-68.png)
![image-69](images/image-69.png)

Once you have signed in you can define the information how to get file
properties.
![image-70](images/image-70.png)
 

The FileID is missing. You need to do a bit trick here:

-   Change parameter to integer
-   add it to the Get file properties
-   Change parameter back to string

![image-71](images/image-71.png)
And select  see more at Variable section in Dynamic content
![image-72](images/image-72.png)
Choose fileid. And yes! (don't forget to change the fileid parameter
back to string)
![image-73](images/image-73.png)
 

At this point we have

-   FileID
-   All file properties
-   Open HTTP request..

Let's close that HTTP request first. Add Response-action and instruct to
close the tab.
**![image-74](images/image-74.png)
**![image-75](images/image-75.png)
 

**Note: here is when you need to progress differently than with Power
Automate Cloud Flow approval**
This is because Azure Logic Apps doesn't have Approval-connection. In
this phase I decided to make the demo easily: writing the approval
request to a SharePoint list in the tenant and and creating a another
Power Automate with a when item is inserted trigger there.
First -- let's create that list where we can write the information to.
We can use Teams Lists -app for that.

![image-76](images/image-76.png)
 

Search for the action in Azure Logic Apps and add Create Item
![image-77](images/image-77.png)
 

![image-78](images/image-78.png)
 

Now, we need to select  Add new parameter to add list columns to the
action.
![image-79](images/image-79.png)
Choosing Approver, FileID, and Outcome. I actually should have named
Approver as Approval Requestor but hopefully it doesn't confuse too
much.
![image-80](images/image-80.png)
 

When filling up information you can use Dynamic values from Get file
properties. Since we don't really know who clicked that request approval
button we just assume it was the person who did changes the last time.

And that's it!
![image-81](images/image-81.png)
Hit save (if you haven't already) and you have the URL in the trigger
action available. Proceed with column formatting [as stated in previous
post](https://myteamsday.com/2021/01/29/approve-files/).

Fast forwarding the Power Automate that is created as a trigger to the
File Approvals -list looks like this:
![image-83](images/image-83.png)
 

Steps are roughly similar to the ones as in the earlier post.

-   The new item is inserted trigger
-   Getting file properties from the Documents (based on the fileID )
-   Updating that file that Approval is processing
-   Storing the file name into a variable
-   Getting a comment from the user that last modified the file why this
    document needs approving
-   I didn't add this one but you could figure out who is really the
    document approver. Perhaps there is metadata that can define that
    one -- or the library / folder itself is tied to a structure that
    defines the real approver
-   Create the approval request
-   Wait for the approval to conclude. I have found out that it is
    better to use Create + Wait combination in separate actions compared
    to the Start & Wait single action. If you need to count your Power
    Automate executions then a single action might make more sense..
-   Add also the check is it approved or rejected. I didn't add this
    either to this demo but this is definitely needed if you are taking
    any real action after the approval process!
-   Updated the outcome to the list and then to the file itself to a
    dedicated columns
-   Added a information about approval request to be sent to a channel

## Conclusion

With Azure Logic Apps it is possible to go the next level without paying
for Premium Power Automates. There are also other create features in
Logic Apps that I didn't even touch on this one: ability to modify the
app in Visual Studio for example. And that means it is easy to add to a
version control as well..

You need to pay attention to the execution costs and make sure that your
Logic Apps stay in the budget. This suits extremely well for low-medium
usage actions.
You may have to switch from a Logic App to Power Automate at some point
-- like we did in this example. Plan carefully how you do the data
exchange and where do you store the information & who can access it. The
HTTP trigger in this example isn't the safest one to use (it lacks
security) so you need to plan how you either add some security to it or
secure it in some other way. In my earlier post I also made some
pointers about this: look them up.
Not all connectors / actions are in the Logic Apps but many of them are.

> Azure Logic Apps are a great way to extend Microsoft Teams and
> integrate it to different systems -- inside and outside of Microsoft
> 365 cloud.
>
[**This blog article is a repost from
MyTeamsDay.Com.**](https://myteamsday.com/2021/02/10/improved-files-approval/)
