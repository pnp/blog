---
title: "How to use Graph Toolkit in Teams App inside Teams Tab"
date: 2022-01-26T02:23:00-04:00
author: "Siddharth Vaghasia"
githubname: siddharth-vaghasia
categories: []
images:
- images/img_61d08358e702f.png
tags: ["Microsoft Graph Toolkit", "Microsoft Teams"]
type: "regular"
summary: "In this article, we will learn about Graph Toolkit and how to integrate Graph toolkit in Teams App."
---

In this article, we will learn about Graph Toolkit and how to integrate Graph toolkit in Teams App.

## What is Graph Toolkit?

Microsoft Graph Toolkit is a library that provides us a collection of reusable components that can be easily configured in our applications(mobile, web, SPA, teams app), etc which takes care of underlying authentication and accessing the data from Graph API and display it to the user. Graph Toolkit provides various authentication providers that also can be used based on our business case. These providers are to be initialized once and then all the components available in Graph Toolkit will automatically use this auth and authorization flow and get data from Graph API.

Once everything is configured properly, it would just take a couple of lines to use the components Available.

Let us see step by step how to use Graph Toolkit in Microsoft Teams App(tab)

Note- if you don’t have Teams Yeoman Generator installed, use the below command to install it

```bash
npm install generator-teams@preview --global
```

## Step 1 –  Create Teams App of type Tab

Open command prompt, create a new folder of your choice in your drive where you wish to create the solution. Run the below command.

```bash
yo teams
```

We would be asked with series of questions, please refer to the below screenshot for options you have to choose.

For this sample, we are going to create a tab without SSO support.

![thumbnail image 1 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d08358e702f.png)

_Note – As we are choosing SSO support as No, the user will have to log in to Teams Tab separately if you wish to make the Graph API calls…We won’t be able to use the Teams Login token to make Graph API calls but have to make separate calls. It is also possible to have SSO support where users don’t have to log in but we would also need to have a backend(server) making use of ID token from Teams App and getting access token to make Graph API call on behalf of the user flow… I would try to write a separate article on it._

![thumbnail image 2 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d086d0b920c.png)

It will take some time and finally you should be able to see below.

## Step – Install Microsoft Graph Toolkit

Let us install required packages via `npm`, run the below command.

```bash
npm install /teams-js /mgt-element /mgt-teams-msal2-provider /mgt-components /mgt
```

_Note – To use Toolkit, we have to also install Teams SDK and required providers and components._

In this sample we are going to use Teams Provider which uses MSAL provider internally, you can read about Teams provider at the below [link](https://docs.microsoft.com/graph/toolkit/providers/teams?tabs=ts)

_Ideally, we should use Teams MSAL2Provider for authentication purposes as it is more secure, but I had some difficulties making it run while writing this article so went ahead and used Teams Provider….After raising the issue in the repo, the Toolkit team has provided me instructions on a mistake I was making and it fixed it…but as all the screenshots, etc was referring to TeamsProvider I have kept the same as in this article…but later I tried with MSAL2Provider and it worked fine…so I have given a side note at end of the article to specify changes to make it work with MSAL2Provider._

So I have separately installed  `@microsoft/mgt` package, make sure you are also doing so.

![thumbnail image 3 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d088492862d.png)

Open your solution in Visual Studio code using `code .`

## Step 3 – Creating the auth popup page

As mentioned before, the user needs to sign in to make use of Graph Toolkit and indirectly get data from Graph API. So in this step, we will create a page in our app that will open in a popup to follow the auth flow. On this particular page, we have to use import the provider class and call handleAuth method, we can make it as fancy as we want based on our need but ideally, if this method would be called it will be automatically asking the user to sign in when the log in Graph Toolkit component is used.

Create a new page in a public folder as  `src\public\auth.html`. Copy below code:

```html
<!DOCTYPE html>
<html>
    <head>
    <script src="https://unpkg.com/@microsoft/teams-js/dist/MicrosoftTeams.min.js" crossorigin="anonymous"></script>
    <script src="https://unpkg.com/@microsoft/mgt@2/dist/bundle/mgt-loader.js"></script>
    </head>
    <body>
    <script>
        mgt.TeamsProvider.handleAuth();
    </script>
    </body>
</html>
```

## Step 4- Create a new app registration in Azure Active Directory

Go to portal.azure.com

Choose Azure Active Directory

Select **App Registration** from left Blade, Select New Registration

![thumbnail image 4 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d0945460a06.png)

Provide the name of your App ‘TeamsAppGraphToolkit1 ‘. Select **Register** at the bottom of the page

![thumbnail image 5 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d094d605263.png)

Once created, select **Authentication** on the left blade, choose Add platform and select Single-page application

![thumbnail image 6 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d09529034e3.png)

Enter ‘Redirect URIs’  as `http://localhost` for a sample, ideally, once you publish this app, it should be the domain of your team’s app. We will also have to change this to ngrok URL while doing testing.

Next thing here we have to enable Implicit this App registration supports. As Teams Provider user MSAL(not MSAL2) which only supports Implicit Flow for OAuth, we have enabled both **Access tokens and ID tokens.** 

![thumbnail image 7 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d148a4dc83a.png)

Save it and note down the client Id of this App from the Overview tab, we would require it later.

## Step – Install Microsoft Graph Toolkit React components.

Run the below command to install mgt react components to be used.

```bash
npm i /mgt-react
```

## Step – Modify code to use Graph Toolkit components

Go to `src\client\graphToolkitDemoTab\GraphToolkitDemoTab.tsx`

Import below libraries

```typescript
import {Providers, TeamsProvider} from '@microsoft/mgt'
import {  Login } from '@microsoft/mgt-react';
```

Modify the Tab component and on top, initialize the Teams Provider

```typescript
export const GraphToolkitDemoTab = () => {
    TeamsProvider.microsoftTeamsLib = microsoftTeams;
Providers.globalProvider = new TeamsProvider({
    clientId: '<span style="color: #ff6600;">4t2eba12-24c4-4e23-b1d8-c22c4051545b</span>',
    scopes: ['User.Read','Mail.ReadBasic'],
    authPopupUrl:"/auth.html"
});
//.....
```

Modify the client ID you noted earlier from Azure AD App Registration.

Next, let us add the Login component to the render method to display the Sign In button.

```typescript
return (
        <Provider theme={theme}>
            <Flex fill={true} column styles={{
                padding: ".8rem 0 .8rem .5rem"
            }}>
                <Flex.Item>
                    <Header content="This is your tab" />
                </Flex.Item>
                <Flex.Item>
                    <div>
                        <div>
                            <Text content={entityId} />
                        </div>
                        <div>
                            <Button onClick={() => alert("It worked!")}>A sample button</Button>
                            <span style="color: #ff6600;">  <Login /></span>
                        </div>
                    </div>
                </Flex.Item>
                <Flex.Item styles={{
                    padding: ".8rem 0 .8rem .5rem"
                }}>
                    <Text size="smaller" content="(C) Copyright Siddharth Vaghasia" />
                </Flex.Item>
            </Flex>
        </Provider>
    );
```

## Step  – Test the app

Once you have all the above setup, let us first see if everything works fine, and then we will try different Graph Toolkit components.

Go to command prompt and run the below command, this command comes with yo teams which run ngrok in the background and also create teams app package for us.

```bash
gulp ngrok-serve
```

Once it has run successfully, it should show some like below

![thumbnail image 8 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d14cc00c1fe.png)

Next thing, we will have to add the ngrok URL in Azure AD App registration as a redirect URL.

![thumbnail image 9 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d14ce80c11c-1024x546.png)

## Step – Test the App in Teams

Go to teams and select **Apps** on the left panel and then select upload a custom app(this button will only be visible if sideloading is enabled by Teams Administrator)

![thumbnail image 10 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d14d4b1bb1a.png)

Select **Upload a custom app**, then **Upload for me and my teams**,  
Select the zip package at `D:\SP\samples\teamsapps\teams-graphtoolkit\package\teamsgraphtoolkit.zip`

Note -This zip file will be updated everything you run gulp ngrok-serve, so you have to make sure you upload the latest zip package whenever you have a new ngrok url and also update the same in App Registration in Azure portal.

Select **Add**

![thumbnail image 11 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d14e07de75e-768x592.png)

Once installed, we should see below output

![thumbnail image 12 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d14e38c591f.png)

As you see the **Sign In** button has come from Login Component which we added. Click on it, it should open below auth popup and ask us to log in

![thumbnail image 13 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d14e831956d.png)

Once logged in, we should see below that our integration with Graph Toolkit worked 

![thumbnail image 14 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d14f089f61d.png)

Now let us see how we can use another component with some minor changes.

## Agenda Component

The agenda component will display the currently logged-in user’s meeting. You can read about the Agenda component in the [Microsoft documentation](https://docs.microsoft.com/graph/toolkit/components/agenda) 

First, modify import to include the Agenda component

```typescript
import {  Login ,Agenda} from '@microsoft/mgt-react';
```

Then add Scope to add permission for the user’s constant.

```typescript
Providers.globalProvider = new TeamsProvider({
    clientId: '4t2eba12-24c4-4e23-b1d8-c22c4051545b',
    scopes: ['User.Read','Mail.ReadBasic','Calendars.Read'],
    authPopupUrl:"/auth.html"
});
```

Add Agenda component to render method

```typescript
return (
        <Provider theme={theme}>
            <Flex fill={true} column styles={{
                padding: ".8rem 0 .8rem .5rem"
            }}>
                <Flex.Item>
                    <Header content="This is your tab" />
                </Flex.Item>
                <Flex.Item>
                    <div>
                        <div>
                            <Text content={entityId} />
                        </div>
                        <div>
                            <Button onClick={() => alert("It worked!")}>A sample button</Button>
                            <Login />
                        </div>
                        <div>
                            My Meetings 
                            <div>
                            <Agenda ></Agenda>                            
                            </div>
                        </div>
                    </div>
                </Flex.Item>
                <Flex.Item styles={{
                    padding: ".8rem 0 .8rem .5rem"
                }}>
                    <Text size="smaller" content="(C) Copyright Siddharth Vaghasia" />
                </Flex.Item>
            </Flex>
        </Provider>
```

You need to rerun the solution again as we have added new scope permission. Run the `gulp ngrok-serve` command again, add the URL in Azure AD app registration and add the new package to Teams,

Select **Sign In**, you must provide consent again as we have added new Scope. Once you Sign In, we should see the current user’s meeting as below

![thumbnail image 15 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d15a198025a-768x743.png)

## Conclusion

In this article, we have seen step by step guide on how to integrate Graph Toolkit in your Teams app and use the available component by just configuration. You can read more about all the components available in the [MGT documentation](https://docs.microsoft.com/graph/toolkit/components/login)

As of today, the below components are available which can be used easily and there are many configurations also available for each component to customize.

![thumbnail image 16 of blog post titled How to use Graph Toolkit in Teams App inside Teams Tab ](images/img_61d15ab513d0c.png)

## Side Note

If you want to use `MSAL2Provider`, you have just made the below changes, everything else should work as it is as we are just changing the provider we are using.

The initialize provider code would look like below `GraphToolkitDemoTab`

```typescript
    TeamsProvider.microsoftTeamsLib = microsoftTeams;
    Providers.globalProvider = new TeamsMsal2Provider({
        clientId: '123213-123-4233-232-c72232312345b',
            scopes: ['User.Read','Mail.ReadBasic','Calendars.Read'],
            authPopupUrl:"/auth.html"
        });
```

Below would be library imports

```typescript
import {Providers, TeamsProvider} from '@microsoft/mgt'
```

In your `auth.html`, there would be below code

```html
<!DOCTYPE html>
<html>
    <head>
    <script src="https://unpkg.com/@microsoft/teams-js/dist/MicrosoftTeams.min.js" crossorigin="anonymous"></script>
    <script src="https://unpkg.com/@microsoft/mgt@2/dist/bundle/mgt-loader.js"></script>
    </head>
    <body>
    <script>
        mgt.TeamsMsal2Provider.handleAuth();
    </script>
    </body>
</html>
```

Hope this helps…Happy Coding..!!!
