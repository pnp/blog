---
title: "Avoid Unnecessary Looping (Apply to each) in Power Automate"
date: 2021-03-06T08:26:00-05:00
author: "Leon Armston"
githubname: LeonArmston
categories: ["Community post"]
images:
- images/LeonArmston_2-1615045186651.png
tags: ["Power Automate"]
type: "regular"
---

## Use Case

Often you want to retrieve just one item in a SharePoint list and then
display the value of a property from it. You will use the SharePoint Get
Items action with a query (ODATA filter query) i.e. **Title eq
'City'** and you know that it should only return one record.
Unfortunately the SharePoint Get Items action by default returns an
array (*collection of items*) even if there is just one item and even if
you specify the Top Count (*items to be returned*) to be 1. So if you
want to use a property from the Get Items action then Power Automate
will automatically add the action to an Apply to each loop as it comes
from an Array (*see image below*).

![LeonArmston_1-1615045186646.png](images/LeonArmston_1-1615045186646.png)

If we test the Flow and we can see there is only one object in the array
so we can see the Apply to each loop is unnecessary as it does not need
to loop through any other items.

![LeonArmston_2-1615045186651.png](images/LeonArmston_2-1615045186651.png)

I always like to reduce the amount of actions and loops in Power
Automate for speed and readability reasons.

## Remove unnecessary Apply to each loops with the first() function

I will now show you how to avoid having unnecessary Apply to each loops
being added to your Flow and instead just access the first element of
the array using an Expression.

## Enter to the room: the Power Automate first function

which is used for retrieving the [first](https://docs.microsoft.com/azure/logic-apps/workflow-definition-language-functions-reference#first ) item from an array or string. Now we will
delete the Apply to each loop from our Flow and then create a new
Compose action where we will enter the following expression to access
just the Title property of the list item without a loop.

![LeonArmston_3-1615045186656.png](images/LeonArmston_3-1615045186656.png)

In the image below I will describe the expression: in **blue** the
first() expression is being used and within it is brackets () in **red**
is a body reference to the SharePoint Get Items action. If you have
renamed the SharePoint Get Items action then you will need to replace
'Get_Items' with the name of your action with spaces replaced by
underscores. Next in **Grey** is the SharePoint value column which holds
all of the SharePoint list item values in an array -- this does not need
to be changed. The first function brackets are then closed in **blue**.
Then finally in **green** enter the internal name of the SP column you
wish display in my case the Title column.

![LeonArmston_4-1615045186663.png](images/LeonArmston_4-1615045186663.png)

The above expression could also be done with the following expression
using **\[0\]** to access the first element of the array. However using
the **first()** function is much better for readability.

I will now test my Flow by running it and we can now see from the image
below that it ran successfully and without a adding the Compose action
to a Apply to each loop.

![LeonArmston_5-1615045186665.png](images/LeonArmston_5-1615045186665.png)

## Summary

So there we have it we have learnt how to remove unnecessary Apply to
each loops when using the SharePoint Get Items action by using the
First() function. You can use the knowledge you have learned in this
article to reduce the amount of actions and loops in your flows in Power
Automate today. As an extra bonus the same first() function can also be
used in Azure Logic Apps which names it's loop For each.
