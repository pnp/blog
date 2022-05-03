---
title: "Use CLI for Microsoft 365 to recognize contributions"
date: 2021-05-14T08:40:00-04:00
author: "Albert-Jan Schot"
githubname: appieschot
categories: ["CLI for Microsoft 365"]
images:
- images/2021-07-29_17-51-58.png
tags: ["CLI for Microsoft 365"]
type: "regular"
---

So, recognition is important, and it is important to keep in mind that
not everything should be automated. But a bit of gamification is a nice
way to show people how they interact with different services. When
considering this approach, the first step is to determine what we
require. 

## What data is available?  

Office 365 provides a whole lot of data you can use. You can choose to
get all actions yourself or using existing reports that are available.
Most of those reports can also be retrieved by the CLI for Microsoft
365. You can use the [Microsoft Docs to read what activity reports are
available](https://docs.microsoft.com/microsoft-365/admin/activity-reports/activity-reports?view=o365-worldwide "Microsoft Docs to read what activity reports are available").
Querying these reports using the CLI is done using a pattern: 

-   *m365* to execute the cli
-   *service* to pass the get the report for
-   *report* to identify the group 
-   *report type* to identify what type of data is returned by the cli. 

You can query services like SharePoint using *spo *or *teams. *And there
are different report types available depending on the type of data you
require. 
 

```bash
m365 spo report activityuserdetail
m365 teams report activeuserdetail 
```
 

The *activityuserdetail* provides insights into what each user is doing.
The *activeuserdetail* returns the amount of active users. For insights
into who is doing what the *activityuserdetail* provides the most value.
Using additional parameters you can specify the timeframe to get
reporting for. You can read all about all options on the [CLI for
Microsoft 365
documentation](https://pnp.github.io/cli-microsoft365/cmd/tenant/report/report-activeusercounts/ "CLI for Microsoft 365 documentation").
In our case we want to post the weekly progress and thus retrieve a
weeks worth of data. And since we are going to work with the data the
output is going to be JSON. Resulting in the following snippet: 

```bash
m365 teams report useractivityuserdetail --period D7 --output json
```

## Working with the result set 

The data returned contains a bit of information we do not require and is
not quite the format that we need to do reporting on. To remediate that
we will use JMESPath to sort and filter the returned data. This ensures
that we get only the information we need. 
The data returned is ordered by the user display name, so the first step
is to order by a metric we care about. The data returned contains four
metrics we can use.

1.  Team Chat Message Count
2.  Private Chat message Count
3.  Call Count
4.  Meeting Count

For this demo we will use the Team Chat Message count, but you can pick
any option you like. Using JMESPath we can use the
*sort_by() *functionality. Add a *reverse()* to make sure it is sorted
with the highest number on top.  And since we only care about the User
itself and do not need other information we can tell JMESPath to only
return the *User Principal Name*. We can even specify that we care only
about the top 3 users. So the full query would look as follows. 
 

```bash
m365 teams report useractivityuserdetail --period D7 --output json --query 'reverse(sort_by(@, &\"Team Chat Message Count\")) | [0:3].\"User Principal Name\"'
```
 

Given that there are other services as well we might use different
options to order by for different services. For SharePoint you could use
the *Viewed or Edited File Count*, *Visited Page Count*, the *Shared
Internally File Count* or the *Shared Externally File count*. And
services like Yammer offer a *Posted Count, Read Count* and Liked
*Count. *
 

```bash
m365 spo report activityuserdetail --period D7 --output json --query 'reverse(sort_by(@, &\"Viewed Or Edited File Count\")) | [0:3].\"User Principal Name\"'
m365 yammer report activityuserdetail --period D7 --output json --query 'reverse(sort_by(@, &\"Posted Count\")) | [0:3].\"User Principal Name\"'
```
 

##  Presenting your results 

With the commands above we can retrieve the information we need to
identify the social champions of last week. The next challenge is to
present this information. On the techcommunity there is a great
walkthrough on [How to send Adaptive Cards with CLI Microsoft
365](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/how-to-send-adaptive-cards-with-cli-microsoft-365/ba-p/2143466 "How to send Adaptive Cards with CLI Microsoft 365").
It explains into detail how to create a new webhook in teams and use the
CLI to send information to this webhook.  If you follow that walkthrough
and perhaps set a fancy logo you will end up with the URL you need and a
welcome post that looks something like the following: 

![social-webhook.png](images/social-webhook.png)

## Sharing your data 

Once the webhook is set up you can use the URL and post results to it.
Since we already have the data present we can use PowerShell to set the
JSON of the card, add our users to it and post the card to Teams. Make
sure to add some emojis to the Adaptive card to make it look pretty 🦾
or tweak it to your own liking. 
 
```bash
$m365Status = m365 status

if ($m365Status -eq "Logged Out") {
  # Connection to Microsoft 365
  m365 login
}

$webhookUrl = "<PUTYOURURLHERE>"

# Send top 3 for SharePoint based on file actions.
$activityUsers = m365 spo report activityuserdetail --period D7 --output json --query 'reverse(sort_by(@, &"Viewed Or Edited File Count")) | [0:3]."User Principal Name"' | ConvertFrom-Json
$title = " SharePoint Weekly Social Champions "
$card = '{ "type": "AdaptiveCard", "$schema": "http://adaptivecards.io/schemas/adaptive-card.json", "version": "1.2", "body": [  {  "type": "TextBlock",  "text": "'+$($title)+'",  "wrap": true,  "size": "Medium",  "weight": "Bolder",  "color": "Attention"  },  {  "type": "TextBlock",  "wrap": true,  "text": "Week '+$(get-date -UFormat %V)+'",  "fontType": "Default",  "size": "Small",  "weight": "Lighter",  "isSubtle": true  },  {  "type": "FactSet",  "facts": [   {   "title": "First place",   "value": "'+$($activityUsers[0])+'"   },   {   "title": "Second place",   "value": "'+$($activityUsers[1])+'"   },   {   "title": "Third place",   "value": "'+$($activityUsers[2])+'"   }  ]  } ] }'
m365 adaptivecard send --url $webhookUrl --card $card
```
 
Executed the result will look as follows:  
![2021-07-29_17-51-58.png](images/2021-07-29_17-51-58.png)


You can find this sample, and many more samples at the [CLI for
Microsoft Sample script
repository](https://pnp.github.io/cli-microsoft365/sample-scripts/ "CLI for Microsoft Sample script repository")!
If you want additional reports the script would look almost the same.
The main difference is the service to call, and the query to sort the
results on. You can use the same approach to see who is active on Teams
or Yammer. Or who is working a lot on OneDrive or Exchange if you like. 

 

```bash
# Send top 3 for Teams based on chat messages
$activityUsers = m365 teams report useractivityuserdetail --period D7 --output json --query 'reverse(sort_by(@, &"Team Chat Message Count")) | [0:3]."User Principal Name"' | ConvertFrom-Json
$title = " Teams Weekly Social Champions "
$card = '{ "type": "AdaptiveCard", "$schema": "http://adaptivecards.io/schemas/adaptive-card.json", "version": "1.2", "body": [  {  "type": "TextBlock",  "text": "'+$($title)+'",  "wrap": true,  "size": "Medium",  "weight": "Bolder",  "color": "Attention"  },  {  "type": "TextBlock",  "wrap": true,  "text": "Week '+$(get-date -UFormat %V)+'",  "fontType": "Default",  "size": "Small",  "weight": "Lighter",  "isSubtle": true  },  {  "type": "FactSet",  "facts": [   {   "title": "First place",   "value": "'+$($activityUsers[0])+'"   },   {   "title": "Second place",   "value": "'+$($activityUsers[1])+'"   },   {   "title": "Third place",   "value": "'+$($activityUsers[2])+'"   }  ]  } ] }'
m365 adaptivecard send --url $webhookUrl --card $card

# Send top 3 for Yammer based on posts
$activityUsers = m365 yammer report activityuserdetail --period D7 --output json --query 'reverse(sort_by(@, &"Posted Count")) | [0:3]."User Principal Name"' | ConvertFrom-Json
$title = " Yammer Weekly Social Champions "
$card = '{ "type": "AdaptiveCard", "$schema": "http://adaptivecards.io/schemas/adaptive-card.json", "version": "1.2", "body": [  {  "type": "TextBlock",  "text": "'+$($title)+'",  "wrap": true,  "size": "Medium",  "weight": "Bolder",  "color": "Attention"  },  {  "type": "TextBlock",  "wrap": true,  "text": "Week '+$(get-date -UFormat %V)+'",  "fontType": "Default",  "size": "Small",  "weight": "Lighter",  "isSubtle": true  },  {  "type": "FactSet",  "facts": [   {   "title": "First place",   "value": "'+$($activityUsers[0])+'"   },   {   "title": "Second place",   "value": "'+$($activityUsers[1])+'"   },   {   "title": "Third place",   "value": "'+$($activityUsers[2])+'"   }  ]  } ] }'
m365 adaptivecard send --url $webhookUrl --card $card
```
 
## What's next 

With that I hope that this blog provided some insights in how you can
recognize your users based on their activity. Keep in mind that just
automating something is not the only way to recognize contributions, but
it is a fun way to see who is doing what. It might even be a great
conversation starter. Or you could use the same approach to identify who
is missing out and instead of sharing that publicly let a Teams Champion
know who might need additional assistance. If you have any questions
regarding the CLI for Microsoft or have feedback let us know! 

We are
always looking for
[contributions](https://github.com/pnp/cli-microsoft365/issues "contributions")
or new [sample script
ideas](https://aka.ms/cli-m365/new-sample-script "CLI for Microsoft 365 sample script ideas")! 
