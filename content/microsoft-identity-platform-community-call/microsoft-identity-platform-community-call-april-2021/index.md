---
title: "Microsoft Identity Platform community call - April 2021"
date: 2021-05-20T05:28:00-04:00
author: "Andrew Benson"
categories: ["Microsoft identity platform community call"]
images:
- images/ViewPorter.png
tags: []
type: "regular"

---

**![EventHubBlockDiagram.png](images/EventHubBlockDiagram.png)

 
## Call summary


This month's in-depth topic:  Get Change notifications delivered via
Azure Event Hubs.  Brief introduction to Graph change notification
(webhooks) and Change notifications delivered via Azure Event hubs. 
 Microsoft Program Manager presenters - George Juma and Kalyan Krishna. 
This session was delivered and recorded on April 15, 2021.  Live and in
chat Q&A throughout call. 

 

**In-depth topic:**

**Get Change notifications delivered via Azure Event Hubs**

 

A new Microsoft Graph platform capability gives developers using change
notification features in Microsoft Graph the option to get change
notifications delivered to their applications more quickly and at scale
using Azure Event hub.   With Microsoft Graph, changes (in data in
Microsoft Graph) are tracked with webhooks, a.k.a., change
notifications.   Presently you get change notifications via a API REST
end-point exposed on the internet. 

 

Azure Event Hub is a real-time events ingestion and distribution service
built for scale.  Ideal for high throughput (no dropped notifications
due to timeouts), no public URL (security), no missed notifications if
temporally off-line.    Operationally, Microsoft Graph Change Tracking
places notifications in Event Hub and your app retrieves messages from
Event Hub rather than from publicly exposed end points on the internet. 
 You need not poll for changes, change notifications are pushed to your
app.  You need only subscribe to notifications.     

 

In the end-to-end demo, the presenter steps through app registration,
provisioning of an Azure Event Hub, an Azure Storage and a container,
add a Shared Access Policy, create an Azure Key Vault (secure connection
strings), add subscription connection string and IDs of resources to the
app.    

 


## Resources

 

-   [Deck](https://www.slideshare.net/OfficeDev/change-notifications-in-azure-event-hubsapril-2021)
    for this call
-   Documentation -  [Use the Microsoft Graph API to get change
    notifications](https://docs.microsoft.com/graph/api/resources/webhooks?view=graph-rest-1.0)
    |
    <https://docs.microsoft.com/graph/api/resources/webhooks?view=graph-rest-1.0>
-   Documentation - [Get change notifications delivered in different
    ways](https://docs.microsoft.com/graph/change-notifications-delivery)
    |
    <https://docs.microsoft.com/graph/change-notifications-delivery>
-   Training - [Microsoft Graph Training Module - Using Change
    Notifications and Track Changes with Microsoft
    Graph](https://github.com/microsoftgraph/msgraph-training-changenotifications/tree/event-hub) 
    |
    <https://github.com/microsoftgraph/msgraph-training-changenotifications/tree/event-hub>
-   Documentation - [Azure Event Hubs --- A big data streaming platform
    and event ingestion
    service](https://docs.microsoft.com/azure/event-hubs/event-hubs-about)
    |
    <https://docs.microsoft.com/azure/event-hubs/event-hubs-about>




## Actions





-   Submit your feedback and topic suggestions -
    <https://aka.ms/IDDevCommunityCallSurvey> 
-   Mark your calendar.  The next Identity Platform Community Call is on
    May 20th


## Stay connected

-   Twitter
    [https://twitter.com/microsoft365dev](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbkdvcDJHcGdzM2VIUkwzU3lOYkJaVFEzM0Q2QXxBQ3Jtc0ttM1NyaTQ2RjFSOFh3a0l4c1pralBRQVI1bDNSQ2RaVm9OdzJrRkdtV1Z1SW5VdmdwamNNLTBEaFdaSmZMc0lQNzdRZ2dDYV9WZVF1ZVIwc2dPQTZBRUZ3b3hoWUVJdDJoQWZUcWdCR2JKdmwtUU43RQ&q=https%3A%2F%2Ftwitter.com%2Fmicrosoft365dev)​
    and @azuread
-   YouTube
    [https://aka.ms/M365DevYouTube](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqa3RzWmpNU2VPRmh6dXBad3hKMmxySjBaQVl6Z3xBQ3Jtc0trVjYyeXZlSXZiX0JydHlyeHdqcTRSUnczX2xrVDloOWhzeGVCYXFibjBiM1VpXzFOd2dZX2dJdlNYQWYtekcyWXZOTHp3VkdoU2JsdmNVQ3dtdkw2ZHF0cVdCS29TQmJ1Z3hoVmJyd3JtYlFxUW92WQ&q=https%3A%2F%2Faka.ms%2FM365DevYouTube)​
-   Blogs <https://aka.ms/M365DevBlog> and
    <https://aka.ms/m365pnp/community/blog>
-   Recurrent Invite  <https://aka.ms/IDDevCommunityCalendar> 
