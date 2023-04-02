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

This blog post shows how a Power Automate Cloud Flow can be used to produce documentation from Process Descriptions.

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

The other key column on the Process table is the Description column:

[different areas set]

---

## Process Documentation Cloud Flow

![Whole Flow](images/WholeFlow.png)

### Trigger

![Trigger](images/Trigger.png)

### List Processes for Documentation

![List Processses](images/ListProcesses.png)

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

