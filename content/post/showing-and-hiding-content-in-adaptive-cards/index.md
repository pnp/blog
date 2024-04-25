---
title: "Showing and hiding content in Adaptive Cards"
summary: "In Adaptive Cards there are multiple ways to show and hide content depending on other content or conditions, or even user interaction. But despite that most of them is available since the version 1.2 (so quite early) it requires a bit of knowledge how to actually implement them."
date: 2022-02-09T03:31:00-05:00
author: "Tomasz Poszytek"
githubname: "tposzytek"
categories: ["Community post"]
images:
- images/image.png
tags: ["Adaptive Cards"]
type: "regular"
---

In Adaptive Cards there are multiple ways to show and hide content depending on other content or conditions, or even user interaction. But despite that most of them is available since the version 1.2 (so quite early) it requires a bit of knowledge how to actually implement them.

There are 3 major ways for showing and hiding content in Adaptive Cards:

1.  Action.ShowCard
2.  Action.ToggleVisibility
3.  Condition defined under "Only show when" property

Let's go now through each of them.

## Action.ShowCard

To use it first you need to add "ActionSet" element to the designer canvas and then select `Action.ShowCard` from the list of available options:

![thumbnail image 1 of blog post titled Showing and hiding content in Adaptive Cards](images/image.png)

Once that is done, define button's properties inside "Element properties" window, such as its title and id.

{{< notice "hint!">}}
To display the other card, that will be shown after clicking on the added button, double click it! It will trigger the hidden card to appear, so you can easily author its contents.
{{< /notice >}}

Next double-click the button, to display the hidden card and author its contents:

![thumbnail image 2 of blog post titled Showing and hiding content in Adaptive Cards](images/image-1.png)

Next, switch to "Preview mode" to see how the card is being shown and hidden after clicking the button:

![thumbnail image 3 of blog post titled Showing and hiding content in Adaptive Cards](images/image-2-1536x336.png)

{{< notice important>}}
If you add "Action.Submit" to the hidden card it will send data from all fields present from that card and "up" - so from all parents of that hidden card. The "Action.Submit" button on a top-most card will only send data from that top card.
{{< /notice >}}

![thumbnail image 4 of blog post titled Showing and hiding content in Adaptive Cards](images/E89C8BF5-4397-4694-944C-A7FBA7D86288.gif)

Data from cards is always submitted from parent to child cards.

## Action.ToggleVisibility

To use it first you need to add "ActionSet" element to the designer canvas and then select `Action.ToggleVisibility` from the list of available options:

![thumbnail image 5 of blog post titled Showing and hiding content in Adaptive Cards](images/image-3.png)

Next, the same as with ShowCard scenario, define properties of the added button.

{{< notice important>}}
Unlike with ShowCard, the ToggleVisibility requires you to do some work directly within the generated JSON payload of the card. There is no UI to configure it any other way.
{{< /notice >}}

Now add elements to the card that you want to show and hide after clicking the button. Then define their properties:

1.  **Id** \- it is absolutely required to define unique ids of the added elements. Ids are used to target elements and toggle their visibility.
2.  **Initially visible** \- define whether elements should be visible as the card is rendered, or hidden. Toggle will then either show them, or hide them. When you unclick the checkbox, element will be overlayed with a greyed pattern.

![thumbnail image 6 of blog post titled Showing and hiding content in Adaptive Cards](images/image-4-1536x397.png)
Now navigate to JSON payload and find ToggleVisibility button's definition. Add there the following code:

`"targetElements": [ "colon delimited list of elements' Ids to toggle" ]`

![thumbnail image 7 of blog post titled Showing and hiding content in Adaptive Cards](images/image-5-1536x701.png)

{{< notice important>}}
The only "downside" of that approach is in case you add an always visible submit button, then it will always send data from all fields even when they are hidden.
{{< /notice >}}

Last step is to test it. Switch to "Preview" mode and examine behavior of your card:

![thumbnail image 8 of blog post titled Showing and hiding content in Adaptive Cards](images/3F6CAEA8-5B83-47D1-A35D-98704C2C206C.gif)

## Only show when

This approach uses "[Adaptive Cards Templating Language](https://learn.microsoft.com/adaptive-cards/templating/language)". To be able to use it, first you need to define Data that will be bind with the card. And once you have the data, then you are able to create a condition that determines when an element should be visible:

![thumbnail image 9 of blog post titled Showing and hiding content in Adaptive Cards](images/image-6-1536x478.png)

You can use different types of comparisons, to both integer, dates, boolean or string data types.

{{< notice important>}}
 Unlike "Toggle", showing and hiding elements based on conditions is actually happening when a card is being rendered. As of today, _Data_ that card is using is only static, so it cannot be changed after the card is displayed. This means, that if a field is having a condition that prevents it from being displayed, even when it has a default value set, its value will not be submitted as long as the field is not visible.
{{< /notice >}}

Finally, enter "Preview" mode to see how your card behaves:

![thumbnail image 10 of blog post titled Showing and hiding content in Adaptive Cards](images/27642CAD-D34E-4EA8-9D10-AE4D0C440503.gif)

And that's it! Hope you will find this tutorial useful. If you have any comments, write them down below. Thanks!
