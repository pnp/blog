---
title: "Save data to app personal folder"
date: 2022-03-27T05:30:00-05:00
# post thumb
images:
  - "images/thumbnail.png"
#author
author: "Adam Wójcik"
githubname: Adam-it
# description
description: ""
summary: ""
# Taxonomies
categories: ["Community post"]
tags: ["SharePoint Framework (SPFx)"]
type: "regular" # available type (epic, trending, popular, or regular)
---

## What's it all about?

So you have this really cool idea for an Spfx solution, you have the workspace ready, you added all needed dependencies, already made you mind up on the whether it's gonna be react or angular or other, and your just about to write that first line of code when suddenly:

*"hmmm…. Where I will store my applications user data?"*

As your app will save some data right? Well most of the apps do, and usually the data saved is somehow personal (in context of the current user) so maybe you will be interested in approach I would like to describe in a bit more detail in this article 😀.

## What options do we have?

Let's see some of them we may use.

- One of the easiest and I think most common approach we may take is storing data in a SharePoint list we may create while provisioning the Spfx (the Spfx package could provision this as asset or some PnP.PowerShell/CLI for Microsoft 365 will do the trick). We will need to consider if the list is going to be somehow hidden. How we should manage storing data per user? Should we create folder per user data. If so, what about permissions? Probably each user should have read permissions only to their own folder. And what's more important is where we keep the list? On each site where the webpart will be added… rather not. Better to have some one site we store the data. Ok, but potentially we want our solution to be not only for SharePoint but Teams and maybe in near future other places as well. Will storing the data in a SharePoint list be the most logical place then? Also managing the data might be a challenge. I mean should we create a column for every peace of metadata our app will store. Probably yes, but then if we want to store more data in future, we will need to probably add more columns. And doesn't this all seem like using SharePoint list as a database which we is a huge “no no”…. Ok fine let's consider something else.
- Ok lets think of a more common place. What about Dataverse. Seems like a well prepared, common database. TBH this seems like perfect for a solution done within Power Platform but for an Spfx solution…hmm…. I don't know. I never seen a Spfx webpart which saved/retrieved data from Dataverse. But maybe that's bad and it is a good idea to investigate for future, even if now doesn't seem like a common approach. Lets leave this as open point and research this later. For now seems more like a perfect place for a Power App rather than a Spfx webpart.
- Ok moving on, what we could also do is add a custom user profile property and store the data there. Creating the custom property might be a challenge as I believe we would need to do it manually, so not a very good use case for and CI/CD pipeline. And if you also had this idea I think there is a very good chance you previously have been working (or still are working) in the On-Prem world right? Seems like a way to go in the good old feature model with a couple of CSOM lines in C#, but doesn't seem like a perfect fit for Spfx. Wouldn't you agree?

Don't get me wrong, all of the above are good ideas for sure. But is there a better common place for each user to store her or his personal data? Well what about OneDrive. Also, is there someway we could save our data in a dynamic structure that we may change in future in an easy way (adding more metadata, like more columns or something like that), which is easy to 'parse' to an object? Well what about XML… only joking… I was going to say JSON.
Well, did you know we may use MS Graph and the

```
/me/drive/special/approot:/${YourFileNameHere}
```

endpoint for all that? Ye, it creates a folder for you app automagically - I mean the first time you make a request to get or save a file the folder for you app is created in user OneDrive automatically. Let's create a dedicated model in our Spfx solution and just serialize the object to a JSON file we keep in each user personal application folder on their OneDrive. I know, this is seems like a very sweet method to use for user personal data. Lets see what we should consider and how to get started with this approach.


## How to get started?

Lets start with a bit of experimenting to try it out in the [graph explorer](https://developer.microsoft.com/graph/graph-explorer) (If you haven't used it before, the graph explorer is a perfect place to test out different MS Graph API requests and also, after login, you may do it in the context of your tenant, which is really cool).

Ok so lets run a simple GET request

```
https://graph.microsoft.com/v1.0/me/drive/special/approot
```

And see what happens.

![requestToAppRoot](images/requestToAppRoot.png)

Ok success, that's nice, but what actually happened. In the response we will see a 'webUrl' param where we may see the

```
me/drive/special/approot
```

was resolved as

```
"webUrl": "https://{YOURTENANTHERE}-my.sharepoint.com/personal/{YOURLOGINHERE}_onmicrosoft_com/Documents/Apps/Graph%20Explorer"
```

And if we go there we see

![oneDriveFolders](images/oneDriveFolders.png)

… hey… a new folder in my personal OneDrive, now that’s nice. In the response we may also find that the folder was created by 'Graph Explorer' app and currently `childcount` is zero.
Ok so that's pretty sweet. With this single request I have a personal folder created for me in the user OneDrive. Isn't it a perfect place to save user defined data?

Ok so lets see how to do that.
In order to add a new .json file with some data we need to run a PUT request

```
https://graph.microsoft.com/v1.0/me/drive/special/approot:/{YOURFILENAMEHERE}.json:/content
```

and in the request body we need to provide some JSON structure string like

```
{"data":"test"}
```

As a result we see a new file added to the catalog with your json object. Also we may use the same request to update the data and since it is JSON we may change the data schema how we want quite dynamically. Adding new properties becomes easy.

![putRequest](images/putRequest.png)

Ok so now lets see how to get our saved data. For this we need another GET request:

```
https://graph.microsoft.com/v1.0/me/drive/special/approot:/{YOURFILENAMEHERE}.json
```

In the response section you should see `@microsoft.graph.downloadUrl` property.

![getData](images/getData.png)

Click on that link and see what happens

![downloadFile](images/downloadFile.png)

… ye our JSON file is downloaded. In the app we may use this approach to get the `.text()` from the response and parse the JSON object back to our model. So in general in our app we will actually need two steps (two requests) to retrieve the data.

There you have it. With a couple of simple requests I was able to create a folder for may data, save it as a .json file in the user OneDrive apps personal folder, and finally get the data back. If only there was some ready to use Spfx sample with some kind of library abstraction that does all that with simple *saveData()*, *getData()* methods, right? Well lucky for you, not that long ago I added a new sample in the *'pnp/sp-dev-fx-webparts'* repo with and Spfx library component that does all this logic for you and a simple webpart which just uses the methods get/save our json object. If you are interested take a look at [react-save-to-onedrive-app-personal-folder sample](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-save-to-onedrive-app-personal-folder).

![manageDataLibraryMethods](images/manageDataLibraryMethods.png)

Before you start creating an Spfx solution that uses this approach there are two things we need to remember.
First one, and this is quite obvious, as we are using MS Graph here, our webpart/library will need to request *webApiPermissionRequests* for *Sites.ReadWrite.All* scope which we may add in the *package-solution.json* config. Then of course, after the app is deployed we need to approve this permission request in the SharePoint admin web api management page.

Second one is not that obvious at first but is quite logical. As the Graph request creates the application folder for us we don't have control over the name. As a result of that each Spfx solution will save it's files in the same place (same folder), which name will be *'SharePoint Online Client Extensibility Web Application Principal'* so it would be a good idea to first create a subfolder for your current solution and store the .json file there. That way we may avoid future problems if we have two (or more) Spfx solutions which save data as .json files with the same name (Saving the data from one Spfx webpart would completely overwrite the data saved by the other one).

![subFolders](images/subFolders.png)

## So what I actually learned after reading this?

Not sure. Probably if you've been working with Spfx for some time now you already know this approach or already have all the needed skills to use this. But if you haven't used this approach I strongly encourage you to give it a shot. Saving data in user application personal OneDrive folder is a pretty sweet approach which sometimes may be a perfect fit for your solution so it’s good to be familiar with this method
