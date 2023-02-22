---
title: "Using Power Automate flow API in your SPFx solution"
date: 2022-01-26T02:22:00-04:00
author: "Adam Wójcik"
githubname: Adam-it
categories: []
images:
- images/flowTitle.png
tags: ["Power Automate", "SharePoint Framework (SPFx)"]
type: "regular"
---

## What's it all about

Ever needed a small feature in your webpart to show a list of flows from Power Automate or maybe show a history of one specific flow or maybe disable/enable a flow straight from you SPFx solution?

Well did you ever wondered how to go about this? Lately I did, and since not that long ego I wanted to reproduce this behavior I figured I will write it down in a small article to have something to get back to and maybe it will be also helpful for someone else.

## How to start

First approach that I was thinking to use was the Microsoft Graph REST API as this should always be the way to go if it is supported and possible of course. So I checked out the [API reference](https://docs.microsoft.com/graph/api/overview?view=graph-rest-1.0&preserve-view=true) (also [the beta one](https://docs.microsoft.com/graph/api/overview?view=graph-rest-beta&preserve-view=true)) and it turned out there is no Flow/PowerAutomate endpoint in the API 🥲 (at least I didn't find one 😀.

Ok so my next attempt to investigate how may I retrieve the list of flows was by checking out how it is already done in the tools used in Microsoft 365 world like the CLI for M365. The CLI offers many many helpful commands that allow you to manage your tenant (but not only that so I strongly encourage you to have a [check on this tool as well](https://pnp.github.io/cli-microsoft365/)). I checked out how the \`[m365 flow list](https://github.com/pnp/cli-microsoft365/blob/main/src/m365/flow/commands/flow-list.ts)\` command was developed (this is the power of the Open Source and PnP Community, why try to figure out all things from scratch when you may check how it was done by someone else and potentially totally better then your approach). Ok and it turned out that the CLI for M365 uses this endpoint 

`${this.resource}providers/Microsoft.ProcessSimple${args.options.asAdmin ? '/scopes/admin' : ''}/environments/${encodeURIComponent(args.options.environment)}/flows?api-version=2016-11-01`

 to get the flow lists (or adds \`_/scopes/admin_\` to the URL if you want to get the flow list as admin). Where the resource is \`_[https://api.flow.microsoft.com](https://api.flow.microsoft.com)_\`. Now that's nice 😀. Lets try to use this same approach in SPFx webpart.

Lets create a simple HelloWorld webpart using SPFx Yeoman and lets just modify the link button and attach a click method to it.

```typescript
public render(): React.ReactElement<IHelloWorldProps> {
    return (
        <div className={styles.helloWorld}>
        <div className={styles.container}>
            <div className={styles.row}>
            <div className={styles.column}>
                <span className={styles.title}>Welcome to SharePoint!</span>
                <p className={styles.subTitle}>flow test</p>
                <p className={styles.description}>{escape(this.props.description)}</p>
                {/* here we made a small change */}
                <button className={styles.button} onClick={() => this.getFlowProperties()}>
                <span className={styles.label}>Learn more</span>
                </button>
            </div>
            </div>
        </div>
        </div>
    );
    }
    // here we added the new method
    private async getFlowProperties(): Promise<void> {}
```

Now lets start working on our _getFlowProperties_ method. First thing that we will need to run this endpoint request is the \`{environment}\` which is your environment Id. So of course you may get it for example from the power platform [admin center](https://admin.powerplatform.microsoft.com/environments) after picking the correct environment the id is in the url. But hardcoding the id would make your solution not reusable so it's always better to try to retrieve the environment id. Ok but how we could do that. Well we may retrieve the id from the AadToken (which will we need any way for authentication). So what we may do is

```typescript
const provider: AadTokenProvider = await this.props.context.aadTokenProviderFactory.getTokenProvider();
const token: any = await provider.getToken("https://service.flow.microsoft.com/");
const decodedToken: any = jwt_decode(token);
const envId: string = decodedToken.tid;
```

So we get the token using the `aadTokenProviderFactory` from the flow service. The `aadTokenProviderFactory` is given as part of `WebPartContext` so we may just pass it in the props of the component from the webpart using `this.context`. Then we decode the token using JWT (in order to use this we need to add `jwt-decode` to our `package.json` and add `import jwt\_decode from "jwt-decode"` at the top of our webpart). After the token is decoded we may get the id from the `tid` (tenant Id) property. Ok since we have the envId lets create our URL to get the flow list.

```typescript
const url: string = `https://api.flow.microsoft.com/providers/Microsoft.ProcessSimple/environments/Default-${envId}/flows?api-version=2016-11-01&$filter=properties/isActive+eq+'true'`;
```


What's worth noticing here is that the API also supports filtering so we may for example filter out only the active flows from the list.

Ok now lets do the http request, wait for the response and `console.log` it. We will be using standard httpClient that we may also get from the `WebPartContext`.

```typescript
const response = await this.props.context.httpClient
        .get(url,
        HttpClient.configurations.v1,
        {
            headers: {
            authorization: `Bearer ${token}`,
            accept: "application/json"
            },
        });
const result = await response.json();
console.log(result);
```

One thing worth mentioning is the authorization. Since This is not a standard _SharePoint REST API_ or _MS Graph API_ we need to pass the authorization token which we got from the provider.

Ok so lets run `gulp serve` and check out what we have will be hopefully working.

![thumbnail image 2 of blog post titled Using Power Automate flow API in your SPFx solution ](images/flow3.png)

Well ok so it turned out it doesn't !:facepalm:. That’s cool !:smile:. But what we see in the error message is an AuthError and that the admin needs to consent to use the application with ID… and so on so on. Ok lets try to extend permissions of this app. When we search for it in the AAD App registrations we will find the 'SharePoint Online Client Extensibility Web Application Principal'. Ok so lets try to add appropriate permissions to make it work. Lets add Flow Service: `Flows.Read.All` permissions to the app and consent to it.

![thumbnail image 3 of blog post titled Using Power Automate flow API in your SPFx solution ](images/flow8.png)

Ok this seems about right lets retry our solution and check it out now.

![thumbnail image 4 of blog post titled Using Power Automate flow API in your SPFx solution ](images/flow1.png)

Sweet it turns out it works 😀. That’s nice 🤩. As you may see as a result we got the list of active flows from current environment. That’s a good starting point to develop any functionality using this API in our SPFx solution.

## Starting point

If you want to start from something working (`git pull` > `gulp bundle` > `gulp package-solution` > deploy > `gulp serve` kind of approach 😀 you may check out something I developed some time ego. It is a small SPFx application extension that allows the user to check list of flows and their current status and details that follows the same approach and concept presented in this article. To check it out please visit the [PnP community sp-dev-fx-extensions](https://github.com/pnp/sp-dev-fx-extensions/tree/main/samples/react-application-my-flows-list)


## Conclusion

I'm not sure if I have any 😀. If you ever had a requirement like that to include power automate flow information in you SPFx solution now you have a good starting point.



