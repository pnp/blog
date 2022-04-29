---
title: "Create and Retrieve Power Automate Flows - WITH CODE!!! :-)"
date: 2021-08-04T11:26:00-04:00
author: "Tracy Sterling"
githubname: TracyGH
categories: ["Community post"]
images:
- images/Tracy_1-1627940128961.png
tags: ["Power Automate"]
type: "regular"
---

As you are probably aware, Microsoft is looking to [eliminate SharePoint
2010 and 2013
workflows](https://support.microsoft.com/office/sharepoint-2010-workflow-retirement-1ca3fff8-9985-410a-85aa-8120f626965f?ui=en-US&rs=en-US&ad=US). In fact, 2010 workflows have already been retired,
while 2013's retirement date(s) are still looming. 
 
Microsoft has advised users to manually rebuild their necessary
SharePoint workflows (SPWF's) as comparable
[M365 Power
Automate](https://docs.microsoft.com/power-automate/getting-started) flows. To that end, Microsoft has provided some
][, including ][a
tool](https://docs.microsoft.com/sharepoint/dev/transform/modernize-scanner) to sniff out SPWF's within your cloud
environment. 
When it comes to planning the migration of your SPWF's to Power Automate
flows, it helps to think of them as two completely different platforms.
Despite that fact that it's all just 'Microsoft' under the covers, Power
Automate is a substantially more robust, complex, and powerful
application than SharePoint Designer. It is simply not 'apples to
apples', which is why you won't find a convenient 'CONVERT' button. 
 
That said, there are opportunities for automating the creation of Power
Automate flows. This will potentially go a long way towards helping
organizations who have invested heavily in SPWF's and now have a
mountain of work ahead of them to convert. In this post, I will walk
through the details of programmatically creating Power Automate flows
with links to a [sample C# console
app](https://github.com/TracyGH/CreatePowerAutomateFlow/tree/master/CreateFlows). 

### Part 1 --- Interacting with 'Solution' Flows 

Because flows under the 'My Flows' tab [are not currently
supported](https://docs.microsoft.com/power-automate/web-api) by Power Automate web API's, you will need to
interact with all programmatic flows via the 'Solutions' tab. 

![](images/Tracy_1-1627940128961.png)
 
**\*\*Note: I have only been able to programmatically create/access
flows within the Default Solution for a relevant [Dataverse
environment](https://docs.microsoft.com/learn/modules/create-manage-environments/). Microsoft does not mention this limitation
in their [web API
documentation](https://docs.microsoft.com/power-automate/web-api) and I am uncertain of the
scalability/performance implications.**


To manually create a new Solutions flow, navigate to the Solutions tab and select Default Solution > New > Cloud flow 

![](images/Tracy_2-1627940129014.png)

To view existing Solutions flows, navigate to the Solutions tab and select Default Solution, then filter ‘Cloud flow’.
To obtain the ID for a specific Solutions flow, select it and copy the GUID value (/flows/[GUID]/) from the browser URL.

![](images/Tracy_3-1627940128946.png)


### Part 2 --- Get ClientData Content for New Flows 

In order to create flows programmatically, we will use the [Power
Automate Management Web
API](https://docs.microsoft.com/power-automate/web-api). The meat and potatoes of the flow payload is
contained in the `clientdata`
[property](https://docs.microsoft.com/power-automate/web-api#create-a-cloud-flow). To help determine appropriate content for populating
this section, I recommend manually creating a 'base' Power Automate flow
using the UI. Then, you can [leverage the
API](https://docs.microsoft.com/power-automate/web-api#list-flows) to get the `clientdata`content from that manual flow and copy/paste it into
the payload for new flow(s).

1.  Follow the instructions for creating a new Solutions flow as shown
    above in Part 1. 
2.  Navigate to your tenant [Power Platform admin
    center](https://admin.powerplatform.microsoft.com/environments) to obtain the environment URL. Update the
    variable at line #17 with the relevant URL. 
3.  Uncomment the `RetrieveFlow`method
    call at [line
    #40](https://github.com/TracyGH/CreatePowerAutomateFlow/blob/master/CreateFlows/SampleProgram.cs)
    and confirm the`CreateFlow` method
    at [line
    #41](https://github.com/TracyGH/CreatePowerAutomateFlow/blob/master/CreateFlows/SampleProgram.cs)
    is commented out.
4.  See Part 1 above to obtain a Flow ID (GUID) for the flow you just
    created. Update the variable at [line
    #113](https://github.com/TracyGH/CreatePowerAutomateFlow/blob/master/CreateFlows/SampleProgram.cs)
    with the flow GUID value. 
5.  Insert a breakpoint at [line
    #122](https://github.com/TracyGH/CreatePowerAutomateFlow/blob/master/CreateFlows/SampleProgram.cs)
6.  Run the project, providing credentials for a user who has access to
    the [Dataverse Web
    API](https://docs.microsoft.com/powerapps/developer/data-platform/authenticate-oauth). (I have only tested with a global admin
    account.)
7.  Copy the string value within the `clientdata` .

### Part 3 --- Programmatically Create a New Flow 

1.  Paste the `clientdata` content from
    above into the variable located on line #61.
2.  Comment out the `RetrieveFlow`method
    call at [line
    #40](https://github.com/TracyGH/CreatePowerAutomateFlow/blob/master/CreateFlows/SampleProgram.cs)
    and confirm the`CreateFlow` method
    at [line
    #41](https://github.com/TracyGH/CreatePowerAutomateFlow/blob/master/CreateFlows/SampleProgram.cs)
    is *not* commented out.
3.  Run the project!
If everything works as expected, you should be able to locate your new
flow by following the instructions in Part 1 to view Solutions
flows. Test your new flow to confirm everything works as expected. 
 
### Part 4 --- 'Tweak' the ClientData Content 

Below is a de-serialized example of the content within the
`clientdata`property of a Power Automate
flow. This particular flow is [triggered when a new
item](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/sharepoint-connector-actions-triggers#when-an-item-is-created) is created within a SharePoint list. The indicated
`table`property at line #52 holds the
value for the GUID of the relevant SharePoint list.
 
To create a new Power Automate flow which targets a different SharePoint
list (within the same Site), simply update that GUID value in the
`clientdata` . While I have only tested
this specific scenario, the potential applications for 'tweaking' values
to facilitate bulk flow creation are endless. 
 
 
```json
{{
  "properties": {
    "connectionReferences": {
      "shared_sharepointonline": {
        "runtimeSource": "embedded",
        "connection": {
          "name": "shared-sharepointonl-ceefa1df-44c6-4e6f-800b-b350-ca17dbda"
        },
        "api": {
          "name": "shared_sharepointonline"
        }
      },
      "shared_office365": {
        "runtimeSource": "embedded",
        "connection": {
          "name": "shared-office365-3bf72576-f215-4852-95ad-69cf-db33f170"
        },
        "api": {
          "name": "shared_office365"
        }
      }
    },
    "definition": {
      "$schema": "https://schema.management.azure.com/providers/Microsoft.Logic/schemas/2016-06-01/workflowdefinition.json#",
      "contentVersion": "1.0.0.0",
      "parameters": {
        "$connections": {
          "defaultValue": {},
          "type": "Object"
        },
        "$authentication": {
          "defaultValue": {},
          "type": "SecureObject"
        }
      },
      "triggers": {
        "When_an_item_is_created": {
          "recurrence": {
            "frequency": "Minute",
            "interval": 3
          },
          "splitOn": "@triggerOutputs()?['body/value']",
          "type": "OpenApiConnection",
          "inputs": {
            "host": {
              "apiId": "/providers/Microsoft.PowerApps/apis/shared_sharepointonline",
              "connectionName": "shared_sharepointonline",
              "operationId": "GetOnNewItems"
            },
            "parameters": {
              "dataset": "https://[M365Domain].sharepoint.com/",
              "table": "e134069a-5a16-4602-bdd5-7f1fec27d45a"
            },
            "authentication": "@parameters('$authentication')"
          }
        }
      },
      "actions": {
        "Send_an_email_(V2)": {
          "runAfter": {},
          "type": "OpenApiConnection",
          "inputs": {
            "host": {
              "apiId": "/providers/Microsoft.PowerApps/apis/shared_office365",
              "connectionName": "shared_office365",
              "operationId": "SendEmailV2"
            },
            "parameters": {
              "emailMessage/To": "@triggerOutputs()?['body/Author/Email']",
              "emailMessage/Subject": "New Item Created!",
              "emailMessage/Body": "<p>New Item Created!<br>\n@{triggerOutputs()?['body/{Link}']}</p>"
            },
            "authentication": "@parameters('$authentication')"
          }
        }
      },
      "outputs": {}
    }
  },
  "schemaVersion": "1.0.0.0"
}}
```
