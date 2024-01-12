---
title: "Introduction to JSON"
date: 2021-02-10T11:47:00-05:00
author: "Bob German"
githubname: BobGerman
categories: []
images:
- images/AdaptiveCardJSON.png
tags: []
type: "regular"

---

It seems like JSON is everywhere these days. [Adaptive cards](https://adaptivecards.io/), [Microsoft Teams app manifests](https://learn.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema?WT.mc_id=m365-00000-rogerman), and [SharePoint list formats](https://learn.microsoft.com/sharepoint/dev/declarative-customization/column-formatting?WT.mc_id=m365-00000-rogerman) are all written in JSON. And JSON is the de-facto standard for REST APIs like [Microsoft Graph](https://learn.microsoft.com/graph/overview?WT.mc_id=m365-00000-rogerman); you can't make a call without it. [Power Apps](https://learn.microsoft.com/powerapps/maker/canvas-apps/functions/function-json?WT.mc_id=m365-00000-rogerman), [Power Automate](https://learn.microsoft.com/power-automate/data-operations?WT.mc_id=m365-00000-rogerman), and [Power BI](https://learn.microsoft.com/power-query/connectors/json?WT.mc_id=m365-00000-rogerman) can all handle JSON too. It really is everywhere except, it seems, in older products which were written when XML was king.

The intent of this article is to teach you what you need to know to use JSON in typical IT, low-code, or JavaScript development scenarios. It's organized in order from simple to complex; if you don't need some sections, just skip over them; you can always come back and read them later!

![Two examples of JSON in Adaptive Card Designer](images/AdaptiveCardJSON.png)

Working with JSON in the [Adaptive Card Designer](https://adaptivecards.io/designer/ "Adaptive Card Designer")

## What is JSON?

JSON is a standard format for representing structured data as text. JSON is commonly used to store data in text files and to exchange data between programs over a network. JSON files usually have a `.json` filename extension.

> Geek Note: JSON serves more or less the same purpose as XML
> (eXtensible Markup Language) but it's shorter and easier to read. CSV
> format serves a similar purpose as well, but it's not a standard so
> the details tend vary, and it can only store tables (rows and columns)
> of data.

JSON data is organized as "objects" which contain name/value pairs. This example is the first step toward building a profile for Parker, the PnP mascot, who has kindly agreed to share personal information for this article.

```JSON
{ "name": "Parker" }
```

JSON objects always begin with `{` and end with `}`; the very shortest valid JSON, `{}`, represents an empty object. The JSON example above contains a single name/value pair; the name is `name` and the value is `"Parker"`. As you can see, the name and value are separated by a `:`. Names are case sensitive and need to be enclosed in double quotes. In this case, since \"Parker\" is a text value, it's enclosed in double quotes as well. Spaces, tabs, and newlines are ignored in JSON, but are helpful for readability.

The values can be simple things like text strings or numbers, collections of values (arrays), or more objects containing their own name/value pairs. If you want to put more than one name/value pair in your JSON, separate them with commas like this:

```JSON
{
  "name": "Parker",
  "species": "porcupine"
}
```

Note that the order of the name/value pairs doesn't matter; this JSON is equivalent to the one above:

```JSON
{
  "species": "porcupine",
  "name": "Parker"
}
```

The values don't need to be text like \"Parker\"; they can also be numbers, booleans, collections, or more JSON objects. This allows you to have objects within objects. Here's a more complete description of the Quilled Crusader that uses all of the JSON data types:

```JSON
{
  "name": "Parker",
  "species": "porcupine",
  "occupation": "mascot",
  "motto": "Sharing is caring",
  "centimeters": 75,
  "kilograms": 28.5,
  "quills": 3.0e+4,
  "friendly": true,
  "bossy": false,
  "nicknames": [
    "Quilled Crusader",
    "Spike"
  ],
  "classification": {
    "kingdom": "animalia",
    "phylum": "chordata",
    "class": "mammalia",
    "order": "rodentia",
    "suborder": "hystricomorpha",
    "infraorder": "hystricognathi"
  },
  "dnaSequence": null
}
```

These are all name/value pairs, but there are several kinds of values; the next few sections will explain each of them.
> Geek note: Turning data objects into JSON is called "serialization";
> turning JSON back into data objects is called "parsing" or sometimes
> "deserialization".

## Strings (Text)

Strings are just text that's part of the data, such as `"Parker"` or `"rodentia"`, and they need to be enclosed in double quotes. That seems simple enough, but what if your string has a double quote in it? `"Parker says "Sharing is caring""` is not a valid JSON value because the parser thinks the `"` before `Sharing` is the end of the string, and then it gets really confused. (Computers are really stupid, aren't they?) So to put a `"` within a string, you need to \"escape\" it by preceding it with a `\`. For example:

```JSON
{
  "name": "Parker",
  "action": "Parker says "Sharing is caring""
}
```

As you might expect, this escaping thing is a bit of a slippery slope, as the parser may now be confused by the `\` character. So you also have to escape the `\` character:

```JSON
{
  "name": "Parker",
  "home": "C:\\Users\\Parker"
}
```

While `"` and `\` are the only characters you *need* to escape, a number of others are available. You can also insert special characters using Unicode (UTF-16) character codes using the format `\uXXXX`, but often it's easier to just type Unicode characters in your JSON.

```JSON
{
  "name": "Parker",
  "mood": "😀"
}
```

## Numbers

Numeric values don't get quotes around them. For example, Parker's length and weight are expressed as numbers.

```JSON
{
  "name": "Parker",
  "centimeters": 75,
  "kilograms": 28
}
```

Note that 75 is not the same as "75"; the quotes would indicate the characters `7` and `5` rather than a number. Numbers are in decimal, and can contain a sign, decimal point, and exponent such as:

```JSON
{
  "quills": 3.0e+4,
  "damage": -10
}
```

## Boolean (True or False)

For boolean values, just use `true` and `false` with no quotes.
```JSON
{
  "name": "Parker",
  "friendly": true,
  "bossy": false
}
```

## Objects (name/value pairs)

All the JSON examples in this article so far have consisted of one JSON object with name/value pairs enclosed in a set of curly braces. But you don't need to limit yourself to one object! You can have as many objects as you want as values inside other objects. This nesting allows you to create a hierarchy.

```JSON
{
  "name": "Parker",
  "classification": {
    "kingdom": "animalia",
    "phylum": "chordata",
    "class": "mammalia",
    "order": "rodentia",
    "suborder": "hystricomorpha",
    "infraorder": "hystricognathi"
  }
}
```

The top-level object has two name/value pairs, `"name"` and `"classification"`, and the value of `"classification"` is itself an object with several name/value pairs of its own. This is very convenient for organizing the data and, when combined with arrays, allows creating lists, tables, and all sorts of other data structures.

## Arrays (collections)

An array is an ordered set of values enclosed in square braces `[` and `]` and separated by commas, such as:

```JSON
{
  "name": "Parker",
  "nicknames": [
    "Quilled Crusader",
    "Spike"
  ]
}
```

or, more succinctly,

```JSON
{
  "name": "Parker",
  "nicknames": [ "Quilled Crusader", "Spike" ]
}
```

Mascots could have any number of nicknames or none at all, and an array allows you to list them. Parker's sister Penny doesn't have any nicknames.

```JSON
{
  "name": "Penny",
  "nicknames": []
}
```

Arrays of objects are especially useful. For example, suppose you wanted to compile a list of Microsoft developer mascots:

```JSON
{
  "mascots": [
    {
      "name": "Bit",
      "species": "raccoon",
      "team": "Microsoft Developer Advocates"
    },
    {
      "name": "G-raffe",
      "species": "giraffe",
      "team": "Microsoft Graph"
    },
    {
      "name": "Parker",
      "species": "porcupine",
      "team": "Microsoft 365 PnP"
    }
  ]
}
```

Remember that spaces, tabs, and newlines are ignored, so this the same data could be written more compactly like this. Suddenly it starts to look a little bit like a table!

```JSON
{
  "mascots": [
    { "name": "Bit",     "species": "raccoon",  "team": "Microsoft Developer Advocates" },
    { "name": "G-raffe", "species": "giraffe",    "team": "Microsoft Graph" },
    { "name": "Parker",  "species": "porcupine", "team": "Microsoft 365 PnP" }
  ]
}
```

> MIND THE COMMAS! There must be exactly one (1) comma between
> name/value pairs and array elements. It's really easy to misplace a
> comma in JSON, especially if you're copying and pasting. Some people
> like to leave an extra comma after the last name/value pair or array
> element to make it easier to re-arrange things, but that's cheating;
> it's not part of the JSON standard and some applications won't
> accept it.


## Dates and other things

Unfortunately, there is no standard way to express a date in JSON. In practice, dates are passed in string values, but different applications use different date formats, which can be a bit maddening at times. The Microsoft Graph API uses [ISO 8601 format](https://www.w3.org/TR/NOTE-datetime).

Images and other binary objects are rarely included in JSON, but if you wanted to do that you'd need to turn them into strings somehow, perhaps by [Base64 encoding](https://en.wikipedia.org/wiki/Base64) them.

## Null

To indicate an empty value, use `null`. For example, Parker hasn't had his DNA sequenced, so there is no value for that in his profile.

```JSON
{
  "name": "Parker",
  "dnaSequence": null
}
```

Note that `[]`, an empty array, and `{}`, an empty object, are different than `null`. They're empty containers whereas `null` is really nothing at all.

## Comments

If only JSON supported comments, we could write much more readable code! Officially there are no comments in JSON, but some products (like the SharePoint Framework) seem to encourage using JavaScript style comments in JSON. It seems harmless but it's not proper JSON, and most applications will choke on them. One trick that's usually OK is to just add a few extra name/value pairs in lieu of comments; most software will simply ignore the extra data. For example:

```JSON
{
  "name": "Parker",
  "classification": {
    "comment": "This is the biological taxonomy",
    "kingdom": "animalia",
    "phylum": "chordata",
    "class": "mammalia",
    "order": "rodentia",
    "suborder": "hystricomorpha",
    "infraorder": "hystricognathi"
  }
}
```

While it's not recommended, it is [legal](https://tools.ietf.org/html/rfc8259#section-4) to have duplicate names in a JavaScript object, so you could have more than one `"comment"` if you're daring. This is valid JSON:

```JSON
{
  "name": "Parker",
  "comment": "Great mascot but gets a bit prickly at times",
  "comment": "Check out "Parker's Place" online apparel shop"
}
```

## Tools

There are a lot of web sites out there that will format and validate your JSON; [this one](https://jsonformatter.org/) does both.

{{< notice warning>}}
Remember to remove any personal or confidential data before using online JSON tools!
{{< /notice >}}

## Schema support

It's often helpful to impose some structure on your JSON, specifying which name/value pairs are required and what value types they should contain. That's the role of [JSON Schema](https://github.com/BobGerman/BlogArticles/blob/dev/Intro%20to%20JSON). This allows validating the JSON and offering features such as intellisense.

A JSON Schema describes a specific JSON structure. For example, all animal mascots need to have a `name` and zero or more nicknames with an optional value for `quills`, such as:

```JSON
{
  "name": "Parker",
  "nicknames": [
    "Quilled Crusader",
    "Spike"
  ],
  "quills": 30000
}
```

This would be expressed in JSON Schema as:

```JSON
{
    "definitions": {},
    "$schema": "http://json-schema.org/draft-07/schema#",
    "$id": "https://example.com/object1607485037.json",
    "title": "Root",
    "type": "object",
    "required": [
        "name",
        "nicknames"
    ],
    "properties": {
        "name": {
            "$id": "#root/name",
            "title": "Name",
            "type": "string",
            "default": "",
            "examples": [
                "Parker"
            ],
            "pattern": "^.*$"
        },
        "nicknames": {
            "$id": "#root/nicknames",
            "title": "Nicknames",
            "type": "array",
            "default": [],
            "items":{
                "$id": "#root/nicknames/items",
                "title": "Items",
                "type": "string",
                "default": "",
                "examples": [
                    "Quilled Crusader"
                ],
                "pattern": "^.*$"
            }
        },
        "quills": {
            "$id": "#root/quills",
            "title": "Quills",
            "type": "integer",
            "examples": [
                30000
            ],
            "default": 0
        }
    }
}
```

If this looks complicated, don't worry; there are many tools that will generate a schema from sample JSON. This is built into Power Apps and Power Automate, and you can generate a schema online using the [JSON Schema Validator and Generator](https://extendsclass.com/json-schema-validator.html); it was used to generate the schema above.

Why bother with a schema? Well once you have one, you can get syntax checking and intellisense in tools like Visual Studio Code. Power Apps and Power Automate use schemas to determine what name/value pairs to expose as properties in your project, and what data types they should be.

You can add a property to your JSON to indicate the URL of the JSON schema; for example, to indicate that a file is a Microsoft Teams manifest, include this schema URL:

```JSON
{
  "$schema": "https://developer.microsoft.com/json-schemas/teams/v1.2/MicrosoftTeams.schema.json"
}
```

When a `$schema` property is present, Visual Studio and Visual Studio Code will validate your JSON automatically and provide intellisense. There are a ton of schemas available at <https://www.schemastore.org/json/> for you to reference. You can even reference a JSON schema in your own project by just specifying a relative path:

```JSON
{
  "$schema": "./myschema.json"
}
```

## OData

You may notice some name/value pairs in your JSON which look kind of odd and begin with `@odata`. For example, here's the beginning of the data returned by the Microsoft Graph call `https://graph.microsoft.com/v1.0/me/messages` (returns messages in the user's inbox):

```JSON
{
  "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users('19671429-1359-457f-bfc1-1be1ee65d4d9')/messages",
  "@odata.nextLink": "https://graph.microsoft.com/v1.0/me/messages?$skip=10",
  "value": [
      {
          "@odata.type": "#microsoft.graph.eventMessage",
          "@odata.etag": "W/"DQAAABYAAADcd/V5PKGOSLpB9pjjNuVqAALT5+Dw"",
          "id": "AAMkADIxMjk0NDNjLTJmNWItNDYzNy04MmQ2LTQyMjhkM2FjOWE3MQBGAAAAAAA7bH43fGymSJWqX6oeXPByBwDcd-V5PKGOSLpB9pjjNuVqAAAAAAEMAADcd-V5PKGOSLpB9pjjNuVqAALV0JNVAAA=",
          "createdDateTime": "2020-12-16T00:14:19Z",
          ...
```

[OData](https://www.odata.org/) is a standard for doing Create, Read, Update, and Delete (CRUD) operations on tabular data using a REST web service, and the Microsoft Graph uses it where appropriate. A folder of email messages is easily expressed as tabular data, so it's no surprise that the Graph uses OData to work with them. The name/value pairs beginning with `@odata.` are OData *control information* used to control the flow of data. For example the value of `@odata.nextLink` is the URL to retrive the next set of rows in a large dataset. You can find details on all the [OData Control Information here](http://docs.oasis-open.org/odata/odata-json-format/v4.0/cos01/odata-json-format-v4.0-cos01.html#_Toc372793050) in the OData documentation.

## JSON and JavaScript

Although JSON stands for "JavaScript Object Notation", and was inspired by the format JavaScript uses for object literals, they are not the same. Indeed, JSON is intended to be language independent. Some major differences between JSON and JavaScript are:

-   In a JavaScript object literal, the names only need to be enclosed
    in quotes if they are reserved words like `for` or `if` in
    JavaScript. Furthermore, you can use either single or double quotes.
    In JSON, names always need to be enclosed in double quotes.
-   JavaScript strings can be contained in single or double quotes; JSON
    strings must be contained in double quotes
-   JavaScript numbers can be in octal (using a leading 0) or
    hexadecimal (using a leading 0x) as well as decimal; JSON numbers
    must be in decimal.
-   JavaScript objects can contain values such as dates, regular
    expressions, and HTML elements, whereas JSON values are limited to
    strings, numbers, boolean, objects, arrays, and null.
-   JavaScript allows comments; JSON does not.

Bottom line: **all JSON objects are valid JavaScript object literals but not all JavaScript object literals are valid JSON.** To convert between JSON and objects, use the `JSON` object that's built into JavaScript. This is preferable to using `eval` which is prone to security issues.
To convert JSON to a JavaScript object:

```javascript
var json = '{"name": "Parker"}';
var o = JSON.parse(json);

console.log(o.name); // Parker
```

To convert a JavaScript object to JSON:

```javascript
var o = new Object();
o.name = "Parker";
var json = JSON.stringify(o);

console.log(json);  // {"name":"Parker"}
```

When you make a REST call, you end up using JSON as well. Here's a call to the Microsoft Graph:

```javascript
// Assume Parker has logged in and a variable called accessToken contains
// a valid Azure AD access token for Parker to call the Microsoft Graph
const response = await fetch("https://graph.microsoft.com/v1.0/me/",
    {
        method: 'GET',
        headers: {
            "accept": "application/json",
            "authorization": "bearer " + accessToken,
        }
    });

if (response.ok) {
    const profile = await response.json();
    const name = profile.displayName;   // Parker
}
```

Notice that to ask the service for a JSON response, the HTTP header is set to accept `application/json`, which is the MIME type for JSON. And the `response` object returned by `fetch()` has a `json()` function built right in to turn the returned JSON into a JavaScript object.

## Conclusion

Learning to work with JSON is an important skill for both low-code and full stack developers, as well as for many IT Pro tasks. Here's hoping this article has helped you to understand and use JSON in your next project!

(This article is cross-posted at [https://bob1german.com](https://bob1german.com/2021/01/11/introduction-to-json))
