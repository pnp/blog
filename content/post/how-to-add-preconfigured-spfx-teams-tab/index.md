---
title: "How to add pre-configured SPFx Teams Tab to a channel"
date: 2022-06-16T08:40:00-04:00
author: "Marcin Wojciechowski"
githubname: mgwojciech
# don't change
categories: ["Community post"]
# link to the thumbnail image for the post
images:
- images/tianyi-ma-WiONHd_zYI4-unsplash.jpg
tags: ["SharePoint Framework (SPFx)", "Microsoft Teams"]
# don't change
type: "regular"
draft: false
---

## Use case

Let's consider following scenario. We developed a SPFx web part and added TeamsTab as a supported host. From now one, users can add our beautiful web part as a Teams Tab to any channel. That's amazing! However we would like to be able to automate adding this web part with some initial configuration without any user interaction.

In this article I will not provide any code samples as I want to keep this tech agnostic. You can perform all of those steps from Power Platform, Powershell, .NET app or some other web part with javascript. To my best knowledge You can use both delegated and app only permissions to execute each provided requests.

## Step one - finding the IDs

To proceed with our task we will need three ids. First two are team and chanel id which identifies the place we want to add our web part. Third one is teams app id associated with our web part.

### Team and channel id

To find a team id You can use following endpoint:

``` JSON
GET: https://graph.microsoft.com/beta/teams
```

Sample response is:

``` JSON
{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams",
    "@odata.count": 16,
    "value": [
        {
            "id": "<team-id>",
            "createdDateTime": null,
            "displayName": "Test Team",
            "description": "Test Team",
            "internalId": null,
            "classification": null,
            "specialization": null,
            "visibility": "private",
            "webUrl": null,
            "isArchived": null,
            "isMembershipLimitedToOwners": null,
            "memberSettings": null,
            "guestSettings": null,
            "messagingSettings": null,
            "funSettings": null,
            "discoverySettings": null,
            "summary": null
        },
        ...
    ]
}

```

If You want to avoid using beta endpoints You can also use:

``` JSON
GET: https://graph.microsoft.com/v1.0/groups?$filter=resourceProvisioningOptions/Any(x:x eq 'Team')&$select=id,displayName
```

Which will return:

``` JSON
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#groups(id,displayName)",
    "value": [
        {
            "id": "<team-id>",
            "displayName": "Test Team"
        },
        ...
    ]
}
```

Once You select a team it's time to find channel id. You can find it using:

``` JSON
GET: https://graph.microsoft.com/v1.0/teams/<team-id>/channels?$select=id,displayName
```

Sample response:

``` JSON
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#teams('<team-id>')/channels(id,displayName)",
    "@odata.count": 2,
    "value": [
        {
            "id": "<channel-1-id>",
            "displayName": "General"
        },
        {
            "id": "<channel-2-id>",
            "displayName": "Project 1"
        }
    ]
}
```

### Teams App id

Now, as we have identified our team and channel, we need to identify our Teams App associated with SPFx web part. By default the externalId property of the app will be the same as web part id we developed. Note - this is "id" property in web part manifest. To find the actual id of the Teams App we can use this query:

``` JSON
GET: https://graph.microsoft.com/v1.0/appCatalogs/teamsApps?$filter=externalId eq '<web-part-id>'
```

Which should return following response:

``` JSON
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#appCatalogs/teamsApps",
    "value": [
        {
            "id": "<teams-app-id>",
            "externalId": "<web-part-id>",
            "displayName": "Test SPFx Web Part",
            "distributionMethod": "organization"
        }
    ]
}
```

Now we do have our app id and we can continue.

## Step two - Preparation of SharePoint site

To make sure we can pre-configure our web part we need to perform two actions on site collection backing our selected team.

- Activate TeamsHostedAppConfig feature
- Add HostedAppConfig for our web part

 With those, we will be able to construct a proper contentUrl for our Teams App configuration.

### Find site associated with the team

To find the url of backing site we call:

``` JSON
GET: https://graph.microsoft.com/v1.0/groups/<team-id>/sites/root
```

 Which returns:

 ``` JSON
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#sites/$entity",
    "createdDateTime": "2019-10-16T09:42:03.22Z",
    "description": "",
    "id": "<tenant-name>.sharepoint.com,<site-id>,<web-id>",
    "lastModifiedDateTime": "2022-06-13T17:08:00Z",
    "name": "TestTeam",
    "web-url": "https://<tenant-name>.sharepoint.com/sites/TestTeam",
    "displayName": "Test Team",
    "root": {},
    "siteCollection": {
        "hostname": "<tenant-name>.sharepoint.com"
    }
}
 ```

### Setup Hosted App Configs list

 To ensure HostedAppConfigs list exists let's activate a feature using:

``` JSON
 POST: <web-url>/web/features/add('96e4ae8d-7cbb-4286-be06-8a688f61440a')
```

 Now, to find the HostedAppConfigs list id we call:

``` JSON
 GET: <web-url>/_api/web/getList('<web-server-relative-url>/lists/hostedappconfigs')?$select=id
```

Expected response is:

``` JSON
{
    "odata.metadata":"https://<tenant-name>.sharepoint.com/sites/TestTeam/_api/$metadata#SP.ApiData.Lists/@Element&$select=id",
    "odata.type":"SP.List",
    "odata.id":"https://<tenant-name>.sharepoint.com/sites/TestTeam/_api/Web/Lists(guid'<list-id>')",
    "odata.etag":"\"0\"",
    "odata.editLink":"Web/Lists(guid'<list-id>')",
    "Id":"<list-id>"
}
```

### Create Hosted App Config item for Your tab

 Finally we want to add hosted app config representing our pre-configuration. First, we need to generate our new web part instance id, which must be a valid guid. We will mark it as \<instance-id>. Next we need to prepare our configuration based on properties defined by our web part definition. A sample would look following:

 ``` JSON
    {
        "description": "Test description",
        "webPartProp1": "Test 1",
        "WebPartProp2": "Test 2"
    }
 ```

Now we can call an endpoint to add our pre-configuration:

``` JSON
POST: <web-url>/_api/web/hostedapps/add
BODY: {
    webPartDataAsJson: '{"id":"<web-part-id>","title":"Amazing web part","instanceId":"<instance-id>","properties":{"description":"Test description","webPartProp1":"Test 1","WebPartProp2":"Test 2"}}'
}
```

 Note webPartDataAsJson is already serialized!

 This call should return:

``` JSON
{
    "value": <list-item-id>
}
 ```

 Now we have everything we need from SharePoint side.
 We have site url, HostedAppConfigs list id, list item id of associated Teams Tab configuration and instance id of our web part in Teams Tab configuration item.

### Build tab content url

 With those we can build contentUrl of our Teams Tab which will look like this:

``` JSON
 https://<tenant-name>.sharepoint.com/_layouts/15/TeamsLogon.aspx?SPFX=true&dest=<web-server-relative-url>/_layouts/15/teamshostedapp.aspx%3Fteams%26webPartInstanceId=<instance-id>%26list=<list-id>%26id=<list-item-id>
```

 I will refer to this url as `\<content-url>`
 This url will be interpreted by Teams in following way:

- Ensure login with TeamsLogon.aspx page
- Once User is authenticated, redirect to teamshostedapp.aspx page in backing site collection
- Get CanvasContent1 property from list `\<list-id>` from item `\<list-item-id>`
- In CanvasContent1 find a tag for web part with `\<instance-id>`
- Render the web part instance (with configuration stored in CanvasContent1)

## Deploy to Teams Channel

With everything ready on SharePoint we can move forward with adding the app as a Teams Tab.

### Ensure app is available

First let's ensure the app is available in selected Team. You can add it using:

``` JSON
POST: https://graph.microsoft.com/v1.0/teams/<team-id>/installedApps
BODY: {
    "teamsApp@odata.bind", "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps/<teams-app-id>"
}
```

With app available in our team we can finally execute the final step, adding Teams Tab.

### Final call

``` JSON
POST: https://graph.microsoft.com/v1.0/teams/<team-id>/channels/<channel-id>/tabs
BODY: {
    "teamsApp@odata.bind", "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps/<teams-app-id>",
    "displayName": "Amazing web part",
    "configuration": {
        "contentUrl": "<content-url>",
        "websiteUrl": "<web-url>",
        "entityId": "<instance-id>",
        "removeUrl": "<content-url>%26removeTab"
    }
}
```

With this step the pre-configured web part will be added to provided channel as a Teams Tab.

## Closing hacks

If You want to provide Your users with configurable personal app You can execute steps from Step two - Preparation of SharePoint site and use the  `\<content-url>` as a static tab content url in your teams app manifest. In my experience this will not work for a root site collection but will work for every other. To update the configuration You can call:

``` JSON
POST: <web-url>/_api/web/hostedapps/getbyid(<list-item-id>)/updatewebpartdata
BODY: {
    webPartDataAsJson: '{"id":"<web-part-id>","title":"Amazing web part","instanceId":"<instance-id>","properties":{"description":"Test description","webPartProp1":"Test 1","WebPartProp2":"Test 2"}}'
}
```

Hope You will find this useful
Thank You and have fun :)
