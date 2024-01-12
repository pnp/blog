---
title: "Adding Custom Metadata Through a Content Pack in Learning Pathways"
date: 2021-02-18T07:46:00-05:00
author: "Emily Mancini"
githubname: eemancini
categories: ["Community post"]
images:
- images/eemancini_1-1613662523389.png
tags: ["SharePoint"]
type: "regular"
---

Learning Pathways is
a [customizable](https://learn.microsoft.com/office365/customlearning/custom_accessadmin)
on-demand learning solution in Microsoft 365. Learning Pathways offers - a
customizable SharePoint Online communication site (that may be used as a
training portal),

- easy provisioning from
the [SharePoint Look
Book](https://lookbook.microsoft.com/details/3df8bd55-b872-4c9d-88e3-6b2f05344239?source=default)
- the ability to make your own training playlists with
[custom
assets](https://learn.microsoft.com/office365/customlearning/custom_addassets)
- a [custom web
part](https://learn.microsoft.com/office365/customlearning/custom_whereiswebpart) to
surface training content across your SharePoint site collections,
- and
up-to-date Microsoft documentation for Microsoft 365
solutions

![eemancini_0-1613662523386.png](images/eemancini_0-1613662523386.png)

The information architecture behind Learning Pathways supports
structuring your playlists by category and subcategory. Within a
playlist, you may add custom assets (in the form of SharePoint site
pages) or use the content provided by Microsoft. For each playlist, you
may add additional information for the playlist title, description,
technology, subcategory, level, and audience. While you may add your own
subcategories to Learning Pathways, out of the box you cannot add new
categories or choices
within technology
level, or
audience.

![eemancini_1-1613662523389.png](images/eemancini_1-1613662523389.png)

Some organizations may find the existing choices do not support their
needs. To customize these fields, you will need to
create a custom content pack within GitHub and add the content pack to
your Learning Pathways instance.

## Deciding to Make a Custom ContentPack

There are two primary reasons an organization may decide to begin using
a custom content
pack:

1.  Edit the information architecture in Learning Pathways further than
    what is capable out of the box. As we discussed,
    there are some fields where you cannot add
    values.


1.  [Control the release of Microsoft's automatic content updates to
    Learning Pathways. Some organizations might want to review the new
    content releases to evaluate what is applicable to the organization
    before it appears in their Learning Pathways
    instance.

Please note, creating a custom content pack also
means you will need to submit a pull request from the
main Learning Pathways repo to your forked repo to take advantage of any
content updates. In layman's terms, you divided your
content from the Learning
Pathways original source so you
will not get the automatic content updates from Microsoft for new
docs.microsoft.com content.
You will instead need to complete
manual steps to get that content into your custom
content
pack.

### Pre-Work: Provision Learning Pathways

[Follow the docs.microsoft.com instructions
for [provisioning Learning
Pathways] ](https://learn.microsoft.com/office365/customlearning/custom_provision#to-provision-learning-pathways)

### Step 1: Fork the Learning Pathways Repo

Navigate
to [https://github.com/pnp/custom-learning-office-365](https://github.com/pnp/custom-learning-office-365)[ and select **Fork** in
the upper-right hand of the page. This will create an identical copy of
the Learning Pathways content in your own repository allowing you to
make customizations to the information architecture through editing the
JSON.

![eemancini_2-1613662523392.png](images/eemancini_2-1613662523392.png)

After you are done forking the repo, you will see your own copy of the
repo in the top left
navigation:

![eemancini_3-1613662523373.png](images/eemancini_3-1613662523373.png)

### Step 2: Turn on GitHub pages

Select **Settings** in
the top
navigation:

![eemancini_4-1613662523375.png](images/eemancini_4-1613662523375.png)

Scroll down the page until you see a header
for **GitHub Pages** . In the
Source dropdowns,
select **Main** and **docs** then
select **Save**
![eemancini_0-1613663078684.png](images/eemancini_0-1613663078684.png)

Upon saving, GitHub will bring you to the top of the page again. Scroll
down to ] **GitHub Pages**  once more
to copy the URL for your
GitHub
pages:

![eemancini_1-1613663087728.png](images/eemancini_1-1613663087728.png)

Follow the docs.microsoft.com instructions
for [adding a content pack to learning
pathways](https://learn.microsoft.com/office365/customlearning/custom_partnerguide_contint#add-a-content-pack-to-learning-pathways). When
adding the URL for your custom content pack, paste the URL from step
3, add **learningpathways** to
the
URL, and select **Save**. For
example:

[https://eemancini.github.io/custom-learning-office-365/learningpathways/](https://eemancini.github.io/custom-learning-office-365/learningpathways/)

This adds your forked copy of Learning Pathways as a tab in the site
page CustomLearningAdmin.aspx of
Learning
Pathways: ]

![eemancini_2-1613663101656.png](images/eemancini_2-1613663101656.png)

### Step 5: Edit metadata in GitHub

As of this step, your custom content pack is an identical copy of
Learning Pathways content as you have not made any edits in the repo.
Navigate
to `https://\[yourusername\].github.io/custom-learning-office-365/learningpathways/v4` to
begin making edits. Open the applicable language
folder, in this example we
will be working in **en-us**. In
this folder you will find 3 JSON files.
Select **metadata.json**

![eemancini_3-1613663112898.png](images/eemancini_3-1613663112898.png)

Explore the [metadata.json
structure](https://learn.microsoft.com/office365/customlearning/custom_partnerguide_contint#metadatajson-structure) for
more guidance on  how to edit the information architecture
within this JSON
file. If you are new to
JSON, [Bob German's Introduction to
JSON](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/introduction-to-json/ba-p/2049369) provides
an excellent overview for
beginners. [Watch an example
video](https://www.youtube.com/watch?v=dzqEI5NKQ2U&t=7m09s) of
editing the existing technologies field and adding new
ones.

### Step 6: Commit changes to main branch of your forked repo

After completing your JSON edits, scroll to the bottom of the page to
the section for **Commit
Changes** Add a title and description that clarifies
what edits you made and select **Commit
Changes**. Once you commit a change, your edits will
automatically appear in Learning Pathways. (Note: You may need to hard
refresh or clear your cache to see these
changes).

### Step 7: Add the web part to a page and filter to the content pack

Now that your custom content is added to Learning Pathways, you can
surface it by adding a Learning Pathways web part to a page. Follow the
docs.microsoft.com instructions on how to [filter to
the content
pack](https://learn.microsoft.com/office365/customlearning/custom_partnerguide_contint#filter-to-the-content-pack-in-the-web-part)


**Conclusion**

Whether you are creating a content pack to customize the metadata or
control the content releases by Microsoft, creating a custom content
pack is a powerful way to support your needs as long as you can support
manually pulling content from the Learning Pathways repo in the
future.
