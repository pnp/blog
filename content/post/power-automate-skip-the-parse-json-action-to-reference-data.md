# Power Automate: skip the Parse JSON action to reference data


## Why? 

Let me emphasize that using the Parse JSON action (as explained in this
great blog post of Luise Freese: [How to use Parse JSON action in Power
Automate](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/how-to-use-parse-json-action-in-power-automate/ba-p/2121861?WT))
is always the way to go when you are starting with Power Automate.
Especially if you want to have properties of your JSON ouput to show up
as Dynamic Content in the rest of your Flow.


However the Parse JSON action is very picky\... The action will fail if
a property is missing, a new property is added later on or an existing
property is giving back a different type of data. In short: any schema
change not being updated in the settings of the action can cause a
:cross_mark: \"*ValidationFailed error*\" :cross_mark:. Such an error
will stop the Flow because the schema validation failed:

![PowerAutomate_ParseJSONfail](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/279338i323A98A1BF42BFF5/image-size/large?v=v2&px=999 "PowerAutomate_ParseJSONfail")


As long as you remind to also update the Parse JSON action schema, it
will continue working fine.\
But in my case, I wanted to know if Power Automate could skip the Parse
JSON action :nerd_face:

## What? 


In this blog post, I can show you a way to skip the Parse JSON action
and reference a property of an action with JSON output directly. This
way, we can have one action less (#LessUsage #LessAPIcalls) and thus one
action less that could fail (#Lean #LessActionsLessRisks).

## How? 

Let\'s first have a look at a simple JSON object:

![PowerAutomate_JSONobject](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/279339i9313C25EF739BD0E/image-size/large?v=v2&px=999 "PowerAutomate_JSONobject")



The output of this Compose action will be this JSON output:


``` wp-block-code
{
  "Property Product": "Product A",
  "Property Product Category": "Product Category 1"
}
```



I am using a Compose action to give JSON output, but in most cases JSON
output will come from actions connected to a data source. In some types
of actions unfortunately Power Automate does not create Dynamic Content.
In these cases, the properties of these action do not show up in the
Dynamic Content Panel for the rest of your Flow. When using the Parse
JSON action on the output of such an action:

![PowerAutomate_parseJSON](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/279340iF22ACD84A9E2CF43/image-size/large?v=v2&px=999 "PowerAutomate_parseJSON")
##  

we can force the rest of the Flow to show us these properties in the
Dynamic Content Panel. Making it easy for us to reference these
properties. The Content input of the Parse JSON action will be the
output of the Compose - SimpleJSONObject action:


``` wp-block-code
@{outputs('Compose_-_SimpleJSONObject')}
```


Thanks to the Parse JSON - SimpleJSONObject action, we can (from this
action on) use the properties defined in its Schema as Dynamic Content:

![PowerAutomate_parseJSONreference](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/279341iF2487F45ACA049EE/image-size/large?v=v2&px=999 "PowerAutomate_parseJSONreference")

The expression of this reference would look like:

``` wp-block-code
@{body('Parse_JSON_-_SimpleJSONObject')?['Property Product Category']}
```


In my first screenshot, you can see the action failing. It failed
because the schema was expecting a string, while the Content input was
giving an integer number. This was because I changed the JSON object
temporarily :smiling_face_with_horns: to:


``` wp-block-code
{
  "Property Product": "Product A",
  "Property Product Category": 1
}
```


**1)** We can also reference the property of the first action Compose -
SimpleJSONObject action directly. We can use an expression like:


``` wp-block-code
@{outputs('Compose_-_SimpleJSONObject')?['Property Product Category']}
```

Power Automate can thus skip the Parse JSON action. Even without this
parsing, we can reference the property of any action with a JSON output:

![PowerAutomate_parseJSONreferenceDirectly](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/279342iC4B3DB0A80608CEA/image-size/large?v=v2&px=999 "PowerAutomate_parseJSONreferenceDirectly")

[No Parse JSON action needed! 8)]
[Originally published
at <https://knowhere365.space/power-automate-skip-the-parse-json-action-to-reference-data/>]
