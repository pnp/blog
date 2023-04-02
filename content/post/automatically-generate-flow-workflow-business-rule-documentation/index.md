---
title: "Automatically generate Flow, Workflow and Business Rule Documentation"
date: 2023-04-10T08:40:00-04:00
author: "Alex McLachlan"
githubname: alex-mcla
# don't change
categories: ["Community post"]
# link to the thumbnail image for the post
images:
- images/myImage.png
# don't change
tags: []
# don't change
type: "regular"
---
## TL;DR

How often do you find yourself writing documentation for Dynamics 365 Power Automate Flows and Business Rules?

And on a large project, how do you to keep track of all the Dynamics 365 Power Automate Flows, Workflows, Business Rules, etc. and get an overview of what they relate to and what they do?

This blog post shows how a Power Automate Cloud Flow can be used to produce documentation from Process Descriptions and link them to Azure DevOps work items.

---

## Contents

- [Dataverse Processes](#dataverse-processes)
-
-
-

---

## Dataverse Processes

Flows, Workflows and Business Rules are all stored on the Dataverse Process table. The Category choice column (option set attribute) distinguishes the different types:

| Value|	Type|
|--|--|
|0	|Workflow|	
|1|	Dialog	|
|2|	Business Rule	|
|3|	Action	|
|4|	Business Process Flow	|
|5|	Modern Flow	|
|6|	Desktop Flow	|

The other key column on the Process table is the Description column as can be seen in Power Automate Cloud Flows:

![Flow Description](images/FlowDescription.png)

And Business Rules:

![Business Rule Description](images/BusinessRuleDescription.png)

---

## Process Documentation Cloud Flow

As Processes are managed as a Dataverse table, this table can be used in a Power Automate Flow to generate documentation.

The top-level view of the flow is:

![Whole Flow](images/WholeFlow.png)

### Trigger

The trigger is manual and uses two parameters:

- **UserEmailMatch**: String for matching against the CRM user email address of the user who created the process. The Dev user email address, or the tenant name could be used.
- **MaxProcesses** (integer): the maximum number of processes to include in the documentation.

![Trigger](images/Trigger.png)

### List Processes for Documentation

The key element of the flow is getting the Processes that match the trigger parameters:

![List Processses](images/ListProcesses.png)

The main filter selects just the workflows, business rules, actions, business process flows, and modern flows (Power Automate Cloud Flows):  

``` xml
    <filter>
      <condition attribute='category' operator='ne' value='1' />
      <condition attribute='category' operator='ne' value='6' />
      <condition attribute='category' operator='ne' value='9000' />
      <condition attribute='type' operator='eq' value='1' />
      <condition attribute='rendererobjecttypecode' operator='null' />
    </filter>
```

The User who created the Process is used in the other filter condition:

``` xml
    <link-entity name='systemuser' from='systemuserid' to='createdby'>
      <filter>
        <condition attribute='internalemailaddress' operator='like' value='%@{triggerBody()['text_1']}%' />
      </filter>
    </link-entity>
```

And the outputs are ordered into the order the documentation will be generated in, firstly by the Process's Primary Entity, then by Category and then by Name:

``` xml
    <order attribute='primaryentity' />
    <order attribute='category' />
    <order attribute='name' />
```

### Variables



### Apply to each Process


Form (can't use expand query in List)

### Save Content to OneDrive



---

## Output



---

## Taking it further - Azure DevOps Wiki and Work Items

The flow on its own gives significant benefits for documenting and understanding the processes across Dataverse.


---

## Tips for Process Descriptions

Being aware that the descriptions are used in Markdown-based documentation opens the possibility of exploiting Markdown features:

---

## Acknowledgements

