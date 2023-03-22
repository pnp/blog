---
title: "🐫(CAML) Query: What is it and why is it relevant in 2023?"
author: "Dan Toft"
githubname: Tanddant
date: 2023-03-07T07:20:04.878Z
# don't change
categories: ["Community post"]
# link to the thumbnail image for the post
images:
- images/thumbnail.webp
# don't change
tags: ["SharePoint"]
# don't change
type: "regular"
canonicalUrl: https://blog.dan-toft.dk/2023/03/caml-query-in-2023/
---

## Why this post

Recently I had the great pleasure of presenting a sample web part [CAML to Table](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-caml2table) on a [PnP Community call](https://www.youtube.com/watch?v=SPJiV5CbRUc), during that presentation something occurred to me from the chat: Not everyone know what CAML is!

Now, not only did that make my presentation confusing to some, it also means they're missing out on some great opportunities.

## So what is CAML?

CAML is short for Collaborative Application Markup Language and is an XML based syntax to query data in SharePoint (Microsoft) Lists.

CAML has been around for at least 10 years at this point, at might have a bit of a "old ring" to it because of it's XML nature, but it's very much hidden right there in plain sight - every time you create a view, filter a list, or even sort a list, it's all CAML, it's just hidden so you don't have to worry about is.

Traditionally CAML has only been something for coders to worry about, but I genuinely believe that if you're doing anything with lists you should at least look at the basics of it, because it can really help you present the data you want to show, and hide the rest!

## Getting started

The easiest way to get started, is to find a list, setup a view with a simple filter - connect to the site with [PnP.PowerShell](https://pnp.github.io/powershell/) and run the following two lines to see the query of the view you've just created

``` PowerShell
$view = Get-PnPView -List "Onboarding tasks" -Identity "Done Tasks" -Includes ViewQuery
Write-Host $view.ViewQuery
```

The output will be in a single line, but using a tool like VS Code to format it you'll notice it's just XML

```XML
<Where>
    <Eq>
        <FieldRef Name="Status" />
        <Value Type="Text">Done</Value>
    </Eq>
</Where>
```

Looking at a simple CAML query it's actually somewhat readable, `WHERE \<The field status> is equal to \<the text value 'Done'>`

Now this query is somewhat simple, but the great part about writing CAML query is that we get to mix and match our `ANDs` and `ORs` and get creative really fast, let's say we want all the Stevens, no matter their age, and Dans that are over 20 and under 30:

```XML
<Query>
    <Where>
        <Or>
            <Eq>
                <FieldRef Name="Name" />
                <Value Type="Text">Steven</Value>
            </Eq>
            <And>
                <Eq>
                    <FieldRef Name="Name" />
                    <Value Type="Text">Dan</Value>
                </Eq>
                <And>
                    <Gt>
                        <FieldRef Name="Age" />
                        <Value Type="Number">20</Value>
                    </Gt>
                    <Lt>
                        <FieldRef Name="Age" />
                        <Value Type="Number">30</Value>
                    </Lt>
                </And>
            </And>
        </Or>
    </Where>
</Query>
```

Now if you're anything like me you can look at that and get an idea of what's going on, but writing it ... no thanks!

Here we're incredibly lucky that the community has our back!

There are two libraries you should know about:

[camljs](https://www.npmjs.com/package/camljs) by [Andrei Markeev](https://twitter.com/amarkeev) is a great JS library that allows you to write CAML queries in a more fluent style - there's also a great [browser extension](https://chrome.google.com/webstore/detail/camljs-console/ohjcpmdjfihchfhkmimcbklhjdphoeac) also by Andrei, that wraps the library in an easy to use way.

Here is the same query from above but written in camljs

```JavaScript
var query = new CamlBuilder().Query().Where()
                    .TextField("Name").EqualTo("Steven").Or()
                    .TextField("Name").EqualTo("Dan").And()
                    .NumberField("Age").GreaterThan(20).And()
                    .NumberField("Age").LessThan(30).ToString();
```

Now if you're writing .NET, there's also a library, [Camlex.NET](https://github.com/sadomovalex/camlex) by [Alexey Sadomov](https://twitter.com/sadomovalex) - which uses LINQ to setup the filters for your query, like here:

```C#
Camlex.Query().Where(x => (string)x["Name"] == "Steven" || (string)x["Name"] == "Dan" && ((double)x["Age"] > 20,0 && (double)x["Age"] < 30,0))
```

## Using the CAML query

Alright, so now you've created an awesome query, and maybe even tested it with the CAML2Table sample I mentioned earlier, now what can we do with it? - well CAML is super awesome because it's the tech behind views, this means we can set a views filter to a CAML query **Beware that this well reset if someone changes the filter and saves the view.**

Setting the filter is done with PnP.PowerShell like this

```PowerShell
Set-PnPView -List "People" -Identity "Stevens and Dans in their 20s" -Values @{ViewQuery = "<Where><Or><Eq><FieldRef Name='Name' /><Value Type='Text'>Steven</Value></Eq><And><Eq><FieldRef Name='Name' /><Value Type='Text'>Dan</Value></Eq><And><Gt><FieldRef Name='Age' /><Value Type='Number'>20</Value></Gt><Lt><FieldRef Name='Age' /><Value Type='Number'>30</Value></Lt></And></And></Or></Where>"}
```

Notice we removed the \<Query> and \</Query>

## CAML vs. SP REST

Now if you've worked with REST and OData you might be thinking "I can do all of that with the REST API easier" - whether it is easier or not I'll leave up to you, but, there are a few REALLY cool tricks we can do with CAML, that cannot be done with REST

### The `IN` statement

Have you ever seen something like this `Name eq 'Dan' or Name eq 'Steven' or Name eq 'Brian'....`

CAML makes this really easy - with up to 1000 values in your filter (There are [workarounds to that limit as well](https://sharepoint.stackexchange.com/questions/80210/caml-query-limitation-of-values-in-in-operator))

```XML
<Where>
    <In>
        <FieldRef Name="Name" />
        <Values>
            <Value Type="Text">Dan</Value>
            <Value Type="Text">Steven</Value>
            <Value Type="Text">Brian</Value>
            ...
        </Values>
    </In>
</Where>
 ```

### Membership operator

This one is REALLY powerful - have you ever had a task list in SharePoint with an assignee field you might've had that case where a task needs to be assigned to a group, now using a SharePoint Group and a person field that allows groups we can use the `Membership` operator to filter based on if the current user is in that group using the `CurrentUserGroups` filter - this way we can have a shared task list:

```XML
<Where>
    <Membership Type="CurrentUserGroups">
        <FieldRef Name="Responsible" />
    </Membership>
</Where>
```

Next level is hiding the tasks that are done, and just like that you have a list of tasks that are pending pr. department

```XML
<Query>
    <Where>
        <And>
            <Membership Type="CurrentUserGroups">
                <FieldRef Name="Responsible" />
            </Membership>
            <Neq>
                <FieldRef Name="Status" />
                <Value Type="Choice">Done</Value>
            </Neq>
        </And>
    </Where>
</Query>
```

### Querying a URL field based on the URL

This one is pretty self explanatory, but is actually not supported in the SharePoint REST API, querying a list item based on the value of a URL field

```XML
<Query>
    <Where>
        <Eq>
            <FieldRef Name="UrlField" />
            <Value Type="URL">https://pnp.github.io/blog/</Value>
        </Eq>
    </Where>
</Query>
```

## Summary

That was a couple of cool things that CAML allows you to do that can't easily be done with anything else, there's also awesome support for date filters, including offsets from `Now` that make it really easy to write a query that'll always be up to date.

The only thing I find myself really missing coming from SQL is the ability to select an item based on the value of two columns relative to each other, i.e Where Modified By and Author aren't the same, this can however be worked around using a calculated column and querying on that.

## TL;DR

CAML Has been around for a really long time, and while it's not as visible as it's been previously, it's not going anywhere anytime soon, so you might as well start learning it today.

## More Resources

* [Read more about CAML](https://learn.microsoft.com/en-us/sharepoint/dev/schema/collaborative-application-markup-language-caml-schemas)
* [Query schema](https://learn.microsoft.com/en-us/sharepoint/dev/schema/query-schema)
* [CAML to Table sample to test queries](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-caml2table)
