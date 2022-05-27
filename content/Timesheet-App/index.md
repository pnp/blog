---
title: "Power App for Time Sheeting"
date: 2022-05-22T08:40:00-04:00
author: "Darren Lutchner"
githubname: Dlutchy
# don't change
categories: ["Community post"]
# link to the thumbnail image for the post
images:
- images/myImage.png
# don't change
tags: []
# don't change
type: "regular"
draft: true
---
# Community Sample Timesheet App
This blog explains how I created a time sheet app in Power Apps. The app is made up of 3 core components
Dataverse – Where all the data is stored
Model Driven App – Manage the Timesheet administration. e.g. Entering new projects  
Canvas App – Where each user enters their time against a project

{{< youtube zgKe9Pu7nWA >}}

## Solution (Package)
The easiest and most efficient way to manage or the components is to create a Solution (Package). The Timesheet App Solution is composed of the following:
{{< image alt="Solution Package Components" src="images/Picture1.jpg" >}}

If you are going to modify the app you should also add any additional components to this Solution.

## Timesheet Administration - Model Driven App
The Model Driven App has 2 Tables (Projects and Timesheets). Each with a form and a view.
{{< image alt="Solution Package Components" src="images/Picture2.jpg" >}}

## Timesheet App – Canvas App
The Canvas App has a single Form. The following is where the “magic” happens.
### Run initialisation commands on App Start
{{< image alt="Solution Package Components" src="images/Picture3.jpg" >}}
'''PowerFX
// Sets a variable for the current user. When the user User saves their timesheet it adds their name to the record.
Set(
    currentUser,
    User()
);

//Create a Collection so the Timesheet data can be used. The Filter ensures that only that users timesheets are retrieved.

ClearCollect(
    colTimesheets,
    Filter(
        Timesheets,
        Person = currentUser.FullName
    )
);

//Create a Collection so all the Projects can be used.
ClearCollect(colProjects,{new_name: Blank()});
Collect(colProjects,Projects);

//Validation to ensure number of hours entered are within range.
Set(
    varHoursEntryValidation,
    false
);
'''

### Take action when Save Button is selected.
{{< image alt="Solution Package Components" src="images/Picture4.jpg" >}}
'''PowerFX
//Patch (Save) Timesheet Record to the Timesheet Dataverse Table
Patch(
    Timesheets,
    {
        'Date Worked': DateWorked_DatePicker.SelectedDate,
        Project: Project_ComboBox.Selected.Name,
        'Hours Worked': Value(HoursWorked_TextInput.Text),
        Person: currentUser.FullName,
        Comments: Comments_TextInput.Text
    }
);
//Refresh the Timesheet collection with the new saved record.
ClearCollect(
    colTimesheets,
    Filter(
        Timesheets,
        Person = currentUser.FullName
    )
);
'''

### Only enable Save Button if data entry is valid
{{< image alt="Solution Package Components" src="images/Picture5.jpg" >}}
'''PowerFX
//Enable button if Hours Worked in valid range
If(
    Or(
        Value(HoursWorked_TextInput.Text) <= 0,
        Value(HoursWorked_TextInput.Text) >24,
        Project_ComboBox.Selected.Name = Blank()
    ),
    Disabled,
    Edit
)
'''
