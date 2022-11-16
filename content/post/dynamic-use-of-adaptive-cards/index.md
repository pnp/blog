---
# this is the title
title: "Working with Adaptive cards as Dynamic data"
# this is the publishing date of your article, usually this should match "now"
date: 2022-11-07T08:00:00-04:00
# This is your name
author: "Nathalie Leenders"
# This is your GitHub name
githubname: "Nathalie-Leenders"
# Don't change
categories: ["Community post"]
# Link to the thumbnail image for the post
images:
- images/AdaptiveCards-CardinTeams.png
# don't change
tags: [Adaptive Cards]
# don't change
type: "regular"
draft: false
---

## What are Adaptive Cards?

Adaptive cards is the name for the pop-up you can get in Teams, with custom content asking you to confirm something, or to submit a remark.

One way of creating them is through https://adaptivecards.io/designer/. 
Another way is to use the new Cards (preview) method in http://make.powerapps.com

1. On https://adaptivecards.io/designer/ design the card the way you want it.
2. Make sure on the right hand side, to add an ID element to your button or choice field.

This ID Element is important so you can recognize your data later on in the PARSE JSON step.

3. Once designed you can copy the code from the lower left corner Card Payload Editor into a text editor (to save for later/backup), or paste directly in your Flow. 

The new Cards Preview function offers the same functionality, however while I find the UI easier to use, the technical coding backend to it doesn't give you an error when you don't specify the ID.
Your flow run will fail as it needs this parameter. (To bypass, I copy/paste the code from the Card Preview option, into the Card Payload Editor from Adaptive Cards.IO and check for an error there.

Power Automate

4. Once you designed your card, insert it in your Power Automate Flow:
5. Add a step, click on **Teams**, **Post an Adaptive Card and wait for a response**.
6. Choose your channel or chat option, and in the body copy/paste the code from the designer or Adaptive Card in your Adaptive Card message body.

Use cases for adaptive cards:

* Approvals
* Needing information through text output
* Different choices of material, feedback or other choice options

(Optional) Add a variable at the top level of your Power Automate Flow, something like VarColor so it can store the information from the output from the Parse JSON. You can of course just keep it as regular dynamic content. 
(If you're using different nested steps a variable may be easier to work with)

![Teams Adaptive card without JSON](images/AdaptiveCard-EmptyBody.png)

7. After your Teams card, add an action for **Parse JSON** (JSON sounds scary but I’ll walk you through it)
8. On outputs, type the name of your card step, add `_` for spaces. Example: `outputs('Post_adaptive_card_and_wait_for_a_response')?['body']`
9. On the schema area type {}
10. Run your flow and check the run.

![Display the card in teams](images/AdaptiveCards-CardinTeams.png)


11. Copy the full output of the Teams Adaptive Card

![Body to copy](images/AdaptiveCard-Bodytocopy.png)

12. Go back into edit, and in your Parse JSON step, click on **Generate from Sample**
13. Paste the whole body there.
14. **Complete/save**

Now the output thats in your newly generated schema will appear as Dynamic content.

![Dynamic output](images/AdaptiveCard-DynamicContentResult.png)

I like to Append to string Variable the Data for Color for example, but of course you can leave this step out.
