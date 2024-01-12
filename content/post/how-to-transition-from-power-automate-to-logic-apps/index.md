---
title: "How to transition from Power Automate to Logic Apps"
date: 2021-01-12T12:07:00-05:00
author: "Paul Bullock"
githubname: pkbullock
categories: ["Community post"]
tags: ["Power Automate", "Azure Logic Apps"]
type: "regular"
---


## Introduction

Hello, are you looking to understand the differences between Power
Automate and Azure Logic Apps -- or not sure what each of these does and
when to use them? Well, you have come to the right place. Let's go
through these, to understand the differences and similarities and to
look at how you can transition between them.

Power Automate is Azure Logic apps under the hood. These share the same
workflow engine, designer surface, allowing the easy and familiar
experience of creating Flows. These have an extensive range of
connectors built in the service, enabling you to build solutions that
connect to a broader range of first and third party services. If these
do not suffice, there is the option to create a custom connector to
integrate your app with Power Automate and Logic Apps.

Both have:


-   Triggers -- the entry point which starts the workflow, such as Item
    Creation or modification, an Email, an event that is triggered by
    another service, scheduled time, and many more.
-   Actions -- the changes you want to make during the workflow. For
    example, updating a data source, perform manipulation of incoming
    data, send an email.
-   Connectors -- provide the connections to a wide range of services
    such as Office 365, Power Apps, Azure, are many more, [see this
    reference for the full range of
    connectors](https://learn.microsoft.com/connectors/connector-reference?WT.mc_id=AZ-MVP-5003816)
    ß this resource is pretty cool as you can filter based on which
    product you are using.

## What are the use cases for each product?

You may be asking yourself, why are there two similar products that
seemingly do the same thing - which the answer sits in how they are
used. So, the primary difference between the two is:

-   Power Automate resides with the Office 365 suite providing an
    end-user focused experience to allow users to build flows without
    the complexity of development knowledge to achieve the goal they
    have in mind.
-   Azure Logic Apps -- well, resides in Azure and provides an option
    use development knowledge to build workflow apps including all the
    benefits this brings such as DevOps, advanced security scenarios and
    integrate with related Azure resources.
This leads to functionality and focuses on the features that support
these features, providing unique capabilities in each product that are
not shared between them. For example,

-   The security controls differ between them such as 
-   Triggers are not the same
-   The licensing model is different for example; Power Automate relies
    on Office 365 license and plans, Logic Apps use subscriptions.

For more detail on comparing the two, check out the section [Compare
Microsoft Power Automate and Azure Logic
Apps](https://learn.microsoft.com/azure/azure-functions/functions-compare-logic-apps-ms-flow-webjobs#compare-microsoft-power-automate-and-azure-logic-apps?WT.mc_id=AZ-MVP-5003816)
in the documentation.

## Transitioning from Power Automate to Logic Apps

So, let's see moving a Flow from Power Automate to Logic Apps. In this
scenario, in Power Automate, a Flow has been created to trigger when a
SharePoint list item, get property from my Office 365 profile and Email
me when the item has changed (btw, this is available as a template), the
Flow would look like this:

![Example Flow in Power Automate](images/Power Automate Flow Example.jpg)

Within Power Automate, you have the option of **exporting** a Flow to
Logic apps:

![Screenshot showing the export option to Logic Apps](images/Export to Logic Apps - When an item is modified.jpg)


The export feature generates an ARM template (an Azure Resource Manager
template are used to provision resources in Azure) in JSON format. If
you are unfamiliar with JSON, refer to the fantastic article from Bob
German - [Introduction to
JSON](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/introduction-to-json/ba-p/2049369).
Using the ARM template, you can go to Azure
(<https://portal.azure.com>), note - this will require an [Azure
Subscription](https://azure.microsoft.com/pricing?WT.mc_id=AZ-MVP-5003816).
Search for "custom template" then find the option to "Deploy a custom
template" as shown below:

![Deploy a template option in the Azure Portal](images/Deploy a custom template.jpg)


Following the instructions and complete the fields in which Azure
presents to you, can deploy the template. After deployment is complete,
navigate to the Logic App Designer, you may need to authenticate the
connections, select  those and a pop-up window will show for you to log
in.

Once completed, you will need to Enable your Logic App then your Flow
will be ready in Azure:
 

![Showing the Logic App Designer and the example Flow](images/Azure Logic App Equivelant.jpg)

Whilst this is not the full instructions for performing the import, if
you want to see the full process of importing the Flow, visit the
article titled [Export Flows from Power Automate and deploy to Azure
Logic
Apps](https://learn.microsoft.com/azure/logic-apps/export-from-microsoft-flow-logic-app-template?WT.mc_id=AZ-MVP-5003816).

## Why would you transition from Power Automate to Logic Apps?


It's a good question. There are many factors that could influence the
decision to move, such as:

-   You need to connect to Azure resources that would require Premium
    connectors -- licensing could be a key factor. If you feel like the
    Flow could provide better value in that environment, then it is
    worth checking the option out with your IT team; additionally, you
    can visit the Azure Calculator to gauge the cost difference.
-   Azure Logic Apps include connectors that connect to Office 365
    services. As you develop or the Flow evolves, you might start to
    realise from an architectural standpoint that it makes sense for the
    Flow to reside in that environment.
-   Take a flow that you are familiar with and explore this in the Azure
    ecosystem to understand what tools, options, and integrations you
    can expand to as part of a learning or exploratory exercise.
-   You have an advanced security scenario that you cannot utilise with
    Power Automate.
-   From a service perspective, you want to hand over to a support team
    that was provided by a third party or customised template over to
    Azure Logic apps to take advantage of the advanced features.

Whilst this is not an exhaustive list of reasons, there will be plenty
of scenarios for the transition. But with the move to Azure, there are
additional factors to consider, especially if you are setting up for the
first time:

-   The security profile in Azure, is this configured? And how the usage
    is monitored, and are there any connectors that are blocked by the
    policy?
-   Who owns the subscription? And bears the cost for the app?
-   Who within the team would be responsible for supporting the app once
    in place?
-   I am deciding on a cool dev tool to explore and expand the logic
    within the app.

Whilst there is a lot to consider when looking at your Flow, you can
rule out elements that do not apply, removing the noise from any
decision.

## What are the licensing implications?

Whilst this is not a licensing guide, this model does change as you move
to Azure. The following provides an overview of the licensing
differences between the two services:

  ------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------------------------------
  ** **         **Power Automate**                                                                                                                                                    **Azure Logic Apps**
  Charged By    Office 365 plan, Per User Plan, Per Flow plan                                                                                                                         Azure Subscription
  Cost change   Predictable cost each month or year -- subscribe to a plan                                                                                                            Consumption-based -- pay for what you use
  Connectors    Shown as Standard or Premium, Premium requires plan elevation from Office 365 plan.                                                                                   Standard or Enterprise Connector executions
  Other costs   Standard cost model with an option to add connectors that require additional licensing such as
  [Adobe Sign](https://learn.microsoft.com/connectors/adobesign/)   You can add services to the Logic Apps such as App Insights, Log Analytics that increases the cost profile.
  ------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------------------------------

When considering a change, ensure that the target service is configured
appropriately and that you have done estimates based on the connectors
used, number of actions, and executions per month to ensure there are no
unexpected bills at the end of each month.
Typically, when you provision Azure Resource Groups (like folders - just
one level ;)) that contain the Azure resources you can planning to
deploy -- the advantage of this, there is a feature called "Budgets"
which allow you to set up an alerting period, e.g. monthly that send
notifications if the costings go over a budget, allowing you to assess
the resource and optimise -- but to note this isn't a cap.
![Azure Resource Group with the Budget settings screen](images/Azure Budget.jpg)

Azure Logic apps also have the option of Integrated Service
Environments, whilst they provide access to dedicated Azure resources,
the cost does go up accordingly. Check out the

[calculator](https://azure.microsoft.com/pricing/calculator?WT.mc_id=AZ-MVP-5003816)

to understand the costs before proceeding.

## Community Resources

If you want to learn more about Power Automate, Logic Apps or the
comparison, here are a list of additional resources that you can use to
explore the technologies further:

-   Microsoft Learn - [Build automated workflows to integrate data and
    apps with Azure Logic Apps - Learn | Microsoft
    Docs](https://learn.microsoft.com/en-us/training/paths/build-workflows-with-logic-apps/?WT.mc_id=AZ-MVP-5003816%3FWT.mc_id%3DAZ-MVP-5003816)
-   Microsoft Learn - [Browse all Power Automate Modules in Microsoft
    Learn | Microsoft
    Docs](https://learn.microsoft.com/learn/browse/?products=power-platform&terms=Flow&WT.mc_id=AZ-MVP-5003816)
-   M365 Community Docs - [Power Automate vs Logic Apps | Microsoft
    Docs](https://learn.microsoft.com/microsoft-365/community/power-automate-vs-logic-apps?WT.mc_id=AZ-MVP-5003816)
-   Example Teams App Templates using Logic Apps and Power Automate -
    [OfficeDev/microsoft-teams-apps-requestateam: Power Apps solution
    that automates the team creation
    pr\...](https://github.com/OfficeDev/microsoft-teams-apps-requestateam)
