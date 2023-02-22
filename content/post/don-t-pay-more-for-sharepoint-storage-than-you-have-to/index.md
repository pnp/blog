---
title: "Don't pay more for SharePoint Storage than you have to :-)"
date: 2022-02-03T12:35:00-05:00
author: "Kasper Bo Larsen"
githubname: kasperbolarsen
categories: ["Community post"]
images:
- images/VersionHistory.png
tags: ["SharePoint"]
type: "regular"
---


Even though most of us likes Microsoft, on some days more than others, there are no reason why we should pay more than necessary.

As you might know each tenant is born with a 1 TB SharePoint Storage allowance. On top of that you get 10 GB per licensed user.

Unless you already have a retention policy or similar in place that will delete the content of your SharePoint Site Collections as the time goes by, you will eventually run out of free SharePoint Storage. At the time of writing additional SharePoint Storage is available in the admin center at $0.20 per GB per month.

First of all it is important to know how the total SharePoint Storage is calculated. In the screen shot below you see the version history of a fairly typical file. It has been updated and reviewed a few times and currently we have a total of 25 versions.

It has been difficult to find any documentation from Microsoft confirming this, but as far as I know Microsoft calculate the Storage for this file as each version multiplied by its size. So in this case our file is roughly 25 \* 39 MB towards the Storage allowance. That is a lot. 

![thumbnail image 1 of blog post titled Don't pay more for SharePoint Storage than you have to ](images/VersionHistory.png)

So what can we do about it?

As usually there are a fair number of options:

A) Set up a Retention policy that will delete some of the content. For some organizations this is not an option as per their Governance policies or fear that the policy might delete too much. 

B) Reduce the number of document versions saved  ( the default is 500 major versions). This will  often require that you have some kind of provision tools in place that will change the default value. The downside of this option is that you might be in a situation where you wish to restore an older version, but that version does not exist anymore.

C) Monitor the Site Collections for activity and enforce that the Owners of a Site Collection deletes any non essential documents once the Site Collection is no longer active. This Governance approach might work in some organizations, but I have yet to see it.

D) Monitor the Site Collections for activity and once it is no longer active the Archiving process starts. Depending on the requirements that could be something like:    

![thumbnail image 2 of blog post titled Don't pay more for SharePoint Storage than you have to ](images/archiveprocess.png)

Step number 2 can be omitted but is there to ensure that it will be possible to locate any version of a given document should the need arise.

The reason for not deleting the entire Site Collection once the documents have been copied to cheaper storage is to ensure that the organization will still able to see the Site Collection and the content. Often the Site Collection was used in a project or similar and the organization needs to store that fact that this project once existed.

There is also possible to extend the process by deleting the Read Only Site Collection after a few months or years.  

If you are thinking "Well this might save us some SharePoint Storage, but I have no idea how to verify it", the PnP Script Samples is the place to go:

[storage savings report](https://pnp.github.io/script-samples/spo-generate-sp-storage-savings-report/README.html)

This script will output a report showing how much Storage you can save per site collection.

## SharingIsCaring

![thumbnail image 3 of blog post titled Don't pay more for SharePoint Storage than you have to ](images/parker.png)
