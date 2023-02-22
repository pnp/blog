---
title: "To write code comments or not, it should not be a question"
date: 2021-03-02T08:47:00-05:00
author: "Elio Struyf"
githubname: estruyf

categories: ["Community post"]
images:
- images/comments1.png
tags: []
type: "regular"
---

Comments, just do it. I write this post because I read a couple of
articles, and messages on social platforms about stop using comments in
your code. In some cases, there is good reasoning behind it, but even
with this reasoning, I believe that comments are too valuable for your
DEV team


To start this article, I want to tell you that using comments or not in
your codebase is an opinion. There are always PROs and CONs with
everything you do or use. I also want to point out that people saying
not to use comments are not wrong or right. They have good intentions
and believe why they think comments should not exist in your code. For
instance, they want to highlight that it is essential to write clean
code, invest more in better documentation, less code smells, and many
more reasons.


I agree that we need to make our code better, write better
documentation, and do more end-to-end testing, but comments have no
impact on these points. They might even improve some of these points.


## Comments == Clean Code 

Writing comments in your code does not mean that your code cannot be
clean.

What is clean code? Clean code is yet again an opinion. It is like when
you ask a kid to clean their room. Two minutes later, they tell you it
is completed. When you go to their room, they put everything in a box.
For them, that is cleaning, but is it for you? Maybe you like that all
of their stuff is sorted in different boxes.

When you write code, the first intent should be to write it so that
everyone can understand it. Sometimes you implement the functionality so
that you need to remind yourself why you did it or tell someone else. If
you would not do it, it can lead to bugs later on in the process, when
someone would refactor the code.


By not writing comments, you make the assumption everyone else is on par
with you. That would be so great, but this is far from the truth.


**Important**: Never assume anything


I still know when C# introduced Linq or Lambda expressions. It was very
easy to refactor all your loops to use this new way of writing your
code. Instead of 10 lines, you ended up with two lines. Incredible, you
might think, but many developers did not even know what was happening.
It was too new, and some developers were using tools to do the
refactoring of this. At that time, in the company I was working in, we
decided to educate everyone before refactoring all the code to use it.
Once everyone understands how it works, we could think about starting to
use it.

Once everyone understood it, we also started commenting when we
refactored these lines. Everyone in the team indeed understood it, so
what is the point? Well, new developers are joining the team.

Another good reason from [Wassim
Chegham](https://twitter.com/manekinekko/status/1365425869909549062 "Link to the tweet of Wassim Chegham")

![comments1.png](images/comments1.png)



## Comments != bad code 

Comments cannot fix bad code or bugs. This statement is something I read
as well in one of the articles. I agree that comments cannot fix bad
code, but what is the reason for the bad code, and what is bad code?

Again, it assumes that the other developer has the same skills as you.

What if a junior developer in your team wrote the code?

If there were comments, you could see where she/he was after. Show the
person how to write the particular code more solidly. Or teach them why
you think this is bad behavior. We were not perfect the first time when
we were writing code, and still, each day, we learn new things
ourselves.

It might even be so that the comments will help you fix the bug, but the
comments will not create the bug. 

## Comments lead to more productivity 

Many believe that comments lead to noise in the codebase, but is this
actually true?

I Believe that having comments in the code is beneficial for
productivity. Imagine if you do not understand a part of the logic or
why functionality was implemented in a particular way.

Having no comments or references, you might need to go through the whole
code step by step to understand the person's thoughts and
implementation. Another option would be to call the person to clear
things out, but two people are less productive during that call.

## Comments are a way of communication 


Communication in your team is crucial. A great team relies on good
communication.

Comments are a way to communicate to other developers to give more
information about how a particular functionality is implemented.

## Challenges 


Comments also come with a couple of challenges, which I believe are a
way of working or guidelines in your team.

### [Outdated comments] 

What do you do when you implement a breaking change? Do you leave your
documentation untouched?

You will have to do an update to your documentation. The same goes for
your comments. When you refactor code, you will have to update the
comments or remove them if it does not make sense anymore.

Updating your comments is good developer behavior.

### Over-documenting 


I also read that many think you need to document in multiple locations
when you are writing comments. Comments are not documentation.

**Documentation**: material that provides official information or
evidence or that serves as a record.

Comments will not serve as the official information about how your
solution works or how you can use it.

**Comments:** an explanatory note in a book or other written text.

1.  Do not write comments for having more lines of code.
2.  Do not write comments to document your code.
3.  Write comments if it makes sense to write them. For instance, to
    prevent someone else from writing the same mistake.
4.  Use them to explain the \`why\`, not the \`what\`.

### Comments create noise in your code 

In my opinion, it also creates structure. It let your eyes rest. Take a
break. For me, line breaks are even more important to add to your code
and the number of code lines.

I have a hard time focusing on code when there are too many lines in one
file, hardly any line breaks, and no comments. When this is the case, it
feels like I am on a boat and get a bit see sick. The reason for this is
due to my astigmatism, also the reason why I am wearing glasses.

As these lines of code might feel noise to you, to me, they give my eyes
a break. Let me focus on the next block of code.

## Why should you comment? 

The most crucial reason to comment is for yourself as this will help the
future you from understanding your own code.

The next reason is to help others understand you. Suppose an employee
takes over a project from you or enters your team. It will make their
lives easier. Or when you do a handover when leaving the company, the
person sill not have any ways to contact you anymore. Would you like it
that you enter a codebase where you do not understand any of the written
logic?

## Commenting tips 

-   KISS: Keep it short and simple - you do not need to write a book.
-   Do not comment-out lines of code. During debugging/testing, this
    might happen, but make sure not to check in these lines. This
    behavior leads to code smells. Be sure your code lives inside
    source-control. That way, you do not have to worry about a deleted
    line of code. The main reason why this behavior happens is not to
    lose that one precious line of code.
-   Write code you understand so that you do not always need to comment.
-   Explain the *why* not the *what*.
    -   If you need to explain the *what*, in many cases, it is too
        difficult to understand. Try to simplify, if not possible, you
        can comment. An example could be the screenshot from above.
        
## Best of both worlds 

There is a solution for everything. Almost everything can be solved by
code. If you are a person that does not like to see comments, I have
created just the VSCode Extension for you. With the [Hide
Comments](https://marketplace.visualstudio.com/items?itemName=eliostruyf.vscode-hide-comments "VSCode Hide Comments Extension") extension,
you decide if you want to show or hide the comments for the project.

![comments2.png](images/comments2.png)
