---
title: "Preparing for Model-Driven Apps Dark Mode Icons - Improved"
date: 2024-07-08T08:00:00-00:00
author: "Alex McLachlan"
githubname: alex-mcla
# don't change
categories: ["Community post"]
# link to the thumbnail image for the post
images:
- images/thumbnail.png
# don't change
tags: [Power Apps]
# don't change
type: "regular"
---

In my previous blog post on how to implement [svg icons to work with dark mode for model-driven apps](https://pnp.github.io/blog/post/preparing-for-dark-mode-model-driven-app-icons/), I showed how to edit the SVG file to work in both light and dark mode using a SVG style. This method is used by many of the out-of-the-box Dynamics table icons.

However, there's a better way that's documented on learn.microsoft.com in [Change model-driven app custom table icons](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/change-custom-entity-icons):

    "Where possible, remove any hard coded fill color attributes and use the `currentColor` keyword to avoid contrast issues."

With a further reference to [Working with Scalable Vector Graphics (SVG) [in model-driven apps]](https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/image-web-resources#working-with-scalable-vector-graphics-svg).

The change is straightforward - it is standard practice to create icons with a black fill colour (#000000):

```XML
<path ... fill="#000000" ... />
```

This needs to be changed to:

```XML
<path ... fill="currentColor" ... />
```

Which gives the same result for light vs dark mode as the style approach:

![](images/updated-mode.png)
