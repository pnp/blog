---
title: "Azure Meeting Bot To Capture Meeting Participants Information"
date: 2021-09-13T02:43:00-04:00
author: "Siddharth Vaghasia"
githubname: siddharth-vaghasia
categories: ["Community post"]
images:
- images/SiddharthVaghasia_0-1630435722443.png
tags: ["Microsoft Teams", "Azure"]
type: "regular"
---

In this article, we will learn about how to create Azure Meeting Bot
which can join a team meeting via Power Automate and can log
participant's information. This use case was build as part of a
solution for one of the customers who wanted to show the dashboard of
active meeting participants about their join and left time in Power
Apps. They also used this information later for analyzing the
participant's activities for a particular event.

## Pre-requisites

-   A valid Azure subscription
-   MS Visual Studio Code
-   Node JS
-   Access to power Automate

## Step - Registering an Azure Bot

Go to azure.portal.com

Select New resource from home page.

Search for Web App Bot.

![SiddharthVaghasia_0-1630435722443.png](images/SiddharthVaghasia_0-1630435722443.png)

Select  Create and we shall see the below page. Enter below the
required details.

![SiddharthVaghasia_1-1630435722896.png](images/SiddharthVaghasia_1-1630435722896.png)

Once you select create, it will validate and start creating resources, we
can see a message in the notification bar.

![SiddharthVaghasia_2-1630435722887.png](images/SiddharthVaghasia_2-1630435722887.png)
Once completed we should see the below message.

![SiddharthVaghasia_3-1630435722444.png](images/SiddharthVaghasia_3-1630435722444.png)

## Step - Enabling Bot for Calling

Next, we would need to enable Teams Channel for this Bot. Please follow
the below steps

Go to the newly created Web App Bot Resource.

![SiddharthVaghasia_4-1630435722736.png](images/SiddharthVaghasia_4-1630435722736.png)

Select Channels from the left blade and then Teams(in the right blade).
![SiddharthVaghasia_5-1630435722747.png](images/SiddharthVaghasia_5-1630435722747.png)

Select  the Calling from the left blade and Enable the Calling
checkbox.

![SiddharthVaghasia_6-1630435722897.png](images/SiddharthVaghasia_6-1630435722897.png)

Webhook (for calling) - We will need to enter a webhook URL (an API
endpoint) which will be called when an event will occur in Teams meeting
where Bot is also a participant.

For now, we can keep empty, we will add this later, for debugging
purposes this can also be ngrok url or APP service URL in the below
format. App service is already provisioned in our previous step where we
have to take the domain and append /api/calling.

*<https://gameetingbotdemo.azurewebsites.net/api/calling>*

## Step - Create Teams Bot

In this step, we will create a bot that will have a webhook on which the
meeting activities would be posted in JSON and from here we can use the
JSON object to dump the information to the choice of your database.

We will be using yo teams to generate our Node JS Based Bot Solution.

Go to Node JS command prompt and type,

```PowerShell
yo teams
```


It will ask you series of questions, you can select as per the below
screenshot.

![SiddharthVaghasia_7-1630435837476.png](images/SiddharthVaghasia_7-1630435837476.png)


## How to get Microsoft App ID

We can get this app ID from portal.azure.com. Go to Web App Bot
Resource(which we created in the previous step).

Select configuration, and in the right blade you will find
MicrosoftAppId in Application settings.

![SiddharthVaghasia_8-1630435837628.png](images/SiddharthVaghasia_8-1630435837628.png)

Please make sure you select yes to the question "Do you want to include
bot calling support?"

## Step - Modify Code to log request object in the console

For the sake of simplicity, we will just log the request body object
which webhook receives when any event happens in Teams meeting. We can
expand this to store the body object in the Database.

***Go to** \\meetingbot\\src\\app\\meetingBot.ts*

Modify /api/calling endpoint code to below,

```JavaScript
/**
 * Webhook for incoming calls
 */
@BotCallingWebhook("/api/calling")
public async onIncomingCall(req: express.Request, res: express.Response) {
    console.log("Incoming call");
    console.log(JSON.stringify(req.body));
    // TODO: Implement authorization header validation
    // TODO: Add your management of calls (answer, reject etc.)
    // default, send an access denied
    // res.sendStatus(200);
}
```

## Step - Modify API Permission in Azure AD APP Registration

As we have created an Azure web app Bot, we can see that a default Azure
AD App Registration would have been created.

Go to portal.azure.com -\> Active Directory -\> Select APP Registration
from left blade.

We can see an App with our Bot name here.

![SiddharthVaghasia_9-1630435867496.png](images/SiddharthVaghasia_9-1630435867496.png)

Select  this App, from the Left blade select  API Permission, and
provide the below Application permissions.

![SiddharthVaghasia_10-1630435867800.png](images/SiddharthVaghasia_10-1630435867800.png)

We would be calling below GRAPH API document at
<https://learn.microsoft.com/graph/api/application-post-calls?view=graph-rest-1.0&tabs=http>
which states the above permissions.

## Step - Create Client Secret

We will need to create a client secret to calls the above graph API.
From the left blade, select  Certificate and secrets, select  new
select secret and note down this secret somewhere safely. We will use
this later.

![SiddharthVaghasia_11-1630435867960.png](images/SiddharthVaghasia_11-1630435867960.png)

Also, note client Id and Tenant Id from the Overview tab.

## Step - Create PowerAutomate to call the Graph API to add Bot to Teams Meeting

Now that we have all the pieces created, we will call GRAPH API from
Power Automate to Add Bot to the Teams meeting.

End Point to be called -
<https://graph.microsoft.com/v1.0/communications/calls>

Method type - Post

**Sample Request Body**


```JSON
{
  "@odata.type": "#microsoft.graph.call",
  "callbackUri": "<span style="color: #0000ff;">https://bot.contoso.com/callback</span>",
  "requestedModalities": [
    "audio"
  ],
  "mediaConfig": {
    "@odata.type": "#microsoft.graph.serviceHostedMediaConfig",
    "preFetchMedia": [
     {
       "uri": "https://cdn.contoso.com/beep.wav",
       "resourceId": "f8971b04-b53e-418c-9222-c82ce681a582"
     },
     {
       "uri": "https://cdn.contoso.com/cool.wav",
       "resourceId": "86dc814b-c172-4428-9112-60f8ecae1edb"
     }
    ],
  },
  "chatInfo": {
    "@odata.type": "#microsoft.graph.chatInfo",
    "threadId": "<span style="color: #0000ff;">19:meeting_Win6Ydo4wsMijFjZS00ZGVjLTk5MGUtOTRjNWY2NmNkYTFm@thread.v2</span>",
    "messageId": "0"
  },
  "meetingInfo": {
    "@odata.type": "#microsoft.graph.organizerMeetingInfo",
    "organizer": {
      "@odata.type": "#microsoft.graph.identitySet",
      "user": {
        "@odata.type": "#microsoft.graph.identity",
        "id": "<span style="color: #0000ff;">5810cede-f3cc-42eb-b2c1-e9bd5d53ec96</span>",
        "displayName": "Bob",
        "tenantId":"<span style="color: #0000ff;">86dc81db-c112-4228-9222-63f3esaa1edb</span>"
      }
    },
    "allowConversationWithoutHost": true
  },
  "tenantId":"<span style="color: #0000ff;">86dc81db-c112-4228-9222-63f3esaa1edb</span>"
}
```


 

Reference URL -
[https://learn.microsoft.com/graph/api/application-post-calls?view=graph-rest-1.0&tabs=http#exam\...](https://learn.microsoft.com/graph/api/application-post-calls?view=graph-rest-1.0&tabs=http#example-5-join-scheduled-meeting-with-service-hosted-media)

Here I have highlighted the values which we have to replace according to
our setup and team meeting. Below is how you will get this information.

**callbackUri** - This has to be the endpoint of your bot API from the
portal.azure. If you have noticed in the previous step we have modified
the code of endpoint '*/api/calling'*

For demo purposes, we will use ngrok URL after running our code and once
we have API published to Azure, we can use a permanent URL also. This
would be basically

*\<appserviceurl>/api/calling :*

*Example(hosted on Azure) -
<https://gameetingbotdemo.azurewebsites.net/api/calling>*

*Example(ngrok url) - <https://ffe966ce902d.ngrok.io/api/calling>*

All other attributes values, we have to extract from Teams meeting URL

*[https://teams.microsoft.com/l/meetup-join/19%3ameeting_NzI0NTkwMDUtY2FjMy00YjJmLThjOGEtMzg0ZDNhMzNmN\...](https://teams.microsoft.com/l/meetup-join/19%3ameeting_NzI0NTkwMDUtY2FjMy00YjJmLThjOGEtMzg0ZDNhMzNmNDFi%40thread.v2/0?context=%7b%22Tid%22%3a%225bac9eb0-1e6b-463d-8dbb-6ba2477914b9%22%2c%22Oid%22%3a%22cd15fc37-4694-4f34-811f-965ca5cc586a%22%7d)*

If you decode this url we will get human readable url like below.

*[https://teams.microsoft.com/l/meetup-join/19:meeting_NzI0NTkwMDUtY2FjMy00YjJmLThjOGEtMzg0ZDNhMzNmNDF\...](https://teams.microsoft.com/l/meetup-join/19:meeting_NzI0NTkwMDUtY2FjMy00YjJmLThjOGEtMzg0ZDNhMzNmNDFi@thread.v2/0?context=){"Tid":"5bac9eb0-1e6b-463d-8dbb-6ba2477914b9","Oid":"cd15fc37-4694-4f34-811f-965ca5cc586a"}*

**ThreadId** - Marked in orange in the above URL is our ThreadId, this
is a unique meeting Id that is generated for every meeting.

**TenantId** - Marked in blue is our Tenant Id from where the meeting is
organized.

**user.id** -Marked in green is objectID which is merely Organizer User
Id.

Now that we have all the required information, let us go to Power
Automate to create a new flow. I will be using Manually trigger flow for
sake of the demo. We will use the above meeting URLs value in the
request body. To make a Graph API Call, we will use HTTP
action(premium).

The first thing Create variables of all the different dynamic values we
have to pass. Initialize it with the default value from the above URL.
Refer to the screenshot below.

![SiddharthVaghasia_12-1630435910359.png](images/SiddharthVaghasia_12-1630435910359.png)

Add action HTTP and configure as below.

![SiddharthVaghasia_13-1630435910363.png](images/SiddharthVaghasia_13-1630435910363.png)

![SiddharthVaghasia_14-1630435910364.png](images/SiddharthVaghasia_14-1630435910364.png)

Select  the Advanced option and select Active Directory OAuth. Here you
have to add the client Id and client secret which we noted in the above
steps from the Azure Ad App Registration screen.

![SiddharthVaghasia_15-1630435910363.png](images/SiddharthVaghasia_15-1630435910363.png)

## Step - Using ngRok to Start the API End Point

Go to command prompt and project path and run

```PowerShell
gulp ngrok-serve
```

Once it runs successfully, it will create a temporary ngrok domain URL
which we have to use in the Power Automate variable
"CallingAPIEndPointURL".

![SiddharthVaghasia_16-1630435933837.png](images/SiddharthVaghasia_16-1630435933837.png)

## Step - Add ngrok URL in Azure Web App Bot Calling Webhook URL

As mentioned earlier we will also have to add this temporary URL(while
we are in development) to Teams Channel in our Azure Bot. In the
published version, this will be according to our app service URL.

![SiddharthVaghasia_17-1630435933853.png](images/SiddharthVaghasia_17-1630435933853.png)

## Step - Let's test

Now that we have our API endpoint ready listening to a particular URL,
let us run PowerAutomate to add Bot to this Team meeting. Once you
trigger the flow and if its runs successfully, we will notice some
logging happening in our node js command prompt.

It takes on around 2 mins before we will receive the request body object
in the webhook. We will receive the same response for every event, this
is documented in the URL

*[https://learn.microsoft.com/graph/api/application-post-calls?view=graph-rest-1.0&tabs=http#exam\...](https://learn.microsoft.com/graph/api/application-post-calls?view=graph-rest-1.0&tabs=http#example-5-join-scheduled-meeting-with-service-hosted-media)*

![SiddharthVaghasia_18-1630435934427.png](images/SiddharthVaghasia_18-1630435934427.png)

Below are some notes based on my experience.

-   The first response we will receive with the state "establishing"
-   the second response we will receive with state "established",
    which means the bot is added to Meeting.
-   Now on every event which will occur in teams meeting like for e.g.,
    participants join, left, someone mutes/unmutes themselves, etc\...
    we will receive a current roster of meeting.
-   By current roster I mean we will receive the list of current
    participants and its information, we will always get the current
    list of participants, the response does not say who joined, who
    left.
-   Basically, it gives us a current snapshot of the meeting when the
    webhook is has received a response.

Below is a sample of JSON which we receive when someone joins.
 

```JSON
{
  "@odata.type": "#microsoft.graph.commsNotifications",
  "value": [
    {
      "@odata.type": "#microsoft.graph.commsNotification",
      "changeType": "updated",
      "resource": "/app/calls/<span style="color: #0000ff;">ed1f5500-9a1f-4c02-953e-13cc0dc32d2c</span>/participants",
      "resourceUrl": "/communications/calls/ed1f5500-9a1f-4c02-953e-13cc0dc32d2c/participants",
      "resourceData": [
        {
          "@odata.type": "#microsoft.graph.participant",
          "info": {
            "@odata.type": "#microsoft.graph.participantInfo",
            "identity": {
              "@odata.type": "#microsoft.graph.identitySet",
              "user": {
                "@odata.type": "#microsoft.graph.identity",
                "id": "12e52958-60b9-425a-8e53-628013cb378a",
                "displayName": "Parth Patel",
                "tenantId": "5bac9eb0-1e6b-463d-8dbb-6ba2477914b9",
                "identityProvider": "AAD"
              }
            },
            "endpointType": "default",
            "languageId": "en-us",
            "platformId": "27",
            "clientVersion": "CallSignalingAgent (27/1.4.00.2879//;release_renarsl/backportsR38NR.2020.38.01.34;releases/CL2020.R38)"
          },
          "mediaStreams": [
            {
              "@odata.type": "#microsoft.graph.mediaStream",
              "mediaType": "audio",
              "label": "main-audio",
              "sourceId": "12",
              "direction": "sendReceive",
              "serverMuted": false
            },
            {
              "@odata.type": "#microsoft.graph.mediaStream",
              "mediaType": "video",
              "label": "main-video",
              "sourceId": "13",
              "direction": "receiveOnly",
              "serverMuted": false
            },
            {
              "@odata.type": "#microsoft.graph.mediaStream",
              "mediaType": "videoBasedScreenSharing",
              "label": "applicationsharing-video",
              "sourceId": "23",
              "direction": "receiveOnly",
              "serverMuted": false
            },
            {
              "@odata.type": "#microsoft.graph.mediaStream",
              "mediaType": "data",
              "label": "data",
              "sourceId": "24",
              "direction": "sendReceive",
              "serverMuted": false
            }
          ],
          "isMuted": false,
          "isInLobby": false,
          "publishedStates": [

          ],
          "meetingRole": "presenter",
          "id": "416cc5c8-4f8c-453e-a688-10ec10aa8e17"
        },
        {
          "@odata.type": "#microsoft.graph.participant",
          "info": {
            "@odata.type": "#microsoft.graph.participantInfo",
            "identity": {
              "@odata.type": "#microsoft.graph.identitySet",
              "application": {
                "@odata.type": "#microsoft.graph.identity",
                "id": "9aee55fc-4a43-42af-b3ca-9ec54a087e94",
                "tenantId": "5bac9eb0-1e6b-463d-8dbb-6ba2477914b9",
                "identityProvider": "AAD"
              }
            },
            "endpointType": "default",
            "clientVersion": "GAMeetingBotDemo (appid:9aee55fc-4a43-42af-b3ca-9ec54a087e94)"
          },
          "mediaStreams": [
            {
              "@odata.type": "#microsoft.graph.mediaStream",
              "mediaType": "audio",
              "label": "main-audio",
              "sourceId": "1",
              "direction": "sendReceive",
              "serverMuted": false
            }
          ],
          "isMuted": false,
          "isInLobby": false,
          "publishedStates": [

          ],
          "meetingRole": "presenter",
          "id": "35733c0a-7979-478e-8f12-4a42501f17ec"
        },
        {
          "@odata.type": "#microsoft.graph.participant",
          "info": {
            "@odata.type": "#microsoft.graph.participantInfo",
            "identity": {
              "@odata.type": "#microsoft.graph.identitySet",
              "user": {
                "@odata.type": "#microsoft.graph.identity",
                "id": "cd15fc37-4694-4f34-811f-965ca5cc586a",
                "displayName": "Siddharth Vaghasia",
                "tenantId": "5bac9eb0-1e6b-463d-8dbb-6ba2477914b9",
                "identityProvider": "AAD"
              }
            },
            "endpointType": "default",
            "languageId": "en-US",
            "clientVersion": "SkypeSpaces/1415/1.0.0.2021012547/os=windows; osVer=10; deviceType=computer; browser=chrome; browserVer=87.0/TsCallingVersion=2020.48.01.8/Ovb=69fa6bdf9f79d2b0267e5549b4b79c54ef9fb06b"
          },
          "mediaStreams": [
            {
              "@odata.type": "#microsoft.graph.mediaStream",
              "mediaType": "audio",
              "label": "main-audio",
              "sourceId": "3",
              "direction": "sendReceive",
              "serverMuted": false
            },
            {
              "@odata.type": "#microsoft.graph.mediaStream",
              "mediaType": "video",
              "label": "main-video",
              "sourceId": "4",
              "direction": "receiveOnly",
              "serverMuted": false
            },
            {
              "@odata.type": "#microsoft.graph.mediaStream",
              "mediaType": "videoBasedScreenSharing",
              "label": "applicationsharing-video",
              "sourceId": "10",
              "direction": "receiveOnly",
              "serverMuted": false
            }
          ],
          "isMuted": true,
          "isInLobby": false,
          "publishedStates": [

          ],
          "meetingRole": "organizer",
          "id": "7a863667-4e82-48e4-bbec-fb3a5feba132"
        }
      ]
    }
  ]
}
```

If you notice in the above JSON object, it is giving us 3 users
including the bot itself and its attributes like the user is presenter,
muted, is in the lobby, etc, userid and display name. Also, the guide
marked in blue is basically a unique call-id for a particular session.
This can help us identify participants in a particular session of the
meeting because we can use the same meeting URL multiple times. Every
time a meeting URL is used a new call-id is generated for that session.

We can dump this JSON object every time we receive JSON object in the
webhook and then we will have to manually write logic to calculate, who
joined when left, etc\... Ideally use this unstructured data and store
it in structure as participant information.

Hope this helps\...Happy coding..!!

P.S.  - This article was originally published at this
[link](https://www.c-sharpcorner.com/article/azure-meeting-bot-to-capture-meeting-participants-information/ "link")
