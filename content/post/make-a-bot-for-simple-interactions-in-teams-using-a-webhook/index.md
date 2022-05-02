---
title: "Make a bot for simple interactions in Teams using a Webhook"
date: 2022-01-18T05:05:00-05:00
author: "Lee Ford"
githubname: LeeFord
categories: ["Community post"]
images:
- images/149174368-58562d12-5554-4625-a902-0df103e00cff.png
tags: ["Azure", "Microsoft Teams"]
type: "regular"
summary: "Have you ever had an idea to ask a bot to perform a simple interaction? Then this article is for you"
---

## Introduction

Have you ever had an idea to ask a bot to perform a *simple
interaction*? Then this article is for you.

A *simple interaction* could be an answer to a question you asked:

-   **You:** *What time is it?*
-   **Bot:** *It's 3.56PM*

You could achieve this (and more) by building a bot using tools such as
Power Virtual Agents or Bot Framework, but that is a little overkill for
a simple interaction.

Instead, let's use **Webhooks** to achieve this.

## The idea 

Before we begin, let's fictionalize a use case. The idea is that users
need to quickly be able to check the current and forecasted for any
location from within a Team.

![Image](images/149214689-3bf95faa-11dc-466d-999d-731f41c6d8f3.png)


## The solution

![Overview of the solution](images/149226058-e5b23a26-ab06-4197-a93e-0343ee3fbbf6.png)


The solution is a Webhook in Teams and a Bot (surprised?). This works as
follows:

1.  User @ mentions the Webhook (same as a would any other bot) in a
    Team channel
2.  This will trigger some external service (bot) HTTP, in this case an
    Azure Function
3.  The external service (Bot) will call a weather API and then return
    the weather information to the Team channel

Let's break this down by component.

### Webhook 

A Webhook is a way for two applications that can communicate with each
other. In our case, a simple bot and Teams.

Teams supports two types of Webhooks:

-   **Incoming Webhook** - An application sends a message to Teams using
    a Webhook address generated in Teams. This could be used if you
    wanted to automate some sort of alert or notification in to a Team
-   **Outgoing Webhook** - Teams sends a message (request) to a Webhook
    address created outside of Teams. The external Webhook address is an
    application that then responds to your request with message
    (response)

For this solution, it is an **Outgoing Webhook**.

There are some limitations to using a Webhook in Teams, so bear these in
mind when choosing Webhooks for your own idea:

-   Webhooks are associated to a single Team. You cannot deploy the same
    Webhook to multiple Teams or outside of a Team (personal context)
-   Everybody in the Team can see the interaction. If the interaction
    should be private (between the user and the bot), this should not be
    used
-   This will work with a simple request and response, or question and
    answer. It will not work with branching dialogs, or multiple
    questions

### The API 

To get the weather information, [OpenWeatherMap
API](https://openweathermap.org/api) will be used. You can register for
an API key.

### The Bot 

The bot is where the magic happens. It is code hosted externally to
Teams that can be called over HTTP (via the Webhook). What that code
does, where it is hosted, is all up to you. For this scenario, there is
an (written in TypeScript), which can be
found here:
[Azure Function HTTP Trigger](https://github.com/leeford/teams-webhook-weatherbot-sample).

You are free to use the linked code as a basis for your own idea, or
create your own code in your choice of programming language. The basic
construct of a bot behavior needs to be as follows:

1.  Authenticate request (using a token from Teams)
2.  Get weather information from API
3.  Send response to request. This **MUST** be a bot "Activity", with
    an attached Adaptive Card otherwise Teams will not handle the
    response correctly

## Setup 

The setup of this solution comprises of two parts:

-   Bot code accessible via HTTP
-   Outgoing Webhook in Teams

### Bot 

A Azure Function HTTP Trigger hosting the code is created. The URL of
the trigger needs to be copied for the next step

![Overview of the solution](images/149174368-58562d12-5554-4625-a902-0df103e00cff.png)

> Disregard the trailing question mark and any other text past this

### Teams Webhook

To add an Outgoing Webhook, the following is done:

1.  Find the Team to host the Webhook

2.  Select the ellipsis (\...) on the Team and choose **Manage team**

    ![Manage teams](images/149214507-8e0f6fac-4fc7-4901-b121-4cdab13d7aae.png)


3.  Under the **Apps** tab, at the bottom right of the page, there will
    be an option to **Create an outgoing webhook**
    
    ![Manage teams](images/149138950-b86db5c1-cef7-4334-bd3e-c52f90a49e75.png)

    Provide the following:
    
    -   **Name**: A short name that will be used to @ mention the
        Webhook. Keep it to one word if you can e.g. *Weather*

    -   **Callback URL**: This is where the URL of the bot is entered
        (e.g. URL of the Azure Functions HTTP Trigger)

    -   **Description**: A description of the purpose and functionality
        of the webhook e.g. *Provides current and forecasted weather for
        any location*

    -   **Icon**: Image that will appear next to the Webhook

        ![Parameters to provide](images/149214338-c8217ed4-bdb9-468d-be26-ccac553a735f.png)

1.  Once the Webhook is created, take a note of the **Security token**
    of the Webhook as it will only be shown once and will be required
    for authentication to the bot

    ![Parameters to provide](images/149213977-50ff69b7-cb4a-44fb-bfc6-277e8214a605.png)

### Configure Bot

With the bot and webhook created, one final step is to configure the
bot. In this case, the following is added under **Configuration** on the
Azure Function:

-   **TeamsSecurityToken**: The **Security token** from the Teams
    Outgoing Webhook. This is used for the bot to validate requests are
    from a trusted source (your Team)
-   **WeatherAPIKey**: The **API key** to grant access to the
    OpenWeatherMap API

![Configure the bot](images/149180772-e8942bd0-217d-4ee9-b734-9f1910ad2535.png)

> To simplify this example, I have stored these in application settings.
> In a production environment, please ensure this is held somewhere more
> secure, such as Azure KeyVault references that can be accessed using
> Managed Identity

## Demo time 

With everything in place, all that is left is to try it! Simply mention
the Webhook and enter a location, and the weather is returned!

![Configure the bot](images/149221643-96f50590-dd93-4616-83f5-98ff9d219a4b.gif)

