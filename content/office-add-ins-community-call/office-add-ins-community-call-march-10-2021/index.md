---
title: "Office Add-ins community call -- March 10, 2021"
date: 2021-03-15T01:52:00-04:00
author: "Vesa Juvonen"
githubname: VesaJuvonen
categories: ["Office add-in developer community call"]
images:
- images/M365ScuccessJourney.png
tags: []
type: "regular"
---

## Call summary


This month's community call features presentations on Excel JS API
v1.13 updates, PowerPoint ribbon updates, UX changes for Outlook add-ins
on the web and Discussion on building for the Microsoft 365 ecosystem. 
Discussion focused on ways Microsoft can help developers to be more
successful building on the M365 ecosystem.  9 enabling components of a
M365 Customer Success Developer Journey were presented.  This month's
Community spotlight recognizes MVP Maarten van Stam.   Thank you!   Q&A
in chat throughout call.  The call was hosted by David Chesnut
(Microsoft). Microsoft Presenters include: Raymond Lu, Lillian Liu,
Hitesh Manwar, Nikhil Verma, Ying Hao.  Recorded on March 10, 2021.

### Topic Summaries

**Excel JS API v1.13 updates** - Excel APIs are in Preview today,
targeting GA release in July.  The APIs are presently available in
Script lab, include Dependent, Workbook, Range/Table, Event, Pivot
Layout and Table style.   Quick demos today on Range/Table APIs.  
Feedback on preview APIs requested.

**PowerPoint ribbon updates** - available in Office Online week of March
15th, Desktop and Mac in May+.  New features shown -- Allowing native
controls, Setting tab location (to any location you want), and Setting
focus for a tab.  All functions accomplished in manifest with new
elements.   

**UX changes for Outlook add-ins on the web** - whenever an Admin
installs an add-in, the user will now see a one-time nudge informing
them that a new item has been installed and prompts the user to
customize the settings as necessary.  UX changes release to OWA
commercial users April 2021.    

**Discussion on building for the Microsoft 365 ecosystem** -- focused on
how Microsoft can help developers to be more successful with M365
ecosystem.  9 enabling components of a M365 Customer Success Developer
Journey shown.  Join the ongoing discussion at [M365 Customer Success
Platform Panel](https://aka.ms/SuccessPanel)  
![M365ScuccessJourney.png](images/M365ScuccessJourney.png)
**Resources**:   

-   Documentation - [Integrate built-in Office buttons into custom
    control groups and
    tabs](https://docs.microsoft.com/office/dev/add-ins/design/built-in-button-integration) 
-   Documentation - [Position a custom tab on the
    ribbon](https://docs.microsoft.com/office/dev/add-ins/design/custom-tab-placement) 

**Actions**:  

-   Join - [Microsoft Customer Success Platform - User Research
    Panel](https://aka.ms/SuccessPanel) to be part of **M365 customer
    success platform panel** and share your challenges/ideas on M365
    adoption & success.  Also you may email the presenters from the
    Customer Success Engineering Team directly - yinghao@microsoft.com,
    nikhilv@microsoft.com  
-   Recurrent Invite - <https://aka.ms/officeaddinscommunitycall>
-   Link to all Microsoft Developer Community calls
    - <https://aka.ms/M365DevCalls>
-   Submit questions for next community call
    - <https://aka.ms/officeaddinsform>
**General Resources: (referenced in every call, blog post only)**:

-   Office Developer Community help: 
    <https://developer.microsoft.com/office> (**Office-js-docs-pr,
    PnP-OfficeAddins**) 
-   Office Add-ins documentation |
    [aka.ms/office-add-ins-docs](https://aka.ms/office-add-ins-docs)
-   Office Scripts |
    [aka.ms/office-scripts-docs](https://aka.ms/office-scripts-docs)
-   Microsoft 365 Developer Program | <https://aka.ms/M365devprogram> 
-   Script Lab | <https://aka.ms/getscriptlab> 
-   [Office Add-ins documentation |]{.underline}
    <https://aka.ms/office-add-ins-docs>{.underline}
-   Stack Overflow (questions) |
    [https://stackoverflow.com](https://stackoverflow.com/)
    (**office-js, outlook-web-addins, office-scripts)**
-   GitHub (issues) |
    [https://github.com/OfficeDev/](https://github.com/OfficeDev/office-js)[**office-js**](https://github.com/OfficeDev/office-js)
-   UserVoice (feature requests) |
    [https://officespdev.uservoice.com](https://officespdev.uservoice.com/)
**Stay connected -- (all groups)  (Blog and YouTube posts)**

-   Twitter
    [https://twitter.com/microsoft365dev](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbkdvcDJHcGdzM2VIUkwzU3lOYkJaVFEzM0Q2QXxBQ3Jtc0ttM1NyaTQ2RjFSOFh3a0l4c1pralBRQVI1bDNSQ2RaVm9OdzJrRkdtV1Z1SW5VdmdwamNNLTBEaFdaSmZMc0lQNzdRZ2dDYV9WZVF1ZVIwc2dPQTZBRUZ3b3hoWUVJdDJoQWZUcWdCR2JKdmwtUU43RQ&q=https%3A%2F%2Ftwitter.com%2Fmicrosoft365dev)​
-   YouTube
    [https://aka.ms/M365DevYouTube](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqa3RzWmpNU2VPRmh6dXBad3hKMmxySjBaQVl6Z3xBQ3Jtc0trVjYyeXZlSXZiX0JydHlyeHdqcTRSUnczX2xrVDloOWhzeGVCYXFibjBiM1VpXzFOd2dZX2dJdlNYQWYtekcyWXZOTHp3VkdoU2JsdmNVQ3dtdkw2ZHF0cVdCS29TQmJ1Z3hoVmJyd3JtYlFxUW92WQ&q=https%3A%2F%2Faka.ms%2FM365DevYouTube)
**Q&A (Question & Answers): **

We welcome you to submit questions and topic suggestions prior to each
call by using our short [survey
form](https://aka.ms/officeaddinsform). 
***Excel API updates for 1.13****** ***

**Q:  Will insertWorksheetsFromBase64 preserve formula references
between worksheets?** 

A:  Yes, it will preserve formula references between worksheets if
reference worksheets are copied as well. Please test this out while it
is in preview. 

**Q:  Will the insertWorksheetsFromBase64 API work on both Excel on
Windows and on the web?** 

A:  Yes, the insertWorksheetsFromBase64 API will work for Excel on
Windows, Excel on Mac, and Excel on the web. 
***PowerPoint ribbon update****** ***

**Q: Are the PowerPoint ribbon updates just for PowerPoint?** 

A:  Our goal is to make sure our user experience features are
consistent across all hosts. Currently, these updates are only
available in PowerPoint. 

**Q:  Can you bring in a ribbon item, that isn't in one of the default
tabs, into your own tab?** 

A:  You can bring in any native feature that is currently supported. See
the following list representing all controls that are currently
supported and visible on the Office
ribbon: [https://github.com/OfficeDev/office-control-ids](https://github.com/OfficeDev/office-control-ids0). 

**Q:  What are the future plans for the shapes API on PowerPoint?** 

A:  We have some of the shapes API in preview documented in the
article [PowerPoint JavaScript preview
APIs](https://docs.microsoft.com/javascript/api/requirement-sets/powerpoint/powerpoint-preview-apis?view=common-js-preview).
We also have some additional APIs planned around adding
shapes, textbox and tags to shapes. We don't have a concrete timeline
yet. 
***Miscellaneous questions**

**Q:  Is there a timeline for support of the message compose command
surface on Outlook for mobile?** 

A:  Compose scenarios are on the backlog, but we do not have an ETA
yet. 

**Q:  In the February call, you mentioned the registry key option to
disable web-plugins for Outlook on Windows. Where can we find
documentation on what registry keys to set and where?** 

A:  We haven't yet documented the Group Policy (\"Deactivate Outlook
web add-ins whose equivalent COM or VSTO add-in is installed\") that
configures this behavior. However, it will be added to the article [Make
your Office Add-in compatible with an existing COM
add-in](https://docs.microsoft.com/en-us/office/dev/add-ins/develop/make-office-add-in-compatible-with-existing-com-add-in). 
