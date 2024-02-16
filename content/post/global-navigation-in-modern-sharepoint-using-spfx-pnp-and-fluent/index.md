---
title: "Global Navigation In Modern SharePoint Using SPFx, PnP And Fluent UI"
date: 2021-09-13T02:44:00-04:00
author: "Dipen Shah"
githubname: dips365
categories: []
images:
- images/GN3.jpg
tags: ["SharePoint Framework (SPFx)"]
type: "regular"
---

## Introduction

Modern SharePoint architecture gives fantastic OOTB global navigation,
and hub site navigation has amazing potential to maintain consistency
throughout the portal. Then why do we need to develop custom global
navigation in modern SharePoint sites?


Let us talk about the business scenario.


Nowadays, a number of organizations are migrating classic intranet
portals to modern sites. Many of them have implemented custom global
navigation in a classic environment with a number of links and complex
tree structures.


Employees are habitual with this global navigation. So, many
organizations prefer similar global navigation in Modern SharePoint
sites.

Let's Begin,


Below Artifacts are going to be used,

-   [SharePoint communication
    Site](https://support.microsoft.com/office/create-a-communication-site-in-sharepoint-7fb44b20-a72f-4d2c-9173-fc8f59ba50eb)
-   [SharePoint Framework
    (SPFx)](https://learn.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview)
-   [Application
    Customizer](https://learn.microsoft.com/sharepoint/dev/spfx/extensions/get-started/using-page-placeholder-with-extensions)
-   [PnP Taxonomy](https://pnp.github.io/pnpjs/sp/taxonomy/)
-   [Fluent Ui Command
    Bar](https://developer.microsoft.com/fluentui#/controls/web/commandbar)

## Steps

1.  Configure Terms in Term Stores
2.  Create Solution for Application Customizer
3.  Import Required Packages
4.  Create React Component
5.  Add React Component Reference to Application Customizer
6.  Get Terms using PnP
7.  Render Terms using Command Bar and styling 
8.  Test Solution

**Step 1 - Configure Terms in Term Store.**

Go to URL
: `https://\<TenantName>-admin.sharepoint.com/\_layouts/15/online/AdminHome.aspx#/termStoreAdminCenter`

Create Term Group.

-   Copy Group GUID and Paste it into one document

Create Term Set inside created Term Group

-   Enable Use Term set for Site Navigation
-   Copy term Set Id and Paste it in one document.

Create Terms Inside create Term Sets.
![Global navigation in Modern SharePoint Using SPFx PnP and Fluent UI.gif](images/Global navigation in Modern SharePoint Using SPFx PnP and Fluent UI.gif)

**Step 2 - Create SPFx Solution for Application Customizer**

Open Node command Prompt.

Go to your physical location where you want to create a solution.

Once all required packages are installed then you will get the below
message.
![GN3.jpg](images/GN3.jpg)

Open Code in visual studio code by typing below one line code in node
command prompt.

```powershell
C:\Demo\GlobalNavigation>code .
```

The solution structure looks like the ad below.
![GV3.jpg](images/GV3.jpg)

## Step 3 - Import required packages from npm

Install PnP npm package,

```javascript
npm install @pnp/sp
```

Install React Fluent UI Package,\

```javascript
npm install @fluentui/react
```

Install react and react Dom and Its Dev Dependencies.

```javascript
npm install react@16.9.0 --save
npm install react-dom@16.9.0 --save
```

Open package.json file which should look like as below.

```json
{
  "name": "sample-demo-application",
  "version": "0.0.1",
  "private": true,
  "main": "lib/index.js",
  "scripts": {
    "build": "gulp bundle",
    "clean": "gulp clean",
    "test": "gulp test"
  },
  "dependencies": {
    "@fluentui/react": "^8.22.3",
    "@microsoft/decorators": "1.12.1",
    "@microsoft/sp-application-base": "1.12.1",
    "@microsoft/sp-core-library": "1.12.1",
    "@microsoft/sp-dialog": "1.12.1",
    "@microsoft/sp-office-ui-fabric-core": "^1.12.1",
    "@pnp/sp": "^2.7.0",
    "react": "^16.9.0",
    "react-dom": "^16.9.0"
  },
  "devDependencies": {
    "@types/react": "16.9.36",
    "@types/react-dom": "16.9.8",
    "@microsoft/sp-build-web": "1.12.1",
    "@microsoft/sp-tslint-rules": "1.12.1",
    "@microsoft/sp-module-interfaces": "1.12.1",
    "@microsoft/sp-webpart-workbench": "1.12.1",
    "@microsoft/rush-stack-compiler-3.7": "0.2.3",
    "gulp": "~4.0.2",
    "ajv": "~5.2.2",
    "@types/webpack-env": "1.13.1"
  }
}
```

## Step 4 - Create React Component

Create new folder called "Components" to
"..src\\extensions\\gobalNavigationBar".

Create 3 files inside the components folder.

1.  GlobalNav.tsx
2.  IGlobalNavProps.ts
3.  IGlobalNavState.ts

![GV4.jpg](images/GV4.jpg)

Add below code to IGlobalNavProps.ts,

```javascript
export interface IGlobalNavProps {
    termGroupId:string;
    termSetId: string;
}
```

Add below code to IGlobalNavState.ts,

```javascript
import { IOrderedTermInfo } from '@pnp/sp/taxonomy';
export interface IGobalNavState {
    loading: boolean;
    terms: IOrderedTermInfo[];
}
```

Add below code to IGlobalNav.tsx,

```javascript
import * as React from 'react';
import { IGlobalNavProps } from "./IGlobalNavProps";
import { IGobalNavState } from "./IGlobalNavState";
export default class GlobalNav extends React.Component<IGlobalNavProps, IGobalNavState> {
    constructor(props: IGlobalNavProps) {
        super(props);
        this.state = {
            loading: false,
            terms: []
        }
    }
    public componentDidMount() {
        // Code here to get items
    }
    public render(): React.ReactElement<IGlobalNavProps> {
        return (


                Hello World
            </div>
        );
    }
}
```

## Step 5 - Add React Component Reference to Application Customizer

Open GobalNavigationBarApplicationCustomizer.ts file and add the below
code.

**GobalNavigationBarApplicationCustomizer.ts**

```javascript
import * as React from 'react';
import * as ReactDom from 'react-dom';
import { sp } from "@pnp/sp";
import { override } from '@microsoft/decorators';
import { Log } from '@microsoft/sp-core-library';
import {
  PlaceholderContent,
  PlaceholderName,
  BaseApplicationCustomizer
} from '@microsoft/sp-application-base';
import GlobalNav from "./Components/GlobalNav";
import { IGlobalNavProps } from "./Components/IGlobalNavProps";
import * as strings from 'GobalNavigationBarApplicationCustomizerStrings';
const LOG_SOURCE: string = 'GobalNavigationBarApplicationCustomizer';
/**
 * If your command set uses the ClientSideComponentProperties JSON input,
 * it will be deserialized into the BaseExtension.properties object.
 * You can define an interface to describe it.
 */
export interface IGobalNavigationBarApplicationCustomizerProperties {
  // This is an example; replace with your own property
  termGroupId: string;
  termSetId: string;
}

/** A Custom Action which can be run during execution of a Client Side Application */
export default class GobalNavigationBarApplicationCustomizer
  extends BaseApplicationCustomizer<IGobalNavigationBarApplicationCustomizerProperties> {
  private _topPlaceholder: PlaceholderContent | undefined;
  @override
  public onInit(): Promise<void> {
    Log.info(LOG_SOURCE, `Initialized ${strings.Title}`);
    super.onInit().then(_ => {
      console.log("super oninit called");
      sp.setup({
        spfxContext: this.context
      });
    }).then((_) => {
      console.log("Sp Initilize");
      this.context.placeholderProvider.changedEvent.add(this, this._renderPlaceHolders);
    });
    return Promise.resolve();
  }

  private _renderPlaceHolders(): void {
    console.log("HelloWorldApplicationCustomizer._renderPlaceHolders()");
    console.log(
      "Available placeholders: ",
      this.context.placeholderProvider.placeholderNames
        .map(name => PlaceholderName[name])
        .join(", ")
    );

    // Handling the top placeholder
    if (!this._topPlaceholder) {
      this._topPlaceholder = this.context.placeholderProvider.tryCreateContent(
        PlaceholderName.Top,
        { onDispose: this._onDispose }
      );

      // The extension should not assume that the expected placeholder is available.
      if (!this._topPlaceholder) {
        console.error("The expected placeholder (Top) was not found.");
        return;
      }
      if (this.properties) {
        // Add refrence of react component to this file.
        const element: React.ReactElement<IGlobalNavProps> = React.createElement(
          GlobalNav,
          {
            termGroupId: this.properties.termGroupId,
            termSetId: this.properties.termSetId
          }
        );
        ReactDom.render(element, this._topPlaceholder.domElement);
      }
    }
  }
  private _onDispose(): void {
    console.log('[HelloWorldApplicationCustomizer._onDispose] Disposed custom top and bottom placeholders.');
  }
}
```

## Step 6: Get Terms using PnP

Open GlobalNav.tsx file and do the below changes.

**GlobalNav.tsx**

Add below references to the file.

```javascript
import { sp } from "@pnp/sp";
import "@pnp/sp/taxonomy";
import { dateAdd, PnPClientStorage } from "@pnp/common";
import { IOrderedTermInfo } from '@pnp/sp/taxonomy';

const myKey: string = "navigationElements";
```

Update below code to **GlobalNav.tsx.**

```javascript
private store = new PnPClientStorage();
   constructor(props: IGlobalNavProps) {
       super(props);
       this.state = {
           loading: false,
           terms: []
       }
   }
```

Update componentdidmount() method with below code in **GlobalNav.tsx.**

```javascript
public componentDidMount() {
        this.setState({}, async () => {
            // this portion is responsible for getting terms from term store
            const cachedTermInfo = await this.store.local.getOrPut(myKey, () => {
                return sp.termStore.groups.getById(this.props.termGroupId).sets.getById(this.props.termSetId).getAllChildrenAsOrderedTree({ retrieveProperties: true });
            }, dateAdd(new Date(), "minute", 10));
            if (cachedTermInfo.length > 0) {
                console.log(cachedTermInfo);
                this.setState({ terms: cachedTermInfo });
            }
        });
```

## Step 7 - Render Terms using Command Bar

Open **GlobalNav.tsx **file.

Add below code before default class.

```javascript
import { IButtonStyles } from '@fluentui/react';
import { createTheme, ITheme } from 'office-ui-fabric-react/lib/Styling';
import { CommandBar, ICommandBarStyleProps } from "@fluentui/react/lib/CommandBar";
const theme: ITheme = createTheme({
    semanticColors: {
        bodyBackground: "#333",
        bodyText: "#fff"
    }
});
const CommandBarProps: ICommandBarStyleProps = {
    theme: theme
};
const buttonStyle: IButtonStyles = {
    root: {
        backgroundColor: "#333",
        color: "#fff"
    },
    menuIcon: {
        color: "#fff",
    }
};
```

Create new method menuItems() in **GlobalNav.tsx **file.

```javascript
private menuItems(menuItem: any, itemType: ContextualMenuItemType) {
        return ({
            key: menuItem.id,
            name: menuItem.defaultLabel,
            itemType: itemType,
            href: menuItem.children.length == 0 ?
                ((menuItem.localProperties != undefined && menuItem.localProperties[0].properties !== undefined && menuItem.localProperties[0].properties.length > 0) ?
                    menuItem.localProperties[0].properties.filter(x => x.key == "_Sys_Nav_SimpleLinkUrl")[0].value !== undefined ? menuItem.localProperties[0].properties.filter(x => x.key == "_Sys_Nav_SimpleLinkUrl")[0].value : null
                    : null)
                : null,
            subMenuProps: menuItem.children.length > 0 ?
                { items: menuItem.children.map((i) => { return (this.menuItems(i, ContextualMenuItemType.Normal)); }) }
                : null,
            isSubMenu: itemType != ContextualMenuItemType.Header,
            buttonStyles: buttonStyle
        });
    }

```

Update render() method in GlobalNav.tsx file.

```javascript

public render(): React.ReactElement<IGlobalNavProps> {
        var commandBarItems: any[] = [];
        if (this.state.terms.length > 0) {
            commandBarItems = this.state.terms.map((i) => {
                return (this.menuItems(i, ContextualMenuItemType.Header));
            });
        }
        return (
            <>
                {
                    this.state.terms.length > 0 &&


                        <CommandBar  {...CommandBarProps}
                            style={{ width: "100%" }}
                            items={commandBarItems}
                        />
                    </div>
                }
            </>
        );
    }
```

## Step 8 - Test Solution

Open "../config/serve.json" file and update a couple of properties.

Update pageUrl Property and Properties,

```javascript
{
  "$schema": "https://developer.microsoft.com/json-schemas/core-build/serve.schema.json",
  "port": 4321,
  "https": true,
  "serveConfigurations": {
    "default": {
      "pageUrl": "https://<tenantName>.sharepoint.com/sites/mySite/SitePages/myPage.aspx",
      "customActions": {
        "aeabebb8-02ce-4958-99b2-d640d0995588": {
          "location": "ClientSideExtension.ApplicationCustomizer",
          "properties": {
            "termGroupId": "<Add your Term Group Id>",
            "termSetId":"<Add your Term Set Id>"
          }
        }
      }
    },
    "gobalNavigationBar": {
      "pageUrl": "https://<tenantName>.sharepoint.com/sites/mySite/SitePages/myPage.aspx",
      "customActions": {
        "aeabebb8-02ce-4958-99b2-d640d0995588": {
          "location": "ClientSideExtension.ApplicationCustomizer",
          "properties": {
            "termGroupId": "<Add your Term Group Id>",
            "termSetId":"<Add your Term Set Id>"
          }
        }
      }
    }
  }
}
```

Run below command in Visual Studio Code Terminal.

```javascript
gulp clean
gulp build
gulp serve --config:"gobalNavigationBar"
```

![Global navigation in Modern SharePoint Using SPFx PnP and Fluent UI5.png](images/Global navigation in Modern SharePoint Using SPFx PnP and Fluent UI5.png)

Copy URL which is highlighted in yellow and paste it into the browser.

![Global navigation in Modern SharePoint Using SPFx PnP and Fluent UI6.gif](images/Global navigation in Modern SharePoint Using SPFx PnP and Fluent UI6.gif)


## Conclusion

We have implemented the SPFx solution and get terms from the term store
using PnP and render items in the command bar which is fluent UI
control.

Happy Coding
