---
title: "Microsoft Lists: How to increase the columns available for calendar view formatting"
date: 2023-10-13T00:00:00-00:00
author: "Tetsuya Kawahara"
githubname: tecchan1107
categories: ["Community post"]
images:
- images/how-to-increase-the-columns-available-for-calendar-view-formatting.png
tags: ["Microsoft Lists", "SharePoint"]
type: "regular"
draft: false
---

## Introduction

Microsoft Lists allows you to create a calendar view and color-code each item.

![screenshot of the calendar view](./images/calendar-view.png)

However, the columns you want to use for color coding may not appear in the formatting screen. This is because the column you want to use for color coding is not included in the calendar view.

![formatting screen before setting view settings](./images/formatting-screen-before-setting-view-settings.png)

So, the following is a method to change the view settings and increase the columns available for use in the calendar view formatting.

## How to increase the columns available for calendar view formatting

To increase the columns available for a calendar view, you must add columns to the view for use in calendar view formatting. There are two methods for adding columns to the view: one is through the "Edit View Columns Panel" , and the other is through the "Edit View Screen"

### Method 1: Adding Columns via the "Edit View Columns Panel"

1. Open the Calendar view in Microsoft Lists
2. Select on the name of the view displayed in the command bar > Select **Add or remove fields**
3. Select the columns to be used in the formatting and put a check mark
4. Select **Apply** button

    ![edit view columns panel](./images/edit-view-columns-panel.png)

### Method 2: Adding Columns via the "Edit View Screen"

1. Open the Calendar view in Microsoft Lists
2. Select the **⚙** icon > Click **List settings**
3. Select on the view name of the calendar view in Views

    ![list settings screen](./images/list-settings-screen.png)

4. Select the columns you want to use for formatting from the list of columns displayed in the Columns section
5. Select **OK** button

    ![edit view screen](./images/edit-view-screen.png)

This completes the settings. When you open the formatting screen, the columns you selected in the Edit View screen will be displayed as available options for color-coding!

![formatting screen after setting view settings](./images/formatting-screen-after-setting-view-settings.png)

## Additional notes

- Method 1 is a new method and may not yet be deployed and available to some of your tenants.

## References

- [List Formatting Samples](https://pnp.github.io/List-Formatting/)
- [Formatting syntax reference | Microsoft Learn](https://learn.microsoft.com/sharepoint/dev/declarative-customization/formatting-syntax-reference)
- [Format calendar view to customize SharePoint | Microsoft Learn](https://learn.microsoft.com/sharepoint/dev/declarative-customization/view-calendar-formatting)
- [Microsoft Lists Calendar Color Coding with View Formatting | YouTube](https://www.youtube.com/watch?v=QkHQs1HX-eE) - [April Dunnam](https://twitter.com/aprildunnam) | @aprildunnam
- [📆How to create a modern and colorful calendar view in SharePoint | YouTube](https://www.youtube.com/watch?v=q-8BzgXEwGk) - [Giuliano De Luca](https://twitter.com/DeLucaGiulian) | @DeLucaGiulian
- [SharePoint Library - calendar view conditional formatting | YouTube](https://www.youtube.com/watch?v=CWS8bMoYTys) - [Ami Diamond](https://twitter.com/ami_diamond) | @ami_diamond
