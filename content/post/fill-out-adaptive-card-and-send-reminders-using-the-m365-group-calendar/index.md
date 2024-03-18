---
# this is the title
title: "Send calendar reminders to particular Teams messages by utilising adaptive cards and the M365 Group Calendar"
# this is the publishing date of your article, usually this should match "now"
date: 2024-03-20T08:40:00-04:00
# This is your name
author: "Hubert Lam"
# This is your GitHub name
githubname: z3019494
# Don't change
categories: ["Community post"]
# Link to the thumbnail image for the post
images:
- images/myImage.png
# don't change
tags: []
# don't change
type: "regular"
---


# Rationale
Microsoft Teams is fantastic for teamwork, but it still has its shortcomings especially when it comes to setting reminders. 

## Planner: Create a task, but the due date doesn't pop up on the calendar
As of writing, the context menu on every Teams Channel message provides a **Create task** button:
![Planner task entry - does not pop up with a reminder](https://github.com/z3019494/blog/blob/main/content/post/fill-out-adaptive-card-and-send-reminders-using-the-m365-group-calendar/images/Planner.png)

However, the Planner task practically does not pop up. In fact, Planner can be quite unhelpful as it keeps generating additional emailed reminders. Hardly a good solution when some of us are suffering from email overload.

## Sending out a calendar event? Power Automate's built in action is limited too.
The best solution so far is to utilise a user's calendar, which will pop up "in your face". 

However, the limitations of Power Automate's **Create an event (V4)** action is quite troublesome - without some sophisticated discovery of the initiating user's default calendar ID, it's not a flow that can be used by any member of the Team. We want every team member to be able to generate these reminders for the rest of the team.


# Solution
The following Power Automate flow will:
* Allow _all_ users of the team to execute
* Uses the Team's Group Calendar to send out events that aren't necessarily online meetings.
  - An optional reminder time can be set (similar to usual Outlook calendar events) and pop up on team member's calendar reminders
* Show all reminders appear on the Group Calendar, whether it be viewed in Outlook or the SharePoint modern web app
![The overall sequence of actions](https://github.com/z3019494/blog/blob/main/content/post/fill-out-adaptive-card-and-send-reminders-using-the-m365-group-calendar/images/Add%20to%20calendar.png)
Note that this solution does not utilise just a plain SharePoint list (with a Calendar view tacked on) or the more special Event list. 

