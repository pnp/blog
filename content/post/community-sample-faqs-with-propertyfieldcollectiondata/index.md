---
title: "Community Sample: React FAQs webpart "
date: 2022-04-04T07:21:00-04:00
author: "Arun Kumar Perumal"
githubname: arunkumarperumal
categories: ["Community post"]
images:
- images/FAQWebpart.png
tags: []
type: "regular"
---

​​Frequently ​Asked Questions (FAQ) is a useful addition to pages where you need to display common requests. The FAQ Web Part can be added to a page as a straight list of questions and answers or a series of grouped questions and answers when the need for a more organized approach is required.

The FAQ Web Part is not only for questions and answers — it can be used for any content that lends itself to expanding/collapsing functionality, such as keywords and definitions or expanding on short phrases.

In my latest community sample, I built an SPFx web part to provide an ability to display FAQs as Accordion or Tab. 

Here is how it looks: 

{{< image alt="FAQ Web Part" src="images/FAQWebPart.png" >}}

In this article, I will share details on how to configure the FAQ webpart.

Below is the default screen of the FAQ webpart, when added to a SharePoint Online page. 

{{< image alt="FAQ Web Part" src="images/Default Screen.png" >}}

FAQ webpart uses PropertyFieldCollectionData which provides page Content Editors the ability to manage the content of the web part within the web part properties. 

Let's see how to manage the FAQ webpart
 
# Changing Title of the web part
Below are the steps to update the Title of the FAQ Web part 

1. Edit the webpart 
1. Select the default text and start typing the text needed as Title for the web part

Check below image for more details. 

{{< image alt="FAQ Web Part" src="images/Updating Title.gif" >}}


You can find the full source code and how to install
it [react-faqs](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-faqs).
 


Thanks for reading. Hope you find this article useful