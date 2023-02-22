---
title: "How to start a new SPFx web part project with Microsoft Graph Toolkit and React"
date: 2021-03-07T07:46:00-05:00
author: "Yves Habersaat"
githubname: yhabersaat
categories: ["Community post"]
images:
- images/mgt-react-result-2.png
tags: ["SharePoint framework (SPFx)", "Microsoft Graph Toolkit"]
type: "regular"
---

**Context**

Microsoft Graph Toolkit is a set of reusable components working with
Microsoft Graph to accelerate your web developments with SharePoint
Online, Microsoft Teams and more. With this kit, developers don't have
to write any code for authentification and authorization so I'm sure
you'll save a lot of time using it in your various projects. Now let's
see how we setup a SPFx web part project with Microsoft Graph Toolkit
and React!

**Create a new SPFx web part project**

First, we need to create a new SPFx web part project with React
framework using Yeoman generator tool:

```javascript
yo @microsoft/sharepoint
```

**Note:** don't forget to choose React framework during the setup of
your project and use default project settings.

**Install Microsoft Graph Toolkit for React**

To install Microsoft Graph Toolkit for React, we need to install two
packages with npm as below:

1.  mgt
2.  mgt-react

But why two packages? Because we need to use **Providers** and
**SharePointProvider** classes included in mgt to pass the web part
context to mgt-react components inside onInit method of the web part.

Install the two required packages with the following npm commands:

```javascript
npm i @microsoft/mgt
npm i @microsoft/mgt-react
```

**Install MGT dependencies**

To use Microsoft Graph Toolkit components with React, we need to use
**TypeScript 3.7** at least. Install this dependency with the following
npm command:

```powershell
npm i @microsoft/rush-stack-compiler-3.7 --save-dev
```

**Note:** -dev command add this package inside the **devDependencies**
section in **package.json** file.
Then we need to update the **tsconfig.json** with the following content
at line 2:

```json
"extends": "./node_modules/@microsoft/rush-stack-compiler-3.7/includes/tsconfig-web.json"
```

Finally remove the following line from **tslint.json** to compile the
project without any warning:

```json
"no-use-before-declare": true
```

**Configure MGT in the project**

Now we have installed all the required dependencies, we can configure
MGT in our project. First you need to add the API permissions in your
**package-solution.json** file as below:

```json
    "webApiPermissionRequests": [
      {
          "resource": "Microsoft Graph",
          "scope": "User.Read.All"
      }
    ]
```

**Note:** you need to add all API permissions depending on which MGT
components you are using in your project. In this example, I just need
to read user profiles to display some properties in the web part with a
Person component.
After this, we need to pass the context of the web part to MGT
components, add the following code in your web part file (in my project
MgtReactDemoWebPart) as below:

```javascript
import { Providers, SharePointProvider } from '@microsoft/mgt';

// ...

protected onInit() {
  Providers.globalProvider = new SharePointProvider(this.context);
  return super.onInit();
}
```

**Use MGT components in the project**

We are ready to use MGT components in our project, in this example I'll
use the Person component to display basic informations about the current
user. To do this, we need to import classes from mgt-react then using
them in our render method as below:

```javascript
import { Person, PersonViewType } from '@microsoft/mgt-react';

// ...

public render(): React.ReactElement<IMgtReactDemoProps> {
    return (
      <div className={ styles.mgtReactDemo }>
        <Person personQuery="me" view={PersonViewType.twolines} line2Property={"jobTitle"}></Person>
      </div>
    );
}
```

We can now build and run our project for SharePoint Online service (no
local workbench) using the following command:

```powershell
gulp serve --nobrowser
```

To debug your web part in SharePoint Online service, use the workbench
located here:

```powershell
https://your-sharepoint-online-site/_layouts/workbench.aspx
```

We can now see the result of our web part using MGT in the SPO
workbench:

![mgt-react-result-2.png](images/mgt-react-result-2.png)

That's it, you have configured a SPFx web part project with Microsoft
Graph Toolkit and React. You can now integrate other components in your
web part project without writing any line of code. And don't forget to
look at the [Get](https://docs.microsoft.com/graph/toolkit/components/get)

component which provides a great way to query any Microsoft Graph
endpoint and display the results with a custom template you made for
your line of business application ;)
You can read this article in my
[blog](https://yhabersaat.ch/2021/03/06/spfx-web-part-microsoft-graph-toolkit-react "blog").

**Resources**

<https://docs.microsoft.com/graph/toolkit/get-started/overview>

<https://docs.microsoft.com/graph/toolkit/get-started/mgt-react>

<https://www.npmjs.com/package/@microsoft/mgt>

<https://www.npmjs.com/package/@microsoft/mgt-react>
