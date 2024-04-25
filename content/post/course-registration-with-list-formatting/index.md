---
title: "Course registration with List formatting"
date: 2022-01-17T12:43:00-05:00
author: "Dennis Goedegebuure"
githubname: expiscornovus
categories: ["Community post"]
images:
- images/51695169286_ae7588984b_c.jpg
tags: ["List formatting", "SharePoint", "PnP PowerShell"]
type: "regular"
---

Recently [Tetsuya](https://twitter.com/techan_k) and [Michel](https://twitter.com/michelcarlo) shared
some great examples of a new option in List formatting, the setValue
action within List formatting. This blog shows an example on how to use
list formatting to create registration or sign-up formatting in a
SharePoint list. 

### ![51695169286_ae7588984b_c.jpg](images/51695169286_ae7588984b_c.jpg)

### Course Registration
 
One of the examples I have seen a lot on the Power Automate community is
registration or sign-up in a SharePoint list. A lot of times a Power
Automate flow would be needed to meet the requirements in these kind of
scenarios. In this article I am going to show you can use the setValue
action to meet most of your requirements without the need of building a
flow.
 
Assume we have the following requirements:

- A user can register for one or several courses
- A course has a number of available places, when all places are taken
registration is not possible
- There is a registration end date, after this registration is not
possible
 
### SharePoint Online list
 
First of all you would need to create the SharePoint Online list and the
columns. To give you a head-start a create a PnP PowerShell script for
this. Feel free to reuse it.
 
 
 
```powershell
<# .SYNOPSIS
    Create list for Course registration.
.DESCRIPTION
    You need to have the latest version of PnP PowerShell
    Create list for Course registration.
.PARAMETER SiteCollection
    Specifies the site collection Url of the SharePoint Online environment.
.PARAMETER ListName
    Specifies the name of the SharePoint Online list.
.NOTES
    Author:
    Expiscornovus
    Current Version:
    0.1
    Version History:
    0.1 - First minor version
.EXAMPLE
    PS> .\create_courseregistration_spolist.ps1 -SiteCollection "https://contoso.sharepoint.com/sites/formatting" -ListName "Courses"

#>
param ([Parameter(Mandatory)]$SiteCollection,[Parameter(Mandatory)]$ListName)
Connect-PnPOnline -Url $SiteCollection -Interactive
New-PnPList -Title $ListName -Template GenericList
Add-PnPField -List $ListName -DisplayName "Registration End Date" -InternalName "RegistrationEndDate" -Type DateTime
Add-PnPField -List $ListName -DisplayName "Course Date" -InternalName "CourseDate" -Type DateTime
Add-PnPField -List $ListName -DisplayName "Register" -InternalName "Register" -Type Text
Add-PnPField -List $ListName -DisplayName "Number of Available Places" -InternalName "NumberofPlaces" -Type Number
Add-PnPFieldFromXml -List $ListName -FieldXml '<Field Type="UserMulti" DisplayName="People Who Registered" UserSelectionMode="PeopleOnly" StaticName="PeopleWhoRegistered" Name="PeopleWhoRegistered" Mult="TRUE" />'
Add-PnPView -List $ListName -Title "All Courses" -Fields "Title","RegistrationEndDate","CourseDate","Register","NumberofPlaces","PeopleWhoRegistered"
Disconnect-PnPOnline
```
 
 
 
### Change format Register column
 
1.  Navigate to your newly created list and select Column settings \>
Format this column.
 
![51695571178_b626326204_c.jpg](images/51695571178_b626326204_c.jpg)
 
1. Insert the json below and select save.
 
 
 
```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/sp/v2/column-formatting.schema.json",
  "elmType": "div",
  "style": {
    "flex-directon": "row",
    "justify-content": "left",
    "align-items": "center",
    "flex-wrap": "nowrap"
  },
  "children": [
    {
      "elmType": "div",
      "style": {
        "display": "=if(indexOf([$PeopleWhoRegistered.email], ) == -1 && length([$PeopleWhoRegistered]) != [$NumberofPlaces] && @now <= [$RegistrationEndDate], 'inherit','none')",
        "flex-directon": "row",
        "justify-content": "left",
        "align-items": "center",
        "flex-wrap": "wrap"
      },
      "children": [
        {
          "elmType": "button",
          "customRowAction": {
            "action": "setValue",
            "actionInput": {
              "Text": "Update",
              "PeopleWhoRegistered": "=appendTo([$PeopleWhoRegistered], )"
            }
          },
          "attributes": {
            "class": "ms-fontColor-themePrimary ms-fontColor-themeDarker--hover"
          },
          "style": {
            "border": "none",
            "background-color": "transparent",
            "cursor": "pointer",
            "display": "flex",
            "flex-directon": "row",
            "justify-content": "left",
            "align-items": "center",
            "flex-wrap": "wrap"
          },
          "children": [
            {
              "elmType": "span",
              "attributes": {
                "iconName": "AddTo"
              },
              "style": {
                "padding": "0px"
              }
            }
          ]
        }
      ]
    },
    {
      "elmType": "div",
      "children": [
        {
          "elmType": "span",
          "txtContent": "Already Registered",
          "style": {
            "display": "=if(indexOf([$PeopleWhoRegistered.email], ) == -1, 'none','inherit')",
            "padding-left": "5px",
            "word-break": "keep-all"
          }
        }
      ]
    },
    {
      "elmType": "div",
      "children": [
        {
          "elmType": "span",
          "txtContent": "Course is full",
          "style": {
            "display": "=if(length([$PeopleWhoRegistered]) != [$NumberofPlaces], 'none','inherit')",
            "padding-left": "5px",
            "word-break": "keep-all"
          }
        }
      ]
    },
        {
      "elmType": "div",
      "children": [
        {
          "elmType": "span",
          "txtContent": "Registration has ended",
          "style": {
            "display": "=if(@now <= [$RegistrationEndDate], 'none','inherit')",
            "padding-left": "5px",
            "word-break": "keep-all"
          }
        }
      ]
    }
  ]
}
```
 
 
 
### Explanation of the json
 
First we try to handle the showing/hiding of the register button. This
is done in the display property of the div.
 
 
 
```json
if(indexOf([$PeopleWhoRegistered.email], ) == -1 && length([$PeopleWhoRegistered]) != [$NumberofPlaces] && @now <= [$RegistrationEndDate], 'inherit','none')
```
 
 
 
In this formula I am using a conditional
operator [if()](https://learn.microsoft.com/sharepoint/dev/declarative-customization/formatting-syntax-reference#expressions).
In that if statement I am checking if three things are all true.

1.  If the e-mail of the person who is creating the list item is not
registered. This expression is using
a [IndexOf](https://learn.microsoft.com/sharepoint/dev/declarative-customization/formatting-syntax-reference#operators) binary
operator and
a [@me](https://learn.microsoft.com/sharepoint/dev/declarative-customization/formatting-syntax-reference#special-string-values) special
string value. When the expression returns -1 it hasn't found the e-mail
and the button will still be shown.
2. It will compare
the [length](https://learn.microsoft.com/sharepoint/dev/declarative-customization/formatting-syntax-reference#operators) unary
operator to check the number of people registered for the current
course. When that isn't equal the number of available places the
register button will still be shown.
3. If the current date is before the registration date the register
button will still be shown.
The [@now](https://learn.microsoft.com/sharepoint/dev/declarative-customization/formatting-syntax-reference#special-string-values) special
string value is used for this.
In the bottom of the json I am using the same expressions only in
individual divs and the true false values will be in reserve. This is to
show a custom message when one of the conditions is met.
 
 
 
```json
{
          "elmType": "button",
          "customRowAction": {
            "action": "setValue",
            "actionInput": {
              "Text": "Update",
              "PeopleWhoRegistered": "=appendTo([$PeopleWhoRegistered], )"
            }
          }
```
 
 
 
And finally the start of this blog, the customRowAction with
a [setValue](https://learn.microsoft.com/sharepoint/dev/declarative-customization/formatting-syntax-reference#customrowaction).
In this case I am using
a [appendTo](https://learn.microsoft.com/sharepoint/dev/declarative-customization/formatting-syntax-reference#operators) binary
operation to add the person who is creating the list item to the
existing list of people who registered.
