---
title: "Hiding the SharePoint page title with Power Automate"
date: 2021-09-14T06:30:00-04:00
author: "Michel Mendes"
categories: ["SharePoint", "Power Automate"]
images:
- images/blog/hiding-the-sharepoint-page-title-with-power-automate/page-title.png
tags: []
type: "regular"
draft: false

---

For any SharePoint modern page that you create manually, there will
always be a page title that you cannot remove using the SharePoint UI at
the moment.
{{< image alt="page-title.png" src="images/blog/hiding-the-sharepoint-page-title-with-power-automate/page-title.png" >}}

The logic behind those options is that on the background they change a
hidden field in the Page, which is the **PageLayoutType** field. This
field is not exposed through the UI but is accessible and editable
through the SharePoint REST API.
If the data is accessible and editable through the SharePoint REST API,
we can manipulate it using a Power Automate flow.
**The idea behind the flow**
To be able to remove the page title using a flow as mentioned above, the
main idea is to build a flow that simply switches the page layout by
updating the **PageLayoutType** field.
If it is a normal page (Article), this flow will switch it to a page
with the home page layout (no title), and vice versa (in case there is a
need to show the title again).
{{< image alt="running-flow.gif" src="images/blog/hiding-the-sharepoint-page-title-with-power-automate/running-flow.gif" >}}
So we want to make this flow available from the library UI, and for this
to happen we need to use the SharePoint flow Trigger: **For a Selected
File**.
Select the site you want to use this functionality. And add the library
too.
{{< image alt="for-a-selected-file.png" src="images/blog/hiding-the-sharepoint-page-title-with-power-automate/for-a-selected-file.png" >}}
Note that the Pages Library is not listed on the options for the
triggers, however, you can add the list manually by adding its id
(GUID), which can be found on the library settings page URL:
{{< image alt="list id.PNG" src="images/blog/hiding-the-sharepoint-page-title-with-power-automate/list id.PNG" >}}

**Accessing Page Data**
For the next steps, we need to use data returned by the flow trigger to
be able to get the current page layout and list item Id from the current
page.
First, manipulate the page relative URL+ site id from data returned by
the Flow's trigger.
Initialise one variable called PageUrl and set it to the property
'**itemUrl**', gathered from the flow's trigger:
{{< image alt="PageURL.PNG" src="images/blog/hiding-the-sharepoint-page-title-with-power-automate/PageURL.PNG" >}}
Then initialise two variables using the following expressions as value
(their values are simply set by manipulating the page full URL by
splitting it and getting the right piece of the string):
**SiteURL**: split(variables('PageUrl'),'SitePages')\[0\]
**PagePath:** split(variables('PageUrl'),'sharepoint.com')\[1\]
{{< image alt="vars.PNG" src="images/blog/hiding-the-sharepoint-page-title-with-power-automate/vars.PNG" >}}

Then you can make a call using REST API to
the **GetFileByServerRelativeUrl **endpoint to retrieve the list item
fields for the current page (explicitly selecting the PageLayoutType
field, otherwise, it wouldn't be returned):
{{< image alt="send an http get data.PNG" src="images/blog/hiding-the-sharepoint-page-title-with-power-automate/send an http get data.PNG" >}}
Use the **Parse JSON** action with the schema below to facilitate
accessing the properties:
 

``` {.lia-code-sample .language-json}
{
    "type": "object",
    "properties": {       
        "Title": {
            "type": "string"
        },
        "PageLayoutType": {
            "type": "string"
        },
        "ID": {
            "type": "integer"
        }
    }
}
```
 

And initialise a new variable called **PageLayout**, having
the **PageLayoutType **parsed from the JSON content as value:
{{< image alt="parse json.PNG" src="images/blog/hiding-the-sharepoint-page-title-with-power-automate/parse json.PNG" >}}
**Updating the Page Layout**
Based on the current page layout value, you can update the variable
value to the other desired (if it is **Home**, you should update it
to **Article**, if it is **Article **you should update it to **Home**.
{{< image alt="switch value.PNG" src="images/blog/hiding-the-sharepoint-page-title-with-power-automate/switch value.PNG" >}}
And then send a **PATCH **HTTP request to SharePoint to update the
current page field:
{{< image alt="patch.PNG" src="images/blog/hiding-the-sharepoint-page-title-with-power-automate/patch.PNG" >}}

**Results**
When you execute the flow, it will switch the page layout as below. If
you execute it again, it will switch back to the previous layout (from
Article to Home or from Home to Article):
{{< image alt="running-flow.gif" src="images/blog/hiding-the-sharepoint-page-title-with-power-automate/running-flow.gif" >}}
 

**Reusing the flow in other Page Libraries**
If you built the flow as demonstrated above, it will be getting the site
and library dynamically based on the trigger values. So, it can be
reused in more libraries using list formatting.
Simply add the column formatting JSON below (sample edited from
Microsoft 365 PnP repository) to a dummy calculated column with fixed
text in other pages library (use the calculated column, so it is hidden
from forms).
Replace the id on the **ActionParams **property with your Flow ID, and
by clicking the button added to this column with the JSON formatter, the
same flow will be called as if it was triggered from the Automate menu.
 

``` {.lia-code-sample .language-json}
  "$schema": "https://developer.microsoft.com/json-schemas/sp/column-formatting.schema.json",
  "elmType": "button",
  "customRowAction": {
    "action": "executeFlow",
    "actionParams": "{"id": "a9dcaeec-61f9-4dd1-9561-679b15bc3e22"}"
  },
  "attributes": {
    "class": "ms-fontColor-themePrimary ms-fontColor-themeDarker--hover"
  },
  "style": {
    "border": "none",
    "background-color": "transparent",
    "cursor": "pointer"
  },
  "children": [
    {
      "elmType": "span",
      "attributes": {
        "iconName": "ChangeEntitlements"
      },
      "style": {
        "padding-right": "6px"
      }
    },
    {
      "elmType": "span",
      "txtContent": "Switch Layout"
    }
  ]
}
```
 

To find your Flow id, just check the URL used when you edit it:
{{< image alt="flow id.PNG" src="images/blog/hiding-the-sharepoint-page-title-with-power-automate/flow id.PNG" >}}

You can then start it normally from any other Site Pages library in the
tenant, where you add the column with the JSON formatting calling the
flow:
{{< image alt="switch_flow.PNG" src="images/blog/hiding-the-sharepoint-page-title-with-power-automate/switch_flow.PNG" >}}
If you run the flow from a library where it was called using only the
formatter, the values will be parsed correctly from the trigger and the
flow will be executed successfully, as the JSON format button sends data
related to the currently selected file and we run the rest of the flow
dynamically based on the values sent by the trigger.\
\
This sample flow is available on the Microsoft 365 PnP Power Automate
Samples
repository: <https://github.com/pnp/powerautomate-samples/tree/main/samples/sharepoint-hide-page-title>
