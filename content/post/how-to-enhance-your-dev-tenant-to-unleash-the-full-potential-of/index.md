---
title: 'How to enhance your "dev tenant" to unleash the full potential of the Power Platform'
date: 2021-02-23T12:13:00-05:00
author: "Michael Roth"
githubname: MichaelRoth42
categories: ["Community post"]
images:
- images/devtenant-micha.png
tags: ["Power Automate", "Power Apps"]
type: "regular"
---

The Microsoft 365 Developer tenant is an amazing feature to learn and experiment in the Microsoft 365 universe (actually I'm talking about your personal development "sandbox" of the Microsoft 365 developer program. 

If you have no idea, what a "dev tenant" is, read the article "[What is a "Dev tenant" and why would you want one](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/what-is-a-dev-tenant-and-why-would-you-want-one/ba-p/2036610)" from [Julie Turner](https://github.com/juliemturner)). 

But there are limitations if it comes to experience the full potential of the Power Platform. Power Platform licensing is a bit complex, but to simplify things: You may use standard connectors within most Microsoft 365 licenses (like E3 or E5), but you can't you can't use premium connectors, or on prem data gateways, or add Microsoft Dataverse to your environments. Since the dev tenant gives only you a Microsoft  365 E5 license, you would need to purchase a standalone license., Which is not ideal if you just want to learn and decide later on if you want to dig deeper into the Power Platform.

Luckily there is the [Power Apps Community Plan](https://powerapps.microsoft.com/communityplan/) and you can add this plan to your developer tenant. 

## What are the advantages of the Power App Community Plan?

With the Community plan, you get a developer environment for free which gives you the possibility to learn and develop your skills (check out the [Power Platform Apps plan docs article](https://docs.microsoft.com/powerapps/maker/dev-community-plan) for more information). Developer environments are exclusively for the Community Plan , you can learn more here in the [environments overview](https://docs.microsoft.com/power-platform/admin/environments-overview) documentation. In this environment you get a lot of possibilities which are not included in the Power Apps license seeded in the Microsoft 365 E5 license:

-   You can use premium connectors (only for data sources within Power
    Apps)
-   You can build unlimited custom connectors
-   You can use Dataverse
-   You're able to export your apps and flows to AppSource for others to
    test

You see, if you want to learn more about the Power Platform and develop
your skills, this is a huge benefit for you. And it comes for free.
![What is included in the Power Apps Community Plan](images/included.png)

## How to join the Community Plan?

Let me walk you through the process. You need your log in data for the
developer tenant: Mail address and password.

Go to the [Power Apps Community Plan
website](https://powerapps.microsoft.com/communityplan/) and click
on **Get started free**.
![The overview page of the Power Apps Community Plan](images/Overview.png)

In the next step you need to insert the mail address of your dev tenant.

That is very important, do not use a different mail address, since you
want the Community Plan to be linked to your dev tenant. After that
select  **Sign Up**.
![The sign in page of the Power Apps Community Plan](images/getstarted.png)

You will get a notification that says, that you're using this address
with another Microsoft Service already. Of course, you do, you use it
for your developer tenant, right? So select  **Sign In**. 
![a pop up mentioning, that you already use the address for a Microsoft Service](images/noworries.png)

The next window is a confirmation that you're signed in and you can
(important, you don't have to) decide to get promotion and offers send
to your address.

You can also decide to share your information with partners in order to
get more relevant information.

You don't have to, so choose wisely.

And naturally by clicking on **Start** you confirm that you've read the
terms and conditions and the Microsoft Privacy Policy. So maybe it's a
good point to read them ;)

![A pop up asking you to agree to the terms and conditions and decide if you want to share your information and get email offers from Microsoft](images/almost.png)

Don't you worry, you're almost done. In order to start with the Power
Apps Community Plan you need to choose the country you're using the
Power Platform in. There are various legal conditions, which differ
depending on the country. Once again you can choose the get the latest
Power Apps tips and information, yet this is no mandatory field.

If you hit that **Accept** button you're done.
![A pop up asking you to choose your country to begin.](images/lastthing.png)

If you check the [Power Platform Admin Center](https://aka.ms/ppac) you
will recognize, that there is another environment, next to the default
one.

Congratulations, you've just joined the Power Apps Community Plan and
can now see your new Developer environment. 
![A picture of two different environments in the Power Platform Admin Center](images/Environments.png)

Now you can start developing apps and flows in this specific
environment.

But there is one more thing you need to pay attention to: If you open
Power Automate or Power Apps, make sure that you're in the correct
environment. In the upper right corner of your browser you can see, what
environment you're currently in. Select  the button **Environments** to
see a list of all your available environments. Now select you newly
created Developer environment (in my case it's **Michael Roth's
Environment**). 

Now you're using the newly created Developer environment
with all the benefits from the Power Apps Community Plan.
![A picture showing the button the select the right environment in the Power Tools](images/Choose_environment.png)
