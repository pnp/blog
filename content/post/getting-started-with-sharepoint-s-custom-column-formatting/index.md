---
title: "Getting started with SharePoint's custom column formatting"
date: 2021-03-14T10:08:00-04:00
author: "Will Holland"
githubname: willholland
categories: ["Community post"]
images:
- images/Will_Holland_0-1615739594928.png
tags: ["Microsoft lists", "SharePoint", "List formatting"]
type: "regular"


---

Have you ever wished that you could turn your boring old SharePoint
list, full of useful data as it may be, into something with a little
more pizzazz? And not just the simple (but highly effective) conditional
formatting that SharePoint can give you for free, but something truly
outside of the box.

Continue reading to learn how to turn this\....

![Will_Holland_0-1615739594928.png](images/Will_Holland_0-1615739594928.png)

...into something like this...

![Will_Holland_1-1615739594936.png](images/Will_Holland_1-1615739594936.png)

## What do you need to get started? 

Thankfully, custom formatting isn't terribly complicated, although it
does take some getting used to. The only thing you'll absolutely need is
a modern SharePoint list with some columns, a basic understanding of
JSON ([this post has you
covered](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/introduction-to-json/ba-p/2049369)),
and some patience.
You'll also need to know that you can customize most, but not all,
column types in SharePoint online. As of this writing, you cannot
customize the following field types: Managed Metadata, Filename (in
Document Libraries), Retention Label, Sealed columns, Multi-line text
column with enhanced rich text.
If you have it, some experience with HTML and CSS will come in handy, as
would a little familiarity with Excel style functions, but none of it is
required to just get started.
If you haven't already, you may also want to at least scan through the
official [documentation for column
formatting](https://docs.microsoft.com/sharepoint/dev/declarative-customization/column-formatting#get-started-with-column-formatting)
to get yourself acquainted with the schema used.

## Schema Basics 

The key to creating your custom column formatting will be in
understanding the basics of the JSON schema used to define your
presentation. Basically, what you're attempting to do is describe some
basic HTML elements and CSS styles using JSON.
Every definition will follow the same basic pattern: An object
representing an HTML element, with optional attributes, CSS styling, and
child elements.
 

```json
{
    "$schema": "https://developer.microsoft.com/json-schemas/sp/v2/column-formatting.schema.json",
    "elmType": "div",
    "attributes": {
        "iconName": "Game"
    },
    "style": {
        "font-size": "48px",
        "color": "red"
    }
}
```
 

In the above sample, we're defining our object as an HTML div element. A
div is just a container for other HTML elements, such as text, images,
links or even other divs. There are other valid values for "elmType" as
well, such as 'span'; 'button'; and 'img'; just to name a few.
In the case here, we're also declaring that our div has an attribute
named "iconName" with a value of "Game". We're also defining the CSS
styling we want to use, setting the font size and color to 'big and
red'.
This definition would turn any column in our list into the below.
![Will_Holland_2-1615739594938.png](images/Will_Holland_2-1615739594938.png)

Our definition only has one element being defined. If all we wanted to
do was display the icon, then we're all set. But what if we also want to
show the text content that was originally being displayed as well?
 

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/sp/v2/column-formatting.schema.json",
  "elmType": "div",
  "style": {
    "width": "48px",
    "display": "block",
    "text-align": "center"
  },
  "children": [
    {
      "elmType": "div",
      "attributes": {
        "iconName": "Game"
      },
      "style": {
        "font-size": "48px",
        "color": "red"
      }
    },
    {
      "elmType": "div",
      "txtContent": "@currentField"
    }
  ]
}
```
 

With this, we've changed our root element to act as a container for two
children. The first child is the same as the original example. The
second child is another div that simply displays the string value of the
column, resulting in the following:
![Will_Holland_3-1615739594938.png](images/Will_Holland_3-1615739594938.png)

## Working with text 

In the last example, we used the *txtContent* property and the
**@currentField** built-in variable. For basic SharePoint field types,
such as text, you can simply do like what was done in that example.
However, some field types -- such as people or date fields - may require
a little extra work.
"There and back again" to the original example with Frodo, you may
have noticed the 'Age' column (yes, Frodo was 50 years old when he
leaves on his adventure). Here is the definition used for the
transformation shown at the beginning.
 

```json
{
    "$schema": "https://developer.microsoft.com/json-schemas/sp/v2/column-formatting.schema.json",
    "elmType": "span",
    "txtContent": "@currentField.displayValue",
    "style": {
        "font-family": "Luminari, Papyrus, Brush Script MT",
        "font-size": "28px",
        "text-align": "center"
    }
}
```

### Raw value vs Display value 

Notice how it's using that **displayValue** property of
**@currentField**? We could have simply done like in the original
example and simply referenced the **@currentField** and have gotten
away with it except that it would only display the raw numeric value,
such as 1234 (sans comma).
By adding the additional property, we're telling SharePoint to "give us
the text as you would have displayed it". For Frodo, there's no
noticeable change, but once we get to some of the longer lived folk in
Middle Earth we'll see the difference.
Here's a before-and-after of what we get if we omit the property and
when we include it...

![Will_Holland_4-1615739594943.png](images/Will_Holland_4-1615739594943.png)

It's a subtle but impactful difference.

### Font styling 

You'll also see that we're not using the standard font to display our
age. We can use the CSS 'font-family' property to use a non-standard
font. In this sample, we've suggested three different styles of font to
use. The browser will attempt to use them in the order specified,
falling back to the next on the list if it doesn't know about the first.
Not all fonts or font-families may be supported and it's a bit of
trial-and-error to find the right one. In general, stick "Web Safe
Fonts" and you'll be alright.

### Working with People fields 

Like with number fields, people fields also have a set of extra
properties we can use to display different things related to our people.
Below is a complete example of a user object.
 

```json
{
   "id": "122",
   "title": "Kalya Tucker",
   "email": "kaylat@contoso.com",
   "sip": "kaylat@contoso.com",
   "picture": "https://contoso.sharepoint.com/kaylat_contoso_com_MThumb.jpg?t=63576928822",
   "department":"Human Resources",
   "jobTitle":"HR Manager"
}
```
 

From this, we can see that that user's display name -- Kayla Tucker --
is stored in the *title* property and the URL for their profile picture
is stored in the "picture" property.
We can use that knowledge (and some CSS) to turn the standard people
picker into something with a little more flair.
![Will_Holland_5-1615739594946.png](images/Will_Holland_5-1615739594946.png)
Here's the JSON definition.
 

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/sp/v2/column-formatting.schema.json",
  "elmType": "div",
  "style": {
    "display": "flex",
    "flex-direction": "column"
  },
  "children": [
    {
      "elmType": "img",
      "attributes": {
        "src": "@currentField.picture",
        "class": "ms-borderColor-themePrimary"
      },
      "style": {
        "border-width": "5px",
        "border-style": "solid",
        "border-radius": "15px"
      }
    },
    {
      "elmType": "div",
      "txtContent": "@currentField.title",
      "style": {
        "margin": "auto",
        "font-family": "Luminari, Papyrus, Brush Script MT",
        "font-size": "1.25em"
      }
    }
  ]
}
```
 

Our schema defines a parent **div** with two child elements: an
**img** element and another **div** for our text.
Our image element has an *attributes* property, which is an object that
has two properties defined: *src & img*.
The *src* property, which is required for all *img* elements, tells
SharePoint where to find the image, which we're specifying as the
location for the **picture** property of the user field.
The other property, *class*, is available for all elements and allows us
to specify a particular CSS class to the element. In this case, we're
telling it to use one of the built-in CSS classes available in
SharePoint. Using these, we can support using theme colors without
worrying about what happens when someone changes the current theme.

### Working with expressions 

There will be plenty of cases where we need to use some programmatic
logic to accomplish your goals. Let's look at our "Race" column example.
Among members of the *Fellowship of the Ring* are representatives of
five of the different races that populate Middle Earth: Ainur, Elf,
Dwarf, Human and Hobbit.
We have a choice column to represent the valid options for our members
but, rather than simply display the name of the race, let's see how we
make the following transformation.
![Will_Holland_6-1615739594947.png](images/Will_Holland_6-1615739594947.png)

Here's the definition:
 

```json
{
    "$schema": "https://developer.microsoft.com/json-schemas/sp/v2/column-formatting.schema.json",
    "elmType": "img",
    "style": {
        "width": "48px"
    },
    "attributes": {
        "src": "=@currentWeb + '/SiteAssets/RaceIcons/' + @currentField + '.svg'",
        "alt": "@currentField"
    }
}
```
 

We've taken some images, which were found -- and purchased -- a website
(there's a link included in the resources section at the end of this
post), and uploaded them into a folder named "RaceIcons" inside of the
standard Site Assets library on my SharePoint site. They're also named
exactly the same as the available choices in the **Race** field on our
list.
By structuring my pictures in this way, I can use an Excel-style
expression to display the right image for the selected race with little
effort.

### Working with multi-valued fields 

Many fields in SharePoint allow the selection of multiple values, such
as lookups, people and choice columns. In these cases, we need to use a
special attribute named *forEach*.
Let's look at our **Weapons** multi-choice field transformation to see
how this works. Perhaps my favorite character to see battling it out on
screen was Gandalf. Watching him swinging a sword and staff around was
really exciting, so we'll use him as our example.
\

![Will_Holland_7-1615739594949.png](images/Will_Holland_7-1615739594949.png)
Here's our definition.
 

```json
{
    "$schema": "https://developer.microsoft.com/json-schemas/sp/v2/column-formatting.schema.json",
    "elmType": "div",
    "children": [{
        "forEach": "weapon in @currentField",
        "elmType": "img",
        "attributes": {
            "src": "=@currentWeb + '/SiteAssets/WeaponIcons/' + [$weapon] + '.svg'",
            "alt": "[$weapon]"
        },
        "style": {
            "display": "flex",
            "height": "32px",
            "margin": "auto"
        }
    }]
}
```
 

Like the previous example, we've loaded up some images in well-known
location, and we've made sure that we've named our image files the same
as the corresponding choices available in the choice field.
What's special here is the use of the *forEach* attribute. The value
"**weapon in @currentField**" tells SharePoint "*Hey, for each selected
option, create a copy of this element*"; in this case, our image
element.
You'll also notice that in our *src* attribute, instead of using the
*@currentField* built-in, we're using the **\[\$weapon\]** variable.
Whatever text you put in front of "**in @currentField**" will be your
variable name, so if we had said "**thing in @currentField**", our
variable would be **\[\$thing\]**.

### Dealing with conditions 

Plenty of times, you'll want to render things differently based on
certain conditions. SharePoint offers a lot built-in support for
conditional formatting if all you need to do is change the text or
background color. A common example would be to set the background or
font color of a "Due Date" field to red if the date has passed.
If you need something more, though, we can use the *if* function in an
expression in our custom formatting.
In our example, the **Role** field is a simple text field used to
describe what role the member had within the group, but rather than
display that text we want to display a different Fabric icon depending
on the role.
![Will_Holland_8-1615739594955.png](images/Will_Holland_8-1615739594955.png)
And here's the definition.
 

```json
{
    "$schema": "https://developer.microsoft.com/json-schemas/sp/v2/column-formatting.schema.json",
    "elmType": "div",
    "style": {
        "width": "48px",
        "height": "48px",
        "font-size": "32px",
        "background-color": "green",
        "color": "white"
    },
    "children": [{
        "elmType": "div",
        "style": {
            "margin": "auto"
        },
        "attributes": {
            "iconName": "=if(@currentField == 'Ring-bearer', 'StatusCircleRing', if(@currentField == 'Guardian', 'Shield', if(@currentField == 'Melee', 'DecisionSolid', 'Bullseye')))"
        }
    }]
}
```
 

For the *iconName* property value, we're using an *if* expression to
walk through the possible conditions until we find the right one.
The *if* expression is straightforward: *if( \<condition to evaluate>, 
\<value if true>, \<value if false>).* Where it gets a little difficult
is when you have multiple conditions, like we do in our example.
In our example, all but the last condition have another *if* statement
for the "value if false" part. To read our statement in English would go
something like this:
"If 'role' is equal to 'Ring-bearer', then use the 'StatusCircleRing'
icon. Otherwise, if 'role' is equal to 'Guardian', then use the the
'Shield' icon. Otherwise, if 'role' is equal to 'Melee', then use the
'DecisionSolid' icon. Otherwise, just use the 'Bullseye' icon".

### A final example 

For our final example, we'll look at the last column in our list:
**From**.
The **From** column is a lookup column that references list items in a
*Middle Earth Locales* list.
![Will_Holland_9-1615739594966.png](images/Will_Holland_9-1615739594966.png)
And the definition\...
 

```json
{
    "$schema": "https://developer.microsoft.com/json-schemas/sp/v2/column-formatting.schema.json",
    "elmType": "div",
    "style": {
        "display": "flex",
        "flex-direction": "column",
        "text-align": "center",
        "font-family": "Luminari, Papyrus, Brush Script MT",
        "font-size": "18px"
    },
    "children": [{
            "elmType": "img",
            "attributes": {
                "src": "=@currentWeb + '/SiteAssets/MiddleEarthLocales/' + @currentField.lookupValue + '.jpg'"
            },
            "style": {
                "height": "48px",
                "width": "48px",
                "border-width": "3px",
                "border-style": "solid",
                "border-color": "=if(@currentField.lookupValue == 'The Shire', 'brown', if(@currentField.lookupValue == 'Rivendell', 'purple', if(@currentField.lookupValue == 'Osgiliath', 'grey', if(@currentField.lookupValue == 'Mirkwood Forest', 'green', if(@currentField.lookupValue == 'Blue Mountains', 'blue', 'gold')))))",
                "border-radius": "100px"
            }
        },
        {
            "elmType": "div",
            "txtContent": "@currentField.lookupValue"
        }
    ]
}
```
 

There's not much new in this example, aside from the use of a lookup
field and its *lookupValue* property to display the value (there's also
a *lookupId* property available, if you need it) but it does illustrate
how we can take all of the previous tactics to create something unique.

## One DOES simply create awesome list visuals 

We've been through all of our columns and we've covered all of the basic
building blocks for creating amazing visuals and really spicing up the
life of our list data, creating a great little breakdown of information
related to members of the Fellowship with interesting visuals and
colors.
![Will_Holland_10-1615739594999.png](images/Will_Holland_10-1615739594999.png)
 

Now that you've seen it all come together, time to get out there and
start your own journey!

## Additional Resources

While this post was pretty long, it still couldn't quite cover
*everything* out there. Below are some additional resources you may find
useful.

* [Examples Repository
(github.com)](https://github.com/willholland/getting-started-with-custom-formatting) -- My repository containing all of the JSON definitions shown in this
blog, as well as a PnP provisioning template you can use to provision
everything.
* [Use column formatting to customize SharePoint | Microsoft
Docs](https://docs.microsoft.com/sharepoint/dev/declarative-customization/column-formatting#get-started-with-column-formatting) -- The official documentation for custom column formatting.
* [Flicon - Fluent UI Icon Search](https://www.flicon.io/)-- A super
handy tool for finding the right Fabric UI icon.
* [SharePoint List Formatting Samples
(pnp.github.io)](https://pnp.github.io/List-Formatting/) -- A PnP
community driven repository of custom column & view formatting samples.
A great place to go to get inspired, or look for other samples if
Hobbits aren't your thing.
* [Iconfinder.com](https://www.iconfinder.com/) -- This is the site I used
to purchase the icons shown for weapons and races.
