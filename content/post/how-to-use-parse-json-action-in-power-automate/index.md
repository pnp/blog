---
title: "How to use Parse JSON action in Power Automate"
date: 2021-02-11T01:50:00-04:00
author: "Luise Freese"
githubname: LuiseFreese
categories: ["Community post"]
images:
- images/parsejson-SPList.png
tags: ["Power Automate"]
type: "regular"
---

We can see a a lot of JSON in our Power Automate flow run history, and
if you wonder, how you can *parse* JSON to make Dynamic Content (which
is selectable) out of it so you can more easily make use of an object,
then this post is made for you.
![james-pond-26vBUtlufFo-unsplash (1).jpg](images/james-pond-26vBUtlufFo-unsplash (1).jpg)

If you want to know what exactly is JSON and what you need to know about
it, please read this [great article by Bob German in the Microsoft 365
PnP Community at
TechCommunity](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/introduction-to-json/ba-p/2049369 "Introduction to JSON") or
watch this [cool video by April
Dunnam](https://www.sharepointsiren.com/2021/02/json-intro-for-microsoft-365-people/ "JSON Intro for Microsoft 365 People") first,
I will just wait here for you.

## a little use case 

Back again? Cool. Now that you know what JSON is, here is a little use
case. Let's say we wanted to post a random item from a SharePoint list
to twitter each day using Power Automate. This is a screenshot of my
list:

![parsejson-SPList.png](images/parsejson-SPList.png)
and this is the overview of the flow that we are going to build:


![parsejson-overview-flow.png](images/parsejson-overview-flow.png)

### Trigger 

First things first, our trigger needs to be the **Recurrence** trigger,
in which we specify, in which rhythm this flow shall run.

### SharePoint Get Items 

Now our flow needs to get all items from the list that we want to
randomly pick one item from.

### Compose 

We need to do some magic so we get a random item, I used the following
expression for that:


`body('Get_items')?['value'][rand(1,length(body('Get_items')?['value']))]`

We use the rand() expression to get a random list item from that list.
The arguments inside of the
expression `1,length(body('Get_items')?['value'])` mean that our flow
needs to pick a random number between 1 and (as this value could change
over time) the amount of list items (which is expressed by
our `length(body('Get_items')?['value']))`expression. The output of this
Compose action will reflect a random list item.

### Parse JSON 

Now to the interesting part of this flow: We want to exactly post this
random list item but we if we look into our Dynamic Content, it gives us
only content from the Get items action, but that is before we get a
random list item, and as we do't want to tweet ALL list items, this
isn't a good idea. How do we solve this now? Well, we parse JSON, which
means that we turn the code into objects again and those objects are
then reflected in the Dynamic Content in Power Automate.

Before we add the Parse JSON action, we need to find out, WHICH JSON we
need to parse. As already mentioned, we can see the JSON code in our run
history, which is why we save our unfinished flow and let it run. Then
we open the run history, and have a look at the Outputs of
the **Compose** action and copy everything inside of that box.


![parsejson-history.png](images/parsejson-history.png)

Now we edit our flow again, add the Parse JSON action, add the Outputs
from our Compose Action as Inputs to that action and click
the **Generate from sample** button. We will now paste the copied JSON
into the **Insert a sample JSON Payload** box and click **Done**. What
we did with that is telling the flow which objects it needs to parse. If
we now look at this action, we can see the JSON inside of our Parse JSON
action, but all values from the run history are replaced by
placeholders: "string" (if it was text), "boolean" (if it was a
yes/no), etc.


Now that this action knows what to parse, we can proceed with the next
action

### Send a tweet 

We can now see a lot of new Dynamic Content which comes from our **Parse
JSON** action.

We can now select all values we need in that tweet, plus some more or
less generic hashtags (Pro's will add hashtags into a dedicated column
in SharePoint.) If we now save and run our flow, it will first GET all
items from the list, then identify a random list element and send out a
tweet with the Title and URL auf exactly that list item.


![parsejson-twitter.png](images/parsejson-twitter.png)

## Conclusion & What's next? 

The Parse JSON action can help you turn Outputs from previous actions
into Dynamic Content which you can then use in your flow. I'd love to
know what you do with Parse JSON, let me know!

*If you are now hungry because of recipes in the
list: [ThatKitchenPrincess.com](https://thatkitchenprincess.com/ "my food blog 😋")*
First published on
[m365princess.com](https://www.m365princess.com "M365Princess.com")
