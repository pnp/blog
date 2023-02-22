---
title: "Teams - an adoption idea? Transfer your group chat emails to Teams with Power Automate"
date: 2021-04-26T12:28:00-04:00
author: "Damo Bird 365"
categories: ["Community post"]
images:
- images/DamoBird365_0-1619420006466.png
tags: ["Microsoft Teams", "Adaptive cards", "Power Automate"]
type: "regular"
---

**Transfer your group chat emails to Teams with Power Automate**

I recently covered this idea on [my
blog](https://damobird365.birdhoose.co.uk/2021/02/11/an-adoption-idea-instantly-transfer-an-email-to-teams-chat-with-powerautomate/) but
it is a Cloud Flow that I make use of often so I thought I would share
it with you all.  My organisation is well in to their Teams adoption
journey and whilst a large proportion of users use Teams for their first
port of call for a group chat, it still often surprises me when a
conversation is struck up via Outlook Email and very quickly we get lost
between reply to alls and reply to sender.  Could Power Automate help
you move that conversation group or one to one to Teams with a mouse
click before the conversation gets out of control?
The simplest way for me, to transfer the conversation from Outlook and
trigger a flow, was to use "When an email is flagged" trigger. Therefore
I can simply flag an email in Outlook and take the conversation onto
Teams.
With the variables provided by the email trigger, I compose (by default)
the to and from fields in order to get all mail recipients (albeit you
may want to include the CC'd emails to) and simply replace the semi
colon with a comma, this is needed for the final and only other step.
Using the "Post your own adaptive card as the Flow bot to a user" step,
I am able to send an adaptive card notification in Teams to myself and
provide a summary of the email I am transferring, from, subject and body
preview and in my case the option to start a one to one chat with the
sender or a group chat if there are more than one recipients of the
email. This is done using the [Deep
Link](https://docs.microsoft.com/microsoftteams/platform/concepts/build-and-test/deep-links#generating-a-deep-link-to-a-chat) feature
of Teams.
I have supplied a copy/paste option at the end of my post that will
allow you to replicate this in your personal PowerAutomate / Teams
environment in a matter of seconds. 


**\*\*NOTE\*\*** ***make sure you update the TO field in the post
adaptive card action as it's currently set to
youremail\[at\]yourdomain\[dot\]com***.


**So, what does the Cloud Flow look like?**


![DamoBird365_0-1619420006466.png](images/DamoBird365_0-1619420006466.png)

The cloud flow only has 2 actions
The flow simply consists of a compose action in order to structure the
list of emails from the email trigger, above I don't include the cc'd
emails.  You've therefore a couple options for the get group email
compose action, do you want to include cc'd or not in the Group Chat
Deep Link?  The below sample snippet expression includes the
ccRecipients, but feel free to adjust as necessary.

```json
replace(tolower(concat(triggerOutputs()?[‘body/toRecipients’], ‘;’, triggerOutputs()?[‘body/from’], ‘;’, triggerOutputs()?[‘body/ccRecipients’])), ‘;’, ‘,’)
```

The second and final step is an adaptive card built via [adaptive cards
designer](https://adaptivecards.io/samples/).  It's a steep learning
curve but Designer site gives you plenty of sample cards to experiment
with and it is here that you need to include the [deep
links](https://docs.microsoft.com/microsoftteams/platform/concepts/build-and-test/deep-links#generating-a-deep-link-to-a-chat) to
your new Teams conversations which will automatically launch a teams
conversation with these users.

**The User Experience**
My colleague Alex, sends me an email with a list of colleagues in the to
field.  Before the conversation gets out of control, I simply flag the
email and instigate a move to Teams Group Chat.
![DamoBird365_1-1619420516989.png](images/DamoBird365_1-1619420516989.png)

Within a matter of seconds, basically as fast as your Flow is triggered,
a Flow Bot message is received to my Teams application with the subject
and summary email body including a link to both a one to one and group
chat.  

![DamoBird365_2-1619420664133.png](images/DamoBird365_2-1619420664133.png)

Clicking on that Group DM in Teams button results in an opening
conversation line and conversation subject (in draft), all courtesy of
the deep link.  Now it's time to get the conversation going.
![DamoBird365_3-1619420755529.png](images/DamoBird365_3-1619420755529.png)

**Want to try the solution quickly?**

Did you know that you can copy and paste Cloud Flow actions between
environments really easily?  Simply by creating a new Cloud Flow with
the "When an email is flagged" trigger you can then copy the provided
code below and paste it into your ClipBoard by clicking Next Step,
selecting My ClipBoard and pasting with Ctrl + V.  The only field you
need to change is the Adaptive Card Recipient which by default is set
to youremail\[at\]yourdomain\[dot\]com.  Just make sure you set this to
your own email address to receive the Adaptive Card.


![HowToCopyPasteSolution.gif](images/HowToCopyPasteSolution.gif)

```json
{"id":"f616b2c7-1645-4360-aff5-1710-a2bfb6a1","brandColor":"#8C3900","connectionReferences":{"shared_office365":{"connection":{"id":"/providers/Microsoft.PowerApps/apis/shared_office365/connections/shared-office365-2c7a215d-616e-4cc2-9dab-9d05f14c21a5"}},"shared_teams_1":{"connection":{"id":"/providers/Microsoft.PowerApps/apis/shared_teams/connections/shared-teams-c32e6b36-e3dd-4ca6-806d-5969ba7e6dee"}}},"connectorDisplayName":"Control","icon":"data&colon;image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzIiIGhlaWdodD0iMzIiIHZlcnNpb249IjEuMSIgdmlld0JveD0iMCAwIDMyIDMyIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPg0KIDxwYXRoIGQ9Im0wIDBoMzJ2MzJoLTMyeiIgZmlsbD0iIzhDMzkwMCIvPg0KIDxwYXRoIGQ9Im04IDEwaDE2djEyaC0xNnptMTUgMTF2LTEwaC0xNHYxMHptLTItOHY2aC0xMHYtNnptLTEgNXYtNGgtOHY0eiIgZmlsbD0iI2ZmZiIvPg0KPC9zdmc+DQo=","isTrigger":false,"operationName":"DamoBird365_Transfer_Email_To_Teams","operationDefinition":{"type":"Scope","actions":{"Get_All_To_and_From_Emails":{"type":"Compose","inputs":"@replace(tolower(concat(triggerOutputs()?['body/toRecipients'], ';', triggerOutputs()?['body/from'])), ';', ',')","runAfter":{}},"Post_your_own_adaptive_card_as_the_Flow_bot_to_a_user":{"type":"OpenApiConnection","inputs":{"host":{"connectionName":"shared_teams_1","operationId":"PostUserAdaptiveCard","apiId":"/providers/Microsoft.PowerApps/apis/shared_teams"},"parameters":{"PostAdaptiveCardRequest/recipient/to":"youremail[at]yourdomain[dot]com;","PostAdaptiveCardRequest/messageBody":"{\n    \"type\": \"AdaptiveCard\",\n    \"body\": [\n        {\n            \"type\": \"TextBlock\",\n            \"size\": \"Medium\",\n            \"weight\": \"Bolder\",\n            \"text\": \"Transfer Email to Chat\",\n            \"wrap\": true\n        },\n        {\n            \"type\": \"ColumnSet\",\n            \"columns\": [\n                {\n                    \"type\": \"Column\",\n                    \"items\": [\n                        {\n                            \"type\": \"TextBlock\",\n                            \"weight\": \"Bolder\",\n                            \"text\": \"@{triggerOutputs()?['body/from']}\",\n                            \"wrap\": true\n                        },\n                        {\n                            \"type\": \"TextBlock\",\n                            \"spacing\": \"None\",\n                            \"text\": \"@{triggerOutputs()?['body/subject']}\",\n                            \"isSubtle\": true,\n                            \"wrap\": true\n                        }\n                    ],\n                    \"width\": \"stretch\"\n                }\n            ]\n        },\n        {\n            \"type\": \"TextBlock\",\n            \"text\": \"@{triggerOutputs()?['body/bodyPreview']}\",\n            \"wrap\": true\n        }\n    ],\n  \"actions\": [\n    {\n      \"type\": \"Action.OpenUrl\",\n      \"title\": \"Start Group DM in Teams\",\n      \"url\": \"https://teams.microsoft.com/l/chat/0/0?users=@{outputs('Get_All_To_and_From_Emails')}&topicName=@{triggerOutputs()?['body/subject']}&message=Hi, regarding your Email (@{triggerOutputs()?['body/subject']}). \"\n    },\n    {\n      \"type\": \"Action.OpenUrl\",\n      \"title\": \"Start 1:1 DM in Teams\",\n      \"url\": \"https://teams.microsoft.com/l/chat/0/0?users=@{triggerOutputs()?['body/from']}&topicName=@{triggerOutputs()?['body/subject']}&message=Hi, regarding your Email (@{triggerOutputs()?['body/subject']}). \"\n    },\n  ],\n    \"$schema\": \"http://adaptivecards.io/schemas/adaptive-card.json\",\n    \"version\": \"1.2\"\n}","PostAdaptiveCardRequest/messageTitle":"Transfer Email To Teams"},"authentication":"@parameters('$authentication')"},"runAfter":{"Get_All_To_and_From_Emails":["Succeeded"]}}},"runAfter":{},"description":"***Please make sure you update the TO: in the Adaptive Card***"}}
```

**Summary**

Get that internal conversation moved from traditional Email into modern
Teams.  Not all conversation is better suited to Teams, I accept, but
it's often far more productive to have the order of conversation in
front of you, expecially if you have had a couple days off.  If a
colleague has taken the initiative to shift a conversation into Teams,
it will save the group a lot of effort having to sift through that email
string and potentially allows you to work in real time seeing if someone
is available/online, rather than wait for that next email to come in or
maybe a couple of people reply to that email at the same time with a
different
opinion -  I've enjoyed working with you email, but Teams
messaging is my preferred internal conversation route these days if I
can't start a call of course.
What trigger would suit you best?

Would you include To/From or CC'd members too in your Group Email?

Have you used Teams Deep Links before?
Check out [my blog](https://damobird365.birdhoose.co.uk/) for more ideas
or if you have an idea of your own but don't know where to start, give
me a shout via the various platforms - DamoBird365
