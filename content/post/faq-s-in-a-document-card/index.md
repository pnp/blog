---
title: "FAQ's in a Document Card"
date: 2021-04-14T06:23:00-04:00
author: "Sam Collins"
githubname: SamC148
categories: ["Community post"]
images:
- images/updateFAQgif.gif
tags: ["SharePoint", "SharePoint framework (SPFx)"]
type: "regular"
---

I recently had a need for a web part for a frequently asked questions
list that was a bit more interactive than what I could find on the
internet. So I decided to build one and once it was finished I thought
it was a great resource to share.
 
Here's what the web part looks like and an idea how it functions

![updateFAQgif.gif](images/updateFAQgif.gif)
 

TLDR: For a tutorial of how to build the whole thing from scratch check
out this video: <https://www.youtube.com/watch?v=oIr-rgGvUUk>
 

A main driver for creating this web part was wanting something that
didn't look like SharePoint or an intranet. I spent some time looking
for examples and inspiration from code samples, the Look Book, and
intranet examples but I felt like I kept landing on the same accordion
look and feel. Don't get me wrong, I appreciate the accordion, I've even
added it into my web part when you're viewing all questions under a
specific category -- but was this really my only option? So I started
looking at external sites and finally found something I thought was cool
enough to build and the react-docCard-faq idea was born!
 
Now that I had a general idea of my data (questions and answers) and
I've picked a layout I need to break out my questions into sub groups,
something to separate them out by. That's where the categories comes in,
questions are grouped into categories. But I wasn't finished there, what
if, you don't want to show every category. It could be that open
enrollment questions only need displayed around that time or you're
launching a new product and only want to highlight it for a short period
of time! So instead of always displaying every category in the FAQ list
you can select which categories you want to view from the property pane
when you add the web part to the page. 
Use cases: 

-   A site can host a single FAQ list and only display certain
    categories on specific pages.
-   Season change, Holiday's, Enrollment time -- all reasons you might
    want to change which categories (or how many) you're showing


 

Once I had the idea that you might want to *change *which categories are
showing and not just always display the same categories, the featured
toggle came in. Adding an additional boolean column let's us not only
select which questions will be showing in main display, but it makes it
incredibly easy for anyone managing the list (not the site) to add or
change which questions will display in the document card.
 

Why in the world did I do a document card for FAQ? A few reasons for the
specific design that includes so much white space. 
First, I wanted something that doesn't look like a standard
intranet/internal site. The layout gives a modern, professional feel
that could be on any external facing site. 
 

Second, not every department/group/team knows what to share on their
site or page but everyone needs FAQ's! Because you control how many
categories and questions are on the page, it can take up more or less
depending on how you lay it out. 
Third, it's a great way to drive adoption to your questions. Tired of
answering the same 3-6 questions over and over? Direct questions to your
SharePoint site where all the answers are! Added bonus, no one has to
wait on you to get back from vacation for an 1 sentence answer 
 
Lastly, it drives whoever's maintaining the list to keep it up to date.
It's not a set of boring questions and answers to go stale. With
category options, a featured toggle, and the ability to write beautiful
answers using rich text you're empowered to take your FAQ to the next
level! 
 
I hope I've inspired you to think outside of the box and get creative!
Code:
<https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-doccard-faq>
