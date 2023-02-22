---
title: "How to use Microsoft graph toolkit react people picker control in SPFx Webpart?"
date: 2021-10-26T06:10:00-04:00
author: "Chandani Prajapati"
githubname: chandaniprajapati
categories: ["Community post"]
images:
- images/Implementations.png
tags: ["SharePoint framework (SPFx)", "Microsoft Graph Toolkit"]
type: "regular"
---

## Purpose

We can use this when we have a requirement to show Azure AD users in
People picker control.

## Microsoft Graph Toolkit with React

The Microsoft Graph Toolkit React components (mgt-react) allow React
developers to use the Microsoft Graph Toolkit in their React
applications. The library wraps all Microsoft Graph Toolkit components
and exports them as React components.
All components are available via the npm package and are named using
PascalCase. To use a component, first, import it at the top.
For more details refer to
[use-toolkit-with-react](https://docs.microsoft.com/graph/toolkit/get-started/use-toolkit-with-react).

## Implementation

-   Open a command prompt
-   Move to the path where you want to create a project
-   Create a project directory using:
    md rect-azure-users
Move to the above-created directory using:
    cd rect-azure-users
Now execute the below command to create an SPFx solution:
    yo @microsoft/sharepoint
It will ask some questions, as shown below,

![Implementations.png](images/Implementations.png)

Now install a Microsoft Graph toolkit React NPM package as below,
    npm i @microsoft/mgt-react
After a successful installation, we can open a project in any source
code tool. Here, I am using the VS code, so I will execute the command:
    code .
Move to the **package-solution.json** and add the below permissions in
**webApiPermissionRequests**,
 

```json
 "webApiPermissionRequests": [
      {
        "resource": "Microsoft Graph",
        "scope": "User.Read.All"
      },
      {
        "resource": "Microsoft Graph",
        "scope": "GroupMember.Read.All"
      },
      {
        "resource": "Microsoft Graph",
        "scope": "Group.Read.All"
      },
      {
        "resource": "Microsoft Graph",
        "scope": "Directory.Read.All"
      }
    ],
```
 

Now go to the **src \> webparts \> webpart \> components \>
I{webpartname}Props.ts** file,
Here we will create a property for graph Client and context as below,
 

```javascript
import { MSGraphClient } from "@microsoft/sp-http";
import { WebPartContext } from "@microsoft/sp-webpart-base";

export interface IReactAzureadUsersProps {
  description: string;
  graphClient: MSGraphClient;
  context: WebPartContext;
}
```
 

Now create a file to manage the state. The filename should
be **I{webpartname}State.ts**. And in this, we will create two
properties groupID and members.
 

```javascript
export interface IReactAzureadUsersState {
  groupId: string,
  memers: any[]
}
```
 

Move to the **{webpartname}.ts** file. Here we will get the graph client
and context and then we will pass it to the property,

1.  Import required packages like **MSGraphClient**, **Providers**, and
**SharePointProvider**.

2.  In **OnInit()**, get context and graph client.

3.  In **render()**, pass properties so we can use them in our
component.
 

```javascript
import * as React from 'react';
import * as ReactDom from 'react-dom';
import { Version } from '@microsoft/sp-core-library';
import {
  IPropertyPaneConfiguration,
  PropertyPaneTextField
} from '@microsoft/sp-property-pane';
import { BaseClientSideWebPart } from '@microsoft/sp-webpart-base';

import * as strings from 'ReactAzureadUsersWebPartStrings';
import ReactAzureadUsers from './components/ReactAzureadUsers';
import { IReactAzureadUsersProps } from './components/IReactAzureadUsersProps';
import { MSGraphClient } from '@microsoft/sp-http';
import { Providers, SharePointProvider } from '@microsoft/mgt-spfx';

export interface IReactAzureadUsersWebPartProps {
  description: string;
}

export default class ReactAzureadUsersWebPart extends BaseClientSideWebPart<IReactAzureadUsersWebPartProps> {

  private graphClient: MSGraphClient;

  public onInit(): Promise<void> {
    if (!Providers.globalProvider) {
      Providers.globalProvider = new SharePointProvider(this.context);
    }
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
    const element: React.ReactElement<IReactAzureadUsersProps> = React.createElement(
      ReactAzureadUsers,
      {
        description: this.properties.description,
        graphClient: this.graphClient,
        context: this.context
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
 

Now move to the **{webpartname}.tsx** file.

1.  Setup the graph context

2.  Create a method to get the Azure group Id by group name and set it
into the state.

3.  Then get group members using by group id and then set it into the
state so we can render it.

4.  Now render it in PeoplePicker control, so here in People property,
we have to pass members.
 

```javascript
import * as React from 'react';
import { IReactAzureadUsersProps } from './IReactAzureadUsersProps';
import { IReactAzureadUsersState } from './IReactAzureadUsersState';
import { graph } from "@pnp/graph";
import "@pnp/graph/users";
import "@pnp/graph/groups";
import {  PeoplePicker } from '@microsoft/mgt-react';

export default class ReactAzureadUsers extends React.Component<IReactAzureadUsersProps, IReactAzureadUsersState> {

  constructor(props: IReactAzureadUsersProps) {
    super(props);
    this.state = {
      groupId: '',
      memers: []
    }
  }

  public onInit(): Promise<void> {
    graph.setup({
      spfxContext: this.context
    })
    return Promise.resolve();
  }

  public componentDidMount() {
    this.getAzureGroupId()
  }

  public async getAzureGroupId() {

    let groupName = "Employees"
    let getGroupIDUrl = `groups?$select=id,displayName&$filter=displayName eq '${groupName}'`;

    if (!this.props.graphClient) {
      return;
    }

    this.props.graphClient
      .api(getGroupIDUrl)
      .version("v1.0")
      .get((err: any, res: any): void => {
        if (err) {
          console.log("Getting error in retrieving azure group =>", err)
        }
        if (res) {
          if (res && res.value.length) {
            console.log(res.value);
            this.setState({
              groupId: res.value[0].id
            })
          }
          this.getGroupMembers(this.state.groupId);
        }
      });
  }

  public getGroupMembers(id: string) {
    if (!this.props.graphClient) {
      return;
    }
    let getGroupMembersUrl = `groups/${id}/members`;
    this.props.graphClient
      .api(getGroupMembersUrl)
      .version("v1.0")
      .get((err: any, res: any): void => {
        if (err) {
          console.log("Getting error in retrieving group members =>", err)
        }
        if (res) {
          if (res && res.value.length) {
            console.log(res.value);
            this.setState({
              memers: res.value
            })
          }
        }
      });
  }

  public render(): React.ReactElement<IReactAzureadUsersProps> {
    return (
      <React.Fragment>
        <h2>Azure AD Users</h2>
        <PeoplePicker
          people={this.state.memers}
          showMax={3}
        />
      </React.Fragment >
    );
  }
}
```
 
 
## Output

![react-ad-mgt-users.gif](images/react-ad-mgt-users.gif)
 

Find the [full source
code](https://github.com/chandaniprajapati/mgt-react-people-pickcer).  

## Summary

In this article, we have seen how to bind AD users in people picker
using the MS graph toolkit react library.

I hope this helps.

Sharing is caring!
