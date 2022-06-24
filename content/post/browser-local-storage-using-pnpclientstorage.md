---
title: "Browser Local Storage using PnPClientStorage"
date: 2021-08-31T01:54:00-04:00
author: "Sudharsan Kesavanarayanan"
githubname: sudharsank
categories: ["Community post"]
tags: []
type: "regular"
---

## Why do we need to use browser storage?

You may ask yourself a question that why do I need to use this? what is
the advantage of using browser storage? Is it secured? Let us see the
features of browser storage.

Almost 90% of the web parts are loaded based on the current logged in
users privilege and most of them will use some information from the UPS
properties defined. The classical model is to pull the information from
UPS on all the web parts whenever is required or to store the
information on a SharePoint list to access it easily. Either way
requires communication to SharePoint. What if there is a way to reduce
the communication and thereby will increase the web part performance?
the solution is to use **Browser Storage**. You can store user property
information of the current user in the local storage and then accessing
the storage value on all the web parts. You can also schedule a time for
the value to refresh.

The browser storage is used mainly for easy access of information that
won't be modified for a long time. Any sensitive data should not be
stored using local storage. The storage should be used with caution
because overloading the browser local storage will have an impact on the
page performance.


## Why do we need to use PnPClientStorage?

The normal local storage method is allowed to store the key-value pair
where the value should always be the string. PnPClientStorage module
provides a thin wrapper over the browser storage options for both local
and session storage. If neither option is available then it shims
storage with a non-persistent in memory polyfill. Also, most of the
boilerplate codes were already written for us to make use of it.


### Focus on the Code

Let us start by creating a new web part project using yeoman SharePoint
generator, before that create a folder where you want to create the web
part. Navigate to that folder and run the below command.

```javascript
yo @microsoft/sharepoint
```

The generator will ask you couple of questions,

-   Enter the web part name as your solution name, and then select
    Enter.
-   Select Create a subfolder with the solution name for where to place
    the files.
-   Select Y to allow the solution to be deployed to all sites
    immediately.
-   Select N on the question if the solution contains unique
    permissions.
-   Enter the web part name
-   Enter the web part description
-   Choose the framework as '**React**'

Once the project is created, install the required **PnP** modules from
npm using the below command. I had created a web part with the
name **LocalStorage**.

```javascript
npm i @pnp/sp @pnp/common --save-exact
```

Open the code in **VSCode** which is my favourite and flexible code
editor for SharePoint Framework. You can directly open the project
folder from the file menu or use the below command to open the VSCode
from the command line.

```javascript
cd \web part folder\
code .
```

Based on my web part name, there is a property file created to store the
properties for the parent component. In my case it
is **ILocalStorageProps.ts**. Copy the content and delete the file,
paste the content in the **LocalStorage.tsx** file and change the import
reference on the tsx and webpart.ts file. Open your webpart.ts file and
copy-paste the below code along with the other code in the file, here we
are setting up the pnp with the current context.

```javascript
import { sp } from "@pnp/sp";
```

Copy-paste the below code under the default class

```javascript
public onInit(): Promise<void> {
    return super.onInit().then(_ => {
        sp.setup(this.context);
    });
}
```

Navigate to your webpart.tsx file and copy-paste the below code.

```javascript
import * as React from 'react';
import styles from './LocalStorage.module.scss';
import { DefaultButton } from 'office-ui-fabric-react/lib/Button';
import { sp } from "@pnp/sp";
import "@pnp/sp/webs";
import "@pnp/sp/site-users";
import { ISiteUserInfo } from '@pnp/sp/site-users/types';
import { PnPClientStorage, dateAdd } from '@pnp/common';

const pnpStorage = new PnPClientStorage();

export interface ILocalStorageProps {
    description: string;
}

export interface ILocalStorageState {
    userinfo: ISiteUserInfo;
}

export default class LocalStorage extends React.Component<ILocalStorageProps, ILocalStorageState> {

    constructor(props: ILocalStorageProps) {
        super(props);
        this.state = {
            userinfo: null
        };
    }

    public _storeCurrentUserInfo = async () => {
        let currentUserInfo: ISiteUserInfo = pnpStorage.local.get("PnP_UserInfo");
        if (!currentUserInfo) {
            currentUserInfo = await sp.web.currentUser.get();
            pnpStorage.local.put('PnP_UserInfo', currentUserInfo, dateAdd(new Date(), 'hour', 1));
        }
    }

    public _getStoredUserInfo = async () => {
        let currentUserInfo: ISiteUserInfo = pnpStorage.local.get("PnP_UserInfo");
        if (currentUserInfo) this.setState({ userinfo: currentUserInfo });
        else this.setState({ userinfo: null });
    }

    public componentDidMount() {
        pnpStorage.local.deleteExpired();
    }

    public render(): React.ReactElement<ILocalStorageProps> {
        return (
            <div className={styles.localStorage}>
                <div className={styles.container}>
                    <div className={styles.row}>
                        <div className={styles.column}>
                            <DefaultButton text="Store User Info" onSelect={this._storeCurrentUserInfo} />
                            <DefaultButton text="Get User Info from Storage" onSelect={this._getStoredUserInfo} />
                            <div style={{ display: 'inline-flex' }}>
                                {this.state.userinfo ? (
                                    <div>
                                        <p>Title: {this.state.userinfo.Title}</p>
                                        <p>EMail: {this.state.userinfo.Email}</p>
                                    </div>
                                ) : (
                                        <div>{"Select the button 'Store User Info' to store the user information!"}</div>
                                    )}
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        );
    }
}
```

Let us see what we have done in the above code.

**Note:** We have used the **local storage** in this sample, there is
also another storage option named **session storage** which is not
covered in this article. More information can be found in the
link [PnP Storage](https://pnp.github.io/pnpjs/core/storage/).

1.  We have used the selective imports concept of PnP to import the sp,
    web and site-users object. We have also
    imported **PnPClientStorage** and **dateAdd** from **@pnp/common**
2.  We have declared a state interface to hold the user information to
    display the data in a div.
3.  We have created 2 methods,
    -   **\_storeCurrentUserInfo** -- Store the current logged in user
        information to the local storage. The method will check whether
        the information is already stored or not, if not then it is
        fetched from SharePoint and stored in the storage.
    -   **\_getStoredUserInfo** -- To display the information from the
        local storage in a div. This method will always pull the
        information from the storage.
4.  We have declared a **componentDidMount** method and deleted all the
    expired values that are stored in the cache. This is the best
    practice recommended by the PnP team to avoid overloading the
    storage or leaving unwanted data. We can also automate this by
    using **CacheExpirationInterval**, the downside of this
    implementation is that there will be settimeout method triggered to
    clear the expired storage.
5.  We have declared two buttons to trigger the above-mentioned methods.

Once the solution is run, you can check your browser console to check
whether the information is stored or not.

## Source Code

The source code along with other samples can be found in the below
GitHub link.

**[SPFx-Demos](https://github.com/sudharsank/spfx-demos)**

 
***Happy Coding...***
