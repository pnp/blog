---
title: "Comparing two arrays without an apply to each?"
date: 2022-02-14T04:56:00-05:00
author: "Damo Bird 365"
categories: []
images:
- images/DamoBird365_0-1644836389622.png
tags: ["Power Automate"]
type: "regular"
summary: "I have two arrays in Power Automate, whilst very similar in structure (key/value pairs) the unique ID for both arrays is named differently (id vs PersonId) but I want to compare both and return only those that do not appear in the Array 1."
---

## The two arrays

I have two arrays in Power Automate, whilst very similar in structure (key/value pairs) the unique ID for both arrays is named differently (id vs PersonId) but I want to compare both and return only those that do not appear in the Array 1.  We can see from the image below that object id 3 & 4 are not present in Array 2.

![thumbnail image 1 of blog post titled Comparing two arrays without an apply to each? ](images/DamoBird365_0-1644836389622.png)

## Using an Apply to Each

The most common method for comparing these two arrays will involve using an apply to each, maybe even nested apply to each actions.  This results in a very inefficient flow.  It will use up far more api calls than are required and result in your flow taking a lot longer to run.  You might even require a variable to append each object during the loop and a final compose to output the contents of the new variable. 

![thumbnail image 2 of blog post titled Comparing two arrays without an apply to each? ](images/DamoBird365_1-1644837296978.png)

Above is an example of an apply to each solution that when run on the two original arrays, takes 2 seconds to complete on 5 records!

## Using Select and Filter Array Actions

### Using Select to establish an array of PersonID's

First, I want to establish an array of PersonID's, as I will use this to check if the ID of the first array appears in the Array of PersonID's. This can be done using a select action in text mode, by clicking on the icon on Select (bottom right hand corner).

![thumbnail image 3 of blog post titled Comparing two arrays without an apply to each? ](images/DamoBird365_2-1644837637842.png)

The output of which demonstrates how we have converted our 2nd Array into an array of ID's.

![thumbnail image 4 of blog post titled Comparing two arrays without an apply to each? ](images/DamoBird365_3-1644837759026.png)

### Using Filter Array to establish missing objects

With Array 1 as the input to our filter array action, we can check if the id **item()?\['id'\]** of each object is not contained (**does not contain**) within the array of PersonID's we have created using the select previously **body('select').**  This is all achieved using a single action and will run on large datasets in a fraction of a second, using only the single api call.

![thumbnail image 5 of blog post titled Comparing two arrays without an apply to each? ](images/DamoBird365_5-1644838204804.png)

Below we can see the input of Array 1, with the history output showing only id's 3 & 4 being returned.

![thumbnail image 6 of blog post titled Comparing two arrays without an apply to each? ](images/DamoBird365_4-1644837898424.png)

Finally, if your requirement is to get an array of id's that are contained within both arrays, i.e. object ID's 1, 2 and 5, you can simply change the expression to contains.

![thumbnail image 7 of blog post titled Comparing two arrays without an apply to each? ](images/DamoBird365_7-1644838602675.png)

## Running this on Larger Data Sets?

Below you will see the flow having run on 100 records in an array.  The Select/Filter method has completed in 0 seconds once more, but the apply to each has taken 40 seconds and whilst you could increase the overall speed by turning on concurrency, do you really want to be running hundreds, maybe thousands of API calls using an apply to each, when you can get the job done in two, **Select** and **Filter**?

![thumbnail image 8 of blog post titled Comparing two arrays without an apply to each? ](images/DamoBird365_9-1644839535098.png)

Please let me know if you have been able to implement this within your own solution and the time/efficiency you have introduced as a result.

## About Me

I am Microsoft 365 Consultant working on the Power Platform, a Microsoft Power Automate Forum Super User and a Microsoft Business Applications MVP (2022).  I have a blog [www.DamoBird365.com](http://www.DamoBird365.com) where I share tips and tricks like this as I explore potential use cases that I am made aware of through work and through play.  I also run a YouTube channel [www.youtube.com/c/DamoBird365](http://www.youtube.com/c/DamoBird365) where I demonstrate tips like above in my walkthrough demos.  I am happy for folk to contact me via Social Media as DamoBird365 to discuss the technology, learn and share ideas and concepts.
