---
title: "Matching the logged in user in a canvas app with a person column in SharePoint"
date: 2021-11-11T05:27:00-05:00
author: "Carmen Ysewijn"
githubname: CarmenYsewijn
categories: ["Community post"]
images:
- images/Hermione-IconVisible.png
tags: ["Power Apps", "SharePoint"]
type: "regular"
---

Recently, I came across an interesting issue using people columns in a
SharePoint list. We were working with a list in which multiple roles had
been identified (reviewer, approver, etc.). Depending on the role a
certain person had for a specific item, they should be able to take
different actions in the canvas app built on top of that list. For
example: approve an item if they are listed as the approver.
We tried to achieve this by checking that the logged in user's email
corresponds to the email of the person for that role. In most cases,
this worked. However, in some cases, a user that is listed as an
approver for an item did not see the approve/reject option. After some
debugging, we figured out this was due to the fact that there was a
mismatch between the result of the `User().Email` function in canvas
apps, which returns the email of the logged in user, and
the **Approver.Email** result, which is the email of the person in the
Approver column.

### The problem 

To illustrate this problem, and the solution, I built a simple Holiday
approval canvas app with a similar setup to the client application. In
the below screenshots, you can see the logged-in user's email address in
the top right corner of the application, below their display name. One
or more of the items in the list are assigned to each of the users. If
the logged in user is the approver, they should have the Approve/Reject
option available in the list, which is indicated with the canvas apps
"DockCheckIcon" icon.
![Hermione-IconVisible.png](images/Hermione-IconVisible.png)

![Harry-IconNotVisible.png](images/Harry-IconNotVisible.png)
![Ron-IconNotVisible.png](images/Ron-IconNotVisible.png)

The first user, Hermione, does not give any issues. The email address of
the logged-in user matches that of the approver in the SharePoint list,
so the icon is visible. For the second user, Harry, the logged-in user's
email is listed as Harry.Potter@domain.com. However, in the list it is
Chosen.One@domain.com, the primary alias that was defined for the user.
Since these do not match, the icon is not visible. Finally, for the
third user, Ron, only the capitalization between the two email addresses
differs, giving the same result: the icon is not visible.
The root cause here is that we are comparing different things: the
result of the `User().Email `function and **Approver.Email** property in
the SharePoint list is not based on the same thing. I
suspect `User().Email` actually provides the UPN (User Principal Name)
of the user, whereas the **Approver.Email **property is the primary
email. This is not necessarily constant, and can change for multiple
reasons. Therefore, this is not a valid check to make.

### The solution 

Instead of comparing two different things, we should compare the UPN for
both the logged-in user and the approver in the SharePoint list.
Let's first get the UPN for the logged-in user. Since I am
only [**assuming **]{.mark .has-inline-color .has-secondary-color}that
the `User().Email` function returns the UPN, but I'm not sure about this
(and this could potentially change in the future), I will not user this
for the check. Instead, I will create a global variable for the UPN in
the **OnStart** of the app and use the Office365Users connector and the
available `MyProfileV2()` function to return the profile of the user
currently logged in to the app. The profile contains a UserPrincipalName
property, which is what we need.
The **OnStart **of the app is as follows:

`Set(varLoggedInUserUPN,Office365UsersV2.MyProfile().userPrincipalName)`

For the approvers, we will need a different function, since we don't
need the logged in user's profile, but the profile of the user specified
in the approver column for each item in the list. In this case, I'm
using the `UserProfileV2()` function.
⚠ Make sure to use **V2** for this one. The `UserProfile()` function
without V2 will not work with the email address, only with the UPN
(which we don't have, we are looking for it).
To make the icon visible only when there is a match, set
the **Visible** property of the icon to

`Office365Users.UserProfileV2(ThisItem.Approver.Email).userPrincipalName = varLoggedInUserUPN`
If we now go back to the application for our 3 users, the approve icon
will be visible when relevant for them.

For Hermione, the result is exactly the same. For Harry and Ron, it now
looks different.
![Harry-IconVisible.png](images/Harry-IconVisible.png)


![Ron-IconVisible.png](images/Ron-IconVisible.png)

### A closing note

This approach is not ideal, especially when working with larger
datasets.
Since every item in the gallery items causes a call to the Office 365
Users connector to get the user profile, this may cause some delay in
loading the screen and specifically the approve icon.
An alternative to avoid this call, could be using
the **Claims** property that you can get from the Approver column
properties (and trimming the prefix). In my tests, this seemed to be the
user principal name (in lowercase), but I could not immediately find any
confirmation for this. For this reason, and the fact that at the
customer the dataset was rather small too, I have not used this
approach. If you would be taking this approach however, make sure to
decapitalize the UPN for the logged-in user too, otherwise there might
be a mismatch still.
