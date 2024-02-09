---
title: "Modern SharePoint list formatting"
date: 2021-02-12T06:56:00-05:00
author: "Luise Freese"
githubname: LuiseFreese
categories: ["Community post"]
images:
- images/daniel-cheung-zky0BmMT5m8-unsplash.jpg
tags: ["SharePoint", "List formatting"]
type: "regular"

---

This article shall give you guidance and inspiration on how to turn your
classic boring lists into interactive modern list experiences, which
will wow your users, let them get information at first sight, and
increase overall productivity. This post is not about the Microsoft 365
list templates; I will cover them in one of the next blog posts.

If you never heard anything about modern SharePoint list formatting,
don't worry; I will guide you through this.

![daniel-cheung-zky0BmMT5m8-unsplash.jpg](images/daniel-cheung-zky0BmMT5m8-unsplash.jpg)

## Why would we use SharePoint lists

First things first: Why should we use SharePoint lists and not use - for
instance - an Excel spreadsheet? Because we don't need to hide
information in cascading folders, that should be at the user's
fingertips. The beauty of lists lies in their simplicity and flexibility
to organize work and track the information that matters most to our
businesses.

Creating, sharing, and tracking lists is easy and available on any
device; everyone stays in the loop, and we can use lists for all kinds
of purposes like tracking issues, assets, routines, contacts, inventory,
and more. Lists can easily be customized to make them visually more
appealing.

## How can we turn on modern experience

Now that we are teased into modern lists and libraries in SharePoint,
it's time to turn on modern experiences. We can do it like this in the
classic experience:

-   select **Library Settings** or **List Settings** on the ribbon
-   select **Advanced settings** and select **List experience**
-   select **New experience**
-  save with **Ok**

### How can we change the look and feel of a list in the UI

Lists can contain different columns, and each column has a certain
column type, depending on the kind of value we want to store in that
column like text, numbers, dates, choice, persons, locations, links, or
images. As lists can contain much information, its brilliant if we
emphasize crucial parts by formatting them in a way that they are

-   easier to read
-   give a grasp on what is going on
-   are mobile-friendly

Already built-in, we will find options to format columns and views.
Formatting a view means modifying the way the entire list is displayed.
Formatting a column means changing the way this particular column looks
like.

![list-formatting-create.png](images/list-formatting-create.png)

 
Formatting Views

-   We can change the format view
 

-   and also display a gallery view

![list-formatting-formatgallery.png](images/list-formatting-formatgallery.png)

#### Formatting columns

-   If we want to change the column's appearance, we can do that very
    end-user-friendly directly in the UI:

![list-formatting-formatcolumns.png](images/list-formatting-formatcolumns.png)

 and even with rules like if - then - else:

![list-formatting-formatrules.png](images/list-formatting-formatrules.png)
 
### How can I apply conditional formatting, aka rules

Rules are a powerful feature to determine how a column should look like.
Let's say we want to apply a background color depending on a number
value. If the number is below 30, the field should be red; between 30
and 70, it should yellow, and above 70, it should be green. Let's see
how this looks like:

![list-formatting.gif](images/list-formatting.gif)

### How can we change the look and feel of a list with JSON

Sometimes, even if those options are already cool, we need some more
flexibility.

![whatif.jpg](images/whatif.jpg)

There is a way to format both columns and views beyond what is already
offered, as seen above. Perhaps you might have noticed the little
link **Advanced mode**? This is where we will find the cool tools to
play with!


![advanced-mode.png](images/advanced-mode.png)

This field expects you to put some JSON code in it to format this
column. If you never heard about JSON, you can quickly get started
with [Intro to
JSON](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/introduction-to-json/ba-p/2049369) by
Bob German, [this video](https://www.youtube.com/watch?v=iiADhChRriM),
or you can learn more
at [w3schools](https://www.w3schools.com/js/js_json_intro.asp).

## Samples

We will browse to the [Microsoft 365 PnP List formatting repository on
GitHub](https://github.com/pnp/sp-dev-list-formatting) and open the
folder `column samples`. In here, we will find free-to-use samples to
make our lists look fantastic.

Instead of having a list like this:

![example list-BEFORE.png](images/example list-BEFORE.png)


we can now look at a list like that:

[![example list.png](images/example list.png)

### How can we apply a sample?

-   Get familiar with the samples that are available on GitHub
-   regularly check for new ones / pin the repo
-   select the one that is interesting for you
-   read the `readme.md` file to know the requirements for your column.
    Some samples only work with choice, text, or number columns
-   open the JSON file
-   copy the code to your clipboard
-   go to your SharePoint list
-   go to column settings \--\> format this column
-   select  **Advanced mode**
-   paste the code
-   click **Save**


![formatsplist.gif](images/formatsplist.gif)
 

One more example how amazing a list can look like? I run a
the [PimpYourOwnDevoce.com](https://pimpyourowndevice.com/) sticker
store together with [Elio Struyf](https://www.eliostruyf.com/) and we
use a SharePoint list as our inventory ([Elio blogged about the whole
architecture
here](https://www.eliostruyf.com/running-online-store-powerplatform-azure/).
With [this
sample](https://lists.handsontek.net/format-image-column-preview-microsoft-lists-sharepoint/) we
can hover over our images to have a big preview:

![listformat-pyod.gif](images/listformat-pyod.gif)

That's
it!!

We will find [view
samples](https://github.com/pnp/sp-dev-list-formatting/tree/master/view-samples) in
the same GitHub repository.

## Want to learn more?

You can find helpful resources to learn more here:

-   [aka.ms/m365pnp](https://aka.ms/m365pnp)
-   [Microsoft 365 PnP List formatting repository on
    GitHub](https://github.com/pnp/sp-dev-list-formatting)

Have fun and happy Modern SharePoint list formatting

- *#SharingIsCaring ❤*

PS: Did you like this post? [I wrote even more about list
formatting](https://m365princess.com/how-we-use-sharepoint-list-formatting-and-power-automate-at-pyod-to-ease-our-marketing/)


*First published on [m365princess.com](https://m365princess.com)*
