---
title: How to contribute to this blog
date: 2022-05-03T09:00:26.767Z
author: Luise Freese
githubname: LuiseFreese
categories:
  - Community post
images:
  - images/clark-tibbs-oqStl2L5oxI-unsplash.jpg
tags: null

type: "trending"
slug: contribute-blog
---


## Everyone's voice matters!

We want to publish your content on all things you build with code, low-code, no-code on and around Microsoft 365. This blog is backed by a GitHub repository and all contributions are done by Pull requests.

## extensive guidance on how contributing works

If you feel like you need some more support with that, you can

* Read the full [contributing guide](https://github.com/pnp/blog/blob/main/CONTRIBUTING.md) (with step-bt-step instructions)
* Sign up for our [Sharing is Caring sessions](https://pnp.github.io/sharing-is-caring/), where we provide you with hands-on guidance on how to use GitHub, submit samples, contribute to documentation and more.

## tl;dr - how to guidance for experienced GitHub users

If you are already familiar with GitHub, please follow this high-level overview:

1. Fork this repository <https://github.com/pnp/blog>
2. Create a new branch that matches the article name that you want to write
3. In the **content/post** folder, create your own folder (you may use the title of your post as the name of the folder, use `-` (dash) instead of ` `  (space))
4. In the newly created folder add an `index.md` file with your article
5. Insert metadata at the top of this file and adjust with your values:

```yml
---
# this is the title
title: "this is the title of your blog post"
# this is the publishing date of your article, usually this should match "now"
date: 2022-04-25T08:40:00-04:00
# This is your name
author: "your Name"
# This is your GitHub name
githubname: yourGitHubUserName
# Don't change
categories: ["Community post"]
# Link to the thumbnail image for the post
images:
- images/myImage.png
# don't change
tags: []
# don't change
type: "regular"
---
```

6. Create a new folder `images` in your article's folder. In the images folder you may save any image/graphic which may be used in your article
7. Pull request your changes, targeting the `main` branch
8. A maintainer will review, so that your article is published soon

## Need help? Have questions?

You can comment below! We will reach out to you as soon as possible!

_Sharing is Caring_ 
