---
title: "Consume Graph API to Adaptive Card Extension (ACEs) SPFx component type"
date: 2021-08-04T03:14:00-04:00
author: "Dipen Shah"
githubname: dips365
categories: ["Community post"]
images:
- images/People1.jpg
tags: ["SharePoint framework (SPFx)", "SPFx Adaptive Card Extensions", "Microsoft Graph"]
type: "regular"
---

## Introduction

SPFx is getting matured platform day by day to make extended
application to M365 platform. Recently, SPFx 1.13.0 Beta launched with
extensive capabilities to extend modern employee experience through
ACEs. ACEs is a type of component which is stand for  Adaptive Cards
Extensions.
ACEs come up with extensive possibilities to make a component which will
be enabled customization to modern employee experience in Microsoft viva
connection dashboard.

## Learning Objectives

1. Create SPFx using Adaptive Card Extension
2. Consume Graph API in ACEs project\
3. Render My team in Card View in ACEs
4. View user details in Quick View in ACEs

## Prerequisites for SPFx ACEs Project

1.  [Node.js v12 LTS](https://nodejs.org/en/blog/release/v12.13.0/)
2.  Gulp v4
3.  Yeoman v3
4.  [Set up SPFx Development
    Environment](https://docs.microsoft.com/sharepoint/dev/spfx/set-up-your-development-environment)
Install latest beta release using below code
 
```bash
npm install /generator-sharepoint@next --global
```
 
## Create SPFx using Adaptive Card Extension

Open node command prompt
Reach to your desire location where you want to create a solution
Run below command
 
```bash
yo @microsoft/sharepoint
```
 
When prompted, enter the below values to each parameter.
![People1.jpg](images/People1.jpg)
 Once all required packages are downloaded then you will get a message
as below.
![People2.jpg](images/People2.jpg)
Now open a solution in visual studio code or editor that you want to
use.
The below command is used to open the solution in VS Code.
 
```bash
code .
```
 
Install require packages to connect graph in solution.
 
```bash
npm install @pnp/sp @pnp/graph @pnp/logging
```
 
## Consume Graph API in ACEs project

Create folder called \"Models\" in \"..\\src\\\".
Create file with name \"mmp.models.ts\" in folder models at location
\"..\\src\\models\\\".
Copy below code and paste it in file.
 
```javascript
export interface IMyTeam {
  userPrincipalName: string;
  displayName: string;
  givenName: string;
  id: string;
  mobilePhone: string;
  officeLocation: string;
  preferredLanguage: string;
  surname: string;
  jobTitle: string;
  mail: string;
}
export interface IConfig {
  members: IMyTeam[];
}
export class Config implements IConfig {
  constructor(
    public members: IMyTeam[] = []
  ) { }
}
```
 
Create a folder called Services in \"..\\src\\\".
Create a new file called \"mmp.service.ts\" in Folder \"Services\" at
location \"..\\src\\Services\".
Copy below code to it.
 
```javascript
import { Logger, LogLevel } from "@pnp/logging";
import "@pnp/graph/users";
import "@pnp/graph/onedrive";
import "@pnp/graph/groups";
import { graph, graphGet, GraphQueryable } from "@pnp/graph";
import forEach from "lodash/forEach";
import { IConfig, Config, IMyTeam } from "../models/mmp.models";
export interface IMMPService {
    GenerateConfig: () => Promise<IConfig>;
}
export class MMPServie implements IMMPService {
    private LOG_SOURCE: string = "MMPServie";
    constructor() {
    }
    public async GenerateConfig(): Promise<IConfig> {
        let mmpConfig: IConfig = null;
        try {
            mmpConfig = new Config();
            mmpConfig.members = await this._directReportsToMe();
        } catch (error) {
            Logger.write(`${this.LOG_SOURCE} (GenerateConfig) - ${error} - `, LogLevel.Error);
        }
        return mmpConfig;
    }
    private async _directReportsToMe(): Promise<IMyTeam[]> {
        let returnValue: IMyTeam[] = [];
        try {
            let directReports = await graph.me.directReports();
            if (directReports.length > 0) {
                forEach(directReports, (o: any) => {
                    returnValue.push({
                        displayName: o.displayName,
                        id: o.id,
                        jobTitle: o.jobTitle,
                        givenName: o.givenName,
                        mail: o.mail,
                        mobilePhone: o.mobilePhone,
                        officeLocation: o.officeLocation,
                        preferredLanguage: o.preferredLanguage,
                        surname: o.surname,
                        userPrincipalName: o.userPrincipalName
                    });
                });
            }
        } catch (error) {
            Logger.write(`${this.LOG_SOURCE} (_directReportsToMe) - ${error} - `, LogLevel.Error);
        }
        return returnValue;
    }
}
```
 
Create a new file called "service.ts" in folder "Services" and add
below code in that.
 
```javascript
import { IConfig, IMyTeam } from "../models/mmp.models";
import { Logger, LogLevel } from "@pnp/logging";
import { IMMPService, MMPServie } from "../services/mmp.service";
export interface IService {
    Init(): Promise<void>;
}
export class Service implements IService {
    private LOG_SOURCE: string = "Service";
    private _mmpService: IMMPService = new MMPServie();
    private _ready: boolean = false;
    private _currentConfig: IConfig = null;
    public async Init(): Promise<void> {
        await this._getConfig();
    }
    public get Ready(): boolean {
        return this._ready;
    }
    public get Config(): IConfig {
        return this._currentConfig;
    }
    private async _getConfig(): Promise<void> {
        try {
            this._currentConfig = await this._mmpService.GenerateConfig();
            this._ready = true;
        } catch (error) {
            Logger.write(`${this.LOG_SOURCE} (_getConfig) - ${error} - `, LogLevel.Error);
        }
    }
}
```
 
Open file "MyPeopleAdaptiveCardExtension.ts" at location
"..\\src\\adaptiveCardExtensions\\myPeople\\MyPeopleAdaptiveCardExtension.ts"\
Import below statement on top.
 
```javascript
import { sp } from "@pnp/sp";
import { graph } from "@pnp/graph";
import { Logger, LogLevel, ConsoleListener } from "@pnp/logging";
import { IConfig, IMyTeam } from '../../models/mmp.models';
import { Service } from "../../services/service";
```
 
 Update Interface with below code
 
```javascript
export interface IMyPeopleAdaptiveCardExtensionState {
  currentIndex:number;
  currentConfig: IConfig;
}
```
 
Define private variable in class.
 
```javascript
 private LOG_SOURCE: string = "MyPeopleAdaptiveCardExtension";
  private service: Service = new Service();
```
 
Update OnInit() with below lines of code
 
```javascript
public async onInit(): Promise<void> {
    Logger.subscribe(new ConsoleListener());
    Logger.activeLogLevel = LogLevel.Info;
    try {
      sp.setup({ spfxContext: this.context });
      graph.setup({ spfxContext: this.context });
      await this.service.Init();
      this.state = {
        currentIndex:0,
        currentConfig: this.service.Config
      };
    } catch (error) {
      Logger.write(`${this.LOG_SOURCE} (_onInit) - ${error} - `, LogLevel.Error);
    }
    this.cardNavigator.register(CARD_VIEW_REGISTRY_ID, () => new CardView());
    this.quickViewNavigator.register(QUICK_VIEW_REGISTRY_ID, () => new QuickView());
    return Promise.resolve();
  }
```
 
## Render My team in Card View in ACEs

Open file Cardview.ts at location
\"..\\src\\adaptiveCardExtensions\\myPeople\\cardView\\CardView.ts\".
Update three methods(Cardbuttons(), data() and onCardSelection()) with
below code.
 
```javascript
public get cardButtons(): [ICardButton] | [ICardButton, ICardButton] | undefined {
    const buttons: ICardButton[] = [];
    if (this.state.currentIndex > 0) {
      buttons.push({
        title: 'Previous',
        action: {
          type: 'Submit',
          parameters: {
            id: 'previous',
            op: -1
          }
        }
      });
    }
    if (this.state.currentIndex < this.state.currentConfig.members.length - 1) {
      buttons.push({
        title: 'Next',
        action: {
          type: 'Submit',
          parameters: {
            id: 'next',
            op: 1 // Increment the index
          }
        }
      });
      return buttons as [ICardButton] | [ICardButton, ICardButton];
    }
  }
  public get data(): IBasicCardParameters {
    const { givenName, mail,displayName } = this.state.currentConfig.members[this.state.currentIndex];
    return {
      primaryText: `Display Name: ${displayName} | mail: ${mail}`,
    };
  }
  public get onCardSelection(): IQuickViewCardAction | IExternalLinkCardAction | undefined {
    return {
      type: 'QuickView',
      parameters: {
        view: QUICK_VIEW_REGISTRY_ID,
      }
    };
  }
```
 
## View user details in Quick View in ACEs

QuickView.ts file is responsible to render user details on card click.
Open Quickview.ts file and import models in it and add new property to
IQuickViewData
 
``` {.lia-code-sample .language-applescript}
import { IMyTeam } from '../../../models/mmp.models';
export interface IQuickViewData {
  subTitle: string;
  title: string;
  description: string;
  item: IMyTeam; // Add it
}
```
 
Update Data method in QuickView.ts file with below code.
 
```javascript
 public get data(): IQuickViewData {
    return {
      subTitle: strings.SubTitle,
      title: strings.Title,
      description: this.properties.description,
      item: this.state.currentConfig.members[this.state.currentIndex]
    };
  }
```
 
Update template() in Quickview.ts file with custom JSON format to
display user information.
 
```javascript
public get template(): ISPFxAdaptiveCard {
    return {
      "type": "AdaptiveCard",
      "version": "1.0",
      "body": [
        {
          "type": "Container",
          "$data": "${item}",
          "items": [
            {
              "type": "TextBlock",
              "weight": "Bolder",
              "text": "Display Name: ${displayName}",
              "color":"attention"
            },
            {
              "type": "Container",
              "spacing": "Small",
              "items": [
                {
                  "type": "TextBlock",
                  "text": "Surname: ${surname}",
                  "spacing": "Small"
                },
                {
                  "type": "TextBlock",
                  "text": "Given Name: ${givenName}",
                  "spacing": "Small"
                },
                {
                  "type": "TextBlock",
                  "text": "Mail: ${mail}",
                  "spacing": "Small",
                  "color": "good",
                }
              ]
            }
          ],
          "separator": true
        }
      ],
      "$schema": "http://adaptivecards.io/schemas/adaptive-card.json"
    }
  }
```
 
Set permission to access graph API from SPFx.
open package-solution.json file at location \"
..\\Manageteam\\config\\package-solution.json\" and add below code.
 
```json
 "webApiPermissionRequests": [
      {
        "resource": "Microsoft Graph",
        "scope": "Directory.ReadWrite.All"
      }
    ]}
```
 
Run solution using below command
 
``` {.lia-code-sample .language-applescript}
gulp serve -l --nobrowser
```
 
Open URL <https://contoso.sharepoint.com/_layouts/workbench.aspx>\
Add your extension using select  add web part button.
![1.gif](images/1.gif)


## Conclusion

In this article, We explored how to create ACEs solution
using SPFx, How to Consume Graph API in ACEs, How to render custom
adaptive card using customization of JSON and add multiple button in
card view.
