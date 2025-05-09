---
# this is the title
title: "Can AI help make SharePoint development easier?"
# this is the publishing date of your article, usually this should match "now"
date: 2025-04-24T08:40:00-04:00
# This is your name
author: "Henry from adenin"
# This is your GitHub name
githubname: HenryAmm
# Don't change
categories: ["Community post"]
# Link to the thumbnail image for the post
images:
- images/2025-03-14_17-26-41.png
# don't change
tags: []
# don't change
type: "regular"
---

Hi 👋 I'm Henry from adenin (find me on [LinkedIn](https://www.linkedin.com/in/henryamm/)), and I'm going to share some background on my SharePoint [hackathon submission](https://github.com/SharePoint/sharepoint-hackathon/issues/19) that was a runner-up in the category "SharePoint Framework".

Like many SharePoint developers and consultants, I've often faced the challenge of turning creative ideas into functional web parts or pages, especially when time or coding expertise are limited. This led me to explore how AI could bridge that gap, resulting in my SharePoint Hackathon submission: 🥢🥢🥢🥁💃 ... Introducing **Web Part Genie** 🧞

## The idea: Getting ideas to a quick mockup

In many organizations, team members have innovative concepts for enhancing their SharePoint environments. However, bringing these ideas to life typically requires development resources, which aren't always readily available. This bottleneck **can stifle innovation** and delay improvements.

Imagine if SharePoint came with a LLM interface that users **simply describe** to whatever functionality or layout they desire. Using natural language, this type of Copilot (or is it more a "Cobuilder"?) then interprets these prompts and generates the corresponding web parts or full pages.

With the **Web Part Genie** web part you could type for example:

> "Create a stock ticker for my company's homepage."

...which results in a functional stock ticker web part ready to be added to your SharePoint page.

![A stock ticker web part for a SharePoint intranet created by AI](https://github.com/HenryAmm/pnp-blog-article-submission/blob/can-ai-help-make-sharepoint-development-easier/content/post/can-ai-help-make-sharepoint-development-easier/images/image.png)

Here are [some more examples](https://github.com/SharePoint/sharepoint-hackathon/issues/19#:~:text=of%20an%20intranet-,Screenshots,-%22Make%20me%20a) of what Web Part Genie can do based on user prompts, including:

- **Weather Widgets**: Displaying current weather conditions and forecasts.
- **Team Holiday Calendars**: Showing team members' upcoming vacations and allowing users to request time off.
- **Gym Class Booking Systems**: Enabling employees to view and book available fitness classes.
- **IT Support Portals**: Offering troubleshooting steps and facilitating support ticket submissions.
- **Project Management Dashboards**: Visualizing project progress, upcoming deadlines, and team activities.
- **HR Welcome Pages**: Providing new employees with essential resources, news, and an employee directory.

## Under the hood

Building Web Part Genie involved integrating several key technologies:

- **SPFx (SharePoint Framework)**: For building the custom web part.
- **AI Integration**: Utilizing the Claude 3.7 model for interpreting natural language prompts.
- **Tailwind CSS**: For responsive and modern designs.
- **ShadCN UI Components**: Ensuring consistent and accessible UI elements.
- **Recharts**: Creating dynamic and interactive charts within generated web parts.

## Looking ahead: Democratizing SharePoint customization

My vision for Web Part Genie extends beyond just a tool; it's about pushing SharePoint customizations to the **next level**. Eliminating the need to code, now everybody can **rapidly prototype and test** new SharePoint experiences.

At [adenin](www.adenin.com), we're **already using** a version of SharePoint Genie to make better SharePoint web parts for our extensive library of app integrations. (See previews of real LLM-generated web parts on our website, for example for [Outlook](https://www.adenin.com/apps/outlook/), [Slack](https://www.adenin.com/apps/slack/) or [LinkedIn](https://www.adenin.com/apps/linkedin/).

This year we're working to bring a version of this to **real SharePoint users** with a feature we internally call "Refine with Genie". Basically a customer would start with any of the templates from our App Directory (see the paragraph just above) but can **suggest any number of further changes** to it, and the LLM will turn them into a **custom-coded artifact** that's unique to their needs – without writing any code.

![A LLM will take user requests to improve the layout of a SharePoint web part](https://github.com/HenryAmm/pnp-blog-article-submission/blob/can-ai-help-make-sharepoint-development-easier/content/post/can-ai-help-make-sharepoint-development-easier/images/2025-04-24_11-24-24.png?raw=true)

> **Do you think "Genie" is a good name, or what should we call it? Let me know in the comments...**
 
## Want to try it yourself?

The Web Part Genie web part is **available to use**, simply by downloading it from my [Github repository](https://github.com/HenryAmm/WebPartGenie). I invite you to explore it, experiment with your own prompts, and see how it can **streamline your SharePoint customizations**.

If you have ideas, feedback, or just want to share your experiences using Web Part Genie, feel free to reach out. Let's continue to **innovate and make SharePoint a more dynamic and user-friendly platform for everyone**. Thank you to Luise for inviting me to post my story.
