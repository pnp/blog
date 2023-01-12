---
title: "How to use fluent UI react persona control in SPFx?"
date: 2021-06-10T05:56:00-04:00
author: "Chandani Prajapati"
githubname: chandaniprajapati
categories: ["Community post"]
images:
- images/Output.png
tags: ["SharePoint Framework (SPFx)"]
type: "regular"
---

## Introduction

A persona is a visual representation of a person across products,
typically showcasing the image that person has chosen to upload
themselves. This control includes an individual's avatar (an uploaded
image or a composition of the person's initials on a background color),
their name or identification, and so on. for more details refer to
[Fluent UI persona](https://developer.microsoft.com/fluentui#/controls/web/persona).

## Scenario 

We will create an SPFx web part in the way to fetch users from any
specific group and render these users using a persona. so let's see
step-by-step implementation.
In the end, our output will be like this,
![Output.png](images/Output.png)

## Implementation  

Open a command prompt\
Move to the path where you want to create a project\
Create a project directory using:
    md spfx-persona

Move to the above-created directory using:


    cd spfx-persona



Now execute the below command to create an SPFx solution:


    yo @microsoft/sharepoint


It will ask some questions, as shown below,

![Project Structure.png](images/Project Structure.png)



Now we will install **pnpjs** as shown below:
    npm install @pnp/sp --save
After a successful installation, we can open a project in any source
code tool. Here, I am using the VS code, so I will execute the command:

```bash
    code .
```

1. Move to
the `src/webparts/spfxpersona/components/**ISpfxpersonaProps.ts` and
create a context property as below,

```javascript
import { WebPartContext } from "@microsoft/sp-webpart-base";

export interface ISpfxpersonaProps {
  description: string;
  context: WebPartContext
}
```

1. Now move to the **SpfxpersonaWebPart.ts **file and here we
initialize an SP context and pass it in the property.

```javascript
import * as React from 'react';
import * as ReactDom from 'react-dom';
import { Version } from '@microsoft/sp-core-library';
import {
  IPropertyPaneConfiguration,
  PropertyPaneTextField
} from '@microsoft/sp-property-pane';
import { BaseClientSideWebPart } from '@microsoft/sp-webpart-base';

import * as strings from 'SpfxpersonaWebPartStrings';
import Spfxpersona from './components/Spfxpersona';
import { ISpfxpersonaProps } from './components/ISpfxpersonaProps';
import { sp } from "@pnp/sp/presets/all";

export interface ISpfxpersonaWebPartProps {
  description: string;
}

export default class SpfxpersonaWebPart extends BaseClientSideWebPart<ISpfxpersonaWebPartProps> {

  public onInit(): Promise<void> {
    return super.onInit().then(_ => {
      sp.setup({
        spfxContext: this.context
      });
    });
  }

  public render(): void {
    const element: React.ReactElement<ISpfxpersonaProps> = React.createElement(
      Spfxpersona,
      {
        description: this.properties.description,
        context: this.context,
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

Create a common component means folder
called **RenderProfilePicture**
inside *src/webparts/spfxpersona/Common/Components. *And inside this
folder create a file **RenderProfilePicture.tsx** **.**


At here we will pass a property as an argument and render it and in the
main component, we will call API to get items so they will be set
through the property. 


```javascript
import * as React from 'react';
import { Persona, PersonaSize } from 'office-ui-fabric-react/lib/Persona';
interface IProfilePicProps {
    loginName: string;
    displayName: string;
    getUserProfileUrl?: () => Promise<string>;
}

export function RenderProfilePicture(props: IProfilePicProps) {

    const [profileUrl, setProfileUrl] = React.useState<string>();
    let { displayName, getUserProfileUrl } = props;

    React.useEffect(() => {
        getUserProfileUrl().then(url => {
            setProfileUrl(url);
        });
    }, [props])

    return (


            <Persona
                imageUrl={profileUrl}
                text={displayName}
                size={PersonaSize.size32}
                imageAlt={displayName}
                styles={{ primaryText: { fontSize: '14px' }, root: { margin: '10px' } }}
            />
        );
}
```

Now move to the **Spfxpersona.tsx** our main component. here we will
call APIs and render the child component here.


Create a state interface and initialize a user state.



At here we are getting the user from a particular group ID so first call
API to get users from the group.

And then we will get user profile properties to get users' profile
picture so after calling the get users method we will call API to get
user profile properties.

And then render the component.


```javascript
import * as React from 'react';
import styles from './Spfxpersona.module.scss';
import { ISpfxpersonaProps } from './ISpfxpersonaProps';
import { escape } from '@microsoft/sp-lodash-subset';
import { sp } from "@pnp/sp/presets/all";
import { RenderProfilePicture } from '../Common/Components/RenderProfilePicture/RenderProfilePicture'

export interface ISpfxpersonaWebPartState {
  users: any[]
}
export default class Spfxpersona extends React.Component<ISpfxpersonaProps, ISpfxpersonaWebPartState> {

  constructor(props: ISpfxpersonaProps) {
    super(props);
    this.state = {
      users: []
    }
  }

  private async getUserProfileUrl(loginName: string) {
    const userPictureUrl = await sp.profiles.getUserProfilePropertyFor(loginName, 'PictureURL');
    return userPictureUrl;
  }

  private async getSiteUsers() {
    const grpUsers = await sp.web.siteGroups.getById(3).users();
    this.setState({ users: grpUsers })
  }

  public componentDidMount() {
    this.getSiteUsers()
  }

  public render(): React.ReactElement<ISpfxpersonaProps> {
    return (
      <div className={styles.spfxpersona}>
        <span>USERS WITH PERSONA CARD</span>
        {this.state.users.map(m =>
          <RenderProfilePicture
            loginName={m.LoginName}
            displayName={m.Title}
            getUserProfileUrl={() => this.getUserProfileUrl(m.LoginName)}  ></RenderProfilePicture>
        )}

    );
  }
}
```


Now serve the application using the below command,


    gulp serve



Now test the webpart in SharePoint-SiteURL +
/\_layouts/15/workbench.aspx.



## Output

![Output.png](images/Output.png)
 

Find here the [full source code
](https://github.com/chandaniprajapati/spfx-fluentui-persona).
 

## Summary

In this article, we have seen the step-by-step implementation of how to
use a persona card to show the users' profile picture.
\
I hope this helps, if this helps you then share it with others.
\
Sharing is caring!
