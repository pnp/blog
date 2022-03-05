---
title: "Flexible and powerful logging using PnP Logging in SPFx"
date: 2021-08-17T05:15:00-04:00
author: "Sudharsan Kesavanarayanan"
githubname: sudharsank
categories: []
tags: []
type: "regular"


---

## Introduction
Logging plays an important role in any application. Whether it is a
simple or complex app, logging helps you to record not only errors but
also other information which you can use to improve your app. In this
article, we will see how we can leverage the logging feature provided by
**PnP** to capture different logs while communicating with SharePoint or
for any other features implemented in the component
 
## Understanding the Logging concept by PnP

The logging module can be used by installing the npm package
named **\@pnp/logging**. This is a very lightweight subscribable and
extensive logging framework. There are multiple ways to make use of this
feature in our web part, let us see the concept of using **Listeners**.
There are 2 listeners provided by **PnP**.
 
### ConsoleListener


This is a very simple listener as the name indicates, the log message is
written to the browser console. There are no settings for this listener.
It writes to the corresponding console method based on the log level.
 
### FunctionListener

This listener type will allow us to wrap our own functionality by
creating a function that takes a LogEntry as its single argument. This
is very useful if we already have a common logging mechanism that we can
leverage on it. Using this listener type, the message can be passed to
any system or stored in a list or in a file based on our own
implementation. The below steps and guidance will use this listener to
write the logs in a SharePoint list. Some of the log levels provided are
-   Verbose
-   Info
-   Warning
-   Error
-   Off
**Focus on Code**
Let us start by creating a new web part project using yeoman SharePoint
generator, before that create a folder where you want to create the web
part. Navigate to that folder and run the below command
 
 
 
```javascript
yo /sharepoint
```
 
 
 
The generator will ask you a couple of questions,
-   Enter the web part name as your solution name, and then select Enter.
-   Select Create a subfolder with the solution name for where to place
    the files.
-   Select **Y** to allow the solution to be deployed to all sites
    immediately.
-   Select **N** on the question if the solution contains unique
    permissions.
-   Enter the web part name.
-   Enter the web part description.
-   Choose the framework as '**React**'.
Once the project is created, install the required **pnp** modules from
npm using the below command. I had created a web part with the
name **PnPLogging**.
 
 
 
```javascript
npm i @pnp/sp @pnp/odata @pnp/logging --save-exact
```
 
 
 
Open the code in **VSCode** which is my favourite code editor for
SharePoint Framework. You can directly open the project folder from the
file menu or use the below command to open the VSCode from the command
line.
 
 
 
```javascript
cd \web part folder\
code .
```
 
 
 
Let's create a new folder under the **components** folder
named **common**. Inside the common folder create 2 files as named below
1.  **CustomLogger.ts** -- This file will have all the interfaces and
    methods for implementing the logging mechanism to write the logs in
    SharePoint List.
2.  **Util.ts** -- This file will have all the log methods to be
    implemented in our custom methods to pass certain information to the
    log entry.
Copy-paste the below code in the **CustomLogger.ts** file.
 
 
 
```csharp
import { LogLevel, ILogListener, ILogEntry } from "@pnp/logging";
import { sp } from "@pnp/sp";
import { IWeb, Web } from '@pnp/sp/webs';
import "@pnp/sp/webs";
import "@pnp/sp/site-users";
import "@pnp/sp/lists/web";
import "@pnp/sp/items/list";
 
export interface ILogData {
    FileName: string;
    MethodName: string;
    StackTrace: string;
}
 
export class LogData implements ILogData {
    constructor(
        public FileName: string = "",
        public MethodName: string = "",
        public StackTrace: string = ""
    ) { }
}
 
export interface ILogItem {
    ApplicationName: string;
    CodeFileName: string;
    MethodName: string;
    LoggedOn: Date;
    LoggedById: number;
    ErrorMessage: string;
    StackTrace: string;
}
 
export class LogItem implements ILogItem {
    constructor(
        public ApplicationName: string = "",
        public CodeFileName: string = "",
        public MethodName: string = "",
        public LoggedOn: Date = new Date(),
        public LoggedById: number = 0,
        public ErrorMessage: string = "",
        public StackTrace: string = ""
    ) { }
}
 
export default class CustomLogger implements ILogListener {
    private _applicationName: string;
    private _logListName: string;
    private _web: IWeb;
    private _userId: number;
    private _currentuser: string;
    private _writeLogFailed: boolean;
 
    constructor(applicationName: string, logWebUrl: string, logListName: string, currentUser: string) {
        //Initialize
        try {
            this._writeLogFailed = false;
            this._applicationName = applicationName;
            this._logListName = logListName;
            this._web = Web(logWebUrl);
            this._currentuser = currentUser;
            //this.init(currentUser);
        } catch (err) {
            console.error(`Error initializing CustomLogger - ${err}`);
        }
    }
 
    private async init(currentUser: string): Promise<number> {
        //Implement an asyncronous call to ensure the user is part of the web where the ApplicationLog list is and get their user id.
        try {
            let userResult = await this._web.ensureUser(`i:0#.f|membership|${currentUser}`);
            return userResult.data.Id;
            //console.log(this._userId);
        } catch (err) {
            console.error(`Error initializing CustomLogger (init) - ${err}`);
        }
    }
 
    public async log(entry: ILogEntry): Promise<void> {
        try {
            //If the entry is an error then log it to my Application Log table.  All other logging is handled by the console listener
            if (entry.level == LogLevel.Error) {
                if (!this._writeLogFailed) {
                    this._userId = await this.init(this._currentuser);
                    let stackArray = null;
                    if (entry.data.StackTrace && entry.data.StackTrace.length > 0)
                        stackArray = JSON.stringify(entry.data.StackTrace.split('\n').map((line) => { return line.trim(); }));
                    let newLogItem: LogItem = new LogItem(this._applicationName,
                        entry.data.FileName,
                        entry.data.MethodName,
                        new Date(),
                        this._userId,
                        entry.message,
                        stackArray);
                    sp.web.lists.getByTitle(this._logListName).items.add(newLogItem);
                }
            }
        } catch (err) {
            //Assume writing to SharePoint list failed and stop continuous writing
            this._writeLogFailed = true;
            console.error(`Error logging error to SharePoint list ${this._logListName} - ${err}`);
        }
        return;
    }
}
```
 
 
 
The main artefacts in the above code are
1.  **ILogData** -- This is an interface that is defined to tell what
    kind of information are gonna be logged to the list.
2.  **ILogItem** -- This is an interface that is defined to map the
    columns in the SharePoint Error log list to write the logs to the
    list.
3.  **CustomLogger** -- The actual class which implements the
    ILogListener interface
4.  **init** -- This method is implemented to get the current user
    information while writing the logs to the list.
5.  **log** -- This is the actual method where we will be implementing
    the actual functionality of parsing the log and write the detailed
    log info in the SharePoint List.
Copy-paste the below code in the **Util.ts** file
 
 
 
```csharp
import { LogLevel, ILogEntry, Logger } from '@pnp/logging';
import { ILogData } from './CustomLogger';
 
export function writeErrorLog(filename: string, methodname: string, stack: string, loglevel: LogLevel, err: any) {
    let data: ILogData = { FileName: filename, MethodName: methodname, StackTrace: stack };
    let logEntry: ILogEntry = { message: `${err.message}`, level: loglevel, data: data };
    Logger.log(logEntry);
}
```
 
 
 
This class has only one method named writeErrorLog which we will call on
the catch block of our function. This method in turn communicate with
the FunctionListener and write the log to the SharePoint List.
 
The logger with the custom methods has been implemented and the util
function to call the method has also been implemented, now let us see
how to subscribe to the listener.
 
Navigate to the \<webpart>.ts file and do the following
 
Import the following modules and classes in addition to the existing
imports
 
 
 
```csharp
import CustomLogger from './components/common/CustomLogger';
import { sp } from "@pnp/sp";
import { Logger, LogLevel, FunctionListener, ILogEntry } from "@pnp/logging";
```
 
 
 
Under the class, copy-paste the below code along with the boilerplate
code.
 
 
 
```csharp
public onInit(): Promise<void> {        
        return super.onInit().then(_ => {
            sp.setup(this.context);
            this.customLogging();
        });
    }
 
    private customLogging(): void {
        try {
            let listener = new FunctionListener((entry: ILogEntry) => {
                try {
                    switch (entry.level) {
                        case LogLevel.Verbose:
                            //console.info(entry.message);
                            break;
                        case LogLevel.Info:
                            //console.log(entry.message);
                            break;
                        case LogLevel.Warning:
                            //console.warn(entry.message);
                            break;
                        case LogLevel.Error:
                            let advanceLogging = new CustomLogger("Sample Logging", this.context.pageContext.site.absoluteUrl, "Error Log", this.context.pageContext.user.loginName);
                            Logger.subscribe(advanceLogging);
                            break;
                    }
                } catch (err) {
                    console.error(`Error executing customLogging FunctionListener - ${err}`);
                }
            });
            Logger.subscribe(listener);
        } catch (err) {
            console.error(`Error initializing customLogging - ${err}`);
        }
        return;
    }
```
 
 
 
In the above code, we are setting up the logger by providing the context
and we are also subscribing our custom logger to the Function Listener.
Navigate to the \<webpart>.tsx and copy-paste the below code
 
 
 
```csharp
import * as React from 'react';
import styles from './PnPLogging.module.scss';
import { IPnPLoggingProps } from './IPnPLoggingProps';
import { DefaultButton } from 'office-ui-fabric-react/lib/Button';
 
import { LogLevel } from '@pnp/logging';
import { sp } from "@pnp/sp";
import "@pnp/sp/webs";
import "@pnp/sp/lists/web";
import "@pnp/sp/items/list";
import * as util from './common/Util';
 
export default class PnPLogging extends React.Component<IPnPLoggingProps, {}> {
 
    constructor(props: IPnPLoggingProps) {
        super(props);
    }
 
    public _generateError = () => {
        sp.web.lists.getByTitle('Branches').items.select('Title').getAll().then(items => {
            console.log(items);
        }).catch((err: Error) => {
            util.writeErrorLog("PnPLogging.tsx", '_generateError', err.stack, LogLevel.Error, err);
        });
    }
 
    public _generateAsyncError = async () => {
        try {
            await sp.web.lists.getByTitle('Branches').items.select('Title').getAll();
        } catch (err) {
            util.writeErrorLog("PnPLogging.tsx", '_generateAsyncError', err.stack, LogLevel.Error, err);
        }
    }
 
    public render(): React.ReactElement<IPnPLoggingProps> {
        return (
            <div className={styles.pnPLogging}>
                <div className={styles.container}>
                    <div className={styles.row}>
                        <div className={styles.column}>
                            <DefaultButton onClick={this._generateError} text="Generate Error" />
                            <DefaultButton onClick={this._generateAsyncError} text="Generate Async Error" />
                        </div>
                    </div>
                </div>
            </div>
        );
    }
}
```
 
 
 
The above code is very simple, I have created 2 buttons to call the
method which will get the items from the list that doesn't exist. The
first method will use the PnP method with then and catch implementation,
the second method will use the same PnP method with async and await.
 
## Error Log list

Before running the above solution or deploying the package, create a
list named '**Error Log**' with the following fields. Make sure to
maintain the same field name.
-   **ApplicationName** -- Name of the application from where the logs
    fired
-   **CodeFileName** -- Name of the file from where the exception
    occurred.
-   **MethodName** -- Name of the method from where the exception
    occurred.
-   **ErrorMessage** -- Friendly message of the exception.
-   **StackTrace** -- Complete details of the exception message.
-   **LoggedBy** -- Current logged in user
-   **LoggedOn** -- Current date and time when the exception occurred.
 
***Source Code***
The source code along with other samples can be found in the below
github link.
 
[SPFx-Demos](https://github.com/sudharsank/spfx-demos)
 
***Happy Coding...***
