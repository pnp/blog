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

Flows, Workflows and Business Rules are all stored on the Process table in Dataverse. The Category choice column (option set attribute) distinguishes the different types:

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

The Processes Dataverse table can be used in a Power Automate Flow to generate documentation and this is detailed below.

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

The User who created the Process is used in the linked filter condition on the User table:

``` xml
    <link-entity name='systemuser' from='systemuserid' to='createdby'>
      <filter>
        <condition attribute='internalemailaddress' operator='like' value='%@{triggerBody()['text_1']}%' />
      </filter>
    </link-entity>
```

And the outputs are sorted into the order the documentation will be generated in, firstly by the Process's Primary Entity, then by Category, and then by Name:

``` xml
    <order attribute='primaryentity' />
    <order attribute='category' />
    <order attribute='name' />
```

### Variables

The first two variable as set:

- Current Table = Empty string
- Current Process = Integer (Blank) 

The Contents varaibles are initialised to include the Table of Contents and the formatted Date/Time. The Table of Contents is an Azure DevOps specific extention to markdown, and can be removed for other systems. There are separate variable for the:

- Table related processes:
	- Business Rules
  - Business Process Flows
  - Workflows
- Non-Table related processes:
	- Actions
  - Flows
- Draft processes - these are included in a simple table for reference

![Variables](images/Variables.png)

### Apply to each Process

The flow then loops through the Processes to generate the documentation. 

![Apply to each](images/ApplyToEach.png)

The key elements of the logic for the **Apply to each** are:

- Separate branches for the table-related Processes, non-table-related Processes and draft Processes
- Adding headings to structure the contents
- Switch branches for the individual Process categories so that category specific content can be included - for example, if workflow logging is on
- Conditions for different situations, such as if there isn't a description, so that this can be highlighted
- For Business Rules, getting the name of the Entity Form the rules applies to (note: this can't use expand query in original list as the Form Id isn't valid for FetchXML)
- Adding details of the Process
- Providing warnings if logging is currently turned on

The full detail of the logic is available in the flow, which includes notes on the Flow steps, and the Visio which was generated using the Flow Visio Builder by Carl Cookson.

### Compose steps for the Markdown content

After the end of the Apply to each loop, there are separate compose steps so that the contents are available should the output to OneDrive fail.  

### Save Content to OneDrive

Finally, the Markdown contents is written to OneDrive. This could be replaced with SharePoint if desired.

![Output to OneDrive](images/OutputToOneDrive.png)

---

## Output

Examples of the outputs are:

### Business Rules

![User Story](images/Tables.png)

### Flows

![Flows](images/Flows.png)

---

## Taking it further - Azure DevOps Wiki and Work Items

The flow on its own gives significant benefits for documenting and understanding the processes across Dataverse, particularly on a large project.

Taking advantage of further features of DevOps Wikis gives further benefits, particularly including DevOps Work Item references to Descriptions using '#{_Work Item Number_}', such as #12345 to reference Work Item 12345.



---

## Tips for Process Descriptions

Being aware that the descriptions are used in Markdown-based documentation opens the possibility of exploiting Markdown features:

---

## Acknowledgements

Carl

Matt - his project