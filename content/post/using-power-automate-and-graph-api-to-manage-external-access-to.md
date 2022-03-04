---
title: "Using Power Automate And Graph API To Manage External Access To Teams"
date: 2021-05-06T08:40:00-04:00
author: "Carl Cookson"
categories: ["Power Automate", "Microsoft Teams", "Microsoft Graph"]
images:

tags: []
type: "regular"
draft: false

---

Matt Collins Jones and I presented [API's -- The most powerful tool,
anyone can
use!](https://d365uguk-22-apr-2021.sessionize.com/session/244458) for
D365 UG and Swiss Power Saturday recently and I thought it would be good
to share the Cloud Flow I created to automate the onboarding of external
users to a Microsoft Team.

This is usually an admin driven activity -- A team owner will have to
type in the email address for each guest they want to add, rather than
something you can push to external users and allow them to request
access.

By using the Graph API via a Custom Connector, Microsoft Forms and Power
Automate, we are able to realise this quickly and save a lot of time and
effort in the manual process.

Also, I have been lucky to have this solution accepted as part of the
samples in the [Microsoft Patterns And
Practices](https://pnp.github.io/) initiative, so the Flow, Custom
Connector and implementation instructions are available in
GitHub [here](https://github.com/pnp/powerautomate-samples/tree/main/samples/teams-invites-via-graph-api).

## Getting Hands-On With Graph 

The main part of this flow is numerous calls to the [Graph
API](https://docs.microsoft.com/en-us/graph/overview). The Graph API is
Microsoft's standard endpoint to expose and interact with data relevant
to your tenant. It includes Microsoft 365 (such as Teams, Exchange,
SharePoint, Workspace Analytics), Enterprise and Mobility and even
Windows 10 activities and devices. It really should be seen as a single
stop shop for anything and everything in your tenant. The only thing it
doesn't expose is D365 data.
There is a [Graph
connector](https://docs.microsoft.com/en-us/connectors/microsoftgraphsecurity/) already
available in Power Automate, but it is very limited to Security
considerations. 

Thankfully, the rest of the Graph API abilities are
available, but you have to go via a custom connector. You could call
these directly via an HTTP request action, but by wrapping the Graph API
in a connector, you are enabling other members of your organisation to
re-use the connector and security you establish.
Microsoft also allows you to "play" with the Graph API as well, via
the [Graph
Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer).
This web interface shows you all the sample calls you can make and also
what permissions you require to call it and allows you to set up a call
without using Power Automate or configuring a connector. It really
should be the starting point for any Graph Customer Connector.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}


If things go wrong, it is usually around the permissions. Within the
Graph Explorer you can consent to these extra permissions on the fly,
but more importantly, tells you what you need to configure in the
permissions of your App registration to allow your connector the same
access.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

Select New client secret give it a name & expiry date and select Save.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

Ensure you copy the Value here, you will only be able to see this for a
short while, if you navigate away it will be gone. Not a big deal, just
recreate the client secret, but you will need it later. Now select API
permissions. This will list what permissions this registration has, and
by inference, the caller using the client secret/application id.
Select the Add a permission button.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

This presents a choice of which API to expose. The first on the list is
Microsoft Graph, the one we want.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

Select Delegated Permissions (Custom connectors doesn't support
Application permissions yet, will run in the context of the person who
runs the flow, so use an admin/system account) then type in the
permission you want, listed here.

-   Directory.ReadWrite.All
-   User.Invite.All
-   User.ReadWrite.All


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

Select Add Permissions to return you to the Configured permissions
screen, then select Grant Admin consent button. This shortcuts and
pre-approves the app.
Leave this tab open and let's go and define our custom connector.
## Defining The Custom Connector 

Jan Bakker has done an excellent job of walking you through
this, [here](https://powerusers.microsoft.com/t5/Power-Automate-Community-Blog/Build-a-custom-connector-for-Microsoft-Graph-API/ba-p/647492).
His article goes into a lot of detail, so I will just take you through
what is needed for this project.
In make.powerapps.com, select the appropriate environment and chose
Custom Connectors under Data. Then select New custom connector. You can
import from various sources, but we want to create from blank, give it a
name then fill out the next page.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

On the next screen, there are four tabs, which we need to step through.
First the General Tab.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

Other stuff is nice to have and you *should *document your work. Ensure
Scheme is HTTPS and Host/Base URL are populated.

-   Host -- graph.microsoft.com
-   Base URL -- /v1.0

Select the Security Tab next, Authentication type is OAuth 2.0. You
should be presented with the below screen.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

Now, this is where we need to use the values you saved (you did save
them?) when you were registering your app
up [here](https://linked365.blog/2021/05/06/using-power-automate-and-graph-api-to-manage-external-access-to-teams/#Granting-Permissions).
Client Id is populated with the Application (client) ID, the Client
secret is populated with the Value from the Client Secret grid. Login
URL will be populated for you. The Resource URL value should be
<https://graph.microsoft.com.Select> Create Connector now, as you need
the Redirect URL, created when you create the connector to put back into
your App registration to complete the security process.

{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

I *think* that this is now standard, but just in case, copy the Redirect
URL and go back to your App Registration in Azure AD. Click on the link
highlighted.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

Select Add a platform then chose Web. Enter the Redirect URL from the
Custom Connector. Now we are ready to define the actions for our
connector.

### Creating the Actions 

For our flow, we need 3 actions, Get the owners of a team, Get a user
and Invite a User. This is where Graph Explorer and Postman help. You
need to establish what you are sending and what you expect back for each
action. For example, lets walk through the Get Owners of a team.
Select New Action and Populate General section. The Operation ID needs
to be unique and is what appears within Power Automate when you select
it.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

I usually use the same for each, but be creative and descriptive. Select
Import from sample then use the url below as the URL and select Get as
the Verb.
URL -- <https://graph.microsoft.com/v1.0/groups/%7BteamId%7D/owners>


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

By placing teamid in curly brackets { } you denote to the custom
connector you want to use a parameter in that URL. You can call
<https://graph.microsoft.com/v1.0/groups/%7BteamId>} (without the
/owners) but that will return the detail from the group. In this I want
get associated data, hence the /owners.
Select Import. You are returned to the definition screen, where we can
see that the request has been populated for us.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

We are ready to test our Get Owners now. Update the connector once more
then head over to the Test tab. You will have to create a connection if
not already done, which prompts you to establish who you are running the
connector under (only for testing). Then supply a team id. These can be
found by using Graph Explorer to find all teams. Hit the Test operation
and if everything is working you will get a 200 response with some JSON
in a body showing you all the information about the owners.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

To just define the others

#### Get User 

Verb: Get, URL: <https://graph.microsoft.com/v1.0/users?$filter=>

#### Invite User 

Verb: Put, URL: <https://graph.microsoft.com/v1.0/invitations>, Body is
below, as you need to define a new invite, with the required parameters.
The data doesn't matter, just the parameters that you need to pass.

``` {.lia-code-sample .language-json}
{
    "invitedUserEmailAddress": "emailaddress",
    "inviteRedirectUrl": "https://myapp.contoso.com",
    "invitedUserDisplayName": "Testy McTest",
    "sendInvitationMessage": true
}
```

Make sure you test all your actions and lets move on to the Form.

## Microsoft Form To Capture Information 

Not going to dwell here, as others are doing a much better job at
describing Forms. Basically, a simple form to define First and Last
name, the email address and a choice field to define which team the user
wants access to.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

The teams list will have to be maintained to those that you want the
public to be able to request access to.
Finally, lets take a look at the flow.

## Power Automate Definition 

This Flow is triggered by a new response being submitted against the
Form defined above. Next, get the response details.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

Next, retrieve all the Teams in your environment. This will return a
JSON object which defines an array of Team definitions. We need to
filter that to the one the user selected so that we can get the team id.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}
To do this, I use the Filter Array action, pass in the output from the
List Teams and ensure we select where team Name is equal to the team
selected (the Which Team? field in my case).


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

Next, is a compose statement. I do that just to simplify the way the
flow works, as the return of filter array is an array, and I just want
the first one.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

``` {.lia-code-sample .language-json}
body('Filter_array')[0]?['id']
```

Next, lets get the Owners of the team selected, using the Id just
retrieved. This is the first time using the Custom Connector, it is
available under the Custom Tab.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

Selecting the connector will show the actions or triggers available.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

The parameters are those that were defined in the Custom connector,
passing in the output from the compose above.

 
{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

Now, the response back from Get Owners is a JSON object, so next, Parse
the JSON so there is a list of JSON objects for the flow to use. All
that is needed in the approval that comes next is the email address(es)
of the return from the owners call. But the approval needs a semi-colon
separated list of emails. To achieve this, firstly use a Select to just
return the email address from the JSON object, then join the output to
that with a semi colon.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

Next, start an approval. This is populated to let the owner know who has
asked for access to the team and which team.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

Check whether the response is positive. If this was for production, I
would probably send an email to the requesting user to let them know
that they were denied access. You could also use the response written in
the rejection.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}
In the Yes path, call the Custom connector again to check if the user is
already a part of your organisation as a guest user. As the parameter is
expecting a query, use the expression below


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

mail eq 'Email Parameter from the Form response'

``` {.lia-code-sample .language-json}
mail eq 'Email Parameter from the Form response'
```
Next, check the length of the returned object from the custom connector.
This basically checks if the user already belongs to your environment.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

``` wp-block-code
length(outputs('GetUser')?['body/value'])
```
If there is a value in the return, use the return to invite the user to
the team.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

The User id is returned by using the expression below

``` {.lia-code-sample .language-json}
body('GetUser')?['value'][0]?['id']
```
On the negative side, firstly invite the user to your organisation by
using the final action of the custom connector.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

And finally, use the response from your custom connector, the invited
user to the team.


{{< image alt="" src="images/blog/using-power-automate-and-graph-api-to-manage-external-access-to/.png" >}}

That's it! There is a lot of configuration here, but you can see how
you can extend your usage of Power Automate to automate a function
usually confined to manual work by the team owner.\
\
This post was originally published on
[LinkeD365.blog](https://linked365.blog/2021/05/06/using-power-automate-and-graph-api-to-manage-external-access-to-teams/)
