---
title: "How to invite external users to a SharePoint site or Microsoft Team using Power Automate & Graph API"
date: 2021-05-26T08:25:00-04:00
author: "Mohamed Ashiq Faleel"
githubname: ashiqf
categories: ["Community post"]
images:
- images/MSForm-ExternalUserdetails.png
tags: []
type: "regular"
---

SharePoint and Microsoft Teams services in Microsoft 365 makes it easier
to share content and collaborate with external users who is outside your
organization. A guest or external user is someone who do not have a
school or work account with your organization, they can be your partner,
vendor, customer etc. In this article let us see how to build a
self-registration experience for external users with the help of
Microsoft Forms & Power Automate to onboard them to a

-   SharePoint online site
-   Microsoft Team

## Microsoft Form to collect details from External User

To start building this experience, create a Microsoft form with the
setting **Anyone can respond** and with fields (Name, Email address etc)
to collect information from the external user to send invitation.

## ![MSForm-ExternalUserdetails.png](images/MSForm-ExternalUserdetails.png) 

## Azure Active Directory Application registration

The next step after creating the form is to register an [application in
Azure
AD](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)
with Microsoft graph API permission to send invitation to external user.
After the app is registered obtain the client id, client secret & tenant
id to be used in the Power Automate flow further down this article to
generate the JSON webtoken to access Microsoft Graph API for sending
invitation. Find below screenshot with the permission User.Invite.All
added to the app. Keep in mind the permission requires Admin consent.

![AdApp-GraphPermissiontoInviteGuestUser.png](images/AdApp-GraphPermissiontoInviteGuestUser.png)

There is also delegated permission available for User.Invite.All.

## Onboard External users to a SharePoint online site 

Once the Microsoft form is ready, we can start building the Power
Automate flow which can send the email invitation to the external user
and for granting access to the SharePoint site. The [external
sharing](https://docs.microsoft.com/sharepoint/external-sharing-overview)
features of SharePoint Online enables users in your organization share
content with people outside the organization. There is no limit to the
number of guests you can invite to SharePoint sites as per this
[SharePoint online
limits](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits#users)
documentation. Find below steps to create the Power Automate flow with a
custom approval on a Microsoft Team

## Power Automate Flow

Create an Automated flow with the trigger **When a new response is
submitted** with the above form name selected on the dropdown and then
add the action **Get response details** with the **Response Id**
selected from the dynamic content for the trigger to get the form
details submitted in the Microsoft form by the external user. Find
screenshot below

![MSFormTrigger-ExternalUser.png](images/MSFormTrigger-ExternalUser.png)

## Adaptive card for Teams Approval

For the Approval in Microsoft Teams, I have used a custom card created
from the [Adaptive card designer](https://adaptivecards.io/designer/)
with elements **ColumnSet, TextBlock** to display information submitted
in the form & **action button** Approve and Reject to take further
action by a Microsoft Teams user to proceed with Invitation for the
Guest account creation. Find screenshot below from the adaptive card
designer

![AdaptiveCard-DesignforApproval.png](images/AdaptiveCard-DesignforApproval.png)

1.  After the card is designed, copy the card payload from the designer
    and go to the flow and then add the action **Post adaptive card and
    wait for a response** and make appropriate selection on the
    available fields as shown below
    -   **Post as**: Flow bot
    -   **Post in**: Channel
    -   **Message**: Payload copied from designer. Replace the fields
        for usrName & userEmail selected from the dynamic content from
        the outputs of the action **Get response details**. The created
        on textBlock element has the flow expression
        formatDateTime(utcNow(),'g') to display the current datetime
        information on the card.

![AdaptiveCard-PAFlow-POSTAdatptivecardandwaitforresponse1.png](images/AdaptiveCard-PAFlow-POSTAdatptivecardandwaitforresponse1.png)


![AdaptiveCard-PAFlow-POSTAdatptivecardandwaitforresponse2.png](images/AdaptiveCard-PAFlow-POSTAdatptivecardandwaitforresponse2.png)

-   **Update Message**: Custom message which appear after an action
    taken in Microsoft Teams
-   **Team**: Select the Team where you would like to post the card
-   **Channel**: Select the channel from the Microsoft Team where you
    would like to have the approval adaptive card posted

Card payload:

``` {.lia-code-sample .language-applescript}
{
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "TextBlock",
            "weight": "Bolder",
            "text": "Approval for adding the External User",
            "wrap": true
        },
        {
            "type": "TextBlock",
            "spacing": "None",
            "text": "Created Add flow expression to get current date",
            "isSubtle": true,
            "wrap": true
        },
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Name:",
                            "wrap": true,
                            "size": "Medium",
                            "weight": "Bolder"
                        },
                        {
                            "type": "TextBlock",
                            "text": "Email:",
                            "wrap": true,
                            "weight": "Bolder",
                            "size": "Medium"
                        }
                    ],
                    "width": "stretch"
                },
                {
                    "type": "Column",
                    "width": "stretch",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "usrName-Replace it from Microsoft Form",
                            "wrap": true
                        },
                        {
                            "type": "TextBlock",
                            "text": "userEmail-Replace it from Microsoft Form ",
                            "wrap": true
                        }
                    ]
                }
            ]
        }
    ],
    "actions": [
        {
            "type": "Action.Submit",
            "title": "Approve",
            "id": "btnApprove"
        },
        {
            "type": "Action.Submit",
            "title": "Reject",
            "id": "btnReject"
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.0"
}
```
 

1.  The above adaptive card is used to get approval from the
    Organization teams user based on the information submitted by the
    external user in the Microsoft form to proceed with the next steps
    for sending the guest account invite. Now we will have to identify
    if the user has clicked the button Approve or Reject. This
    information can be easily obtained from the Outputs of the action.

**Note**: Adaptive card can also be sent using a Microsoft Graph API
with the card payload in Attachments field

<https://docs.microsoft.com/graph/api/channel-post-messages?view=graph-rest-beta&tabs=http>

### Adaptive card for Teams - Dynamic content Missing

As of the time I am writing this article there is an issue in getting
the output as dynamic content for the **Post adaptive card and wait for
a response** action if there is dynamic content added on the JSON
Payload (Name, Email from Forms). The fix is to run the flow till the
post adaptive card action and take an action on Microsoft Teams by
clicking either Approve or Reject and then go to the Flow run from the
history as shown below

![AdaptiveCard-PAFlow-POSTAdatptivecardandwaitforresponseRunHistory.png](images/AdaptiveCard-PAFlow-POSTAdatptivecardandwaitforresponseRunHistory.png)

From the above screenshot, we can see if the user has clicked the
Approve or Reject button from the field **submitActionId**. To get this
value in Flow, use the expression

``` {.lia-code-sample .language-applescript}
outputs('Post_adaptive_card_and_wait_for_a_response').body.submitActionId
```

or

``` {.lia-code-sample .language-applescript}
@outputs('Post_adaptive_card_and_wait_for_a_response')?['body/submitActionId']
```

Spaces in the name of the action is replaced with underscore.

To get the userPrincipalName, the expression is

``` {.lia-code-sample .language-applescript}
outputs('Post_adaptive_card_and_wait_for_a_response').body.responder.userPrincipalName
```

or

``` {.lia-code-sample .language-applescript}
@outputs('Post_adaptive_card_and_wait_for_a_response')?['body/responder/userPrincipalName']
```

To get the submitActionId, enter the expression
outputs('Post_adaptive_card_and_wait_for_a\_response').body.submitActionId
in the compose action, then add a condition control to decide action
based on users approval

![AdaptiveCard-cardactionoutput.png](images/AdaptiveCard-cardactionoutput.png)

I have observed this issue occurs in other team's adaptive card actions
as well, the above fix should work. Now we can implement the logic to
send the Guest Invitation using Microsoft Graph API. To send the
invite, we will use the Azure AD application registered above.

## Generate JSON Web token to Access Graph API

Be ready with the ClientId, Client Secret and Tenant Id collected from
the AD app registration you have done initially. The only authentication
flow to generate a access token for application permissions is [Client
credentials](https://docs.microsoft.com/azure/active-directory/develop/msal-authentication-flows#client-credentials).

To generate a token

1.  Store the Client Secret on a String variable or a compose action
2.  Make a HTTP request using the HTTP connector with the following
    details. Make sure to replace the string for tenantId,
    azureAdAppclientId and azureAdAppclientSecret

Add a HTTP connector action to the flow for making a POST request per
the following information

**HTTP Method**: POST

**URI**:
<https://login.microsoftonline.com/yourtenantId/oauth2/v2.0/token>

**Headers**:

[*Key*]: Content-Type

[*Value*]: application/x-www-form-urlencoded

**Body**:
 

``` {.lia-code-sample .language-applescript}
tenant=yourtenantId&client_id=azureAdAppclientId&client_secret=@{decodeUriComponent(variables('azureAdAppclientSecret'))}&grant_type=client_credentials&scope=https://graph.microsoft.com/.default
```
 

For the client secret make sure to URL encode using the expression
encodeUriComponent(variables('clientSecret')) else the request will fail
due to the presence of special characters.

![MSGraph-GenerateJSONWebToken.png](images/MSGraph-GenerateJSONWebToken.png)

In the above screen, I have added a compose action to store the
SharePoint site address to be used for granting the external user access
to. To extract the token from the above request, add the parse JSON
action with Content from the **HTTP request body** and the following
schema
 

``` {.lia-code-sample .language-applescript}
{
    "type": "object",
    "properties": {
        "token_type": {
            "type": "string"
        },
        "scope": {
            "type": "string"
        },
        "expires_in": {
            "type": "integer"
        },
        "ext_expires_in": {
            "type": "integer"
        },
        "access_token": {
            "type": "string"
        },
        "refresh_token": {
            "type": "string"
        }
    }
}
```
 

![MSGraph-ParseJSONWebToken.png](images/MSGraph-ParseJSONWebToken.png)

Include the access token when calling the Microsoft Graph API on the
Headers section or raw as shown in the next section.

## Send Invitation using Microsoft Graph API

Before sending the invitation, validate if the user already exists in
your organization AD tenant by using the email address of the external
user with the help of the action **Search for users** as shown below

![SearchforexternalUser.png](images/SearchforexternalUser.png)
If there is null response for the action **Search for users**, then the
user does not exist. This can be calculated using the expression length
and by passing the value as a parameter, if it is equals zero then the
external user does not exist. If the user already exists, we can
directly proceed to granting the external user access to SharePoint.

Graph API to check if a guest user already exists:

[https://graph.microsoft.com/v1.0/users?\$filter=UserType eq
'Guest'&\$filter=mail eq
exteruseremailadd\...](https://graph.microsoft.com/v1.0/users?$filter=UserType%20eq%20'Guest'&$filter=mail%20eq%20exteruseremailaddress@domain.com') 

or

[https://graph.microsoft.com/v1.0/users?\$filter=startswith(mail,'[exteruseremailaddress@domain.com]'u)](https://graph.microsoft.com/v1.0/users?$filter=startswith(mail,'fejom29487@troikos.com'))

Find below the Graph API endpoint http request details to [invite the
external
user](https://docs.microsoft.com/graph/api/invitation-post?view=graph-rest-1.0&tabs=http)

**Method**: POST

**URL**: <https://graph.microsoft.com/v1.0/invitations>

**Request Body**:
 

``` {.lia-code-sample .language-applescript}
{
  "invitedUserDisplayName": "External User Name",
  "invitedUserEmailAddress": "External User Email Address",
  "sendInvitationMessage": true,
  "inviteRedirectUrl": "SharePoint site URL or any URL",
  "invitedUserMessageInfo": {
    "messageLanguage": "en-US",
    "customizedMessageBody": "Welcome to the M365PAL SharePoint site! Select the link below and sign in."
  }
}
```
 

![MSGraph-SendInvitationforExternaluser.png](images/MSGraph-SendInvitationforExternaluser.png)

In HTTP request body, use the dynamic content of the form to populate
the fields invitedUserDisplayName & Emailaddress. The invite redirectUri
is the output of the compose action which has the SharePoint site url. I
have added a delay of one minute before granting access to SharePoint
site for the external user, this step is to make sure there is an entry
in Azure AD for the external user/guest account.

Custom connector can be used for calling the Graph API for sending
invitations instead of using HTTP connector, you can refer to the post
[Call Microsoft Graph API in Power Apps and Power Automate using a
Custom
connector](https://ashiqf.com/2021/03/16/call-microsoft-graph-api-in-power-apps-and-power-automate-using-a-custom-connector/)
for detailed instructions.

## Grant Access to SharePoint site for the external user

As soon as the guest account invite is sent from the above Microsoft
graph API request HTTP action, it is time to grant access to the
SharePoint site for the external user. There is a SharePoint REST API
endpoint to add a user to a SharePoint group (Owners, Member, Visitors),
find below the request details

**Request URL**: [https://tenantname.sharepoint.com/sites/siteName/
\_api/web/sitegroups/GetById(groupId)/users](https://tenantname.sharepoint.com/sites/siteName/%20_api/web/sitegroups/GetById(groupId)/users)

For the groupId to the corresponding SharePoint group, refer to the
following table

  ---------------------- -------------
  **SharePoint Group**   **GroupId**
  Owners                 3
  Members                5
  Visitors               4
  ---------------------- -------------
**Headers**:

[*Key*]: accept [*value*]:
application/json;odata.metadata=none

[*Key*]: content-type [*value*]:
application/json

**Body**:

```bash
{'LoginName':'i:0#.f|membership|userPrinipalNameorEmailaddressofExternalUser'}
```

For the external user, the email address used to send the invite works.

Go back to the flow and add the action **Send an HTTP request to
SharePoint** to call the above REST api. Find below the screenshot of
the action

![AddUsertoSharePointGroup.png](images/AddUsertoSharePointGroup.png)

The above action uses delegated permission, the user of the connection
should have access to the SharePoint site. As of now, there is no Graph
API for adding the user to a SharePoint group but you can register an
app in Active directory and add permission for SharePoint to call the
above REST API. Refer to the documentation [Granting access via Azure AD
App-Only](https://docs.microsoft.com/sharepoint/dev/solution-guidance/security-apponly-azuread)
for calling the REST API using the registered AD app.

## Testing the flow

The whole flow can now be tested by submitting the form which sends the
adaptive card on Teams first as shown below

![AdaptiveCard-InTeamsChannel.png](images/AdaptiveCard-InTeamsChannel.png)

After the card is approved, the invite is sent to the external user.
After the external user accepts the invite, the user should be
automatically redirected to the SharePoint site with the appropriate
access. The access to the SharePoint site for the external user can be
validated by the checking the membership of the SharePoint group in the
site even before the user accepts the invitation. The site members can
also be validated by accessing the URL for All users list:

<https://tenantName.sharepoint.com/sites/siteName/_layouts/15/people.aspx?MembershipGroupId=0>

This approach of granting access to SharePoint site for external user
can be applied to internal users by [turning off the access
requests](https://support.microsoft.com/office/set-up-and-manage-access-requests-94b26e0b-2822-49d4-929a-8455698654b3).

## Limit External Sharing by domain

The external sharing on SharePoint can be restricted based on domain of
the external user. To enable the setting login into the SharePoint admin
center \> Policies \> Sharing \> Enable the checkbox Limit external
sharing by domain \> Add domain

![ExternalSharing-RestrictDomain.png](images/ExternalSharing-RestrictDomain.png)

### Onboard External users to a Microsoft Team

To onboard the external user to a Microsoft Team, the only change to the
above flow is, instead of adding the user to the SharePoint group the
user must be added as a Member to the Microsoft 365 group connected to
the Microsoft Teams. The graph API to [add a
member](https://docs.microsoft.com/graph/api/team-post-members?view=graph-rest-1.0&tabs=http)
to a Microsoft Team is

**Request Type**: POST

**Request URL**:
[https://graph.microsoft.com/v1.0/teams/{team-id}/members](https://graph.microsoft.com/v1.0/teams/%7bteam-id%7d/members)

The team-id is the Microsoft 365 group object Id, as there is always a
Microsoft 365 group connected to a Microsoft Team.

**Body**:

```JSON
{
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"],
    "user@odata.bind": "https://graph.microsoft.com/v1.0/users(userObjectIdofGuest')"
}
```

The expression to get the user object Id of the external user as per the
below screenshot is

``` {.lia-code-sample .language-applescript}
outputs('HTTP-SendGuestInvitation').body.invitedUser.Id
```
 

The expression can be used in a compose action to get the Object Id of
the external user which can be used in the Graph API request to add the
member to a Team. **HTTP-SendGuestInvitation** is the name of the HTTP
Action.

![externalUserObjectId.png](images/externalUserObjectId.png)

## Permission for the Azure AD App to add a member to a Microsoft Team

The application permission Group.ReadWrite.All has to be added on the
Azure AD app, if you are going to be using the same JSON webtoken
generated above. There is delegated permission as well for adding
members.

<https://graph.microsoft.com/Group.ReadWrite.All>

I recommend you read the following documentation from Microsoft for
External sharing

<https://docs.microsoft.com/microsoftteams/manage-external-access>

<https://docs.microsoft.com/microsoftteams/guest-access>

<https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations>

## Summary

With this, the Power Automate flow should send the invitation as shown
below to the external user.

![externalUserInvitationEmail.png](images/externalUserInvitationEmail.png)

If it is for a Microsoft Team, the external user should be licensed for
teams service to open it on their teams client. The same flow can be
also configured for Microsoft 365 group.

This post was originally published in
[ashiqf.com](https://ashiqf.com/2021/05/26/how-to-invite-external-users-to-a-sharepoint-site-or-microsoft-team-using-power-automate-and-graph-api/)
