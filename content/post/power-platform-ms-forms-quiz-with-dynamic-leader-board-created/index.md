---
title: "Power Platform MS Forms Quiz with dynamic Leader Board created using Power Automate and HTTP Trigger"
date: 2021-04-29T08:40:00-04:00
author: "Damien Bird"
githubname: DamoBird365
categories: ["Community post"]
images:

tags: ["Power Automate"]
type: "regular"
---

Here is an example Power Automate solution where we query a real
SharePoint List acting as a Quiz Leader Board on my dev tenant and bring
the contents to this very blog post (at the bottom of the page).  Using
the Power Automate and the HTTP trigger we can retrieve, embed and
display content from our Office 365 environments.
The competition is rife at the top of this Leader Board.  The aim is to
get 100% and it is ordered by last completed to give everyone a chance
to be top, albeit I am sorry to say that there is no official badge for
this one.

**Want to test your Power Automate knowledge?   [Click
Here](https://forms.office.com/pages/responsepage.aspx?id=0QHJFmOXsUmWHGzXAfXQ92JiZGxvT_tLiMeGs9ElLKxUQ1RRWFpGSEtVTjFDQ0QwNU1FUlkzSDlKMC4u)**
![DamoBird365_0-1619726369840.png](images/DamoBird365_0-1619726369840.png)

For the **first flow** of **two**, using Microsoft Forms and Power
Automate I have built a pretty standard process.  The user completes the
quiz, the form gives them feedback on how well they have done and I
capture the answers to a SharePoint List - seen below.
![DamoBird365_0-1619730541847.png](images/DamoBird365_0-1619730541847.png)
 

I use the **when a new \[form\] response is submitted** trigger and
during the next couple of actions I calculate their score again (based
on their answers) as the score is not passed back to the Cloud Flow via
the Response Body.
![DamoBird365_1-1619726475005.png](images/DamoBird365_1-1619726475005.png)

**What's the Score?**

In order to calculate the score I have created an array via a
**compose** action and used the equals expression.  If the response
equals the answer, it will return true.  I then use a **filter** action
on the **item()** of each output from the select and filter on true. 
This will leave me with an array of true values.  During the create item
score field and tweet action, I use the **length()** expression (i.e.
length of array from 10 possible true answers) to return the number of
answers equaling true and multiply by 10 to get the percentage correct.
![DamoBird365_2-1619726584442.png](images/DamoBird365_2-1619726584442.png)

The final stage of this flow is a **condition **where I check to see if
the user has supplied a twitter handle.  If it's not empty I tweet out
their score.  The only disappointment here is that Twitter will not let
you tag users due to
spamming !
 any attempt to include an @ result in it being
stripped out.

**The Leader Board**

The interesting piece though, is the **second flow**, using the HTTP
trigger action to present the leader board to the web and seen below (at
least until my *premium trial* has not expired).  Using the trigger we
can run an action to get items, prepare HTML table rows using a select
action and send back a response to the website in a fraction of a
second.  The end user loading the website almost doesn't know it's
happening, albeit there is a slight delay for the flow to run, i'll
admit. *Did you notice the delay in this page loading?*

![DamoBird365_3-1619727062254.png](images/DamoBird365_3-1619727062254.png)

The reponse to the embedded IFrame on my Blog and indeed this article
which is simply calling the url provided by the HTTP Request trigger is
an HTML table.  I create the table header and then using the select
action body, I use the **join()** expression to join the elements of the
array with '' into a string and complete the HTML table.
![DamoBird365_4-1619727245209.png](images/DamoBird365_4-1619727245209.png)
I'm not a web developer and I am sure that there will be slicker ways
to embed the results of the http response into your site and for that I
would be grateful to hear from those with experience but what do you
think of this idea?  *Are you on the leader board yet?*  
As things stand - here is the leader board.  Can you resist not talking
part?  **[Click
Here](https://forms.office.com/pages/responsepage.aspx?id=0QHJFmOXsUmWHGzXAfXQ92JiZGxvT_tLiMeGs9ElLKxUQ1RRWFpGSEtVTjFDQ0QwNU1FUlkzSDlKMC4u)**

  Name     Score   Date
  -------- ------- ------------------
  Fabian   90      07/01/2022 13:45
  Sam      60      27/12/2021 15:48
  jc2318   40      19/01/2022 17:21



Tweets with your result will be posted via my twitter handle
[DamoBird365](https://twitter.com/DamoBird365)
Meanwhile, if you are looking for a certificate for your efforts, fill
out my [form
here](https://forms.office.com/Pages/ResponsePage.aspx?id=0QHJFmOXsUmWHGzXAfXQ92JiZGxvT_tLiMeGs9ElLKxURVQ0WkgwUkdPRVRWOUVDNkJUTE5CRUYzTy4u)
**Happy
quizzing !**
