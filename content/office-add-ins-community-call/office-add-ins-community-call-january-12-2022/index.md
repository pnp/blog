---
title: "Office Add-ins community call - January 12, 2022"
date: 2022-01-18T10:19:00-05:00
author: "David Chesnut"
githubname: davidchesnut

categories: ["Office add-in developer community call"]
images:
- images/office-add-ins-Thumb Jan 2022.png
tags: []
type: "regular"
---


## Call summary

This month's community call features updates on **Excel shortcut
customization APIs** (introducing 3 new APIs to assist with keyboard
shortcuts management) from Abid Rahman (Microsoft), an **SSO update for
Office Add-in** (call to action: add new SSO service in Azure for your
SSO enabled add-ins) by Matt Geimer (Microsoft), and the latest
**Outlook event-based activation on Mac** (announcing Mailbox 1.10 APIs
and Event-based add-ins are GA in New Outlook for Mac) from Ashima
Mathur (Microsoft). This month's Community spotlight recognizes [Eric
Legault](https://twitter.com/elegault) (Eric Legault Consulting) and
[Maarten van Stam](https://twitter.com/aafvstam) (Deloitte) for their
continued contributions to this community.  Q&A both at end of call and
in chat throughout call. Please register for the [PnP Recognition
Program](https://aka.ms/m365pnp-recognition). The call was hosted by
Alex Jerabek (Microsoft). Recorded January 12, 2022.


## Microsoft Presenters

-   Alex Jerabek, Dev Writer 
-   Abid Rahman, Program Manager
-   Matt Geimer, Senior Program Manager
-   Ashima Mathur, Program Manager 

## Agenda

-   **Excel shortcut customization APIs** -- Abid Rahman, Program
    Manager (Microsoft) -- [00:38](https://youtu.be/ncFuSJ4T58k?t=38)
-   **SSO update for Office Add-in** -- Matt Geimer, Senior Program
    manager (Microsoft) -- [13:48](https://youtu.be/ncFuSJ4T58k?t=828)
-   **Outlook event-based activation on Mac** -- Ashima Mathur, Program
    Manager (Microsoft) -- [18:42](https://youtu.be/ncFuSJ4T58k?t=1122)
-   **Community spotlight** -- [Eric
    Legault](https://twitter.com/elegault) (Eric Legault Consulting) and
    [Maarten van Stam](https://twitter.com/aafvstam) (Deloitte) --
    [24:06](https://youtu.be/ncFuSJ4T58k?t=1446)
-   **Q&A** -- [24:45](https://youtu.be/ncFuSJ4T58k?t=1485)

## Actions

-   Use [Excel KeyboardShortcuts
    1.1](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/excel-keyboard-shortcuts)
    API set.
-   If you're using SSO on the web, add the new SSO service in Azure
    Portal for your SSO enabled add-ins. See [New Single Sign-on service
    for Office Add-ins rolling out in Office on the
    web](https://devblogs.microsoft.com/microsoft365dev/new-single-sign-on-service-for-office-add-ins-rolling-out-in-office-on-the-web/) blog
    post.
-   Update to the latest builds of Mailbox 1.10 APIs and Event-based
    add-ins on new Outlook for Mac and test your add-ins.
-   Register for the [PnP Recognition
    Program](https://aka.ms/m365pnp-recognition).


## Q&A (Question & Answers)


**Will shortcut key APIs be available on all hosts?**\
Shortcut key APIs are only available on Excel right now. We don't have
plans for the other hosts yet.

**If a shortcut key is already in use by another add-in, is there a way
for the user to override it?**\
Yes, the host (Excel) will prompt the user to make a choice between
them. For more information, see [Add custom keyboard shortcuts to your
Office
Add-ins.](https://learn.microsoft.com/office/dev/add-ins/design/keyboard-shortcuts#avoid-key-combinations-in-use-by-other-add-ins)

\
**Can I display a local image in a task pane? I want to use a path to a
file, like file:///C:/Users/user/Downloads/logo.png, but the browser
forbids this action with the error "Not allowed to load local
resource."**

Due to the sandboxed nature of how Office Add-ins run in a browser, this
isn't possible. Access files from a URL location on OneDrive, or other
locations. Please consider submitting a feature request with more
details about this scenario at <https://aka.ms/m365dev-suggestions>.

\
**For the new SSO service, if the group authorization id is already in
the list of authorized client applications, then there are no changes
required?**\
Correct, but you may still want to do a quick test with the new auth
option to make sure you don't see any issues.

\
**Are there any advantages to using SSO in Office, instead of MSAL,
apart from the amount of code you have to write?**\
You should still use MSAL as a fallback authentication approach (when
using Microsoft identity platform), in case SSO isn't available or has
an error. The advantage of SSO is you get the token without opening
dialogs, and extra steps for the user. With SSO you can also enable
admin consent via centrally deployed add-ins.



**Is there a way at runtime to determine if we're in Compose or Read
mode? Currently I can check certain APIs to see if they are available or
not, but a global option to tell me which mode we're in would be very
helpful.**\


If you're trying to execute different functions in Compose vs Read
mode, specify that in the different extension points. For event-based
add-ins, you can specify on which event the add-in should automatically
launch (such as on message compose).


**The latest Outlook requirement set is 1.11. but iOS and Android only
support requirement set 1.5. Are there plans to update those platforms
to support later requirement sets?**\
We are exploring specific scenarios for Outlook mobile extensibility.
While the exact requirement sets may not be replicated, we plan to
unlock some of the key scenarios with specific API support.

**Azure AD provides a way to disable user consent entirely to always
require administrator consent for all applications. Without resorting to
this option, is there a way to grant administrator consent (on behalf of
your organization's users) to an app and in doing so, entirely bypass
the user consent flow for a smoother first-use experience?​**

For add-ins using SSO, there is a mechanism via centralized deployment
that allows an admin to consent for the permissions for all users, even
if the user was allowed to consent. You can also utilize this mechanism
using tenant-wide admin consent in Azure. For more details, see [Grant
tenant-wide admin consent to an
application​](https://learn.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent).
**Can Microsoft Outlook Policy Tips be used in conjunction with add-ins
REST/EWS send API? Full description of problem described on Stack
Overflow:
[https://stackoverflow.com/questions/70619981/can-microsoft-outlook-policy-tips-be-used-in-conjunctio\...](https://stackoverflow.com/questions/70619981/can-microsoft-outlook-policy-tips-be-used-in-conjunction-with-add-ins-rest-ews-s)
​**

​The team is looking into this question and will follow up on Stack
Overflow.


## Resources

### Excel shortcut customization APIs

-   Sample Repo -- [Use keyboard shortcuts for Office add-in
    actions](https://github.com/OfficeDev/Office-Add-in-samples/tree/main/Samples/excel-keyboard-shortcuts) 
-   Documentation -- [Add custom keyboard shortcuts to your Office
    Add-ins](https://learn.microsoft.com/office/dev/add-ins/design/keyboard-shortcuts) 
-   Documentation -- [Keyboard Shortcuts 1.1 requirement
    sets](https://learn.microsoft.com/office/dev/add-ins/reference/requirement-sets/keyboard-shortcuts-requirement-sets) 
-   Documentation -- [Avoid key combinations in use by other
    add-ins](https://learn.microsoft.com/office/dev/add-ins/design/keyboard-shortcuts#avoid-key-combinations-in-use-by-other-add-ins) 
-   Documentation -- [Enable custom keyboard shortcuts for specific
    users
    (preview)](https://learn.microsoft.com/office/dev/add-ins/design/keyboard-shortcuts#enable-custom-keyboard-shortcuts-for-specific-users-preview) 
-   Feedback Repo -- [Issues --
    OfficeDev/Office-js](https://github.com/OfficeDev/office-js/issues){style="color: inherit; font-family: inherit; font-size: 18px;"}

### SSO Update for Office Add-in

-   Documentation -- [Privacy and security for Office
    Add-ins](https://learn.microsoft.com/office/dev/add-ins/concepts/privacy-and-security) 
-   Documentation -- [Register an Office Add-in that uses SSO with the
    Azure AD v2.0
    endpoint](https://learn.microsoft.com/office/dev/add-ins/develop/register-sso-add-in-aad-v2) 
-   Blog post -- [New Single Sign-on service for Office Add-ins rolling
    out in Office on the
    web](https://devblogs.microsoft.com/microsoft365dev/new-single-sign-on-service-for-office-add-ins-rolling-out-in-office-on-the-web/) 

### Outlook event-based activation on Mac 

-   Documentation -- [Outlook add-in API requirement set
    1.10](https://learn.microsoft.com/office/dev/add-ins/reference/objectmodel/requirement-set-1.10/outlook-requirement-set-1.10) 

### Q&A

-   Documentation -- [Grant tenant-wide admin consent to an
    application](https://learn.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent) 
-   Question -- [Can Microsoft Outlook Policy Tips be used in
    conjunction with add-ins REST/EWS send
    API?](https://stackoverflow.com/questions/70619981/can-microsoft-outlook-policy-tips-be-used-in-conjunction-with-add-ins-rest-ews-s) 

### Office Add-ins community call

-   [Upcoming agenda and previous call
    resources](https://aka.ms/officeaddinsagenda)
-   [Recurring, monthly community call calendar
    invite](https://aka.ms/officeaddinscommunitycall)
-   [Community call topic requests and
    questions](https://aka.ms/officeaddinsform)
-   Community call recordings on the [YouTube Microsoft 365 community
    channel](https://www.youtube.com/channel/UC_mKdhw-V6CeCM7gTo_Iy7w)

### Office Add-ins feedback

-   Technical questions -- Microsoft Q&A
    ([office-js-dev](https://learn.microsoft.com/answers/topics/office-js-dev.html)),
    ([office-addins-dev](https://learn.microsoft.com/answers/topics/office-addins-dev.html))
-   Issues -- [GitHub](https://github.com/OfficeDev/office-js/issues)
-   Recommendations and suggestions -- [Microsoft 365 Developer Platform
    ideas](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform)
 
