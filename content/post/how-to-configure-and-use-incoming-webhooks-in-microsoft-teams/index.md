---
title: "How to configure and use Incoming Webhooks in Microsoft Teams"
date: 2021-01-11T03:37:00-05:00
author: "Rabia Williams"
githubname: rabwill
categories: ["Community post"]
images:
- images/connector-select.png
tags: ["Microsoft Teams"]
type: "regular"
---

## Intro

[Incoming webhooks](https://learn.microsoft.com/microsoftteams/platform/webhooks-and-connectors/how-to/add-incoming-webhook?WT.mc_id=m365-12509-rwilliams) are a way to send updates or messages in a channel in Teams
without a user interface,
typically done via scripts or code
programmatically. Having talked about omitting the
graphical user interface does not mean it needs a
developer to set it up. The simplicity in
implementing this in any automation makes it a perfect fit for any
makers, be it
fusion developers, low code
programmers or
consultants to leverage this
hidden gem for notification or logging
mechanism. ]

In short, [Incoming
Webhooks](https://learn.microsoft.com/microsoftteams/platform/webhooks-and-connectors/how-to/add-incoming-webhook?WT.mc_id=m365-11878-rwilliams) are
built-in connectors used to send updates back to a channel in Teams once
configured. ]

The good thing is, it is easy to set up and even
more comfortable to design your
messages you want to send through it. The messages can be plain text, or
[actionable
messages](https://learn.microsoft.com/outlook/actionable-messages/?WT.mc_id=m365-11878-rwilliams)
or [adaptive
cards](https://learn.microsoft.com/adaptive-cards/authoring-cards/getting-started?WT.mc_id=m365-11878-rwilliams) .
**Incoming
Webhooks

The documentation around
these is easy enough for anyone to
understand what they are, but here
is
the blurb. ]
[Incoming
Webhooks](https://learn.microsoft.com/microsoftteams/platform/webhooks-and-connectors/how-to/add-incoming-webhook?WT.mc_id=m365-12509-rwilliams)
is a special type of Connector in
Teams
that provide a
simple way for an external app to share content in
team channels and are often used as tracking and notification tools.
Teams provides a
unique URL to send
a JSON payload with the
message you want
to POST, typically in a card
format. Cards are user-interface (UI)
containers containing content and
actions related to a single topic and consistently present message
data. Being
just a POST operation with a JSON payload, you can use it
in maybe
your  PowerAutomate 
actions or  PowerShell  or  cURL 
scripts [see how you can do the scripts
here](https://learn.microsoft.com/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-using?WT.mc_id=m365-11878-rwilliams)

or any web app that can invoke a POST
operation. ]*
[In this article, we will take you
through the configuration and
testing of this connector in the next
sections. But before we jump in,
make sure you know that the unique URL mentioned above can be used
anonymously to send messages to
the channel
using HTTP POST, which
is why treating your webhook URL as a secret might be a good
thing, the same way as you would
treat
your PowerAutomate's  **[When
an HTTP request is received **trigger. There
are heaps of articles by the
community on securing
the URL. ]
**[Steps to
configure]**

-   Navigate to the channel where you want to add the
    webhook,
    (1) Select
    (•••) and (2)
    Choose ]**[Connectors]**

![connector-select.png](images/connector-select.png)


-  Search
    for **[Incoming
    Webhooks** and **[Add]**



![incoming-webhook.png](images/incoming-webhook.png)

-   once added, configure it by giving a name, optionally upload an
    icon and once
    done, click **[Create]**



![create.png](images/create.png)

-   Copy the URL that is unique for the channel, and
    we will later use this URL to post the
    message. 


![url.png](images/url.png)
 

[Now we have successfully configured the connector in the
channel; you should see something
like
below ]



![success.png](images/success.png)
 

## Test the connector with PowerShell

A [HTTP POST
operation](https://en.wikipedia.org/wiki/POST_(HTTP)) is
what you need to send messages using this connector. Here, let 's see
how we can test this using
PowerShell.
[Open the [Windows PowerShell]](https://learn.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7.1)

 terminal and
run the below script assuming you
have installed and are familiar
with terminal.  ]
Alternatively, you could also
run a [cURL](https://documentation.matillion.com/docs/2326784)[ script to
achieve the same (especially
for macOs and Linux
users). For
that, [see post
here](https://learn.microsoft.com/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-using#post-a-message-to-the-webhook-using-curl)
here I am using
PowerShell.
 

```powershell
Invoke-RestMethod -Method post -ContentType 'Application/Json' -Body '{"text":"Hello World!"}' -Uri  <URL of the webhook you copied> 
```
 

[![powershell.png](images/powershell.png)

If the
configuration is successful, we
can see the message already sent by the script to our
channel.

![messagesent.png](images/messagesent.png)


Now, if we want to try sending an
adaptive card, let us try one as
well.

[Let's go
to [adaptivecards.io]](https://adaptivecards.io/samples/)  and
copy a sample for an adaptive card which will be in
[JSON](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/introduction-to-json/ba-p/2049369?WT.mc_id=m365-0000-rwilliams)
format and declare
a PowerShell
variable **$json** in the below
format.
 

```json
{ 

      "type": "message", 

      "attachments": [ 

        { 

          "contentType": "application/vnd.microsoft.card.adaptive", 

          "content": <PASTE THE COPIED ADAPTIVE CARD JSON HERE> 

        }] 

} 

 
```
 

We will run the same script we ran before but with a slight change, 
the **Body** parameter
is passed with the
variable **\$json **that we
declared earlier.
 

```powershell
Invoke-RestMethod -Method post -ContentType 'Application/Json' -Body $json   -Uri  <URL of the webhook you copied> 
```
 

And here is the
result after running
the above  script

![adaptivecard.png](images/adaptivecard.png)

Hope you found this simple out of
the box capability useful and
would be using it for many situations where you want to send updates
regularly to a Team's
Channel.
What problems are you going to solve today using Incoming Webhooks? Let
us know. 
Author has also blogged about Incoming Webhooks in her personal
blog:  [Use Incoming Webhooks in SPFx app to send page feedback to
Microsoft Teams
channel.](https://rabiawilliams.com/teams/spfx-teams-incoming-webhooks/)
