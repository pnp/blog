---
title: "Build a vacation tracker app with Lists and SharePoint for Teams"
date: 2022-09-30T02:04:00-05:00
author: "Anand Ragav"
githubname: anandragav
categories: ["Community post"]
images:
- images/image49.png
tags: ["SharePoint", "Lists"]
type: "regular"
---

# Build a vacation tracker app with Lists and SharePoint for Teams

When it is summer or the holidays season, we know it is vacation time. A likely number one question would then be when everyone else in the team is going to be on vacation. And that means someone in the team is creating or re-using a tracker, usually made with excel, to track people’s vacation days. This is usually complimented with a quick round-the-table update in a team meeting or chat, and sometimes this is the only way the information is shared. ​​​​​​​​

 
## Keep track of everyone’s vacation dates with smart lists

With Lists, there is a smarter way to do that. Lists is your smart information tracking app across Microsoft 365. Lists are flexible and can be used to meet several different scenarios — business, team and personal. The calendar view in Lists offers a month-based view, with a customizable form interface to capture vacation information, making it a useful, easy-to-update vacation tracker, with neat display and accessibility options in Teams and SharePoint.


![image1.png](images/image1.png)

 
### Teams

The vacation tracker can be added as a tab in a Teams channel using the Lists app, from where everyone can add their vacation days and view others’ vacation days. With the Lists calendar view, each day in the calendar shows up to 5 entries in the view. Upon selecting the day, the events pane on the right shows all the entries for the day, which is, everyone who is on vacation that selected day.

 
![image2.png](images/image2.png)



### SharePoint

When added to a SharePoint communication or teamsite, with the addition of a helper list (a second list) that contains just the team members names, it is then possible to create dynamic filters for the vacation tracker. So, when selecting a name in the helper list, the vacation tracker is filtered to show the selected team members’ vacation days.


![image3.png](images/image3.png)


If you would like to set this up for your team, follow the below steps under “Creating the vacation tracker using the lists app in Teams”. If you would like to extend that and add additional capability of dynamic filtering illustrated in the image above, follow the steps under “Extending the vacation tracker for dynamic filtering using SharePoint page in Teams”


![image4.png](images/image4.png)




## Creating the vacation tracker using the lists app in Teams

### How to create the vacation tracker list and display it in a Teams channel

In your team’s Teams channel, add a tab and select the “Lists” app.

 
![image5.png](images/image5.png)


Save the tab.

 
![image6.jpg](images/image6.png)


Create the list.

 
![image7.jpg](images/image7.png)

 
Start from a blank list.


![image8.png](images/image8.png)

 
Give it a name and create.

 
![image9.png](images/image9.png)

 
Use the “Add column” button to add fields for start & end dates. You could add more fields that are relevant for your team, if needed.

Optional at this stage: click “New” and add your own vacation entry, to get some initial data in.

 
![image10.png](images/image10.png)


Create the calendar view.

 
![image11.png](images/image11.png)


Set the view as the default view.


![image12.png](images/image12.png)


That is, it and the list calendar is ready to use.

To add an entry to the vacation tracker list, click the new button to open the form.

 
![image13.png](images/image13.png)


In the form, fill up your name and vacation start and end dates and save.


![image14.png](images/image14.png)

 
You should then see your entry show up in the calendar view of the list.


![image15.png](images/image15.png)

 
At this point you can stop and use the list (vacation tracker) as it is. But if you would like to add more flexibility to it by adding the ability to filter and see anyone’s vacation days, read on. The steps under “Extending the vacation tracker for dynamic filtering using SharePoint page in Teams” below show you how to add that dynamic filtering to the vacation tracker, which will be useful especially for a large team.



## Extending the vacation tracker for dynamic filtering using SharePoint page in Teams


### How to display the vacation tracker list on a SharePoint page


From the Posts tab in your teams' channel, open the connected SharePoint team site.


![image16.png](images/image16.png)


Head to the Home tab


![image17.png](images/image17.png)


Create a new page


![image18.png](images/image18.png)
![image19.png](images/image19.png)


Give the page a title


![image20.png](images/image20.png)


Add the Lists web part


![image21.png](images/image21.png)


Select the team vacation tracker list you just created.


![image22.png](images/image22.png)


Select the vacation tracker view and apply the settings below.


![image23.png](images/image23.png)


Save and publish the page.


![image24.png](images/image24.png)


Once published, the page looks like this below.


![image25.png](images/image25.png)



## How to create the helper list


The helper list is a list of all team members that can be used to filter the team vacation tracker list.

From the SharePoint page, open the home page in a separate tab/window.


![image26.png](images/image26.png)


In the new browser tab/window, create a new List.


![image27.png](images/image27.png)


Create the list from a blank List


![image28.png](images/image28.png)


Give the list a name and create


![image29.png](images/image29.png)


Edit in Grid view


![image30.png](images/image30.png)


Enter all team members’ names in the Title field and then Exit grid view to save the data.


![image31.png](images/image31.png)



## How to connect the helper list to the vacation tracker list


Head back to the Vacations tracker page you created earlier, which is in the previous tab/window of the browser.

Edit the page.


![image32.png](images/image32.png)


Add a vertical section to the page.


![image33.png](images/image33.png)
![image34.png](images/image34.png)


Add the list web part.


![image35.png](images/image35.png)


Select the Team members list.


![image36.png](images/image36.png)


Apply the below settings.


![image37.png](images/image37.png)


Now that the two lists are displayed on the page, the last step is to connect them both. To do that, select the vacations tracker list on the page and click Edit. Enable dynamic filtering and apply the settings shown below.


![image38.png](images/image38.png)


Save the page and republish.

Now, when one or more of the team members are selected, the vacations tracker list on the page will only show the vacation days of the selected team member names.


![image39.png](images/image39.png)



## How to display the Vacations tracker SharePoint page in a teams channel


By doing this last step, you bring the page directly into a teams channel as a tab, so everyone can quickly access the information.

In your teams channel, add a tab and select the app SharePoint pages.


![image40.png](images/image40.png)


Select the Vacations tracker page and save.


![image41.png](images/image41.png)


To allow team members to add their vacation entries, edit the page and enable the command bar for the vacations tracker list.
 

![image42.png](images/image42.png)

![image43.png](images/image43.png)


Save and republish the page.


![image44.png](images/image244.png)


Everyone in the team can add vacation entries using the form.


![image45.png](images/image45.png)



## Bonus: color code the tracker


With the new conditional formatting feature for Calendar views, you can color code your vacation tracker to give it more flavor.

Open the view, format it and set colors based on rules applied on fields available in the view.


![image46.png](images/image46.png)


Add rule.


![image47.png](images/image47.png)


Apply the settings below and save the rule. Go back and create a rule for each team member and save.


![image48.png](images/image48.png)


The final result is a vacation tracker that looks like this.


![image49.png](images/image49.png)



Hope you enjoyed this article and can benefit from the Lists app in SharePoint and Teams.

What other use cases do you think Lists can be useful for? Let me know in the comments.  

