---
title: "How to get started with Graph Explorer"
date: 2021-03-26T07:40:00-04:00
author: "Luise Freese"
githubname: LuiseFreese
categories: ["Community post"]
images:
- images/adi-suryanata-5T0bY-x9A8U-unsplash.jpg
tags: []
type: "regular"
---

Microsoft Graph offers us a single endpoint
<https://graph.microsoft.com> to access data in Microsoft 365, Windows
10, and Enterprise Mobility and Security and can be used by makers and
developers. To get started to use the Graph API, the Graph Team offers
us a very fantastic tool called **Graph Explorer**.
What does it do? Well, it lets us explore Graph! It's a learning
playground where we can try out requests, get responses, learn about
permission scopes, and more. To access Graph Explorer, visit
[aka.ms/ge](https://aka.ms/ge) and make yourself familiar with it:

![overview.png](images/overview.png)

### Authentication 

You can decide if you want to sign in or if you want to try out with

sample data provided by Microsoft. I recommend 'playing' in your
developer tenant; if you don't have one, [learn here how to join the
Microsoft 365 developer program and get a developer
tenant](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/what-is-a-dev-tenant-and-why-would-you-want-one/ba-p/2036610).
The benefit of signing in with your (developer) account is, that you can
execute all requests including POST and DELETE requests, which is not
possible in the sample account.
When you select the gear icon, you will find a shortcut to the Microsoft
365 developer program website (to get your sandbox with sample data),
and you can change the theme as it suits your needs best. I like dark
mode most :black_heart:.
![gear.png](images/gear.png)

### Sample queries 

You will find sample queries below authentication - some may be disabled
if you are not logged in. If you select  a sample, like I did in the
screenshot below, Graph Explorer will send this HTTP request to
Microsoft Graph - and get my joined teams. We can see this in the
request area (upper part) and the response area (lower part):
![teams-channel.png](images/teams-channel.png)

We now want to create a channel called 'Microsoft Graph' in the Team
'Insidious Word Domination Plans'. We first copy the ID of the Team
from the response of that request and then use this ID in the next
sample we try out, which is:

![post-teams-channel.png](images/post-teams-channel.png)

We then replace the \`{teams-id}\` placeholder with the copied ID value
from the previous request and change the body to our needs:

![post-teams-channel-replace.png](images/post-teams-channel-replace.png)

In the \*\*Modify permissions\*\* tab, we can learn about - and consent
to permissions needed to execute this request:

![modify-permissions.png](images/modify-permissions.png)

But the awesomeness of this tool doesn't stop here - we get
ready-to-use code snippets in different languages to insert them into
our applications:

![code-snippet-js.png](images/code-snippet-js.png)

And for some GET requests, we even get Adaptive Cards:

![adaptivecards-json.png](images/adaptivecards-json.png)

We can also try out Microsoft Graph Toolkit components right here,
although I would personally recommend doing this in the dedicated
[Microsoft Graph Toolkit Playground](https://mgt.dev). If you are
unfamiliar with Microsoft Graph Toolkit, you can read how I started to
use it - in my [blog series about
MGT](https://m365princess.com/exploring-microsoft-graph-toolkit-lap-as-non-developer/) -
I also recommend having a look at the beautiful \[Microsoft Graph
component\](<https://developer.microsoft.com/graph/components> )
browser.
Last but not least: Documentation to every sample is nicely tied in -
select  the pop-out icon next to the sample queries:

![pop-out-docs.png](images/pop-out-docs.png)


## How does Graph Explorer help building apps? 

I use Microsoft Graph in Power Apps with custom connectors or in Power
Automate and Azure Logic Apps with the HTTP action to execute actions
that are not present (yet). If you never did that, but want to learn
about it, here are two blog posts that will get you started:

[How to use a custom
connector](https://m365princess.com/how-to-use-a-custom-connector-in-power-automate/)

[How to get started with HTTP requests in Power
Automate](https://m365princess.com/how-to-get-started-with-http-requests-in-power-automate)
To get from the rough idea to a working up, I follow this process:

1.  Read the docs. I mean, seriously. learn, which endpoint you will
    need to call, which permissions you will need.
2.  Try out in Graph Explorer; when it works, proceed to step 3, in case
    it doesn't, go back to step 1 :')
3.  Register your application in Azure AD with the permission scope that
    was needed for the request in Graph Explorer
4.  Try out the flow/the action of your custom connector in a basic
    sample flow/app.
5.  Now replace all hard-coded values like a Teams ID with Dynamic
    Content from within your flow
You see, Graph Explorer is an amazing tool to learn and try out - it
gets you a step closer to a working solution, but you do not need to
worry upfront about app registration, permissions etc. It's a cool way
to do a proof of concept - trying out if you can get, post, patch,
update or delete the resources you like to before you start building
your app.

## Feedback and what's next? 

I am curious - which other tools help you developing with Microsoft
Graph? Recently, [Elio Struyf published a VSCode
extension](https://marketplace.visualstudio.com/items?itemName=eliostruyf.vscode-msgraph-autocomplete),
that auto-completes Graph URLs for you, read more about it:
[vscode-msgraph-autocomplete](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/new-vscode-extension-for-autocompleting-your-microsoft-graph/ba-p/2231013).
Also, please share below what you build with Microsoft Graph? And how
you use Graph Explorer? If you like to contribute, you can check out
[Graph Explorer on
GitHub.](https://github.com/microsoftgraph/microsoft-graph-explorer-v4)
I am looking forward to your feedback!

❤ Sharing is Caring
 
