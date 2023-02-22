---
title: "Creating a video portal in SharePoint with JSON formatted document library"
date: 2021-12-03T02:18:00-05:00
author: "Anand Ragav"
githubname: anandragav
categories: ["Community post"]
images:
- images/AnandVRagav_1-1638227104052.png
tags: ["SharePoint", "List formatting"]
type: "regular"
---

Often times we store videos in SharePoint and use the file viewer or the
highlighted content web parts to display videos on the homepage of the
site. With Microsoft Stream also moving towards SharePoint for storing
meeting recordings, the use of videos in SharePoint site pages could
increase. Recently I worked on an event page in SharePoint and thought
it would be useful to have a video portal created for the event to store
and display event session recordings.
 
![AnandVRagav_1-1638227104052.png](images/AnandVRagav_1-1638227104052.png)
 
In this post are the details of the document library and how to display
that in the SharePoint site page.
 
## Document library

The document library exists at the same level as the default shared
documents library on the site.
 
![AnandVRagav_2-1638227193903.png](images/AnandVRagav_2-1638227193903.png)
 
Video files are uploaded to the document library.
![AnandVRagav_3-1638227225340.png](images/AnandVRagav_3-1638227225340.png)
 
Additional columns can be created in the library, these additional
columns provide rich information that can be displayed in the video
portal. Rich metadata such as title, description, people, tools/topics
covered, social sharing options like yammer, share and like buttons can
compliment the video portal experience.
 
![AnandVRagav_4-1638227250191.png](images/AnandVRagav_4-1638227250191.png)
 
When video files are uploaded and the metadata fields are filled in with
the information, the default "All Documents" view can look like this.
 
![AnandVRagav_5-1638227276106.png](images/AnandVRagav_5-1638227276106.png)
 
The default view or a new view can be created with all the columns
included. The view can be formatted using JSON to get the card view in a
gallery style layout. Each card has the video title, a description,
tools covered using icons from Flicon.io, people featuring in the video
with hover cards opening their office profile and a timestamp to
indicate when the video was published. The "Watch" button opens the
video in a new browser tab, the learning button opens the item in a
learning application like a Learning Management system so user can add
to their profile, the Yammer button opens the connected thread in Yammer
for conversations, the share button opens the default share option
within SharePoint/OneDrive so user can send the item through email or
copy link, the thumbs-up button registers user likes in the "User"
person column using the recently released setValue function in List
formatting.
 
![AnandVRagav_6-1638227301475.png](images/AnandVRagav_6-1638227301475.png)
 
To achieve this formatting, the view needs to be formatted using JSON.
 
![AnandVRagav_7-1638227333192.png](images/AnandVRagav_7-1638227333192.png)
 
 
![AnandVRagav_8-1638227355460.png](images/AnandVRagav_8-1638227355460.png)
 
The complete JSON is provided below.
 
```json
{
  "schema": "https://developer.microsoft.com/json-schemas/sp/view-formatting.schema.json",
  "height": 400,
  "width": 280,
  "debugMode": true,
  "hideSelection": true,
  "hideColumnHeader": true,
  "formatter": {
    "elmType": "div",
    "attributes": {
      "class": "ms-borderColor-neutralLight"
    },
    "style": {
      "box-sizing": "border-box",
      "width": "100%",
      "border-width": "2px",
      "box-shadow": "0px 1.6px 3.6px 0 #00000024, 0px 0.3px 0.9px 0 #00000024",
      "border-style": "solid",
      "padding": "0 0 0 0px",
      "margin-bottom": "2px",
      "display": "flex",
      "flex-direction": "column"
    },
    "children": [
      {
        "elmType": "div",
        "attributes": {
          "class": "ms-fontSize-s"
        },
        "style": {
          "width": "100%",
          "line-height": "1.5em",
          "padding": "4px",
          "padding-left": "16px",
          "background-color": "=if([$Track] =='Keynote', '#0fc373', if([$Track] =='Product Roundtables', '#ff8c0a',  if([$Track] =='Breakout', '#af78d2' '#0082f0')))",
          "color": "white",
          "font-size": "13.5px"
        },
        "txtContent": "[$Track]"
      },
      {
        "elmType": "div",
        "attributes": {},
        "style": {
          "width": "100%",
          "flex": "0px 1px 1px",
          "display": "flex",
          "align-items": "center"
        },
        "children": [
          {
            "elmType": "img",
            "attributes": {
              "src": "[$Image.serverRelativeUrl]"
            },
            "style": {
              "float": "left",
              "width": "100%"
            }
          }
        ]
      },
      {
        "elmType": "div",
        "style": {
          "flex": "0 0 0px",
          "display": "flex",
          "flex-wrap": "wrap",
          "flex-direction": "column"
        },
        "children": [
          {
            "elmType": "div",
            "style": {
              "flex": "0 0 0px",
              "box-sizing": "border-box",
              "padding": "10px"
            },
            "children": [
              {
                "elmType": "div",
                "attributes": {
                  "class": "ms-fontSize-xl"
                },
                "style": {
                  "border": "0",
                  "padding": "4px",
                  "color": "white",
                  "position": "absolute",
                  "left": "10px",
                  "top": "40px",
                  "background-color": "transparent",
                  "cursor": "pointer"
                },
                "txtContent": "[$Session]",
                "customRowAction": {
                  "action": "defaultClick"
                }
              },
              {
                "elmType": "div",
                "attributes": {
                  "class": "ms-fontSize-m"
                },
                "style": {
                  "line-height": "1.5em",
                  "margin-bottom": "8px",
                  "padding-top": "6px"
                },
                "customCardProps": {
                  "openOnEvent": "hover",
                  "directionalHint": "rightCenter",
                  "isBeakVisible": true,
                  "beakStyle": {
                    "backgroundColor": "#3c3c3c"
                  },
                  "formatter": {
                    "elmType": "div",
                    "style": {
                      "color": "white",
                      "background-color": "#3c3c3c",
                      "width": "300px",
                      "padding": "10px"
                    },
                    "txtContent": "[$About]"
                  }
                },
                "txtContent": "=if(indexOf([$About] + '|', '|' ) > 180, substring([$About], 0, 180) + '...', [$About])"
              },
              {
                "elmType": "div",
                "attributes": {
                  "class": "sp-row-listPadding"
                },
                "style": {
                  "position": "absolute",
                  "left": "10px",
                  "top": "320px",
                  "font-size": "13px"
                },
                "txtContent": "=if([$Age] <=1, 'Today', [$Age] + ' days ago')"
              },
              {
                "elmType": "span",
                "style": {
                  "background-color": "white",
                  "border-radius": "10%",
                  "position": "absolute",
                  "left": "12px",
                  "top": "165px",
                  "display": "flex",
                  "flex-direction": "row"
                },
                "children": [
                  {
                    "forEach": "choiceIterator in [$Tool]",
                    "elmType": "div",
                    "attributes": {
                      "class": "ms-bgColor-themePrimary ms-fontColor-white ms-fontSize-xl",
                      "title": "=[$choiceIterator]",
                      "iconName": "=if([$choiceIterator] == 'Teams', 'TeamsLogo' , if([$choiceIterator] == 'Forms', 'OfficeFormsLogo' , if([$choiceIterator] == 'SharePoint', 'SharepointLogo' , if([$choiceIterator] == 'Whiteboard', 'WhiteboardApp32' , if([$choiceIterator] == 'Stream', 'StreamLogo' , if([$choiceIterator] == 'Office', 'OfficeLogo' , if([$choiceIterator] == 'Computer', 'System' , if([$choiceIterator] == 'PowerApps', 'PowerApps' ,  if([$choiceIterator] == 'Power Automate', 'MicrosoftFlowLogo' , if([$choiceIterator] == 'Mobile', 'CellPhone' , if([$choiceIterator] == 'Outlook', 'OutlookLogo' ,  if([$choiceIterator] == 'Planner', 'PlannerLogo' ,  if([$choiceIterator] == 'To-Do' ,'ToDoLogoInverse', if([$choiceIterator] == 'Security' , 'LaptopSecure', 'SharePointLogo')))))))))"
                    },
                    "style": {
                      "background-color": "white",
                      "border-radius": "100%",
                      "width": "25px",
                      "height": "20px",
                      "text-align": "center",
                      "padding": "2px",
                      "margin": "1px",
                      "color": "=if([$choiceIterator] == 'Teams', '#6264a7',  if([$choiceIterator] == 'SharePoint', '#036C70', if([$choiceIterator] == 'Forms', '#007F70', if([$choiceIterator] == 'Outlook', '#0078D4', if([$choiceIterator]== 'Stream',  '#BC1948', if([$choiceIterator] == 'PowerApps', '#752875', if([$choiceIterator] == 'Mobile', '#0E41B1', if([$choiceIterator] == 'Computer', '#73276C', if([$choiceIterator] == 'Power BI', '#EDBF2C', if([$choiceIterator] == 'Whiteboard', '#1E8EE5', if([$choiceIterator] == 'To-Do' , '#175BBD', '#252423' )))))))))"
                    }
                  }
                ]
              }
            ]
          },
          {
            "elmType": "div",
            "attributes": {
              "class": "ms-bgColor-transparent sp-css-borderColor-neutralLight"
            },
            "style": {
              "position": "absolute",
              "right": "8px",
              "top": "150px"
            },
            "children": [
              {
                "elmType": "div",
                "attributes": {
                  "class": "sp-card-previewColumnContainer"
                },
                "children": [
                  {
                    "elmType": "div",
                    "style": {
                      "display": "flex"
                    },
                    "children": [
                      {
                        "elmType": "p",
                        "attributes": {
                          "class": "sp-card-userEmptyText"
                        },
                        "txtContent": "=if(length([$Responsible]) == 0, '–', '')"
                      },
                      {
                        "forEach": "personIterator in [$Responsible]",
                        "elmType": "a",
                        "attributes": {
                          "class": "=if(loopIndex('personIterator') >= 5, 'sp-card-userContainer', 'sp-card-userContainer sp-card-keyboard-focusable')"
                        },
                        "style": {
                          "display": "=if(loopIndex('personIterator') >= 5, 'none', '')"
                        },
                        "children": [
                          {
                            "elmType": "img",
                            "defaultHoverField": "[$personIterator]",
                            "attributes": {
                              "src": "=getUserImage([$personIterator.email], 'S')",
                              "title": "[$personIterator.title]",
                              "class": "sp-card-userThumbnail"
                            },
                            "style": {
                              "display": "=if(length([$Responsible]) > 5 && loopIndex('personIterator') >= 4, 'none', '')",
                              "border-radius": "50%",
                              "padding": "-1px"
                            }
                          },
                          {
                            "elmType": "div",
                            "attributes": {
                              "class": "ms-bgColor-neutralLight ms-fontColor-neutralSecondary sp-card-userOthers"
                            },
                            "style": {
                              "display": "=if(length([$Responsible]) > 5 && loopIndex('personIterator') == 4, '', 'none')",
                              "border-radius": "50%"
                            },
                            "customCardProps": {
                              "formatter": {
                                "elmType": "div",
                                "attributes": {
                                  "class": "sp-card-personCallout"
                                },
                                "children": [
                                  {
                                    "forEach": "personIterator in [$Responsible]",
                                    "elmType": "div",
                                    "attributes": {
                                      "class": "sp-card-userContainer sp-card-userCustomCard"
                                    },
                                    "style": {
                                      "display": "=if(loopIndex('personIterator') < 4, 'none', '')",
                                      "border-radius": "50%"
                                    },
                                    "children": [
                                      {
                                        "elmType": "img",
                                        "defaultHoverField": "[$personIterator]",
                                        "attributes": {
                                          "src": "=getUserImage([$personIterator.email], 'S')",
                                          "title": "[$personIterator.title]",
                                          "class": "sp-card-userThumbnail"
                                        }
                                      }
                                    ]
                                  }
                                ]
                              },
                              "openOnEvent": "hover"
                            },
                            "children": [
                              {
                                "elmType": "span",
                                "txtContent": "='+' + toString(length([$Responsible]) - (4))"
                              }
                            ]
                          }
                        ]
                      }
                    ]
                  }
                ]
              }
            ]
          },
          {
            "elmType": "span",
            "style": {
              "flex": "0px 10px 0px",
              "display": "flex",
              "flex-direction": "row"
            },
            "children": [
              {
                "elmType": "span",
                "children": [
                  {
                    "elmType": "button",
                    "customRowAction": {
                      "action": "defaultClick"
                    },
                    "style": {
                      "position": "absolute",
                      "left": "-1px",
                      "top": "350px",
                      "width": "60px",
                      "margin-left": "10px",
                      "display": "span",
                      "background-color": "transparent",
                      "border-radius": "4px",
                      "border-color": "#0082f0"
                    },
                    "txtContent": "Watch",
                    "attributes": {
                      "class": "sp-row-button ms-borderColor-blue sp-row-button ms-bgColor-purpleDark--hover ms-fontWeight-semibold ms-fontColor-black"
                    }
                  }
                ]
              },
              {
                "elmType": "span",
                "children": [
                  {
                    "elmType": "a",
                    "customRowAction": {
                      "action": "defaultClick"
                    },
                    "style": {
                      "position": "absolute",
                      "left": "110px",
                      "top": "348px",
                      "width": "40px",
                      "margin-left": "10px",
                      "display": "span",
                      "background-color": "transparent",
                      "border-radius": "4px"
                    },
                    "attributes": {
                      "title": "Join the conversation",
                      "class": "sp-row-button sp-row-button ms-bgColor-purpleDark--hover ms-fontWeight-semibold ms-fontColor-black",
                      "href": "=if([$Yammer] == '', 'https://web.yammer.com/main/topics/eyJfdHlwZSI6IlRvcGljIiwiaWQiOiI2NzYwNDM4OTg4OCJ9/all', [$Yammer])",
                      "target": "_blank"
                    },
                    "children": [
                      {
                        "elmType": "span",
                        "style": {
                          "color": "#0082f0",
                          "align-content": "center",
                          "padding": "6px",
                          "padding-left": "12px",
                          "white-space": "normal"
                        },
                        "attributes": {
                          "iconName": "YammerLogo",
                          "class": "ms-font-xl"
                        }
                      }
                    ]
                  }
                ]
              },
              {
                "elmType": "span",
                "children": [
                  {
                    "elmType": "button",
                    "customRowAction": {
                      "action": "setValue",
                      "actionInput": {
                        "User": "=if(indexOf([$User.email] , @me) > -1 , removeFrom([$User.email] , @me) , appendTo([$User.email] , @me))"
                      }
                    },
                    "style": {
                      "position": "absolute",
                      "right": "45px",
                      "top": "350px",
                      "width": "40px",
                      "margin-left": "10px",
                      "display": "span",
                      "background-color": "transparent",
                      "border-radius": "4px"
                    },
                    "attributes": {
                      "title": "",
                      "class": "sp-row-button sp-row-button ms-bgColor-purpleDark--hover ms-fontWeight-semibold ms-fontColor-black"
                    },
                    "children": [
                      {
                        "elmType": "span",
                        "style": {
                          "color": "#0082f0",
                          "align-content": "left",
                          "justify-content": "left",
                          "padding": "4px",
                          "white-space": "normal"
                        },
                        "attributes": {
                          "iconName": "=if(indexOf([$User.email] , @me) > -1 ,'LikeSolid', 'Like')",
                          "class": "ms-font-xl"
                        }
                      }
                    ]
                  },
                  {
                    "elmType": "div",
                    "attributes": {
                      "class": "sp-row-listPadding"
                    },
                    "style": {
                      "position": "absolute",
                      "left": "230px",
                      "top": "358px",
                      "font-size": "18px"
                    },
                    "txtContent": "=if(length([$User]) > 0, length([$User]), ''"
                  }
                ]
              },
              {
                "elmType": "span",
                "children": [
                  {
                    "elmType": "button",
                    "customRowAction": {
                      "action": "share"
                    },
                    "style": {
                      "position": "absolute",
                      "left": "150px",
                      "top": "350px",
                      "width": "40px",
                      "margin-left": "10px",
                      "display": "span",
                      "background-color": "transparent",
                      "border-radius": "4px"
                    },
                    "attributes": {
                      "title": "Share it",
                      "class": "sp-row-button sp-row-button ms-bgColor-purpleDark--hover ms-fontWeight-semibold ms-fontColor-black"
                    },
                    "children": [
                      {
                        "elmType": "span",
                        "style": {
                          "color": "#0082f0",
                          "align-content": "left",
                          "justify-content": "left",
                          "padding": "4px",
                          "white-space": "normal"
                        },
                        "attributes": {
                          "iconName": "Share",
                          "class": "ms-font-xl"
                        }
                      }
                    ]
                  }
                ]
              },
              {
                "elmType": "span",
                "children": [
                  {
                    "elmType": "a",
                    "customRowAction": {
                      "action": "defaultClick"
                    },
                    "style": {
                      "position": "absolute",
                      "left": "70px",
                      "top": "348px",
                      "width": "40px",
                      "margin-left": "10px",
                      "display": "span",
                      "background-color": "transparent",
                      "border-radius": "4px"
                    },
                    "attributes": {
                      "title": "Join the conversation",
                      "class": "sp-row-button sp-row-button ms-bgColor-purpleDark--hover ms-fontWeight-semibold ms-fontColor-black",
                      "href": "[$Learning]",
                      "target": "_blank"
                    },
                    "children": [
                      {
                        "elmType": "span",
                        "style": {
                          "color": "#0082f0",
                          "align-content": "center",
                          "padding": "6px",
                          "padding-left": "12px",
                          "white-space": "normal"
                        },
                        "attributes": {
                          "iconName": "D365TalentLearn",
                          "class": "ms-font-xl"
                        }
                      }
                    ]
                  }
                ]
              }
            ]
          }
        ]
      }
    ]
  }
}
```
 
The final step is then to embed this view in the SharePoint site page
using the Document library web part.
 
![AnandVRagav_9-1638227433322.png](images/AnandVRagav_9-1638227433322.png)
 
And choosing the library to be embedded. "Session recordings" is the
name of my library.
 
![AnandVRagav_10-1638227461663.png](images/AnandVRagav_10-1638227461663.png)
 
Editing the web part to set the correct view, hiding the command bar and
"See all" buttons.
 
![AnandVRagav_11-1638227490353.png](images/AnandVRagav_11-1638227490353.png)
 
The final result can look like this. Optionally a support list to filter
down videos by topic or category can be added to enhance the experience.
 
![AnandVRagav_12-1638227543478.png](images/AnandVRagav_12-1638227543478.png)
 
Hope you found this useful. I would be interested to hear your thoughts
and if you would use this and how you might enhance this.
 