---
title: "Understanding Data Connectors with Microsoft Power Apps"
date: 2022-06-06T10:56:00-04:00
author: "Favour Adekunle"
githubname: Favour-dgreat
# don't change
categories: ["Community post"]
# link to the thumbnail image for the post
images:
- images/banner.webp
# don't change
tags: ["Power Apps"]
# don't change
type: "regular"
---

In today's article, I will be looking at working with Data Connectors while building with Microsoft Power Apps. 

## What are Data Connectors?

Data is very important while building every native application, this is because in every application, it is either you are requesting/fetching data, sending data, or perhaps doing both. And while building applications with Microsoft Power Apps, there is no difference. 

In very clear terms, "Data Connectors" connects or communicates with the data source in every power app. Data is stored in a data source, and you bring that data into your app by creating a connection.

In Microsoft Power Apps a connector may provide tables of data or actions. Some connectors provide only tables, some provide only actions, and some provide both. Also, your connector may be either a **standard or custom connector**.


### Popular Connectors used in Microsoft Power Apps


![Popular Connectors used in Microsoft Power Apps](images/banner.webp)


### Standard and Custom Connectors

Standard Connectors are connectors provided by Power Apps for many commonly used data sources. If Power Apps has a standard connector for the type of data source that you want to use, you should use that connector, those are what are referred to as Standard Custom Connectors.

The image above showing popular connectors are all Standard Connectors. 

But in a situation where you want to connect to other types of data sources, such as the one you built, then they are referred to as Custom Connectors 

Check out this article for more on  Custom Connectors - [Register and use custom connectors](https://docs.microsoft.com/powerapps/maker/canvas-apps/register-custom-api)


## Connecting to Microsoft Dataverse

Microsoft Dataverse lets you securely store and manage data that are used by business applications. 
Data within Dataverse is stored within a set of tables. A table is a set of rows (formerly referred to as records) and columns (formerly referred to as fields/attributes). Each column in the table is designed to store a certain type of data, for example, name, age, salary, and so on.

Now with the understanding of the Dataverse let us get into this codelab!

## Building a simple record-keeping app with Google Sheets (a Standard Connector):

1. [Sign in to Power Apps](https://powerapps.microsoft.com) If you don't already have a Power Apps account, click the Start Free button. 

![Power Apps HomePage Screenshot](images/image1.png)

2. After successful sign in to Power Apps this is what you should have now! 

![Power Apps Screen after successful sign-in](images/image2.png) 
Click on the Dataverse card. 

3. You should have this screen now, showing previous connections. Then you click on New Connection

![PowerApps Connection screen](images/image3.png)

4. If you followed the previous step properly, you should have this now, then click on Google Sheets and authenticate with your Google account. 

![google sheet connection power pages screenshot](images/image4.png)
Now you choose a dataset, from a set of previous google sheet documents or perhaps you search for the one you have in mind just as I have done here. 

5. The next option is to choose a table or create a new one. 

![Power Pages Connection sheet](images/image5.png)

6. And finally you should have a very simple app for you with the data from the table you chose or created. Just as I have here too. 

![App screen](images/image6.png)

That is the end of this codelab and hope you were able to follow it properly. 

I will also be ending this article here now, leaving you with resources for further study. 

## Resources

1. [Overview of connectors for canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/connections-list)
2. [Use custom connectors in a Power Apps canvas app](https://docs.microsoft.com/learn/modules/use-custom-connectors-in-powerapps-canvas-app/)
3. [Microsoft Dataverse Documentation](https://docs.microsoft.com/powerapps/maker/data-platform/)
4. [Use custom connectors with the timeline control](https://docs.microsoft.com/powerapps/maker/model-driven-apps/custom-connectors-timeline-control)

So concluding now, in this article we understood what are Data connectors, Popular connectors used in Microsoft Power Apps, Standard and Custom connectors, Connecting to Microsoft Dataverse and finally had a codelab that taught us how to Connect or Build an app with data gotten from Google Sheet, which is an example of a Standard Connector. 

Thank You. 
