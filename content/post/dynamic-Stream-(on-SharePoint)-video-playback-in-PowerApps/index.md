---
title: "Dynamic Stream (on SharePoint) video playback in PowerApps"
date: 2024-04-21T02:04:00-05:00
author: "Anand Ragav"
githubname: anandragav
categories: ["Community post"]
images:
- images/image10.png
tags: ["Power Apps", "Power Automate", "Stream on SharePoint"]
type: "regular"
---


The new Stream control in Power Apps lets you embed Microsoft Stream (on SharePoint) videos directly in your canvas app. To add a Steam video in your canvas app, you will need the embed URL of the video.

![Embed code for Stream video.png](images/image1.png "Embed code for Stream video")

But what if you need to display a playlist of videos from SharePoint in your PowerApp and let the stream player dynamically play a video in the list that a user selected?

The Unique ID and the URL needed for the new Stream control is not available in the SharePoint connector so that means the standard connector is not useful for that.

Thankfully, you can resolve this with Power Automate.

## Power Automate flow

Assuming you have a SharePoint document library or list for your videos, create a flow in Power Automate using the PowerApps trigger.

![A Power Automate flow.png](images/image2.png "A Power Automate flow")
 
Send an HTTP request to SharePoint to fetch the Unique ID besides other metadata needed for the playlist.

![HTTP request action.png](images/image3.png "HTTP request action")

Test-run the flow to verify the desired results in the outputs of the HTTP action. Copy the JSON from the Outputs.

![Copy JSON from HTTP action.png](images/image4.png "Copy JSON from HTTP action")

Parse the JSON from the body of the HTTP action. Use the copied JSON to generate the schema from a sample.

![Parse JSON action.png](images/image5.png "Parse JSON action")

With a select data operation step, build the data table that will then be used by the PowerApp to display the list of videos from SharePoint.

![Select data operation action.png](images/image6.png "Select data operation action")


Use the Respond to PowerApp action to send the results from the Select action to the PowerApp.
![Respond to PowerApp action.png](images/image7.png "Respond to PowerApp action")


The next step is to connect to this flow from the PowerApp and call the flow to execute either by using a button or the OnStart property of the app.

In your PowerApp, connect the flow.

![Connect the flow in the PowerApp.png](images/image8.png "Connect the flow in the PowerApp")

Add a button and in the OnSelect property add the PowerFx code shown below.

This code calls the connected Flow that returns a list of videos in JSON format, and parses this JSON into a table, iterates over this table to extract and convert necessary fields, and finally, store all these records in the VideoList collection.

![Button OnSelect in PowerApp.png](images/image9.png "Button OnSelect in PowerApp")


Display the results in the collection using a Gallery called VideoGallery.

Add a Stream control and set its StreamUrl property as shown below.

“https://<yoursite>.com/sites/TeamAllStars/_layouts/15/embed.aspx?UniqueId=” & VideoGallery.Selected.UniqueID

Now, when selecting a video item from the gallery the Stream control can dynamically play the selected video.

![Dynamic Stream playback in PowerApp.png](images/image10.png "Dynamic Stream playback in PowerApp")

Hope you find this post useful.

Hopefully, in the future Microsoft will enable the standard SharePoint connector to support Unique ID of Stream videos.
