---
title: "Preparing for Dark Mode - Model-Driven App Choices"
date: 2025-02-09T08:00:00-00:00
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

![thumbnail](images/thumbnail.png)

## Issues

Light mode has a dark grey text colour #242424 rather than black #000000.

Current dark mode has white text colour #FFFFFF

Contrast checker such as https://webaim.org/resources/contrastchecker/ would just provide WCAG AA pass for colours at bottom (contrast ratio 4.5:1 or better) for both light and dark mode if black text was used rather than dark grey.

WCAG AAA required 7:1 or better, which is why pastel colours are preferred.

Possible ways forward:

1. Light mode has black text for choices, allowing colour selection for WCAG AA
2. Introduce different choice colours for light and dark mode, allowing WCAG AAA

## Dark Mode

Dark mode has become increasingly popular in software applications, providing a sleek and eye-friendly alternative to the traditional light theme. While it’s not officially available for model-driven apps, you can experiment with it by adding a simple URL flag. In this post, we’ll delve into the impact of dark mode on choice colours within model-driven app views.

## Caveats

Microsoft haven't released any information on how dark mode will work, so below is just experimentation. It may even be that Microsoft implement a light mode colour and separate dark mode colour.

## Enabling Dark Mode

In my [previous blog post on choice colours](https://pnp.github.io/blog/post/preparing-for-dark-mode-model-driven-app-choices/), for [dark mode in model-driven apps](https://hackingpowerplatform.com/dark-mode-for-microsoft-dataverse/) I looked at how to adapt choice colours to work with both light and dark mode. While it's not officially available yet, you can experiment with it by adding a specific URL flag to enable the new alternative look:

To enable [Dark mode for model-driven apps](https://hackingpowerplatform.com/dark-mode-for-microsoft-dataverse/) add the following URL flag to your model-driven app’s URL:

```
&flags=themeOption%3Ddarkmode
```

## Colour Readability in Dark Mode

### Pastel Colours

[Megan Walker's blog post](https://meganvwalker.com/grid-components-in-model-driven-apps-d365/) shows how choice colours are set up and used in model-driven app views. But how will dark mode impact this?

Potentially it could make some colours difficult to read if light / pastel colours are used:

![Pastel colours](images/pastel.png)

### Bright Colours

For optimal readability across both light and dark modes, bright colours are your best bet. These colours strike a balance, maintaining visibility in both modes:

![Mid-range colour](images/mid-range.png)

### Deep Colours

There are some special cases that need to be taken into account:

- White text tends to disappear against a yellow background in dark mode. To address this, choose a darker shade of yellow. It ensures that the text remains visible:

![Darker shade of yellow](images/yellow.png)

- Conversely, black text can get lost against a blue background. Opt for a lighter shade of blue to maintain readability. Finding the right balance ensures that your content stands out regardless of the mode:

![Lighter shade of blue](images/blue.png)

## Achieving Balance

This gives:

![Balanced colours](images/balanced.png)

Striking the right balance between light and dark mode requires iteration. Test your colour choices thoroughly to ensure they work well in both scenarios. A well-thought-out colour palette enhances the overall user experience.

|Colour|Contrast radio white text|Contrast radio black text|
|--|:--:|:--:|
|Red #ED665F|4.51|4.65|
|Yellow #80760C|4.65|4.51|
|Blue #127ABA|4.51|4.64|
|Green #268721|4.59|4.56|
|Purple #A54ADE|4.53|4.63|

## Conclusions

In summary, while dark mode introduces new challenges, thoughtful colour selection can create a harmonious and visually appealing app. Experiment, iterate, and find the sweet spot that works for your model-driven app!
