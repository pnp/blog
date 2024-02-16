---
title: "Getting started with Graph API in SPFx webpart"
date: 2021-06-03T03:59:00-04:00
author: "Chandani Prajapati"
githubname: chandaniprajapati
categories: ["Community post"]
images:
- images/Permssions.png
tags: ["Microsoft Graph", "SharePoint framework (SPFx)"]
type: "regular"
---


## What is Graph API?
 
Microsoft Graph provides a unified programmability model that you can
use to build apps for organizations and consumers that interact with the
data of millions of users. You can easily access Microsoft Graph also
from SharePoint Framework solutions.
 
Microsoft Graph exposes REST APIs and client libraries to access data on
the following Microsoft services like  Bookings, Calendar, Delve, Excel,
Microsoft 365 compliance eDiscovery, Microsoft Search, OneDrive,
OneNote, Outlook/Exchange, People (Outlook contacts), Planner,
SharePoint, Teams, To Do, Workplace Analytics. for more details refer to
[Graph API](https://learn.microsoft.com/graph/overview?view=graph-rest-1.0 "Graph API").
 
## How to test API in graph explorer?
 
Before creating an SPFx web part implementation with Graph API we can
explore APIs in [Graph
Explorer](https://developer.microsoft.com/graph/graph-explorer "Graph Explorer").
At here To access your own data you have to log in with your O365
Credentials.
 
Whenever you sign in it will ask for Permission so you have to Accept
it.
 
In the left panel, you can find multiple sample queries by category so
you can check them and run them.
 
If you are testing any API and get an **error** like this:

`Forbidden -
403 - You need to consent to the permissions on the Modify permissions
(Preview) tab.`

Then follow the below steps,
 
1. Select Permissions
![Select Permssion.png](images/Select Permssion.png)
2. Then select the category in which you want to set permission and
select the **Consent** button.
 
![Permssions.png](images/Permssions.png)
 
3 After clicking on the Consent it will open a popup so check the
checkbox and Accept it.
 
![AcceptPermission.png](images/AcceptPermsiion.png)

Then select  the run query and it will retrieve the results. that's
it :)
 
 
Now lets' move to the SPFx implementation.
 
## Implementation
 
Open a command prompt\
Move to the path where you want to create a project\
Create a project directory using:
 
    md GraphAPIDemo
 
Move to the above-created directory using:
 
    cd GraphAPIDemo
 
Now execute the below command to create an SPFx solution:
 
     yo @microsoft/sharepoint
 
It will ask some questions, as shown below,
 
![Project Structure.png](images/Project Structure.png)


After a successful installation, we can open a project in any source
code tool. Here, I am using the VS code, so I will execute the command:

```PowerShell
    code .
```

Now will create a demo to read messages of a user. for more details
refer to
[Microsoft Graph](https://learn.microsoft.com/graph/api/message-get?view=graph-rest-1.0&tabs=http "this").
 
So first of all we have to set permission as per our endpoint in
**package-solution.json**. Now the question is which permission we have
to add so there are multiple ways.


**1. In the graph explorer**
 
For eg. we have to use messages endpoint so first, we will test it in
graph explorer. so while we running the query there is an **permission**
tab under the **run query** button so after the response checks the
permission tab. It shows all required permissions for the endpoint as
below.
 
![Modify Permission.png](images/Modify Permission.png)
 
**2. Official documentation for endpoint**
 
You can also find all the details in the official document for all the
endpoints. 
 
## Implementation
 
**1**. In the **package-solution.json** file we will add permission.
 
```json
"webApiPermissionRequests": [
      {
        "resource": "Microsoft Graph",
        "scope": "Mail.Read"
      }
]
```
 
2.  Move to the **IGraphApiDemoProps.ts** and update as below,
 
```javascript
import { MSGraphClient } from "@microsoft/sp-http";
export interface IGraphApiDemoProps {
  description: string;
  graphClient: MSGraphClient;
}
```
 
3.  Create a file IGraphApiDemoState.ts inside
**src\\webparts\\graphApiDemo\\components** and create a state interface
as below
 
```javascript
export interface IGraphApiDemoState {
    messages: [{
        subject: string;
    }]
}
```
 
4.  Move to the**{WebpartName}Webpart.ts**
 
Import MSGraphClient module
Create an OnInit() to initialize the Graph Configuration for the current
context.
In the render() set the graphClient property
 
```javascript
import * as React from 'react';
import * as ReactDom from 'react-dom';
import { Version } from '@microsoft/sp-core-library';
import {
  IPropertyPaneConfiguration,
  PropertyPaneTextField
} from '@microsoft/sp-property-pane';
import { BaseClientSideWebPart } from '@microsoft/sp-webpart-base';
import * as strings from 'GraphApiDemoWebPartStrings';
import GraphApiDemo from './components/GraphApiDemo';
import { IGraphApiDemoProps } from './components/IGraphApiDemoProps';
import { MSGraphClient } from '@microsoft/sp-http';
export interface IGraphApiDemoWebPartProps {
  description: string;
}
export default class GraphApiDemoWebPart extends BaseClientSideWebPart<IGraphApiDemoWebPartProps> {
  private graphClient: MSGraphClient;
  public onInit(): Promise<void> {
    return new Promise<void>((resolve: () => void, reject: (error: any) => void): void => {
      this.context.msGraphClientFactory
        .getClient()
        .then((client: MSGraphClient): void => {
          this.graphClient = client;
          resolve();
        }, err => reject(err));
    });
  }
  public render(): void {
    const element: React.ReactElement<IGraphApiDemoProps> = React.createElement(
      GraphApiDemo,
      {
        description: this.properties.description,
        graphClient: this.graphClient,
      }
    );
    ReactDom.render(element, this.domElement);
  }
  protected onDispose(): void {
    ReactDom.unmountComponentAtNode(this.domElement);
  }
  protected get dataVersion(): Version {
    return Version.parse('1.0');
  }
  protected getPropertyPaneConfiguration(): IPropertyPaneConfiguration {
    return {
      pages: [
        {
          header: {
            description: strings.PropertyPaneDescription
          },
          groups: [
            {
              groupName: strings.BasicGroupName,
              groupFields: [
                PropertyPaneTextField('description', {
                  label: strings.DescriptionFieldLabel
                })
              ]
            }
          ]
        }
      ]
    };
  }
}
```
 
5.  Move to the **GraphApiDemo.tsx** and call API here and render the
data.
 
```javascript
import * as React from 'react';
import styles from './GraphApiDemo.module.scss';
import { IGraphApiDemoProps } from './IGraphApiDemoProps';
import { IGraphApiDemoState } from './IGraphApiDemoState';
import { escape } from '@microsoft/sp-lodash-subset';
export default class GraphApiDemo extends React.Component<IGraphApiDemoProps, IGraphApiDemoState> {
  constructor(props: IGraphApiDemoProps) {
    super(props);
    this.state = {
      messages: [{
        subject: ''
      }]
    }
  }
  public getDriveItems() {
    let getMessages: string = "me/messages";
    if (!this.props.graphClient) {
      return;
    }
    this.props.graphClient
      .api(getMessages)
      .version("v1.0")
      .select("subject,sentDateTime,webLink")
      .top(5)
      .get((err: any, res: any): void => {
        if (err) {
          console.log("Getting error in retrieving mesages =>", err)
        }
        if (res) {
          console.log("Success");
          if (res && res.value.length) {
            console.log(res.value);
            this.setState({
              messages: res.value
            })
          }
        }
      });
  }
  public componentDidMount() {
    this.getDriveItems();
  }
  public render(): React.ReactElement<IGraphApiDemoProps> {
    return (
      <div className={styles.graphApiDemo}>
        { this.state.messages.map(m => <><span>{m.subject}</span><br /></>)}
      </div>
    );
  }
}
```
 
Now serve the application using the below command,
 
    gulp serve
 
Now test the web part in SharePoint-SiteURL +
/\_layouts/15/workbench.aspx.
 
## Output
 
![Output.png](images/Output.png)
 
Find the [full source code](https://github.com/chandaniprajapati/GraphAPIDemo).
 
## Summary
 
In this article, we have seen how to use graph API in SPFx web part and
graph explorer.
 
I hope this helps.
 
Sharing is caring!!
