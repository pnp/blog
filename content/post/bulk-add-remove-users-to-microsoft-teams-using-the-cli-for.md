---
title: "Bulk add/remove users to Microsoft Teams using the CLI for Microsoft 365"
date: 2021-10-05T03:08:00-04:00
author: "Patrick Lamber"
githubname: plamber
categories: ["CLI For Microsoft 365"]
tags: []
type: "regular"
---


We will continue our journey with the most popular [sample
scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/entra/bulk-manage-group-users/)
created  for the CLI for Microsoft 365. This time we will show you how
to add and remove users to Microsoft Teams in bulk. The original script
was created by our community member [Joseph
Velliah.](https://blog.josephvelliah.com/)

The script requires a CSV file with different parameters:

- groupMailNickname: the mail alias used for the Microsoft 365 Group
associated to the current team

- userPrincipalName: the UPN of the user that should be processed
-
- role (owner, member): the role of the user. Can be owner or member.
Keep it empty if you want to remove a user

- operation (add, remove): operation to execute


``` {.lia-code-sample .language-applescript}
groupMailNickname1, user1@domainname.com, owner, add
groupMailNickname2, user2@domainname.com, member, add
groupMailNickname3, user3@domainname.com, , remove
```
 

The script in question looks as follows:


```powershell
$taskItems = import-csv "sample-input-file.csv" –header mailNickname, userEmail, role, action
$groups = m365 aad o365group list -o json | ConvertFrom-Json

ForEach ($taskItem in $taskItems) {

    $mailNickname = $($taskItem.mailNickname)
    $userEmail = $($taskItem.userEmail)
    $role = $($taskItem.role)
    $action = $($taskItem.action)

    $group = $groups | Where-Object { $_.mailNickname -eq "$mailNickname" }
    $user = m365 aad user get --userName $userEmail -o json | ConvertFrom-Json

    Write-Host "Processing: User --> " $user.mail " Group --> " $group.mailNickname

    If ($action -eq "add") {

        If ($role -eq "owner") {
            m365 aad o365group user add --groupId $group.id --userName $user.mail --role Owner;
            Write-Host $user.mail " added as owner in " $group.mailNickname
        }
        ElseIf ($role -eq "member") {
            m365 aad o365group user add --groupId $group.id --userName $user.mail
            Write-Host $user.mail " added as member in " $group.mailNickname
        }
        Else {
            Write-Host "Invalid user role '" $role "'"
        }
    }
    ElseIf ($action -eq "remove") {
        m365 aad o365group user remove --groupId $group.id --userName $user.mail --confirm
        Write-Host $user.mail " removed from " $group.mailNickname
    }
    Else {
        Write-Host "Invalid task action '" $action "'"
    }
}
```

You can find this and many more samples on how to use the CLI for
Microsoft 365 in our [official samples
section.](https://pnp.github.io/cli-microsoft365/sample-scripts/introduction)


## What is the CLI for Microsoft 365?

[CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) is a
cross-platform CLI that allows you to manage various configuration
settings of Microsoft 365 and SharePoint Framework projects no matter
which operating system or shell you use.

While building solutions for Microsoft 365 expands beyond the Windows
operating system, managing many of the platform settings is possible
only through PowerShell on Windows. As more and more users work on
non-Windows machines, it's inconvenient for them to have to use a
Windows virtual machine to configure their tenants. With the CLI for
Microsoft 365, you can configure your tenant no matter which operating
system you use. Additionally, using CLI for Microsoft 365, you can
manage your SharePoint Framework projects.

### Try it today

Get the latest release of the CLI for Microsoft 365 from npm by
executing:


```bash
npm i -g @pnp/cli-microsoft365
```

If you need more help getting started or want more details about the
commands, the architecture or the project, go to
[aka.ms/cli-m365](https://aka.ms/cli-m365).

If you see any room for improvement, please, don't hesitate to reach out
to us either on [GitHub](https://github.com/pnp/cli-microsoft365) or
[twitter](https://twitter.com/climicrosoft365).
