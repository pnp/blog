---
title: "React Groups and Teams Filters"
date: 2021-05-15T04:02:00-04:00
author: "Alison Collins"
githubname: ReactIntern
categories: ["Community post"]
images:
- images/img1.png
tags: ["SharePoint Framework (SPFx)"]
type: "regular"
---

In this article I'll go over both of the filters you can find in my
React Groups and Teams Filters web part. The web part is useful for site
managers, admins, and users to find their sites and
it's information.The
first filter switches the All Groups in my Organization to My Groups and
the second filters the visibility of the groups ( Public/Private/All )

In the screenshot below you can see the code for the buttons.
![img1.png](images/img1.png)


## Visibility Filters

The first three buttons are the visibility filters. They filter the
MyGroupResultsFiltered to be the button text you clicked. For example,
if you select the 'Public' button MyGroupResultsFiltered will be filtered
to include only groups with the visibility set as 'Public'.

  Let's dive deeper into what's happening. On select of, for instance, Private, the button calls the SwitchGroupList2 function (line 69) and passes through 'Private' as a parameter.   ![img2.png](images/img2.png)

That parameter 'Private' is now called 'Switch' and next we check if
that equals 'All'.
If it does and you clicked the button titled 'All', we want to set the
state of AllGroupsresults to the state holding all of the items. We do
this because if I were to filter the AllGroupsresults to private and
then switch to public and filter that, we're just filtering a filtered
list and you won't get back any results. AllGroupsresults hold all of
the results for Groups in my Organization and AllGroupsresultsFiltered
is the filtered version of that list.

In other words, when we get back
the Groups ( both Groups in my Org and My Groups ) we make a copy of
this list that we can filter however we would like and we can call on
that list and filter it and assign it to the AllGroupsresultsFiltered
value.


If the selected filter is anything other than 'All' we go ahead and
create a constant that is assigned the filtered list. What this filter
does is it maps through AllGroupsresults and checks if every group has
the visibility that you selected, keeps the groups that has the
visibility, and assigns the value to SwitchedALL. Same thing for
MyGroupResults; It maps through MyGroupResults and filters the groups to
be the ones that match the visibility you selected. Next, we set the
state of AllGroupsresultsFiltered and MyGroupResultsFiltered to be
SwitchedALL and SwitchedMY, respectively.

In our case, we selected the
button with the text 'Private' so AllGroupsresultsFiltered and
MyGroupResultsFiltered will reflect this change and only show the groups
with the visibility 'Private'.
The last part is, after the if/else statement, we want to set the state
'mode' to be the selected filter. We're doing this so that the button we
clicked will have the 'SelectedFilter' styling. How we do this is by
inputting a ternary operator in the code so that, depending on if the
mode equals 'Private', we change the styling. If you selected the
Private button the SwitchGroupList2 function will set the mode to be
'Private' and, consequently, rendering the button with the class
'Selected Filter'.


![img3.png](images/img3.png)


## Option Filter

  On the bottom right of the heading before the groups you will either see a button titled 'My Groups' or 'Groups In My Organization'.   ![option filter.png](images/option filter.png)

This button allows you to toggle between either displaying groups you
are a member of or groups in your organization. On select of this button
you call the SwitchGroupList function. ( Not the SwitchGroupList2
function mentioned earlier )

  In this function we check if the title in state is 'Groups In My Organization'. The title is what is displayed, meaning that if the button text is 'View My Groups' the title is 'Groups In My Organization'.   ![switch group list.png](images/switch group list.png)

If the title is 'Groups In My Organization' we change it to be 'My
Groups'. The opposite also applies- if the title is 'My Groups' we go
ahead and change it to be 'Groups In My Organization'.
Why is this part of the code? For two reasons: the first is because we
want to toggle the button text and header text between 'Groups In My
Organization' and 'My Groups' and also so that we can display the right
information.

  ![ternary.png](images/ternary.png)  In the render there is a ternary operator that checks if the current selected option is 'My Groups'.

If this is true it maps through MyGroupResultsFiltered and displays the
groups. If not, it renders All of the groups in your organization.
I hope you liked this article and it helped you out with your filters!

You can view the code here:
<https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-groups-teams>
