---
title: "Create and add a OneNote tab to your Microsoft Teams team channel using Power Automate + Graph API"
date: 2021-02-24T09:36:00-05:00
author: "Vesa Nopanen"
githubname: veskunopanen
categories: ["Community post"]
images:
- images/image-13.png
tags: ["Power Automate", "Microsoft Graph"]
type: "regular"
---
 
I was asked to share how I have been adding new OneNote tabs to a team
channel in Microsoft Teams using Power Automate + Graph API. If you look
at
the [documentation ](https://docs.microsoft.com/graph/teams-configuring-builtin-tabs?WT.mc_id=M365-MVP-5003326)it
shows you this:
![image-13](images/image-13.png)
 
Of course I never believed that but found earlier a way to hack OneNote
into a channel as tab but also updated my methods when it became much
simpler than before. In this blog post I show you the simple way how to
add OneNote book as a tab.
 
1.  You need t use a Premium licensing if you are using Power Automate
    since this is done using Graph API calls.
2.  Set up Azure AD App Registration with application id and client
    secret with [required permissions for
    OneNote](https://docs.microsoft.com/graph/api/onenote-post-notebooks?view=graph-rest-beta&tabs=http&WT.mc_id=M365-MVP-5003326) and [to
    adding a
    tab](https://docs.microsoft.com/graph/api/channel-post-tabs?view=graph-rest-beta&WT.mc_id=M365-MVP-5003326) to
    create OneNote books and adding them to tabs.
3.  You need a team id and a channel id you want to put the OneNote book
    into as a tab
 
![image-14](images/image-14.png)
 
Adding a new notebook is done directly to the team. The creation is
quite simple -- I used the team name as part of the Notebook's name.
Once you have created the notebook you need to parse the body for some
important variabled.
 
![image-16](images/image-16.png)
 
 
I created the schema based on one creation body to retrieve essential
info about notebook ID and also it's weburl.
 
 
 
 
```json
{
     "type": "object",
     "properties": {
         "@@odata.context": {
             "type": "string"
         },
         "id": {
             "type": "string"
         },
         "self": {
             "type": "string"
         },
         "createdDateTime": {
             "type": "string"
         },
         "displayName": {
             "type": "string"
         },
         "lastModifiedDateTime": {
             "type": "string"
         },
         "isDefault": {
             "type": "boolean"
         },
         "userRole": {
             "type": "string"
         },
         "isShared": {
             "type": "boolean"
         },
         "sectionsUrl": {
             "type": "string"
         },
         "sectionGroupsUrl": {
             "type": "string"
         },
         "createdBy": {
             "type": "object",
             "properties": {
                 "user": {
                     "type": "object",
                     "properties": {
                         "id": {
                             "type": "string"
                         },
                         "displayName": {
                             "type": "string"
                         }
                     }
                 }
             }
         },
         "lastModifiedBy": {
             "type": "object",
             "properties": {
                 "user": {
                     "type": "object",
                     "properties": {
                         "id": {
                             "type": "string"
                         },
                         "displayName": {
                             "type": "string"
                         }
                     }
                 }
             }
         },
         "links": {
             "type": "object",
             "properties": {
                 "oneNoteClientUrl": {
                     "type": "object",
                     "properties": {
                         "href": {
                             "type": "string"
                         }
                     }
                 },
                 "oneNoteWebUrl": {
                     "type": "object",
                     "properties": {
                         "href": {
                             "type": "string"
                         }
                     }
                 }
             }
         }
     }
 } 
```
 
 
 
 
 
The final piece is to use this information to add OneNote as a tab to a
channel. For this you need the notebook id, the channel id along with
the team id.
 
![image-18](images/image-18.png)
 
 
 
I got the display name directly out of parsed JSON but you can rename
the tab better.
And that's that.
 
![image-20](images/image-20.png)
 
Of course we could take this further by adding new sections and pages to
the OneNote -- or even content. But even as this is now this is very
useful when doing a custom team provisioning. If you have premium
licenses for Power Automate.
 
![image-22](images/image-22.png)
 
 
**Instead of using Power Automate Premium this could be very well done
with Azure Logic Apps, which can provide a cost-effective way to use
occasional Graph API calls (it always depends): do the ROI calculation
for your situation/platform.**
 
This article is a [repost from my
blog](https://myteamsday.com/2020/12/07/add-a-onenote-tab-to-team/).
