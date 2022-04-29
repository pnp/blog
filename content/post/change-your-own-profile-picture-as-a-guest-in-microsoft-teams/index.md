---
title: "Change your own profile picture as a Guest in Microsoft Teams"
date: 2021-04-06T01:37:00-04:00
author: "Yannick Reekmans"
githubname: YannickRe
categories: ["Community post"]
images:
- images/image.png
tags: ["Microsoft Teams", "Azure AD"]
type: "regular"
---
I love Microsoft Teams and I also love controlling my online appearance,
but sadly both aren't big friends when you are a Guest in another
tenant. There still isn't a good/easy way of controlling your own
profile picture, which is sad because you are reduced to a
not-very-personal colored circle with initials:
![image.png](images/image.png)
Fellow MVP [Kazushi Kamegawa](https://twitter.com/kkamegawa) shared a
method of changing your profile picture in a private forum, but it
stopped working due to some UI changes in the Azure Portal. Luckily,
with some more "hackery", we can still make it work!
The tl;dr version:

1.  Tenant switch to the tenant where you want to change your profile
    picture
2.  Figure out the ID of your user account in that tenant
3.  Open your user profile page in the Azure Portal using a direct link
4.  Edit the profile, upload a profile picture
5.  Wait for about a week to have the profile picture synced into Teams

## Switch tenants

If you found this blogpost, it's probably safe to assume that you know
how to switch tenants. For the purpose of this guide, it is **VERY**
important you do this in your browser because otherwise authentication
will get confused ;).

1.  Open your browser, go to <https://teams.microsoft.com> and sign in
    with your credentials
2.  Top right of the Teams UI, switch to the tenant where you want to
    change the profile picture of your Guest account

![image-1.png](images/image-1.png)

## Get ID of user account

I don't know of any place in the UI that shows the id of your Guest
account in a tenant, so I had to find a way using the Developer Tools of
Chrome/Edge.

1.  After switching to the Guest tenant, hit the F12 key to open the
    Developer Tools
2.  Select the `Applications` tab
3.  In the left part underneath `Storage` and  `Local storage`, select
    `https://teams.microsoft.com`
4.  In the right part, do a search for `ts.tenantList`. It should only
    show one result, select it.
5.  It shows all tenants you are part of as a Guest, open up the one you
    are currently in. You'll need the value next to the `userId`
    property. In my screenshot, it is the GUID that starts with
    `f35707ec-...`
![image-3.png](images/image-3.png)

## User profile page in Azure Portal

Now that you have your user account ID, you can open up your profile
page in the Azure AD of the Guest tenant!

1.  In the same browser window, open <https://portal.azure.com>
2.  Top right of the portal, make sure you are in the tenant where you
    are a Guest. Most probably that is not the case, so do a tenant
    switch in the Azure Portal too.
3.  In the same browser window, open up this link:
    `https://portal.azure.com/#blade/Microsoft_AAD_IAM/UserDetailsMenuBlade/Profile/userId/<userId>`.
    Make sure to replace `<userId>` with the id you copied in the
    previous step.
4.  You should now see your profile page in the Azure AD where you are a
    Guest.
![image-4.png](images/image-4.png)

## Edit profile and upload picture

Finally time to upload your profile picture!

1.  Top of the profile, select the `Edit` button
2.  With your profile in edit mode, you can browse for a photo on your
    computer and upload it to your profile!
 ![image-5.png](images/image-5.png)

## Wait and enjoy success 

It takes a while for your profile picture to show in Teams, and it might
even show for a short while and go away again. But if you have enough
patience, after about a week or so, your profile picture should show
consistently across the Teams UI both for you and for others!
![image-6.png](images/image-6.png)

Until Microsoft Teams or Microsoft 365 gives us an easier way to change
our profile picture, this is the best way to do it self service. The
days of the anonymous circle with initials are over, time to show your
personality also in your Guest tenants!
