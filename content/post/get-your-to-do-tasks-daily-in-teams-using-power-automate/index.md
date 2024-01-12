---
title: "Get your To Do tasks daily in Teams using Power Automate"
date: 2021-01-12T03:12:00-05:00
author: "Lee Ford"
githubname: LeeFord
categories: []
images:
- images/Teams.png
tags: ["Microsoft Teams", "Power Automate"]
type: "regular"
---


> This blog post is inspired by Ayca Bas's [excellent blog
> post](https://dev.to/azure/get-your-to-do-tasks-every-morning-on-microsoft-teams-using-azure-logic-apps-3ci1)
> on this subject using Azure Logic Apps instead of Power Automate

## Introduction

Microsoft To Do is a great tool for allowing you to keep lists of tasks
across your personal and work life. This could be something as simple as
a shopping list or a project or anything that can be split down into
individual tasks.

With the [release of the To Do APIs in Microsoft
Graph](https://learn.microsoft.com/en-gb/graph/todo-concept-overview), it
is now possible to integrate with your To Do tasks outside of To Do.


![Teams.png](images/Teams.png)


## A Helpful Reminder

Whilst you can set reminders against tasks in To Do, wouldn't it be
awesome to have these surface outside of the To Do app too? Before we
start, make sure you have some pending tasks on your **Tasks** list in
To Do!

![ToDo.png](images/ToDo.png)

In this article, we will go over how we can have Power Automate send
your outstanding tasks daily into Microsoft Teams. To achieve this, we
will undertake the following:

-   Learn how to interact with the Microsoft Graph To Do APIs in
    [Microsoft Graph
    Explorer](https://developer.microsoft.com/graph/graph-explorer)
-   Register an [Azure Active Directory
    app](https://learn.microsoft.com/azure/active-directory/develop/quickstart-register-app)
-   Create a Power Automate Custom Connector to interface with the
    Microsoft Graph To Do APIs
-   Create a Power Automate Flow to automate sending tasks to Microsoft
    Teams using the Microsoft Teams Flow Bot

## Microsoft Graph To Do APIs in Graph Explorer

To understand how the Microsoft Graph To Do API queries work, let's use
[Microsoft Graph
Explorer](https://developer.microsoft.com/graph/graph-explorer) to make
a query against your own data. The first task is to select **Sign in to
Graph Explorer**. Microsoft Graph Explorer is a great web-based tool for
using Microsoft Graph without having to create anything yourself. If you
want to test something will work (before you create your app) or try out
a new command, this is the quickest and easiest way to do so.

Once signed in, under the **Getting Started** section of **Sample
queries** run the **my To Do task lists** query. This should run the
query of *<https://graph.microsoft.com/v1.0/me/todo/lists>* and return
your task lists.

![GraphExplorer.png](images/GraphExplorer.png)

You will notice inside the response there is a task list with an *id*.
Using the *id*, change the address of the query to
*<https://graph.microsoft.com/v1.0/me/todo/lists/%7BtaskListId%7D/tasks>*,
with *{taskListId}* being replaced with the *id* in the response.


> If the task lists response contains multiple task lists, don't worry,
> just choose the list with the name *Tasks*
>
Based on my response above, my query would be
*[https://graph.microsoft.com/v1.0/me/todo/lists/AQMkAGYxYjhlNDIxLTRlN2YtNGMwNi1hYzg2LTJmMzVkMDYxYzQ1N\...](https://graph.microsoft.com/v1.0/me/todo/lists/AQMkAGYxYjhlNDIxLTRlN2YtNGMwNi1hYzg2LTJmMzVkMDYxYzQ1NQAALgAAA_Q4rkw0lJdNrFQfLSNpWB8BAA_o0Quzv4FCs60F7sB5NAAAAwESAAAA/tasks)*


![GraphExplorer2.png](images/GraphExplorer2.png)

 
> Ensure you set the request type to *GET* and the version to *v1.0*
Take a copy of your request address as we will need that later on.
 
## Register an app in Azure Active Directory

To be able to read your To Do task data using Microsoft Graph, we will
need to grant an Azure AD application permission to access it.
 
> This app registration can be used for more than one user, should you
> wish for multiple users to use this solution, the same registration
> can be used for each Power Automate Flow
>
### Registration

First, go to **Azure Active Directory** in the [Azure
Portal](https://portal.azure.com). Under **App registrations** select
**New registration** from the top menu.

![AADApp.png](images/AADApp.png)


Give the app an arbitrary **Name** e.g. *To Do_PowerAutomate*, leave
**Supported account types** and **Redirect URI** with the default
values. Select **Register** to create the app.


![AADApp2.png](images/AADApp2.png)

With the app created, take note of the **Application (client) ID** as
this will be needed later.

![AADApp3.png](images/AADApp3.png)

**Create a secret**
Next, we need to create a secret under **Certificates and secrets** on
the left-hand menu. To create a secret, select **New client secret** and
give the secret a **Description** and when it **Expires**.

![AADApp4.png](images/AADApp4.png)
![AADApp5.png](images/AADApp5.png)

Before the next step, take a copy of the **Value** of the secret and
store it securely somewhere. This has to be copied now as once we move
away the secret value will be hidden.

![AADApp6.png](images/AADApp6.png)

**Assign Microsoft Graph permissions**
Finally, we need to assign Microsoft Graph To Do permissions to our app.
This allows our app to query To Do APIs in Microsoft Graph as we did in
Microsoft Graph Explorer earlier.

Under **API permissions** on the left-hand menu, select **Add a
permission**.

![AADApp7.png](images/AADApp7.png)

Select **Microsoft Graph** as the **Microsoft API** and **Delegated
permissions**. Search for *Tasks* and choose the *Tasks.Read* permission
and select **Add permissions**.

![AADApp8.png](images/AADApp8.png)

You should now see *Tasks.Read* under **Configured permissions**.

> Tasks.Read is one of many different API permissions in Graph.
> Helpfully, there is a full breakdown of the different [Microsoft Graph
> Permissions](https://learn.microsoft.com/graph/permissions-reference)
![AADApp9.png](images/AADApp9.png)
That is all we need to do here for now, but there is one final step to
be done, later on, so leave the page open in your browser.

**Create Power Automate Custom Connector**
Moving over to [Power Automate](https://flow.microsoft.com), we need to
create a Custom Connector. A Custom Connector is a way of interfacing
with APIs in specific ways, in our case - talking to Microsoft Graph and
obtaining our list of tasks.

To create a Custom Connector, go to **Data \> Custom connectors** on the
left-hand menu in Power Automate. Here, select **New custom connector**
and **Create from blank**

**![PA.png](images/PA.png)

Give your connector an arbitrary **Connector name** e.g. *To
Do_Connector* and choose **Continue**

**![PA2.png](images/PA2.png)

For the first step, we need to specify the **Host** as
*graph.microsoft.com* and select **Security** to move on to the next
step.

![PA3.png](images/PA3.png)

For security, set as follows:

-   **Authentication type**: *OAuth 2.0*
-   **Identity Provider**: *Azure Active Directory*
-   **Client id**: **Application (client) ID** we noted down when
    creating the Azure AD app
-   **Client secret**: **Client secret** we noted down when creating the
    Azure AD app
-   **Resource URL**: *<https://graph.microsoft.com>* with no trailing
    */*
-   Everything else can be left as it is
Select **Definition** to move on to the next step.

![PA4.png](images/PA4.png)mage-alt="PA4.png" style="width: 888px;"}

We now need to create an **Action**. An **Action** is an operation that
our connector will perform when asked. In our case, our connector will
retrieve our To Do tasks for us.

Select **New action** and provide the action with the following:

-   **Summary**: A summary of what the action is doing e.g. *Get To Do
    tasks*
-   **Description**: A more in-depth description on what the action is
    doing e.g. *Get To Do tasks for signed-in user*
-   **Operation ID**: Unique identifier of the action. Use
    *GetToDoTasks*
-   **Visibility**: *Important*

![PA5.png](images/PA5.png)

Under the **Request** section, we need to provide it with sample data so
the action understands what the data from Microsoft Graph will look
like. Choose **Import from sample** and provide the following:

-   **Verb**: *GET*
-   **URL**:
    *<https://graph.microsoft.com/v1.0/me/todo/lists/%7BtaskListId%7D/tasks>* -
    you should have a copy of this (with your *taskListId*) from when we
    used Graph Explorer earlier.
-   **Headers**: Leave blank
Select **Import**

**![PA6.png](images/PA6.png)

Finally, select **Create connector** at the top right. Once saved, go to
the **Security** section and copy the **Redirect URI**

**![PA7.png](images/PA7.png)

If we now briefly head back to the Azure AD App with the **Redirect
URI**. Under **Authentication**, select **Add a platform** and paste the
**Redirect URI** you copied into the **Redirect URIs** text box. Select
**Configure** to add it.

![AADApp10.png](images/AADApp10.png)

**Create Power Automate Flow**
Now we are going to tie everything together with a Power Automate Flow.
A Flow is essentially a no/low code way to script something. In our
case, we are scripting retrieving our To Do tasks and sending them into
Microsoft Teams.

To do this, head back the [Power Automate](https://flow.microsoft.com)
and select **Create** from the left-hand menu and choose **Scheduled
cloud flow**.

![PA8.png](images/PA8.png)

> By sheduling this flow trigger type, it can be scheduled to run as
> frequently as you like.


Give your flow a **Name** and set a **Repeat every** of *1 Day*. Once
done, select **Create**

**![PA9.png](images/PA9.png)
As this is a Flow, the logic will behave as a flow chart would. Under
the **Recurrance** trigger, we need to add some additional steps to the
Flow.

To start, select **New step** and here we need to find the action we
created. The quickest way is to change the type to **Custom** and then
select it under **Actions**.

![PA10.png](images/PA10.png)

Next, you need to sign in to your account to get your tasks.

> As mentioned earlier, this can be used in multiple flows, allowing a
> whole team to use the connector to get their own tasks
>
![PA11.png](images/PA11.png)

During the sign-in process, you will need to consent the app to read
your task lists.

![PA12.png](images/PA12.png)

Before we go any further, select **Save** at the top of the page and
then go back to **My flows**. Hover over the Flow you created and choose
**Run**.

![PA13.png](images/PA13.png)

Hopefully, it was successful and you can see the result in the **Flow
Runs Page**.

![PA14.png](images/PA14.png)

Looking at the **body** of the **Output** there is some data (which is
the same as what was shown in Graph Explorer earlier). Copy the **body**
output and then select **Edit** at the top of the page to finish off the
last bits of the Flow.

![PA15.png](images/PA15.png)

The body output is great in JSON format, but we need to be able to split
it down into smaller chunks (tasks). To do this, we need to be able to
parse (read) the JSON output. Add a **Parse JSON** step and set the
**Content** as *Body*. To create a **Schema** choose **Generate from
sample**.

![PA16.png](images/PA16.png)

Paste in the body output from earlier and select **Done**.

![PA17.png](images/PA17.png)

The next step we need to add is **Initialize variable**. We need to
create an Array. An array is a collection of values or objects. In our
case, ours is a collection of tasks. Give the variable the name of
*Tasks* and set the type to *Array*.

![PA18.png](images/PA18.png)

After creating the *Tasks* array, we need to populate it with the tasks.
This is achieved by adding an **Apply to each** step. A **Apply to
each** is a type of loop. In our case, it will loop through all the
tasks in our body JSON we parsed earlier and pick out the values for
each task.

Start by adding an **Apply to each** loop and selecting *value* output
from **Parse JSON**

![PA19.png](images/PA19.png)

Next, within the **Apply to each** step, **Add an action** and choose
**Compose**. This will take a specific value from the task. Under
inputs, choose *title* under **Parse JSON**.

![PA20.png](images/PA20.png)

The next step we need to add in the loop is an **Append to array
variable**. We will use this to add the task *title* to the *Tasks*
array we created earlier. Set the **Value** to the *Outputs* of
**Compose**.

![PA21.png](images/PA21.png)

Now we should have a list of tasks ready to use. The next step is to
send these to us in Teams. To do this, we need to add **Post a choice of
options as the Flow bot to a user**, making sure this is added after the
**Apply to each** and not inside it.

Before entering any details, change the options type to an array by
clicking the *T* icon.

![PA22.png](images/PA22.png)

Now, add the following:

-   **Options**: *Tasks* variable
-   **Recipient**: The same account you signed in to the Flow with
-   **Message**: Something like *Hey, here are your outstanding tasks
    for today*
-   **Headline**: Something like *Your tasks for the day*
-   **IsAlert**: *Yes* - This makes it so you are notified of the
    message in Teams

![PA23.png](images/PA23.png)

If you were to run the Flow now, you will see the list of tasks appear
in Teams. However, choosing any of the tasks doesn't do anything.

![Teams.png](images/Teams.png)

Back in the Flow, we need to fix it so when an option (task) is chosen,
we do something with it. Add another **Apply to each** and like the
previous loop, select *value* output from **Parse JSON**.

![PA24.png](images/PA24.png)


Within this **Apply to each** step, **Add an action** and choose
**Condition**. A **Condition** is a way to verifying a value is what we
want/don't want. In our scenario, we are looping through tasks and
looking for the one that matches what the user selected in Teams. To do
this set the first value as *selectedOption* under **Post a choice\...**
and the second value is *title* under **Parse JSON**.

![PA25.png](images/PA25.png)

We now need to act upon when the condition is met (the task equals the
chosen option in Teams). Under **If yes**, add **Post message as the
Flow bot to a user**. Complete it as follows:

-   **Recipient**: The same account you signed in to the Flow with
-                             **Message**: A message containing the details of the task (see
    image)
-   **Headline**: *Title* from **Parse JSON**
-   **IsAlert**: *Yes* - This makes it so you are notified of the
    message in Teams

![PA26.png](images/PA26.png)

Leave **If no** blank.

**Finishing up**
If you now run the Flow it should send you a message with your tasks.

![Teams2.png](images/Teams2.png)

Choosing a task will then return details on that task.

![Teams3.png](images/Teams3.png)

Congratulations, you have now managed to create an Azure AD application,
talk to Microsoft Graph, pass that into Power Automate and on to Teams!\
\
*This is post is cross-posted at my [personal
blog](https://www.lee-ford.co.uk/to-do-power-automate-teams/)*
