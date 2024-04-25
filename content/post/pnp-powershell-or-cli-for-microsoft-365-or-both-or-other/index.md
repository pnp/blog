---
title: "PnP PowerShell or CLI for Microsoft 365 or both or other"
date: 2022-01-11T15:40:24+06:00
# post thumb
images:
  - "images/post-thumb.png"
#author
author: "Adam Wójcik"
githubname: Adam-it
# description
description: "During my SP consultant/dev work I most of the times used the last two. From time to time I got the question: which one is better?"
summary: "During my SP consultant/dev work I most of the times used the last two. From time to time I got the question: which one is better?"
# Taxonomies
categories: ["Community post"]
tags: ["CLI for Microsoft 365", "PnP PowerShell"]
type: "regular" # available type (epic, trending, popular, or regular)

---

## The intro (what's up)

There are many ways we may manage Microsoft 365. To name a few we may
use [Microsoft Graph PowerShell
SDK](https://learn.microsoft.com/graph/powershell/get-started) or
[SharePoint Online Management
Shell](https://learn.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) or
[PnP PowerShell](https://pnp.github.io/powershell/) or [CLI for
Microsoft 365](https://pnp.github.io/cli-microsoft365/). During my SP
consultant/dev work I most of the times used the last two. From time to
time I got the question: which one is better?
And probably you are expecting the answer to this question at the
conclusion of this article but since this is one of my first articles
ever I will do it a bit differently and give my answer now
😀. IMO we should use both, I mean it's not about which
one is better but in the end it's all about which tool is more suitable
for the task you are up against and the more tools you know (or you may
use in your company) the more possibilities you have to succeed in your
task.

## PnP PowerShell

This one is almost always used and it's quite understandable. I mean
usually many of SP consultants used to work with the OnPrem version of
SharePoint, and sooner or later there was always a need of some small
provision or other setup kind of script to be created (at least this was
my story and most of the people I worked with). The first thing usually
used was the [SharePoint
PowerShell](https://learn.microsoft.com/sharepoint/sharepoint-powershell).
The next cool thing that happened was the SharePointPnPPowerShell
2013/16/19 and all the improvements it gave. After some time it was the
'must have tool' when it comes to developing PowerShell scripts to
manage SharePoint. Now it's all about the cloud and every company wants
to be Online and not only use SharePoint Online but all of Microsoft 365
capabilities.
PnP PowerShell is a newer version of the SharePointPnPPowerShellOnline
module (which is not maintained anymore) which is cross platform, that's
right, it will work not only on Windows but on MacOS or Linux as well,
all thanks to PowerShell Core.
So it's natural many just picked PnP PowerShell. Currently it has
almost 600 commands ([check full docs
list](https://github.com/pnp/powershell/tree/dev/documentation)) that
gives the possibility to manage SharePoint Online, Microsoft Teams,
Microsoft Planner and Power Platform (mainly Power Automate (for
PowerApps there is also the[PowerApps.PowerShell](https://learn.microsoft.com/power-platform/admin/powerapps-powershell)
which may be used.
It's straight forward and easy to use and it's a perfect pick for any
quick day to day tenant management as well as for huge scripts that may
run every day to add that additional logic to your tenant (either
reporting or maintenance or provisioning or other). And Like every other
SharePoint module you may just install it using

```powershell
Install-Module -Name "PnP.PowerShell"
```

command and you're good to go.
Maybe you would like to contribute? You would like to make something new
or do a fix. That's great, as it is written in C# (so how hard can it
be right?), it uses CSOM (as expected for C# code and SP Online things)
but also MS Graph, and there even is a [ready guide to help you get
started](https://pnp.github.io/powershell/articles/buildingsource.html)

## CLI for Microsoft 365

And What's this? And why would I need this? TBH those were my questions
when I first go to know this tech. Please be aware at that time
SharePointPnPPowerShellOnline (as the PnP.PowerShell was not out yet)
was only for Windows (it could only run on windows PowerShell because of
its dependencies), so the huge advantage of CLI for M365 was that you
may use it on every platform just like that. Now of course
PnP.PowerShell is also cross platform.
You may use CLI for Microsoft 365 to manage many things. To name a few,
you may manage OneDrive, Planner, Power Apps and Automate, Teams,
Yammer, SharePoint (of course), now there is even a dedicated command to
help you set up Viva and the list keeps on growing an growing. But
that's not only about managing Microsoft 365.
CLI helps you also manage your own spfx environment (check out
the [doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor/))
or projects (rename, upgrade etc.). This is something I think
PnP.PowerShell does not have.
Some commands do simple things but some actually are ready to use
scenarios all done under a single command. Check out the [full list of
commands](https://pnp.github.io/cli-microsoft365/cmd/login/#usage)
That's nice right. But how does it work. Well CLI for M365 is given as a
npm package, that's right you need Node.js (that's why it's cross
platform), and if you are guessing that it's probably all written in
javascript than you are right again. How cool is that. I mean if it's
not cool for you then I will just bring a life example I had. Usually
when you apply for an SharePoint dev kind of role there always is a
PowerShell skill in the 'must have' in the job description. That's
understandable but still there are not many SharePoint developers so
usually companies are looking for web developers. For SharePoint online
maybe the story is not that different, at least not like for an SP
OnPrem version where feature model is still used... now those are very
specific skills and knowledge you need. Now for the SP Online a web
developer may seem like a perfect fit but the PowerShell skill may seem
a bit challenging for a developer who now using javascript may basically
do all she or he needs (web page frontend using React or Angular or
whatever + a backend web API using node.js). But now... well now (thanks
to CLI for M365) with javascript that web developer may also manage
Microsoft 365 and the PowerShell skills in the job description may not
be that 'must have' as it used to be before.
If you haven't used it before probably you are also wondering how
similar it is to PnP.PowerShell (in terms of commands). [Check out this
map
table](https://pnp.github.io/cli-microsoft365/about/comparison-powershell/)
You may also think how much it is used? To answer this please check out
[PnP script samples gallery
matrix](https://pnp.github.io/script-samples/matrix.html) and checkout
were you see the most likes (yes in the CLI for M365 column).
So maybe you would like to contribute? You tried it out and something
did not work well and you want to add a fix. That's great! It is
written in javascript and mainly uses MS Graph and standard Web API
(like SharePoint Rest API). Please check the [contribute wiki page to
get you started](https://github.com/pnp/cli-microsoft365/wiki)
BTW did you know there are also ready to use CLI for Microsoft 365
GitHub actions you may use for you CI/CD workflows. Ever had this "ye
and when we push on the master branch it would be nice if the webpart
would be build and pushed to a test/QA tenant". If yes then you have to
see this [GitHub Actions - CLI for Microsoft 365
pnp.github.io](https://pnp.github.io/cli-microsoft365/user-guide/github-actions/)

## When? What? Why?

Using either PnP.PowerShell or CLI for M365 is rather simple and totally
logical. Lets have a look at this very simple script from PnP Script
Sample gallery (<https://pnp.github.io/script-samples>) added by Paul
Bullock. The script gets the site and disables the delete option on a
list.

```powershell
Connect-PnPOnline -Url "https://<tenant>.sharepoint.com" -Interactive
$list = Get-PnPList -Identity "<list or library>"
$list.AllowDeletion = $false
$list.Update()
Invoke-PnPQuery
Write-Host "Done! :-)" -ForegroundColor Green
```

source: [Remove delete option on a document library | PnP
Samples](https://pnp.github.io/script-samples/remove-delete-option-library/README.html?tabs=pnpps)
So the flow is simple. We connect to the site to which we want to make
some changes, we do those changes and that's it.
Now lets look at the same thing done with CLI for M365.

```powershell
$m365Status = m365 status
if ($m365Status -eq "Logged Out") {
    m365 login
}
$site = "<site>"
$list = "<list or library>"
$json = m365 spo list get --title $list --webUrl $site
$json = $json | ConvertFrom-Json
m365 spo list set --webUrl $site --id $json.Id --allowDeletion false
Write-Host "Done! :-)" -ForegroundColor Green
```

What is the flow here? First we login (or we check if we are still
logged in) to the tenant. And then we execute commands to get and/or
modify passing the web url as an param.
It does look very similar don't you think? Both are really readable,
logical and easy to maintain. Of course there will be scenarios when one
is better over the other or one just does not support it (yet).
In this simple example above we see the way we 'connect' is different.
In PnP.PowerShell we usually connect to the site we want to change but
in CLI for M365 we connect to the tenant, and not only that, the
CLI [persists the
connection](https://pnp.github.io/cli-microsoft365/concepts/persisting-connection/).
This is very handy when you do CLI work on your tenant every day on
multiple sites and you don't want to start every time from logging in
(connecting).
Also it would seem that CLI for M365 would be better for a scenario were
we have a list of sites we need to loop and apply some change.
So lets say we have

```powershell
$sites = @('https://thisisverycooltenant.sharepoint.com/sites/hr-live', 'https://thisisverycooltenant.sharepoint.com/sites/demoportal')
```

And now when using PnP.PowerShell we may do it like this

```powershell
$Credential = Get-Credential
[SecureString]$SecurePass = ConvertTo-SecureString $Credential.GetNetworkCredential().password -AsPlainText -Force
[System.Management.Automation.PSCredential]$PSCredentials = New-Object System.Management.Automation.PSCredential($Credential.GetNetworkCredential().username, $SecurePass)
foreach ($site in $sites)
{
    Connect-PnPOnline -Url $site -Credentials $PSCredentials
    Set-PnPWeb -Title 'test'
    Disconnect-PnPOnline
}
```

Of course we would not need to pass the credentials, as there are other
authenticate options we might use like credential manager (but then
it's windows only) or Microsoft.PowerShell.SecretManagement and
Microsoft.PowerShell.SecretStore (multi platform), please check [this
link](https://pnp.github.io/powershell/articles/authentication.html) for
more info. But regardless of authenticate option still the concept of
connecting and disconnecting would remain.
Now when using CLI for M365 we might just do

```powershell
$m365Status = m365 status
if ($m365Status -eq "Logged Out") {
   m365 login
}
foreach ($site in $sites)
{
    m365 spo web set --webUrl $site --title 'test'
}
```

Now should we say that one approach is better over the other... I don't
know ;). For me both tools did what I needed in a reasonable amount of
time.
The above example is just a simple case were but we may already have a
feeling when and why we could use one tool over the other.

## Both\... really?

Using those both together. Now that's strange. TBH I totally agree, but
let's think of example case were we already have some script ready in
PnP.PowerShell doing something on the site (let's say changing the
title so the example will be similar to the previous one) but we just
don't know which sites should be modified and we need to query the
lists of sites that match some pattern and apply changes only there.
Well there is a single line for it in the CLI for M365, and it would be
a shame not to use it.

```powershell
$m365Status = m365 status
if ($m365Status -eq "Logged Out") {
    m365 login
}
$sites = m365 spo site list --type CommunicationSite --filter "Url -like 'demoportal'"
$sites = $sites | ConvertFrom-Json
$Credential = Get-Credential
[SecureString]$SecurePass = ConvertTo-SecureString $Credential.GetNetworkCredential().password -AsPlainText -Force
[System.Management.Automation.PSCredential]$PSCredentials = New-Object System.Management.Automation.PSCredential($Credential.GetNetworkCredential().username, $SecurePass)
foreach ($site in $sites)
{
    Connect-PnPOnline -Url $site.Url -Credentials $PSCredentials
    Set-PnPWeb -Title 'test123'
    Disconnect-PnPOnline
}
```

Now I totally wouldn't recommend this kind of approach for any script
which is supposed to be scheduled and runed iteratively. This is because
the authorization process may be hard to maintain. But if this was some
kind of one time task we need to do, why not combine the tools and the
skills we already have and just go on with your work. Sticking to one
tool and one approach only, may make our work less efficient. Of course
it is almost always possible to do the same things in both tools but if
one of those allows to do something easier why not combine the two and
do what needs to done faster.

## The End? Already?

Yes\... I hope you will agree with me that using both, rather than
picking the better one is the correct approach. If you are already using
one of those tools try the other one. I strongly encourage you to try to
reproduce one of your existing scripts you already have in tech you did
not use to see the difference and maybe notice some improvements it
might bring (or not).
If you are already using both I would really love to here your opinion.
Are you already using PnP.PowerShell or CLI for Microsoft 365? Or maybe
both? Do you see some benefits of one over the other? Do you think one
of those tools are lacking something important? Any comment is
appreciated and also may be a good tip for the repo maintainers or
friendly contributors.
