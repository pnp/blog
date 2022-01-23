# How to build an FAQ bot for Microsoft Teams with Power Virtual Agents
# ![walle.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258087i2A84790A2AF88C09/image-size/large?v=v2&px=999 "walle.png")

In this blog I want to show you, how you can build, test and publish an
FAQ bot for Microsoft Teams within minutes. We will use the Power
Virtual Agents for Teams, which means, that you will not need any
additional license to your Microsoft 365 license, for reference see
also [Power Virtual Agents for Microsoft Teams
plan](https://docs.microsoft.com/en-us/power-virtual-agents/requirements-licensing-subscriptions#power-virtual-agents-for-microsoft-teams-plan).

## What is Power Virtual Agents? 

Power Virtual Agents belongs like Power Apps, [Power
Automate](https://flow.microsoft.com/) and Power Bi to the Power
Platform (wow, that was a powerFULL sentence :smiling_face_with_halo:).
You can create chatbots, which can interact with users in apps and
websites, trigger workflows and more, without the need of writing code.
You can choose if you want to use it in the [Power Virtual Agents
standalone web app](https://powerva.microsoft.com/) or as [app within
Microsoft Teams](https://aka.ms/PVAForTeams).

## Let\'s build a bot 

I will guide you how to create an FAQ bot. To feed our bot we will need
some FAQ so that our can bot can learn them. I will use [FAQ regarding
licensing](https://docs.microsoft.com/en-us/power-platform/admin/powerapps-flow-licensing-faq) :nerd_face:,
but you can choose any FAQ from a website or PDF or even Word file that
you like.

-   Open Teams
-   Click on the **Apps** icon
-   Search for **Power Virtual Agents**



![pva-teams.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258047i4D727683FAB7BA38/image-size/large?v=v2&px=999 "pva-teams.png")

 
-   Click **Add**




![add-pva.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258048iE2750DD868F9766A/image-size/large?v=v2&px=999 "add-pva.png")
 


 

![pva-create.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258049i2B7D1A99DDF1AC3A/image-size/large?v=v2&px=999 "pva-create.png")

-   Give your bot a name ans select a language that your bot shall
    understand (should be the same language as your FAQ)


 

![pva-create2.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258050i0CA12D149E3475EC/image-size/large?v=v2&px=999 "pva-create2.png")
-   Click **Chatbots** - here you get an overview of ALL your chatbots

 

![my-chatsbots.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258051i1F2F575698232B9F/image-size/large?v=v2&px=999 "my-chatsbots.png")
### Add topics from any website 

-   Click **Topics**


![topics.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258052iDFFEE39414CA626B/image-size/large?v=v2&px=999 "topics.png")
 
You see, that some basic topics are already created for you. You can
take a look later.

-   Click **Suggested**


![suggested.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258053i7ABB44D54672E47A/image-size/large?v=v2&px=999 "suggested.png")
Now we want to work on feeding our bot with the FAQ from the website
that we selected.

-   Copy the URL auf the FAQ website
-   Paste the URL into the **Link to online content** field



![getfaq.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258054iF13078A33B0AA221/image-size/large?v=v2&px=999 "getfaq.png")

  

-   Click **Add**
-   Click **Start**

This may take now a couple of minutes. Grab a coffee in the
meanwhile: :hot_beverage:. Soon you will see the message that your new
suggested topics are now in:



![success.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258055i4A6ADD0E36B10D1B/image-size/large?v=v2&px=999 "success.png")

 
 

### Review & edit topics 

You can now review and edit each topic:

![edit-topics.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258056iEDD7F31C9FEBB637/image-size/large?v=v2&px=999 "edit-topics.png")

-   Click **Save Topic**

After you are done with reviewing and editing your topics, you will need
to turn on the topics

-   Switch the toggle to **on**



![turn-on.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258057i877244E5AA61A017/image-size/large?v=v2&px=999 "turn-on.png")

> Train your bot by entering more trigger phrases. This way, it is more
> likely that the Chatbot understands users asking questions even if
> they don\'t exactly match the trigger phrases
> 

Time to test the bot!



![end-connversation.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258059iC04C900BD583AAF4/image-size/large?v=v2&px=999 "end-connversation.png")

You can now review and edit your topics until you are happy with the
results.

### Publish your Bot to Microsoft Teams 

-   Click the **Publish** icon


 

![publish.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258060iEB4A27B839C6EBF7/image-size/large?v=v2&px=999 "publish.png")
-   Click **Add**

 

![add.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258061iD22851E6ED15DC6A/image-size/large?v=v2&px=999 "add.png")
-   Click **Add to Teams**



![publish-bot.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258063i7EDD3D44B29CB3A4/image-size/large?v=v2&px=999 "publish-bot.png")



-   Use your bot


![chat.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/258062iE8CC4A96B8545791/image-size/large?v=v2&px=999 "chat.png")

## Conclusion & what\'s next

It took us only a few minutes to create, test and publish a chatbot,
that now works inside of Microsoft Teams. Want to do some more? We could
extend the capabilities of our Power Virtual Agents bot: Let\'s say our
bot can\'t answer a question and needs to transfer the chat to a human
agent, who will answer that question. What if we trained the bot with
that answer so that our bot gets smarter over time? I will cover that in
one of my next blog posts. What do you use chatbots for? Did you already
try to make a 5 minute bot? Please share below :)
