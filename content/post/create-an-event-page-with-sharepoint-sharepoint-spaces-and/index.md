---
title: "Create an event page with SharePoint, SharePoint Spaces and formatted Lists"
date: 2021-11-23T02:10:00-05:00
author: "Anand Ragav"
githubname: anandragav
categories: ["Community post"]
images:
- images/AnandVRagav_0-1637611061380.png
tags: ["SharePoint"]
type: "regular"
---

Recently I shared with the PnP community an event page I was working on
and how I used SharePoint, Spaces and formatted Lists to design the user
experience. In this post is explained the details of how the page, space
and lists are made.

![AnandVRagav_0-1637611061380.png](images/AnandVRagav_0-1637611061380.png)
 
I will break down the components first and then go into the details one
by one.

1.  a headerless SharePoint page as the event page
2.  a SharePoint Space
3.  an events list in SharePoint
4.  a SharePoint list to store the sessions information
5.  Optional: a SharePoint list to store session track
6.  a SharePoint list to store people information]
7.  a timer web part
8.  an about list web part.
 
 
## A headerless page

For the event
page, I chose to have a headerless page in my SharePoint site. My
intention was to save some real-estate on the page because there is no
header image banner on a headerless
page.
To create the headerless page, make a copy of the site homepage (the
default home page created when you create a new site does not have a
header and title at the top), rename the URL and rename the page title
in page properties. The copy gets added to the page library with url
ending "..home1.aspx".
For comparison see the amount of space saved below.
 
![AnandVRagav_1-1637607933245.png](images/AnandVRagav_1-1637607933245.png)
 

For comparison see the amount of space saved below.
![](images/AnandVRagav_2-1637607984045.png)

![](images/AnandVRagav_4-1637607984059.png)

For the page layout choose the vertical section. This puts a vertical
section for the full length of the page on the right-hand-side.
![](images/AnandVRagav_6-1637608010041.png)

## SharePoint Space

Within the same SharePoint site, I activated
Spaces. Spaces is a feature that needs to be activated at each site
level. Do that from Site settings \> Manage Site features \> Spaces \>
Activate.

![](images/AnandVRagav_8-1637608057361.png)

You can learn how to create Spaces from the [Microsoft support
documentation](https://support.microsoft.com/office/create-a-sharepoint-space-77e0bb2a-625e-40a9-b38e-1ca84db6cf65 "Create a Space")
[Below image snapshot shows the design of my Space and the web parts I
used.]
 
![AnandVRagav_9-1637608480549.png](images/AnandVRagav_9-1637608480549.png)
 
[Now with the Space created, copy the URL to the Space and to add it to
the event page (the headerless page) using the embed web part on the
page.]
 
![AnandVRagav_10-1637608513774.png](images/AnandVRagav_10-1637608513774.png)
 
[Paste the URL to the Space in the embed web part and save the page. If
you want to customize the height and width properties of the embedded
Space, use an iFrame embed code like the below and adjust the properties
to
taste.]
 
``` {.lia-code-sample .language-markup}
<iframe src="https://<Replace with your Space URL>" width="100%" height="550" style="border:1px solid black;">
</iframe>
```

[To get a similar result as shown below you may need to adjust the
positions of the web parts in the Space by checking how they are aligned
once embedded on the event
page.]
 
![AnandVRagav_11-1637608636463.png](images/AnandVRagav_11-1637608636463.png)
 
## Events list

The sessions are scheduled using the events calendar in
the SharePoint site. However I chose not to display them on the event
page using the events web part; instead I chose a SharePoint list
(details in next section).
From the events calendar, for each event we can get the event URL. This
information is needed to let users add the event to their calendars. To
create the events, use the Events web part on a separate hidden page or
use the events list from the backend through Site contents. Use
[Microsoft support
documentation](https://support.microsoft.com/office/use-the-events-web-part-5fe4da93-5fa9-4695-b1ee-b0ae4c981909#bkmk_addevent)
for help
list****to
display the sessions information: **[To display the sessions on the
event page, I created a list in the SharePoint site with the below
columns. The field labels for the columns were renamed later to suit the
event
needs.
 
![AnandVRagav_0-1637608851038.png](images/AnandVRagav_0-1637608851038.png)

style="width: 999px;"}
 
[If you are new to lists and want to learn how to work with lists and
add entries, follow the [Microsoft
documentation](https://support.microsoft.com/office/introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7).

After adding the session entries, I formatted the columns using JSON to
give it a better format and styling like the below. I recommend creating
a separate view before proceeding with formatting the columns. That way
you have a view to embed on the event page and another view in the
backend for editing
purposes.
 
![AnandVRagav_1-1637608940183.png](images/AnandVRagav_1-1637608940183.png)
 

Let's look at the formatting, let us take them column by column starting
with the Session column.
The session column is a single line text column and has a left-hand-side
border, session title and a share button. The share button opens the
default share option for list items to allow users to share session
links through email or copy the link to share through Teams or another
channel.

![AnandVRagav_0-1637611467410.png](images/AnandVRagav_0-1637611467410.png)


To get that format, use the below JSON code. Open the drown-down arrow
next to the column header \> select column settings \> select Format
this column. Then paste the below JSON and select save.

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/sp/column-formatting.schema.json",
  "elmType": "div",
  "attributes": {
    "class": "sp-css-backgroundColor-neutralBackground"
  },
  "style": {
    "border-color": "=if([$Sessiontrack] =='Keynote', '#0fc373', if([$Sessiontrack] =='Product Roundtables', '#ff8c0a',  if([$Sessiontrack] =='Breakout', '#af78d2' '#0082f0')))",
    "border-left-style": "solid",
    "border-width": "4px",
    "border-radius": "4px",
    "background-color": "sp-css-backgroundColor-neutralBackground",
    "white-space": "normal",
    "padding-top": "0px",
    "display": "flex",
    "flex-direction": "row",
    "height": "60px",
    "margin-left": "-10px"
  },
  "children": [
    {
      "elmType": "span",
      "style": {
        "margin-left": "3px",
        "display": "flex",
        "flex-direction": "column",
        "justify-content": "center"
      },
      "children": [
        {
          "elmType": "span",
          "style": {
            "padding-top": "0px",
            "display": "flex",
            "flex-direction": "row"
          },
          "children": [
            {
              "elmType": "span",
              "style": {
                "padding": "6px",
                "white-space": "normal",
                "font-size": "13.5px",
                "font-weight": "400"
              },
              "txtContent": "@currentField"
            },
            {
              "elmType": "span",
              "style": {
                "align-content": "right",
                "justify-content": "right",
                "padding-left": "2px",
                "white-space": "normal"
              },
              "children": [
                {
                  "elmType": "button",
                  "customRowAction": {
                    "action": "share"
                  },
                  "attributes": {
                    "class": "ms-fontColor-themePrimary ms-fontColor-themeDark--hover",
                    "title": "Share Item"
                  },
                  "style": {
                    "padding-top": "4px",
                    "border": "none",
                    "background-color": "transparent",
                    "cursor": "pointer"
                  },
                  "children": [
                    {
                      "elmType": "span",
                      "style": {
                        "align-content": "left",
                        "justify-content": "left",
                        "padding": "4px",
                        "white-space": "normal"
                      },
                      "attributes": {
                        "iconName": "Share",
                        "class": "ms-font-l"
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
```

 
The About column is a multi-line text column and has the below
formatting
applied.
 
![AnandVRagav_1-1637611523762.png](images/AnandVRagav_1-1637611523762.png)
 
```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/sp/column-formatting.schema.json",
  "elmType": "div",
  "style": {
    "flex-direction": "row",
    "justify-content": "start"
  },
  "children": [
    {
      "elmType": "div",
      "txtContent": "=substring(@currentField, 0, 70) + '...'",
      "style": {
        "white-space": "normal",
        "padding": "2px 0",
        "font-size": "13px",
        "margin": "6px 4px 4px -6px"
      },
      "attributes": {
        "class": ""
      }
    },
    {
      "elmType": "div",
      "attributes": {
        "title": "@currentField.description",
        "class": "ms-fontColor-neutralPrimary sp-card-content sp-card-urlContent  sp-card-content sp-card-highlightedContent",
        "iconName": "MoreVertical"
      },
      "style": {
        "margin-top": "1px",
        "font-size": "13px",
        "padding": "0 4px",
        "color": "black",
        "pointer-events": "=if (@currentField == '', 'none', 'auto')",
        "text-decoration": "=if (@currentField == '', 'none', 'auto')"
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
          "txtContent": "@currentField"
        }
      }
    }
  ]
}
```
 
The Host column is a Person type column and allows multi selection. It
has the below
formatting.

 
![AnandVRagav_2-1637611559251.png](images/AnandVRagav_2-1637611559251.png)
 
 
```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/sp/column-formatting.schema.json",
  "elmType": "div",
  "children": [
    {
      "forEach": "personIterator in @currentField",
      "elmType": "div",
      "style": {
        "border-color": "#0050ca",
        "border-style": "solid",
        "border-width": "2px",
        "width": "30px",
        "height": "30px",
        "overflow": "hidden",
        "border-radius": "50%",
        "margin": "2px",
        "display": "=if(loopIndex('personIterator') >= 3, 'none', '')"
      },
      "children": [
        {
          "elmType": "img",
          "attributes": {
            "src": "='/_layouts/15/userphoto.aspx?size=S&accountname=' + [$personIterator.email]",
            "title": "[$personIterator.title]"
          },
          "style": {
            "position": "relative",
            "top": "50%",
            "left": "50%",
            "width": "100%",
            "height": "auto",
            "margin-left": "-50%",
            "margin-top": "-50%",
            "display": "=if(length(@currentField) > 3 && loopIndex('personIterator') >= 2, 'none', '')",
            "vertical-align": "baseline"
          }
        },
        {
          "elmType": "div",
          "attributes": {
            "title": "=join(@currentField.title, ', ')",
            "class": "ms-bgColor-neutralLight ms-fontColor-neutralSecondary"
          },
          "style": {
            "width": "100%",
            "height": "100%",
            "text-align": "center",
            "line-height": "30px",
            "font-size": "14px",
            "display": "=if(length(@currentField) > 3 && loopIndex('personIterator') == 2, '', 'none')"
          },
          "children": [
            {
              "elmType": "span",
              "txtContent": "='+' + toString(length(@currentField) - (2))"
            }
          ]
        }
      ]
    }
  ]
}
```
 
The Day 1 and Day 2 columns are Hyperlink columns and have the below
formatting. The time value is stored in the Description field of the
Hyperlink field. The "Add to calendar" element holds the URL to the
event in the events
list.]
 
![AnandVRagav_3-1637611581623.png](images/AnandVRagav_3-1637611581623.png)
 
```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/sp/v2/column-formatting.schema.json",
  "elmType": "div",
  "style": {
    "white-space": "normal",
    "flex-wrap": "wrap",
    "display": "flex"
  },
  "children": [
    {
      "elmType": "div",
      "style": {
        "width": "135px",
        "flex-direction": "column",
        "border-color": "#0050ca",
        "border-style": "solid",
        "border-width": "1px",
        "box-sizing": "border-box",
        "padding": "4px 8px 5px 8px",
        "display": "flex",
        "border-radius": "4px",
        "height": "100%",
        "align-items": "left",
        "white-space": "wrap",
        "overflow": "hidden",
        "margin": "6px 4px 4px -5px"
      },
      "attributes": {
        "class": "ms-bgColor-themePrimary sp-css-borderColor-themePrimary sp-card-borderHighlight sp-card-subContainer"
      },
      "children": [
        {
          "elmType": "a",
          "attributes": {
            "title": "@currentField.description",
            "class": "ms-fontColor-neutralPrimary sp-card-content sp-card-urlContent sp-card-content sp-card-highlightedContent",
            "href": "@currentField",
            "target": "=if (@currentField== '', '', '_blank')"
          },
          "style": {
            "margin-bottom": "6px",
            "font-size": "14px",
            "padding": "0 4px",
            "color": "white",
            "pointer-events": "=if (@currentField == '', 'none', 'auto')",
            "text-decoration": "=if (@currentField == '', 'none', 'auto')"
          },
          "txtContent": "=' '+'@currentField.desc'"
        },
        {
          "elmType": "a",
          "attributes": {
            "title": "@currentField.description",
            "class": "ms-fontColor-neutralPrimary sp-card-content sp-card-urlContent  sp-card-content sp-card-highlightedContent",
            "href": "@currentField",
            "target": "=if (@currentField== '', '', '_blank')",
            "iconName": "AddEvent"
          },
          "style": {
            "margin-top": "1px",
            "font-size": "13px",
            "padding": "0 4px",
            "color": "white",
            "pointer-events": "=if (@currentField == '', 'none', 'auto')",
            "text-decoration": "=if (@currentField == '', 'none', 'auto')"
          },
          "txtContent": " View/save event",
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
                "color": "White",
                "background-color": "#3c3c3c",
                "width": "100px",
                "padding": "10px"
              },
              "txtContent": "View/add to calendar"
            }
          }
        }
      ]
    }
  ]
}
```

The Join columns are of type Hyperlink and have the below formatting
applied. The URLs stored in the Hyperlink fields are URLs to meetings
created in Microsoft
Teams
 
![AnandVRagav_4-1637611605702.png](images/AnandVRagav_4-1637611605702.png)
 
 
```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/sp/v2/column-formatting.schema.json",
  "elmType": "div",
  "style": {
    "flex-wrap": "wrap",
    "display": "flex",
    "white-space": "normal"
  },
  "children": [
    {
      "elmType": "div",
      "style": {
        "box-sizing": "border-box",
        "border-color": "=if(Date('11/17/2021') <= @now + 86400000, '#464775', 'gray'",
        "border-style": "solid",
        "border-width": "1px",
        "background-color": "=if(Date('11/17/2021') <= @now + 86400000, '#464775', 'gray')",
        "padding": "4px 8px 5px 8px",
        "display": "flex",
        "border-radius": "4px",
        "height": "50px",
        "align-items": "center",
        "white-space": "nowrap",
        "overflow": "hidden",
        "margin": "6px 4px 4px -5px"
      },
      "attributes": {
        "class": "sp-field-borderBottomRegular sp-field-borderBottomSolid sp-css-borderColor-WhiteFont"
      },
      "children": [
        {
          "elmType": "span",
          "style": {
            "font-size": "14px",
            "color": "=if(Date('11/17/2021') <= @now + 86400000, 'white', 'black')",
            "display": "inline-block",
            "padding": "0 6px"
          },
          "attributes": {
            "iconName": "TeamsLogo"
          }
        },
        {
          "elmType": "a",
          "attributes": {
            "title": "@currentField.description",
            "class": "ms-fontColor-neutralPrimary sp-card-content sp-card-urlContent sp-card-content sp-card-highlightedContent",
            "href": "=if(Date('11/17/2021') <= @now + 86400000, [$Link], ''",
            "target": "=if ([$Link] == '', '', '_blank')"
          },
          "style": {
            "font-size": "13px",
            "padding": "0 6px",
            "color": "=if(Date('11/17/2021') <= @now + 86400000, 'white', '')",
            "pointer-events": "=if ([$Link] == '', 'none', 'auto')",
            "text-decoration": "=if ([$Link] == '', 'none', 'auto')"
          },
          "txtContent": "Join",
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
                "width": "100px",
                "padding": "10px"
              },
              "txtContent": "=if(Date('11/17/2021') <= @now + 86400000, 'Join the session', 'Check back on the 17th'"
            }
          }
        }
      ]
    }
  ]
}
```
 
The Session tracks column is a Single line text column with below
formatting
applied.
 
![AnandVRagav_5-1637611630100.png](images/AnandVRagav_5-1637611630100.png)
 
 
``` {.lia-code-sample .language-js
{
  "$schema": "https://developer.microsoft.com/json-schemas/sp/v2/column-formatting.schema.json",
  "elmType": "div",
  "style": {
    "flex-wrap": "wrap",
    "display": "flex"
  },
  "children": [
    {
      "elmType": "div",
      "style": {
        "width": "135px",
        "box-sizing": "border-box",
        "padding": "4px 8px 5px 8px",
        "display": "flex",
        "border-radius": "4px",
        "height": "50px",
        "align-items": "center",
        "white-space": "nowrap",
        "overflow": "hidden",
        "margin": "6px 4px 4px -12px"
      },
      "attributes": {
        "class": {
          "operator": ":",
          "operands": [
            {
              "operator": "==",
              "operands": [
                "[$Sessiontrack]",
                "Keynote"
              ]
            },
            "sp-css-backgroundColor-BgWhite sp-field-borderBottomRegular sp-field-borderBottomSolid sp-css-borderColor-WhiteFont",
            {
              "operator": ":",
              "operands": [
                {
                  "operator": "==",
                  "operands": [
                    "[$Sessiontrack]",
                    "Product Roundtables"
                  ]
                },
                "sp-css-backgroundColor-BgDarkWhite sp-field-borderBottomRegular sp-field-borderBottomSolid sp-css-borderColor-WhiteFont",
                {
                  "operator": ":",
                  "operands": [
                    {
                      "operator": "==",
                      "operands": [
                        "[$Sessiontrack]",
                        "Breakout"
                      ]
                    },
                    "sp-css-backgroundColor-BgWhite sp-field-borderBottomRegular sp-field-borderBottomSolid sp-css-borderColor-WhiteFont",
                    {
                      "operator": ":",
                      "operands": [
                        {
                          "operator": "==",
                          "operands": [
                            "[$Sessiontrack]",
                            ""
                          ]
                        },
                        "",
                        ""
                      ]
                    }
                  ]
                }
              ]
            }
          ]
        }
      },
      "children": [
        {
          "elmType": "span",
          "style": {
            "white-space": "normal",
            "overflow": "hidden",
            "text-overflow": "ellipsis",
            "padding": "0 3px"
          },
          "txtContent": "[$Sessiontrack]",
          "attributes": {
            "class": {
              "operator": ":",
              "operands": [
                {
                  "operator": "==",
                  "operands": [
                    "[$Sessiontrack]",
                    "Keynote"
                  ]
                },
                "sp-field-fontSizeSmall sp-css-color-BlackFont",
                {
                  "operator": ":",
                  "operands": [
                    {
                      "operator": "==",
                      "operands": [
                        "[$Sessiontrack]",
                        "Product Roundtables"
                      ]
                    },
                    "sp-field-fontSizeSmall sp-css-color-BlackFont",
                    {
                      "operator": ":",
                      "operands": [
                        {
                          "operator": "==",
                          "operands": [
                            "[$Sessiontrack]",
                            "Breakout"
                          ]
                        },
                        "sp-field-fontSizeSmall sp-css-color-BlackFont",
                        {
                          "operator": ":",
                          "operands": [
                            {
                              "operator": "==",
                              "operands": [
                                "[$Sessiontrack]",
                                ""
                              ]
                            },
                            "",
                            ""
                          ]
                        }
                      ]
                    }
                  ]
                }
              ]
            }
          }
        }
      ]
    }
  ]
}
```
 

Now that the formatting is done, the list is embedded on the event page.
Select the view to be shown, hide the command bar and Apply. We will
cover the Dynamic filtering in the next section.
 
![AnandVRagav_2-1637609958440.png](images/AnandVRagav_2-1637609958440.png)
 
 
## Optional: a SharePoint list to store session tracks information

I
added a support list in my site to help users filter down the sessions
by tracks. This list is what is used to dynamically filter the sessions
list as you see in the image above. So, when the user selects the track
in the Tracks list, they will see sessions listed under the selected
track in the Sessions list.
The Tracks list has two columns, the default Title column and an About
column, which is a multi-line text column.
 



![AnandVRagav_3-1637610034852.png](images/AnandVRagav_3-1637610034852.png)

 
I have used JSON formatting of the view on this list. Create a view for
the list and apply the below JSON under "Format view"
 
![AnandVRagav_6-1637610078483.png](images/AnandVRagav_6-1637610078483.png)
 


View format JSON:
 
```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/sp/v2/tile-formatting.schema.json",
  "height": 105,
  "width": 310,
  "hideSelection": false,
  "fillHorizontally": false,
  "formatter": {
    "elmType": "div",
    "attributes": {
      "class": "sp-row-card sp-card-borderHighlight"
    },
    "style": {
      "width": "310px",
      "height": "105px",
      "border-color": "=if([$Title] =='Keynote', '#0fc373', if([$Title] =='Product Roundtables', '#ff8c0a',  if([$Title] =='Breakout', '#af78d2' '#0082f0')))",
      "border-style": "solid",
      "border-width": "2.5px",
      "border-radius": "4px",
      "background-color": "white",
      "white-space": "normal",
      "padding": "4px 4px 4px 4px",
      "font-size": "13px",
      "flex-direction": "column"
    },
    "children": [
      {
        "elmType": "div",
        "attributes": {
          "class": "ms-bgColor-white sp-css-borderColor-neutralLight sp-card-subContainer"
        },
        "children": [
          {
            "elmType": "div",
            "attributes": {
              "class": "sp-card-displayColumnContainer"
            },
            "children": [
              {
                "elmType": "div",
                "style": {
                  "background-color": "white",
                  "white-space": "normal",
                  "padding": "4px 4px 4px 4px",
                  "font-size": "17px",
                  "font-weight": "600"
                },
                "attributes": {
                  "title": "[$Title]",
                  "class": "ms-fontColor-neutralPrimary sp-card-content sp-card-highlightedContent"
                },
                "txtContent": "=if ([$Title] == '', '–', [$Title])"
              }
            ]
          },
          {
            "elmType": "div",
            "style": {
              "background-color": "white",
              "white-space": "normal",
              "padding": "0px 4px 4px 4px",
              "font-size": "14px"
            },
            "attributes": {
              "class": "sp-card-lastTextColumnContainer"
            },
            "children": [
              {
                "elmType": "p",
                "attributes": {
                  "title": "[$About]",
                  "class": "ms-fontColor-neutralPrimary sp-card-content "
                },
                "txtContent": "=if ([$About] == '', '–', [$About])"
              }
            ]
          }
        ]
      }
    ]
  }
}
```
 
 
Next, on the event page, embed the Tracks list on the right hand side
column in line with the Sessions list web
part.
 
![AnandVRagav_7-1637610296235.png](images/AnandVRagav_7-1637610296235.png)
 

With the Tracks list now embedded, we can now look at the Dynamic
filtering of the Sessions list. Connect the two lists as show in the
image illustration below and save the
page.
 
![AnandVRagav_8-1637610455816.png](images/AnandVRagav_8-1637610455816.png)

 
## a SharePoint list to store people information

For every event there
are people behind it and I have used a third list to show this
information. The reason I chose a list instead of the native people web
part is, in the available space on page, I can show 5 people in one row
using the list as opposed to 3 people with the people web part. I also
get additional control with lists in terms of formatting and what
information of the people is shown.
The people list has two columns, the default Title column and a Person
column.
 


![AnandVRagav_9-1637610530919.png](images/AnandVRagav_9-1637610530919.png)
 

Create a view for the list and apply the below JSON under "Format
view"

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/sp/v2/tile-formatting.schema.json",
  "height": 76,
  "width": 254,
  "hideSelection": false,
  "fillHorizontally": true,
  "formatter": {
    "elmType": "div",
    "attributes": {
      "class": "sp-card-container"
    },
    "children": [
      {
        "elmType": "button",
        "attributes": {
          "class": "sp-card-defaultClickButton",
          "role": "presentation"
        },
        "customRowAction": {
          "action": "defaultClick"
        }
      },
      {
        "elmType": "div",
        "attributes": {
          "class": "ms-bgColor-white sp-css-borderColor-neutralLight sp-card-borderHighlight sp-card-subContainer"
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
                    "txtContent": "=if(length([$Member]) == 0, '–', '')"
                  },
                  {
                    "forEach": "personIterator in [$Member]",
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
                          "display": "=if(length([$Member]) > 5 && loopIndex('personIterator') >= 4, 'none', '')"
                        }
                      },
                      {
                        "elmType": "div",
                        "attributes": {
                          "class": "ms-bgColor-neutralLight ms-fontColor-neutralSecondary sp-card-userOthers"
                        },
                        "style": {
                          "display": "=if(length([$Member]) > 5 && loopIndex('personIterator') == 4, '', 'none')"
                        },
                        "customCardProps": {
                          "formatter": {
                            "elmType": "div",
                            "attributes": {
                              "class": "sp-card-personCallout"
                            },
                            "children": [
                              {
                                "forEach": "personIterator in [$Member]",
                                "elmType": "div",
                                "attributes": {
                                  "class": "sp-card-userContainer sp-card-userCustomCard"
                                },
                                "style": {
                                  "display": "=if(loopIndex('personIterator') < 4, 'none', '')"
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
                            "txtContent": "='+' + toString(length([$Member]) - (4))"
                          }
                        ]
                      }
                    ]
                  },
                  {
                    "elmType": "div",
                    "attributes": {
                      "class": "sp-card-userTitle"
                    },
                    "style": {
                      "display": "=if(length([$Member]) == 1, '', 'none')"
                    },
                    "defaultHoverField": "[$personIterator]",
                    "txtContent": "[$Member.title]"
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
 
The result is a formatted people web part. Another good thing about
this it also lets the users hover/select  the people to get their
office profile
information.
 
![AnandVRagav_0-1637610654153.png](images/AnandVRagav_0-1637610654153.png)
 
Other web parts in the vertical section on the right-hand-side.
**Countdown timer:** In the vertical section I thought it would be
useful to have the countdown timer web part with a countdown towards the
event date.
 
![AnandVRagav_6-1637611708366.png](images/AnandVRagav_6-1637611708366.png)
 
## About web part

 I used the fourth list web part to show "what",
"when", "where", "who" of the event.
 
![AnandVRagav_1-1637610757197.png](images/AnandVRagav_1-1637610757197.png)
 

The list is view formatted with the below JSON
 

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/sp/v2/tile-formatting.schema.json",
  "height": 350,
  "width": 300,
  "hideSelection": true,
  "fillHorizontally": true,
  "formatter": {
    "elmType": "div",
    "attributes": {
      "class": "sp-row-card"
    },
    "children": [
      {
        "elmType": "div",
        "attributes": {},
        "customRowAction": {}
      },
      {
        "elmType": "div",
        "attributes": {
          "class": "ms-bgColor-white sp-card-subContainer"
        },
        "children": [
          {
            "elmType": "div",
            "style": {
              "background-color": "white",
              "font-size": "15px"
            },
            "attributes": {
              "class": "sp-card-displayColumnContainer"
            },
            "children": [
              {
                "elmType": "span",
                "children": [
                  {
                    "elmType": "span",
                    "style": {
                      "display": "inline-block",
                      "background-color": "white",
                      "white-space": "normal",
                      "padding": "0 4px",
                      "font-size": "15px"
                    },
                    "attributes": {
                      "class": "ms-fontColor-neutralSecondary sp-card-label",
                      "iconName": "Info"
                    }
                  },
                  {
                    "elmType": "span",
                    "style": {
                      "display": "inline-block",
                      "background-color": "white",
                      "white-space": "normal",
                      "padding": "0 4px",
                      "font-size": "15px"
                    },
                    "txtContent": "[!Title.DisplayName]"
                  }
                ]
              },
              {
                "elmType": "p",
                "style": {
                  "background-color": "white",
                  "white-space": "normal",
                  "padding": "0px 0px 10px 28px",
                  "font-size": "15px"
                },
                "attributes": {
                  "title": "[$Title]",
                  "class": "ms-fontColor-neutralPrimary sp-card-content sp-card-highlightedContent",
                  "role": "heading",
                  "aria-level": "3"
                },
                "txtContent": "=if ([$Title] == '', '–', [$Title])"
              }
            ]
          },
          {
            "elmType": "div",
            "style": {
              "background-color": "white",
              "font-size": "15px"
            },
            "attributes": {
              "class": "sp-card-displayColumnContainer"
            },
            "children": [
              {
                "elmType": "span",
                "children": [
                  {
                    "elmType": "span",
                    "style": {
                      "display": "inline-block",
                      "background-color": "white",
                      "white-space": "normal",
                      "padding": "0 4px",
                      "font-size": "15px"
                    },
                    "attributes": {
                      "class": "ms-fontColor-neutralSecondary sp-card-label",
                      "iconName": "Event"
                    }
                  },
                  {
                    "elmType": "span",
                    "style": {
                      "display": "inline-block",
                      "background-color": "white",
                      "white-space": "normal",
                      "padding": "0 4px",
                      "font-size": "15px"
                    },
                    "txtContent": "[!When.DisplayName]"
                  }
                ]
              },
              {
                "elmType": "p",
                "style": {
                  "background-color": "white",
                  "white-space": "normal",
                  "padding": "0px 0px 10px 28px",
                  "font-size": "15px"
                },
                "attributes": {
                  "title": "[$Title]",
                  "class": "ms-fontColor-neutralPrimary sp-card-content sp-card-highlightedContent",
                  "role": "heading",
                  "aria-level": "3"
                },
                "txtContent": "=if ([$When] == '', '–', [$When])"
              }
            ]
          },
          {
            "elmType": "div",
            "style": {
              "background-color": "white",
              "font-size": "15px"
            },
            "attributes": {
              "class": "sp-card-displayColumnContainer"
            },
            "children": [
              {
                "elmType": "span",
                "children": [
                  {
                    "elmType": "span",
                    "style": {
                      "display": "inline-block",
                      "background-color": "white",
                      "white-space": "normal",
                      "padding": "0 4px",
                      "font-size": "15px"
                    },
                    "attributes": {
                      "class": "ms-fontColor-neutralSecondary sp-card-label",
                      "iconName": "TeamsLogo"
                    }
                  },
                  {
                    "elmType": "span",
                    "style": {
                      "display": "inline-block",
                      "background-color": "white",
                      "white-space": "normal",
                      "padding": "0 4px",
                      "font-size": "15px"
                    },
                    "txtContent": "[!Where.DisplayName]"
                  }
                ]
              },
              {
                "elmType": "p",
                "style": {
                  "background-color": "white",
                  "white-space": "normal",
                  "padding": "0px 0px 10px 28px",
                  "font-size": "15px"
                },
                "attributes": {
                  "title": "[$Title]",
                  "class": "ms-fontColor-neutralPrimary sp-card-content sp-card-highlightedContent",
                  "role": "heading",
                  "aria-level": "3"
                },
                "txtContent": "=if ([$Where] == '', '–', [$Where])"
              }
            ]
          },
          {
            "elmType": "div",
            "style": {
              "background-color": "white",
              "font-size": "15px"
            },
            "attributes": {
              "class": "sp-row-cardr"
            },
            "children": [
              {
                "elmType": "span",
                "children": [
                  {
                    "elmType": "span",
                    "style": {
                      "display": "inline-block",
                      "background-color": "white",
                      "white-space": "normal",
                      "padding": "0 4px",
                      "font-size": "15px"
                    },
                    "attributes": {
                      "class": "ms-fontColor-neutralSecondary sp-card-label",
                      "iconName": "Group"
                    }
                  },
                  {
                    "elmType": "span",
                    "style": {
                      "display": "inline-block",
                      "background-color": "white",
                      "white-space": "normal",
                      "padding": "0 4px",
                      "font-size": "15px"
                    },
                    "txtContent": "[!Who.DisplayName]"
                  }
                ]
              },
              {
                "elmType": "p",
                "style": {
                  "background-color": "white",
                  "white-space": "normal",
                  "padding": "0px 0px 10px 28px",
                  "font-size": "15px"
                },
                "attributes": {
                  "title": "[$Title]",
                  "class": "ms-fontColor-neutralPrimary sp-card-content sp-card-highlightedContent",
                  "role": "heading",
                  "aria-level": "3"
                },
                "txtContent": "=if ([$Who] == '', '–', [$Who])"
              }
            ]
          }
        ]
      }
    ]
  }
}
```
 
Finally towards the end of the event page, I added a Microsoft Forms
link to collect a Net promoter score feedback question, and this would
help me understand how users feedback the
event.
 
The final result is an event page made with SharePoint, and enhanced by
SharePoint Spaces, Formatted Lists and other web parts.

 
I believe SharePoint offers some amazing opportunities to create pages
that can meet a variety of business needs.
Hope
you found the information in this post useful and I would love to see
how you implement this and how you might enhance this. Feel free to
comment. 
