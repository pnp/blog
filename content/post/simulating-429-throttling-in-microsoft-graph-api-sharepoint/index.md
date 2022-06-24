---
title: "Simulating 429 Throttling in Microsoft Graph API (SharePoint/OneDrive workloads)"
date: 2021-08-20T06:14:00-04:00
author: "Cameron Dwyer"
githubname: CameronDwyer
categories: ["Community post"]
images:
- images/image.png
tags: ["Microsoft Graph"]
type: "regular"
---

Developing and testing your error handling code is really important to ensure the end product is resilient. I've always found this area to be a bit of a minefield when developing against SharePoint and more recently the Microsoft Graph API. 

I usually resort to using some software that intercepts the calls being made (e.g. [Fiddler](https://camerondwyer.com/2019/05/16/top-6-fiddler-tips-for-developers/)) and returns a mocked error response. Some error messages (such as a 502 Bad Gateway) are pretty easy to mock, but others are much harder, and must contain certain headers and body content. If you are using some of the SDKs the problem can become even more challenging as they are expecting certain error responses to have particular body structure and content.

An addition made to the SharePoint REST API some years ago that I really loved was the ability to "ask" the SharePoint API itself to return a mock 429 (throttling) error. This is brilliant in it's simplicity, no longer do you need a piece of software intercepting and trying to hand craft valid error responses (especially a tricky one like a 429 with retry-after headers). The way this works with the SharePoint REST API is that you simply add the test429=true URL parameter.
 

`http://camtoso.sharepoint.com/_api/web/lists?test429=true`


Using this URL would cause SharePoint to respond with a valid 429 error instead of trying to process the request. This lets you easily test your error handling code to ensure your code can handle and retry those 429 when they do crop up in production. Waldek Mastykarz wrote a great [post on this behavior in the SharePoint REST API](https://blog.mastykarz.nl/simulating-throttling-sharepoint/).

Now we've all moved to the Microsoft Graph API I assumed this technique wouldn't work anymore. I recently got curious and tried it anyway, to my surprise it actually does work! Maybe I shouldn't be that surprised as the Graph API conceptually is passing the calls on to the underlying workload (SharePoint). Now don't get too excited, it doesn't work for every call to the Graph API, it will only work for calls that are being passed through to SharePoint so don't expect to be able to call /teams and use this trick. Using the [Microsoft Graph Explorer](https://developer.microsoft.com/graph/graph-explorer/preview?WT.mc_id=M365-MVP-5002900) it was really easy to poke around, here's some calls that I have tried.

SharePoint (`/sites`)

`https://graph.microsoft.com/v1.0/sites/root/drives?test429=true`
 

![image](images/image.png)

SharePoint List Items

`https://graph.microsoft.com/v1.0/sites/root/lists/{listid}/items?test429=true`
 
![Graph Explorer](images/image-2.png)

OneDrive (`/drive`)

`https://graph.microsoft.com/v1.0/me/drive/root/children?test429=true`
 

![image-1](images/image-1.png)
 
Look at those beautiful 429 responses that I no longer have to intercept and hand craft. Now what would be amazing is if the Graph API standardized on this and gave us a way via parameters (or headers) to ask the Graph to respond with all the different types of errors that were possible so we could write and test code that was truly resilient and not just "theoretically" resilient until we hit an actual error one day in production and get a response that was a little different to what we were expecting.

