---
title: "How to create a button in a Model Driven (Dataverse) Power App that launches a Power Automate Flow in a Solution"
date: 2023-01-12T08:40:00-04:00
author: "Darren Lutchner"
githubname: Dlutchy
# don't change
categories: ["Community post"]
# link to the thumbnail image for the post
images:
- images/Title.png
# don't change
tags: []
# don't change
type: "regular"
draft: true
---
## Introduction

This article explains how I was able create a button in a Model Driven (Dataverse) App that launches a Power Automate Flow in a solution. The requirement came with a few additions that made it even more tricky to implement.

1. The flow needed to know who the App user is so it can send a notification to that user.
2. The flow also needed to know which Dataverse record was selected.
3. The App and Flow in part of a solution that will be sent as a Managed Solution to Test and Production environments. So, I could not hard code the Flows URL.

This work required some tricky JavaScript. My admission is I have little knowledge about JavaScript and this article is primarily for myself, so I remember how I did this for next time. So, this work took me many days of trial and error to get right.

Note — As you are going to migrate this work to another environment all components must be built in a Power Platform Solution (Not a stand alone app and flow).

Click image below to watch a video of this article.
[![Watch the video](images/1.%20Title.png)](https://youtu.be/XF_M4Jqox5Q)

## 1.Create the Flow
The trigger is the tricky part here. Because the flow will be launched by JavaScript the trigger will need to be **When an HTTP request is received**.

To meet my requirement the Trigger needs to carry the variables for Username of the person using the App and the Dataverse Table Record ID.

To create this trigger with these variables you need a sample Payload. Some simple JSON is required here.

![Sample Payload](images/2.%20Sample%20JSON%201.png)

![Sample JSON](images/3.%20When%20HTTP%20request%20is%20received.png)

This article is not about building the flow. Therefore, the remaining actions in the flow can be anything you want and can include the variables **username** and **AccountID**. I created a flow that finds the Account Record in the Account Table and sends an email to the user that the account has been created.

![Power Automate FLow](images/4.%20Flow.png)

**Testing the trigger**

Before creating the JavaScript I suggest you test the flow by triggering using Postman. Make sure you copy the Flows Trigger URL and paste as a POST function in Postman. If the flow runs then your all good to go to the next step in this article.

![Testing the Trigger](images/5.%20Testing%20Trigger.png)

## 2. Create an Environment Variable for the Flow URL

In the JavaScript you are going to need reference the flow to be triggered. However, you cannot hard code the flow URL in the JScript because in the other environments (TEST/PROD) the JScript will be part of a Managed Solution which can’t be modified. Therefore, we are going to use Environment Variables to store the Flows URL.

In the Solution create an Environment Variable:

![Environment Variable](images/6.%20Environment%20Variable.png)

## 3. Create JavaScript

If you have never created JavaScript before I suggest starting on something smaller before attempting this.

Using a Text editor (I prefer NotePad++) you need to write the JavaScript that will run in your Browser when the Power App Button is selected.

~~~JavaScript
//This JavaScript allows a button in a Model Driven (Dataverse) Power App that launches a Power Automate Flow in a Solution
//D.Lutchner
//Jan 2023

function LaunchFlow(formContext){

//Retrieves current Dataverse Record ID
var thisId = formContext.data.entity.getId().replace("{", "").replace("}", "");
console.log(thisId); //For Debugging Purpose

//Get the current Users Name
var UserName = Xrm.Page.context.getUserName();
console.log(UserName); //For Debugging Purpose

//Headers required by flow trigger
var myHeaders = new Headers();
myHeaders.append("Content-Type", "application/json");

//Retrives current Power Apps UserName and Customer Account ID
var raw = JSON.stringify({"username": UserName,"AccountID":thisId});
console.log(raw); //For Debugging Purpose

var requestOptions = {
  method: 'POST',
  headers: myHeaders,
  body: raw
};
console.log(requestOptions); //For Debugging Purpose

//Retrieves Environment Variable that contains the Flow URL
Xrm.WebApi.retrieveMultipleRecords("environmentvariabledefinition", "?$select=defaultvalue&" + "$filter=schemaname eq 'new_MyFlowsURL'").then(
    function success(results) {
        console.log(results); //For Debugging Purpose
  for (var i = 0; i < results.entities.length; i++) {
   var result = results.entities[i];
   // Columns
   var flowURL = result["defaultvalue"]; // URL
   console.log('This is flowURL ',flowURL); //For Debugging Purpose
   //Run the Power Automate Flow. This URL comes from copying the Trigger in the Flow Action - When a HTTP request is received
   fetch(flowURL, requestOptions)
   .then(response => response.text())
   .then(result => console.log(result))
   .catch(error => console.log('error', error));
  }
        // perform operations on record retrieval
    },
    function (error) {
        console.log(error.message);
        // handle error conditions
 }
);


var alertStrings = { confirmButtonLabel: "OK", text: "Your flow is running you will receive a message when it is complete", title: "Flow running" };
var alertOptions = { height: 120, width: 260 };
Xrm.Navigation.openAlertDialog(alertStrings, alertOptions).then(
    function (success) {
        console.log("Alert dialog closed");
    },
    function (error) {
          console.log(error.message);
    }
);
}
~~~

Because we cannot hard code the Flow URL using a Managed Solution the following line is required to find the Global Variable Default Value. And its a bit tricky to get right:
*Xrm.WebApi.retrieveMultipleRecords(“environmentvariabledefinition”, “?$select=defaultvalue&” + “$filter=**schemaname** eq ‘**new_MyFlowsURL**’”)*

The line of code basically retrieves records from a standard Dataverse Table called **Environments Variable Definition** and filters for a record where the Column **Schema Name** where it equals the Schema Name property of the Environment Variable.

![Environment Variable](images/7.%20Environment%20Variable%202.png)

## 4. Create Button in App Command Bar

Now we need to create a button on the Model Driven Power App Form which triggers the Java Script.

i. Edit the App then find the Page that you want to add the Button to.

ii. Select Edit Command Bar

![Create Button](images/8.%20Create%20button%20in%20App.png)

iii. Select Main Form then Edit button. — This is the records main form.

![Edit Command Bar](images/9.%20Edit%20command%20bar.png)

iv. Add a new Command

![Add Command Bar](images/10.%20Add%20Command%20Bar.png)

Add the following:

* Label — Type a label name for the Button
* Icon — Choose an Icon
* Action — Run JavaScript
* Library — (Refer step below)
* Add Function name — This is the function name at the top of your Javascript
* Parameter 1 — Set to Primary Control

![Primary Control](images/11.%20Primary%20Control.png)

v. Library

Click on Pencil to open the Edit Web Resource screen.

Choose Javascript File then Save and Publish.

![Save File](images/12.%20Save%20file.png)

## 5. Testing and Debugging

Once you have published you should be able to test the App.

When I first tested nothing happened. That is because I had errors in the JavaScript and the only way I could pick it up was using the Browser Debugger Console. I have a couple of suggestions for debugging:

1 — I assume you are using Microsoft Edge. Therefore Read the Debugging Documentation [ Get started debugging JavaScript — Microsoft Edge Development | Microsoft Learn](https://learn.microsoft.com/microsoft-edge/devtools-guide-chromium/javascript/).

2 — In your Script remove remark out your lines (using//) until you find the bad line of code.

## Conclusion

Good luck and leave yourself plenty of time to resolve issues. Also there are plenty of resources in the Internet to help.
