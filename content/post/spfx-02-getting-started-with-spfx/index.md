---
title: "Getting started with SPFx – Building your first extensibility for Microsoft 365"
date: 2023-01-03T08:00:00.000Z
author: Vesa Juvonen
githubname: VesaJuvonen
categories:
  - SPFx
images:
  - images/02-getting-started-spfx.png
tags:
  - Microsoft Teams
  - Microsoft Viva  
  - SharePoint
  - SharePoint Framework (SPFx)
type: regular
videos:
- https://www.youtube.com/watch?v=ijaJgc3J-iE
- https://www.youtube.com/watch?v=Cxx9MdjEiEw
- https://www.youtube.com/watch?v=6WTtjXP5yW4
- https://www.youtube.com/watch?v=5M3zDpgxIMs
- https://www.youtube.com/watch?v=FkFg32NSTM0
- https://www.youtube.com/watch?v=N-KowN-UwTM
---

[SharePoint Framework](https://aka.ms/spfx) (SPFx) is an extensibility model for Microsoft 365 enabling developers to build different kinds of extensibility for Microsoft Viva, Microsoft Teams, Outlook, Microsoft 365 app (Office), and SharePoint. SPFx has multiple benefits like automatic Single Sign On, automatic hosting in the customer tenant, reuse same code across the service and industry standard web stack tooling.

-	*You got me curious – how would I start using SPFx – how to get started?*
-	That is a great question. Let’s reference our getting started documentation and tutorial video series on learning how to get started

{{< notice note>}}
This blog post is part of the a month long SPFx series for January 2023. Each business day we'll publish a new blog post covering different aspects of the SPFx.

* Previous blog post in this series - [What is SPFx? – An extensibility model for Microsoft 365](https://pnp.github.io/blog/post/01-what-is-spfx/)
{{< /notice >}}


## SPFx – the basics of development

SPFx development happens using TypeScript which gives you great benefits compared to using vanilla JavaScript. Key advantage is the development time intelligence to support higher quality code. Development of SPFx solutions will happen locally from your own computer, but you can do direct debugging and testing your solution in the Microsoft 365 tenant.

Here are the steps to get started on building SPFx solutions within Microsoft 365:

1.	Subscribe to [Microsoft 365 Developer program](https://developer.microsoft.com/en-us/microsoft-365/dev-program) to get a free development tenant which you can use for building your custom solutions
2.	Install the SPFx development tooling based on the documentation
3.	Scaffold your first SPFx solution using the SPFx Yeoman generator
4.	Develop, test and debug the solution in a tenant based on your objectives

One of the coolest things in the SPFx is its ability to package solutions as automatically hosted packages in the tenant. This means that when the solution is ready to be used, you can simply package the solution to a specific package type, which can be easily deployed to any tenant in the world. 

You are **production ready in a matter of minutes** with the automatically hosted code without any need to figure out a location to host your code in Microsoft Azure or in other location in cloud.


## Step-by-step tutorials on getting started

Following 6 videos is a great baseline series on getting started with SPFx. This series focuses on building your first web part, which is a client-side component with UX elements. Web part is a baseline component for UX elements shown in SharePoint and it's also the same component type which can be used to be exposed in Microsoft Teams, Outlook or in Microsoft 365 app (Office). We'll cover the differences on the different hosts within upcoming blog posts within this series.

**Setting up your Microsoft 365 tenant**

- [Tutorial documentation](https://learn.microsoft.com/en-us/sharepoint/dev/spfx/set-up-your-developer-tenant)
- [Tutorial in video format in YouTube](https://www.youtube.com/watch?v=ijaJgc3J-iE&list=PLR9nK3mnD-OXvSWvS2zglCzz4iplhVrKq&index=1)

  {{< youtube ijaJgc3J-iE >}}

**Set up development environment**

- [Tutorial documentation](https://learn.microsoft.com/en-us/sharepoint/dev/spfx/set-up-your-development-environment)
- [Tutorial in video format in YouTube](https://www.youtube.com/watch?v=Cxx9MdjEiEw&list=PLR9nK3mnD-OXvSWvS2zglCzz4iplhVrKq&index=2)

  {{< youtube Cxx9MdjEiEw >}}

**Build your first SharePoint client-side web part (Hello World part 1)**

-	[Tutorial documentation](https://learn.microsoft.com/en-us/sharepoint/dev/spfx/web-parts/get-started/build-a-hello-world-web-part)
-	[Tutorial in video format in YouTube](https://www.youtube.com/watch?v=6WTtjXP5yW4&list=PLR9nK3mnD-OXvSWvS2zglCzz4iplhVrKq&index=3)

  {{< youtube 6WTtjXP5yW4 >}}

**Connect your client-side web part to SharePoint (Hello World part 2)**

- [Tutorial documentation](https://learn.microsoft.com/en-us/sharepoint/dev/spfx/web-parts/get-started/connect-to-sharepoint)
-	[Tutorial in video format in YouTube](https://www.youtube.com/watch?v=5M3zDpgxIMs&list=PLR9nK3mnD-OXvSWvS2zglCzz4iplhVrKq&index=4)

  {{< youtube 5M3zDpgxIMs >}}

**Deploy your client-side web part to a SharePoint page (Hello World part 3)**

- [Tutorial documentation](https://learn.microsoft.com/en-us/sharepoint/dev/spfx/web-parts/get-started/serve-your-web-part-in-a-sharepoint-page)
-	[Tutorial in video format in YouTube](https://www.youtube.com/watch?v=FkFg32NSTM0&list=PLR9nK3mnD-OXvSWvS2zglCzz4iplhVrKq&index=5)

  {{< youtube FkFg32NSTM0 >}}

**Host your client-side web part from Microsoft 365 CDN (Hello World part 4)**

- [Tutorial documentation](https://learn.microsoft.com/en-us/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)
-	[Tutorial in video format in YouTube](https://www.youtube.com/watch?v=N-KowN-UwTM&list=PLR9nK3mnD-OXvSWvS2zglCzz4iplhVrKq&index=6)

  {{< youtube N-KowN-UwTM >}}


## Frequent questions around getting started with SPFx

**Which Node version is supported by SPFx?** 

This depends on the used version. In the time of writing this blog post, the supported version would be Node 16.x. Version is updated as part of the new version of the SPFx. You can always find the latest status from the official documentation.

As SPFx is also used by the Microsoft engineering team to build the native experiences in the Microsoft 365, updating to the latest Node can take a while, as the native out-of-the-box experiences will need to be updated for the latest version. This is why the supported Node version might be a bit behind the latest released version. 

**What’s the most common issue with getting started?** 

Most common issue is a mismatch of the environment with the supported technologies, so for example you are using too new Node version vs what’s supported by the SPFx tooling. 

**I’m having challenges with the dev certificate installation** 

Notice that you’ll need to first scaffold a project and after that you can execute the ‘gulp dev-cert’ command to create the developer certificate for hosting the code locally. This is needed so that the Microsoft 365 hosted online workbench can request the locally hosted files with https. 

**I still can’t make things work – where to get help?**

Please use the sp-dev-docs issue list for any questions around SPFx development. This is the GitHub repository where we store all SPFx dev documentation, and we use it also for tracking any issues from the customers and partners. Microsoft engineering and our MVPs are helping with the questions in this location.

## References

Here are some initial references to get started with the SPFx in your development. Please do provide us with feedback and suggestions on what is needed to help you to get started with the SPFx development for Microsoft 365.

-	SPFx documentation – https://aka.ms/spfx
-	Issues and feedback around SPFx - https://aka.ms/spfx/issues
-	Microsoft 365 Platform Community – https://aka.ms/m365/community
-	Public SPFx and other community calls – https://aka.ms/m365/calls 
    - These calls are for everyone to take advantage to stay up to date on the art of possible within Microsoft 365 and to provide guidance for beginners and more advance users
-	SPFx samples in the Microsoft 365 Unified Sample gallery – https://aka.ms/m365/samples

- - -

We will provide more details on the different options and future direction of the SPFx in upcoming blog posts. This post focused on the getting started steps with SPFx - more details coming up with this series with one post within each business day of January 2023.
