---
title: "Looking at things in profile"
date: 2021-09-29T08:40:00-04:00
author: "Simon Hudson"
githubname: SimonJHudson
categories: ["Community post"]
images:
- images/Account.png
tags: ["Azure AD", "SharePoint"]
type: "regular"
---

## User Profiles are an increasingly important part of a modern organisation

While they have always been important as a (often underused) tool for
finding staff and searching for people with certain skills, the changes
in work practice wrought by the COVID-19 pandemic now mean that staff
spend less time together physically, so have less opportunity to know
their colleagues and create the social and personal links that
team-building and socialisation rely on. The need to understand, use and
maintain useful staff profiles has never been greater.

Since profiles are complex, and the spread of technologies in Microsoft
365 are wide and constantly evolving, there is inevitable complexity.
Knowing what profile elements exist where and how both staff and admin
should access them is important.

This blog runs through the profile scatter at a high level, so that we
at least know where we should look.

## Azure

Azure provides the core user identity and essential profile service for
Microsoft 365 and beyond, via AAD (Azure Active Directory).

When creating a new user in AAD, you must add their Name and User Name
(email address) as well as any Groups or Roles they should be in.

![AAD.png](images/AAD.png)

AAD also allows other 'organisational information' about the user to be
added, specifically:

-   Profile Picture
-   First Name, Last Name, Maiden name
-   Job Title, Department, Manager, Employee ID, Company Name
-   Contact information (address, phone numbers)
-   Minors and Consents

This is all useful stuff, but user profiles can, and should, go a lot
further than the basics that AAD provides.

**See**: [Manage user profiles in the SharePoint admin center --
SharePoint in Microsoft 365 | Microsoft
Docs](https://learn.microsoft.com/sharepoint/manage-user-profiles#:~:text=%20Manage%20user%20profiles%20in%20the%20SharePoint%20admin,use%20OneDrive%2C%20but%20you%20don%27t%20want...%20More%20)

**Access AAD
profiles**: <https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/UsersManagementMenuBlade/MsGraphUsers>

## Microsoft 365

Microsoft 365 provides an extend set of profile attributes, with the
focus being on staff being able to add and extend their own information.

### Update personal profile

Staff can update many of their own personal information (but not most of
the things controlled in AAD) in the profile using the [Delve profile
page](https://gbr.delve.office.com/) and selecting *Me* and *Update
profile. *The pencil edit icon appears next to anything they are allowed
to change in the main profile, generally contact information and broader
profile information such as *About me* (personal biography), *Projects,
Skills and expertise, Schools and education, Interests and hobbies*.

There is also a deeper level (also based on the pre-Modern UI) which you
can get to from this
URL: `https://emicoltd-my.sharepoint.com//_layouts/15/editprofile.aspx?UserSettingsProvider`.
Custom Properties, if any, can be edited from the ellipsis (Custom
Properties)

![Delve.png](images/Delve.png)

They can also set who can see the information via a small Globe icon.

![Delve2.png](images/Delve2.png)

There are multiple 'ports of entry' to the profile update page:

-   Delve *Me* page
    `https://%3Ctenantname%3E-my.sharepoint.com/person.aspx`
-   Your account menu in Microsoft 365 (select your profile picture or
    initials)

[![Account.png](images/Account.png)

-   Any Microsoft 365 People card

[![People card.png](images/People card.png)

### Admin management of profiles

Microsoft 365 admins can manage core profile attributes from the *Users
| Active Users* page in the [Microsoft 365 admin
center](https://admin.microsoft.com/?auth_upn=it.development%40emico.co&source=applauncher#/users);
specifically:

-   User Name, email address
-   Profile picture
-   Display name (from Manage contact information, though normally this
    is locked and managed via Azure Active Directory).

## SharePoint Online

SharePoint Server has its own user profile service, there are a few
traces of that still to be found in SharePoint Online.

### SharePoint User Profile Service

The SharePoint User Profile Service stores information about SharePoint
users in a central location in SharePoint Server. It enables My Sites,
social computing features such as social tagging and newsfeeds, and
creating and distributing profiles across multiple sites and farms in
on-premises and hybrid scenarios. It is largely deprecated in SharePoint
Online, with Azure and the Microsoft 365 profile service (exposed via
Delve and Profile Cards in SharePoint) taking on most of the functions
it provided and exposing them to the Microsoft 365 Graph ('The Graph').
Legacy support still exist and it can be used for things like custom
profile properties.

### Add and edit user profile properties in SharePoint

If your organization uses the cloud Identity approach then your user
accounts are stored in Azure AD and admins manage user profile info in
the [Microsoft 365 admin center](https://admin.microsoft.com/#/users).
You can also manage user profiles (including adding user pictures and
defining user managers) in the [Azure AD admin
center](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade).

**See** [Add or change profile information for a user in Azure Active
Directory](https://learn.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal). 

### Adding custom profile attributes

If you need to create custom user profile properties, such as languages
spoken, emergency contact info, or sales account, you can use User
Properties in SharePoint.

Use the [More features page of the new SharePoint admin
center](https://admin.microsoft.com/sharepoint?page=classicfeatures&modern=true),
which uses the pre-modern SharePoint UI and profile service:

1.  Under User profiles, select Open.
2.  Under People, select Manage User Properties.

![Custom attributes.png](images/Custom attributes.png)

1.  Select New Property.
2.  In the Name box, enter a unique name for the property.

![Custom attributes 2.png](images/Custom attributes 2.png)

1.  In the Display Name box, enter the profile property name that will
    be displayed to all users. (This name doesn't have to be unique.)
2.  In the Type list, select the data type for the property.
     Note\
    If you select string (Multi Value), the property will be permanently
    set as a multi-valued property. You cannot change this setting after
    you select OK. You can only delete the property and add it again as
    a new single-value property.
3.  If you selected binary, HTML, or string, use the Length box to enter
    the maximum number of characters allowed for property values.
4.  If you selected string and want to associate the profile property
    with a [managed metadata term
    set](https://learn.microsoft.com/sharepoint/managed-metadata),
    select Configure a Term Set to be used for this property. Then
    select a term set from the list.
5.  Make sure Default User Profile Subtype is selected so the default
    user profile subtype is associated with this user profile property.
6.  In the Description box, enter the instructions or information that
    is displayed to users about this profile property.
7.  In the Policy Settings section, select the policy setting and
    default privacy setting that you want for this property. Select
    the User can override box to enable users to override these
    settings.
8.  If you want users to be able to change this profile information for
    themselves, select Allow users to edit values for this property.
9.  In the Display Settings section, specify whether and how the
    property will be viewed by users.
10. In the Search Settings section, select Alias if the property is the
    equivalent of a user's name. For example, you might do this if you
    create a property for a "Stage name" and want searches for all
    documents by John Kane to return the same results as searches for
    the user's real name. Select the Indexed if you want searches to
    return all the user profiles matching that property. For example, if
    you have a property for "University," a search for that value would
    return all alumni from that university.
     Note\
    The Alias check box is available only if you set the Default Privacy
    Setting > Everyone.
11. Select OK.

Note: Custom properties from Active Directory or Azure AD are not
synchronized with SharePoint.

**See** <https://learn.microsoft.com/sharepoint/add-and-edit-user-profile-properties>

### Bulk updates profiles and custom attributes

Many enterprises need to replicate custom attributes to the SharePoint
user profile service, or do bulk set up for multiple members of staff.
Microsoft provide a user profile bulk API,
the [UserProfile.BatchUpdate.API](https://github.com/SharePoint/PnP/tree/master/Samples/UserProfile.BatchUpdate.API).
PowerShell is the usual way of driving this, with a JSON import file
holding the attributes to be set.

**See**: [Bulk update custom user profile properties for SharePoint
Online](https://learn.microsoft.com/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online)

**See:** [Call the import API from
PowerShell](https://learn.microsoft.com/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online#call-the-import-api-from-powershell).

## User Profile Sync

Microsoft SharePoint uses the Active Directory synchronization job to
import user and group attribute information into the [User Profile
Application](https://learn.microsoft.com/sharepoint/install/create-a-user-profile-service-application#:~:text=%20Create%20a%20User%20Profile%20service%20application%20,an%20existing%20application%20pool%20from%20the...%20More%20) (UPA). When
a new user is added to Azure Active Directory (Azure AD), the user
account information is sent to the SharePoint directory store and the
UPA sync process creates a profile in the User Profile Application based
on a predetermined set of attributes. Once the profile has been created,
any modifications to these attributes will be synced as part of
regularly scheduled sync process.

 From
`https://learn.microsoft.com/sharepoint/user-profile-sync`

### Properties that are synced into SharePoint user profiles

The following Azure AD user attributes are synced to the UPA.

  ---------------------------- -------------------------------------------- ---------------------------------------------------------------------------------------------------------------------- -------------------
  **Azure AD attribute**       **User profile property display names**      **Notes**                                                                                                              **Sync to sites**
  UserPrincipalName            Account Name User Name User Principal Name   Example: i:0#.f \<|\> membership \<|\> gherrera@contoso.com gherrera@contoso.com                                   Yes
  DisplayName                  Name                                                                                                                                                                Yes
  GivenName                    FirstName                                                                                                                                                           Yes
  sn                           LastName                                                                                                                                                            Yes
  telephoneNumber              Work phone                                   Example: (123) 456-7890                                                                                                Yes
  proxyAddresses               Work Email SIP Address                       Work Email is set to the value prefixed with SMTP. (SMTP:gherrera@contoso.com) Example: gherrera@contoso.com         Yes
  PhysicalDeliveryOfficeName   Office                                                                                                                                                              Yes
  Title                        Title Job Title                              Job Title contains the same value as Title and is connected to a term set.                                             Yes
  Department                   Department                                   Department is connected to a term set.                                                                                 Yes
  WWWHomePage                  Public site redirect                                                                                                                                                No
  PreferredLanguage            Language Preferences                         Used by SharePoint to determine language for the user when the multilingual user interface (MUI) feature is enabled.   Yes
  msExchHideFromAddressList    SPS-HideFromAddressLists                                                                                                                                            No
  Manager                      Manager                                      User Manager for organization hierarchy                                                                                Yes
  ---------------------------- -------------------------------------------- ---------------------------------------------------------------------------------------------------------------------- -------------------

### Note

UPA synchronization is limited to a preconfigured set of properties to
guarantee consistent performance across the service.

**See**: [About user profile synchronization -- SharePoint in Microsoft
365 | Microsoft
Docs](https://learn.microsoft.com/sharepoint/user-profile-sync)

## Viva

Microsoft is rapidly developing its Employee Experience platform,
Microsoft Viva.

Topics will, almost certainly, be added to personal profiles, to better
link people with content and colleagues and aid findability of skills by
topic, while [Viva
Insights](https://eus-streaming-video-rt-microsoft-com.akamaized.net/a8403aec-bcb3-4e52-95d9-5b5d7c4d599e/b6c275d1-5bcc-4558-afc3-25c9a27e_2250.mp4) provides
analytics on individual and team activity and productivity. It seems
reasonable that profile information may be incorporated into the UI of
Viva and that the Delve experience will be deprecated.

**See**: [Employee Experience & Engagement | Microsoft
Viva](https://www.microsoft.com/en-gb/microsoft-viva)

**See:** [Microsoft 365 user profiles are adding Topics and skills to
improve Microsoft Search results --
OnMSF\...](https://www.onmsft.com/news/microsoft-365-user-profiles-are-adding-topics-and-skills-to-improve-microsoft-search-results)

## Other Applications

Much of the Microsoft 365 user profile information is exposed through
the Graph API and the Office 365 Users Connection provider. These let
you get the current users profile or another user's profile as well as
related users (notably their manager and reports). There is good support
for this in Power Automate, Power Apps, Logic Apps.

Then there is LinkedIn, which is being gradually embedded into the M365
stack and adds yet another profile source.

### Final word -- Profile Pictures

Profile pictures are really important -- they not only help reinforce
that you are working with a real person and let you recognise someone if
you actually meet them in an office (remember those days), but having a
picture of the person you are talking to actually improves engagement
and empathy. Sadly, maintaining profile pictures is a bit more complex
than you might expect. Different products (Experiences as Microsoft
would have you call them) source the image from different places; the
last time I checked it was:

![Profile pictures.png](images/Profile pictures.png)

Updating a profile in one place will, usually, update it everywhere, but
it can take up to 72 hours.

I strongly recommend that *everyone* is encouraged to do this though.

**See:** [Information about profile picture synchronization in Microsoft
365](https://support.microsoft.com/office/information-about-profile-picture-synchronization-in-microsoft-365-20594d76-d054-4af4-a660-401133e3d48a#:~:text=1%20Browse%20to%20the%20My%20Profile%20page%20by,updated%20to%20reflect%20the%20profile%20picture%20synchronization%20state.)
