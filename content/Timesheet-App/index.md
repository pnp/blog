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
---
# Community Sample Timesheet App
This blog explains how I created a time sheet app in Power Apps. The app is made up of 3 core components
Dataverse – Where all the data is stored
Model Driven App – Manage the Timesheet administration. e.g. Entering new projects  
Canvas App – Where each user enters their time against a project

## Solution (Package)
The easiest and most efficient way to manage or the components is to create a Solution (Package). The Timesheet App Solution is composed of the following:
{{< image alt="Solution Package Components" src="images/Picture1.jpg" >}}