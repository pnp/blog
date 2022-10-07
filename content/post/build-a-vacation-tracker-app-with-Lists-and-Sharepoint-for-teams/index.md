---
title: "Build a vacation tracker app with Lists and SharePoint for Teams"
date: 2022-09-30T02:04:00-05:00
author: "Anand Ragav"
githubname: anandragav
categories: ["Community post"]
images:
- images/image49.png
tags: ["SharePoint", "Microsoft Lists"]
type: "regular"
draft: false
---


When it is summer or the holidays season, we know it is vacation time. A likely number one question would then be when everyone else in the team is going to be on vacation. And that means someone in the team is creating or re-using a tracker, usually made with excel, to track people’s vacation days. This is usually complimented with a quick round-the-table update in a team meeting or chat, and sometimes this is the only way the information is shared.

 
## Keep track of everyone’s vacation dates with smart lists

With Lists, there is a smarter way to do that. Lists is your smart information tracking app across Microsoft 365. Lists are flexible and can be used to meet several different scenarios — business, team and personal. The calendar view in Lists offers a month-based view, with a customizable form interface to capture vacation information, making it a useful, easy-to-update vacation tracker, with neat display and accessibility options in Teams and SharePoint.

![Vacation tracker calendar list on a SharePoint page.png](images/image1.png "Vacation tracker calendar list on a SharePoint page")

### Teams

The vacation tracker can be added as a tab in a Teams channel using the Lists app, from where everyone can add their vacation days and view others’ vacation days. With the Lists calendar view, each day in the calendar shows up to 5 entries in the view. Upon selecting the day, the events pane on the right shows all the entries for the day, which is, everyone who is on vacation that selected day.

 
![Vacation tracker as a tab in a Teams channel.png](images/image2.png "Vacation tracker as a tab in a Teams channel")

### SharePoint

When added to a SharePoint communication or teamsite, with the addition of a helper list (a second list) that contains just the team members names, it is then possible to create dynamic filters for the vacation tracker. So, when selecting a name in the helper list, the vacation tracker is filtered to show the selected team members’ vacation days.


![Vacation tracker with filters embedded in a SharePoint page.png](images/image3.png "Vacation tracker with filters embedded in a SharePoint page")


If you would like to set this up for your team, follow the below steps under “Creating the vacation tracker using the lists app in Teams”. If you would like to extend that and add additional capability of dynamic filtering illustrated in the image above, follow the steps under “Extending the vacation tracker for dynamic filtering using SharePoint page in Teams.”





## Creating the vacation tracker using the lists app in Teams

### How to create the vacation tracker list and display it in a Teams channel

In your team’s Teams channel, add a tab and select the “Lists” app.

![Add the Lists app as a tab in Teams.png](images/image4.png "Add the Lists app as a tab in Teams")


Save the tab.

 
![Save the Lists tab.png](images/image5.png "Save the Lists tab")


Create the list.

 
![Create the list.png](images/image6.png "Create the list")


Start from a blank list.


![Start from a blank list..jpg](images/image7.png "Start from a blank list.")

 
Give it a name and create.


![Name the list.png](images/image8.png "Name the list")


Use the “Add column” button to add fields for start & end dates. You could add more fields that are relevant for your team, if needed.

Optional at this stage: click “New” and add your own vacation entry, to get some initial data in.

 
![Add and rename columns.png](images/image9.png "Add and rename columns")


Create the calendar view.

![Create a new view.png](images/image10.png "Create a new view")

 
![Create the calendar view.png](images/image11.png "Create the calendar view")


Set the view as the default view.


![Set the view as the default view.png](images/image12.png "Set the view as the default view")


That is, it and the list calendar is ready to use.

To add an entry to the vacation tracker list, click the new button to open the form.

 
![Add an entry to the list.png](images/image13.png "Add an entry to the list")


In the form, fill up your name and vacation start and end dates and save.


![Fill up the form to complete the entry.png](images/image14.png "Fill up the form to complete the entry")

 
You should then see your entry show up in the calendar view of the list.


![Your entry show up in the list.png](images/image15.png "Your entry show up in the list")

 
At this point you can stop and use the list (vacation tracker) as it is. But if you would like to add more flexibility to it by adding the ability to filter and see anyone’s vacation days, read on. The steps under “Extending the vacation tracker for dynamic filtering using SharePoint page in Teams” below show you how to add that dynamic filtering to the vacation tracker, which will be useful especially for a large team.



## Extending the vacation tracker for dynamic filtering using SharePoint page in Teams


### How to display the vacation tracker list on a SharePoint page


From the Posts tab in your teams' channel, open the connected SharePoint team site.


![Open the connected SharePoint team site.png](images/image16.png "Open the connected SharePoint team site")


Head to the Home tab


![Head to the Home tab.png](images/image17.png "Head to the Home tab")


Create a new page


![Create a new page.png](images/image18.png "Create a new page")
![Create a new page.png](images/image19.png "Create a new page")


Give the page a title


![Give the page a title.png](images/image20.png "Give the page a title")


Add the Lists web part


![Add the Lists web part.png](images/image21.png "Add the Lists web part")


Select the team vacation tracker list you just created.


![Select the vacation tracker list.png](images/image22.png "Select the vacation tracker list")


Select the vacation tracker view and apply the settings below.


![Select the vacation tracker view.png](images/image23.png "Select the vacation tracker view")


Save and publish the page.


![Save and publish the page.png](images/image24.png "Save and publish the page")


Once published, the page looks like this below.


![The published page with the list embedded.png](images/image25.png "The published page with the list embedded")



## How to create the helper list


The helper list is a list of all team members that can be used to filter the team vacation tracker list.

From the SharePoint page, open the home page in a separate tab/window.


![Open the home page in a separate browser tab or window.png](images/image26.png "Open the home page in a separate browser tab or window")


In the new browser tab/window, create a new List.


![Create a new List.png](images/image27.png "Create a new List")


Create the list from a blank List


![Create the list from a blank List.png](images/image28.png "Create the list from a blank List")


Give the list a name and create


![Give the list a name and create.png](images/image29.png "Give the list a name and create")


Edit the list in Grid view


![Edit in the list in Grid view.png](images/image30.png "Edit in the list in Grid view")


Enter all team members’ names in the Title field and then Exit grid view to save the data.


![Create entries in the list and save.png](images/image31.png "Create entries in the list and save")



## How to connect the helper list to the vacation tracker list


Head back to the Vacations tracker page you created earlier, which is in the previous tab/window of the browser.

Edit the page.


![Edit the Vacations tracker page.png](images/image32.png "Edit the Vacations tracker page")


Add a vertical section to the page.


![Add a vertical section to the page.png](images/image33.png "Add a vertical section to the page")
![Add a vertical section to the page.png](images/image34.png "Add a vertical section to the page")


Add the list web part.


![Add the list web part.png](images/image35.png "Add the list web part")


Select the Team members list.


![Select the Team members list.png](images/image36.png "Select the Team members list")


Apply the below settings.


![Apply settings.png](images/image37.png "Apply settings")


Now that the two lists are displayed on the page, the last step is to connect them both. To do that, select the vacations tracker list on the page and click Edit. Enable dynamic filtering and apply the settings shown below.


![Apply dynamic filter settings.png](images/image38.png "Apply dynamic filter settings")


Save the page and republish.

Now, when one or more of the team members are selected, the vacations tracker list on the page will only show the vacation days of the selected team member names.


![Filter in action.png](images/image39.png "Filter in action")



## How to display the Vacations tracker SharePoint page in a teams channel


By doing this last step, you bring the page directly into a teams channel as a tab, so everyone can quickly access the information.

In your teams channel, add a tab and select the app SharePoint pages.


![Add the SharePoint pages app as a tab in Teams.png](images/image40.png "Add the SharePoint pages app as a tab in Teams")


Select the Vacations tracker page and save.


![Vacations tracker page.png](images/image41.png "Vacations tracker page")


To allow team members to add their vacation entries, edit the page and enable the command bar for the vacations tracker list.
 

![Enable the command bar for the list.png](images/image42.png "Enable the command bar for the list")

![Enable the command bar for the list.png](images/image43.png "Enable the command bar for the list")


Save and republish the page.


![Save and republish the page.png](images/image244.png "Save and republish the page")


Everyone in the team can add vacation entries using the form.


![The command bar is enabled.png](images/image45.png "The command bar is enabled")



## Bonus: color code the tracker


With the new conditional formatting feature for Calendar views, you can color code your vacation tracker to give it more flavor.

Open the view, format it and set colors based on rules applied on fields available in the view.


![Format the calendar view.png](images/image46.png "Format the calendar view")


Add rule.


![Add rule.png](images/image47.png "Add rule")


Apply the settings below and save the rule. Go back and create a rule for each team member and save.


![Apply settings and save the rule.png](images/image48.png "Apply settings and save the rule")


The final result is a vacation tracker that looks like this.


![The end result of the vacation tracker, embedded in SharePoint and displayed in Teams.png](images/image49.png "The end result of the vacation tracker, embedded in SharePoint and displayed in Teams")



Hope you enjoyed this article and can benefit from the Lists app in SharePoint and Teams.

What other use cases do you think Lists can be useful for? Let me know in the comments.  
