---
title: "Preparing for Dark Mode - Model-Driven App Choices"
date: 2024-02-05T08:00:00-00:00
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

[Dark mode for model-driven apps](https://hackingpowerplatform.com/dark-mode-for-microsoft-dataverse/) is not officially available, but can be experimented with now by adding the following URL flag with the new look enabled:

```
&flags=themeOption%3Ddarkmode
```

[Megan Walker's blog post](https://meganvwalker.com/grid-components-in-model-driven-apps-d365/) shows how choice colours are set up and used in model-driven app views. But, how will dark mode impact this?

Potentially it could make some colors difficult to read if light colours are used:

![Pastel colours](images/pastel.png)

In order to make choices readable in both light and dark mode, a mid-range colour is better:

![Mid range colour](images/mid-range.png)

There are some special cases that need to be taken into account:

- White text doesn't show very well against a yellow background, so a darker shade is needed:

![Darker shade of yellow](images/yellow.png)

- Black text doesn't show very well against a blue background, so a lighter shade is needed:

![Lighter shade of blue](images/blue.png)

This gives:

![Balanced colours](images/balanced.png)

I've found that it takes a number of iterations to get a good balance over both modes.
