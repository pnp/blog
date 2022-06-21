---
title: "Community Sample: React FAQs webpart "
date: 2022-04-04T07:21:00-04:00
author: "Arun Kumar Perumal"
githubname: arunkumarperumal
categories: ["Community post"]
images:
- images/FAQWebpart.png
tags: ["SharePoint framework (SPFx)"]
type: "regular"
draft: false
---

Frequently Asked Questions (FAQ) is a useful addition to pages where you need to display common requests. The FAQ Web Part can be added to a page as a straight list of questions and answers or a series of grouped questions and answers when the need for a more organized approach is required.

The FAQ Web Part is not only for questions and answers — it can be used for any content that lends itself to expanding/collapsing functionality, such as keywords and definitions or expanding on short phrases.

In my latest community sample, I built an SPFx web part to provide an ability to display FAQs as Accordion or Tab.

Here is how it looks:

![FAQ Web Part](images/FAQWebpart.png)

In this article, I will share details on how to configure the FAQ webpart.

Below is the default screen of the FAQ webpart, when added to a SharePoint Online page.

![Default Screen](images/Default-Screen.PNG)

FAQ webpart uses PropertyFieldCollectionData which provides page Content Editors the ability to manage the content of the web part within the web part properties.

Let's see how to manage the FAQ webpart

## Changing Title of the web part

Below are the steps to update the Title of the FAQ Web part

1. Edit the webpart.
1. Select the default text and start typing the text needed as Title for the web part.

Check below image for more details.

![Change Title](images/Updating-Title.gif)

## Adding/Updating Categories

Below are the steps to update the Add/Update Categories of the FAQ Web part

1. Edit the webpart.
1. Select "Configure Categories" in the web part properties.
1. Property pane is open providing ability to add/update categories.

Check below image for more details.


![Updating Categories](images/Updating-Categories.gif)

## Adding/Updating FAQs

Below are the steps to update the Add/Update FAQs of the FAQ Web part

1. Edit the webpart.
1. Select "Configure Faqs" in the web part properties.
1. Property pane is open providing ability to add/update faqs.

Check below image for more details.

![Updating Faqs ](images/Updating-FAQs.gif)


## Search FAQs

Below are the steps to update the Add/Update FAQs of the FAQ Web part

1. Enter the search text in the search box.
1. Web part automatically filters and shows the FAQs grouped by Categories.

Check below image for more details.

![search faq ](images/search-faq.gif)

## Type Options

FAQ webpart has the ability to display the FAQS as an Accordion or Tab. Below are the steps to change the display type of the FAQ Web part

1. Edit the web part. Enter the search text in the search box.
1. Choose the Type option in the web part properties as either "Accordion" or "Tab"

Check below image for more details.

![Type Options ](images/Type-Options.PNG)


Check below image to see how to change the type from Accordion to Tab

![Change type from Accordion to Tab ](images/change-type-from-Accordion-to-Tab.gif)

Check below image to see how to change the type from Tab to Accordion

![Change Type Tab to Accordion ](images/Change-type-from-Tab-to-Accordion.gif)

## Changing the Sort Order for FAQs


![Changeing the sort order](images/Changing-the-sort-order.gif)

## Source Code

You can find the full source code and how to install
it [react-faqs](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-faqs).
 
Thanks for reading. Hope you find this article useful
