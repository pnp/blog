---
title: "Export conversations from Microsoft Teams Channels using the CLI for Microsoft 365"
date: 2021-09-20T02:30:00-04:00
author: "Patrick Lamber"
githubname: plamber
categories: ["CLI For Microsoft 365"]
tags: []
type: "regular"
---


We utilize Teams during incidents and create channels for each. We would like to be able to export conversation history.

-   right now the only option we have is to go through Security &
    Compliance.
-   Teams usage is growing in every organization and it would soon
    become unreasonably to only have Administrators be the ones doing
    exports of channels for all the Teams.
This post will show you one of the most popular [sample
scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/teams/export-teams-conversations/)
created  for the CLI for Microsoft 365. The original script was created
by our community member [Joseph
Velliah.](https://blog.josephvelliah.com/export-conversations-from-microsoft-teams)
 
```powershell
function  Get-Teams {
  $teams = m365 teams team list -o json | ConvertFrom-Json -AsHashtable
  return $teams
}
function  Get-Channels {
  param (
    [Parameter(Mandatory = $true)] [string] $teamId
  )
  $channels = m365 teams channel list --teamId $teamId -o json | ConvertFrom-Json -AsHashtable
  return $channels
}
function  Get-Messages {
  param (
    [Parameter(Mandatory = $true)] [string] $teamId,
    [Parameter(Mandatory = $true)] [string] $channelId
  )
  $messages = m365 teams message list --teamId $teamId --channelId $channelId -o json | ConvertFrom-Json -AsHashtable
  return $messages
}
function  Get-MessageReplies {
  param (
    [Parameter(Mandatory = $true)] [string] $teamId,
    [Parameter(Mandatory = $true)] [string] $channelId,
    [Parameter(Mandatory = $true)] [string] $messageId
  )
  $messageReplies = m365 teams message reply list --teamId $teamId --channelId $channelId --messageId $messageId -o json | ConvertFrom-Json -AsHashtable
  return $messageReplies
}
Try {
  $teamsCollection = [System.Collections.ArrayList]@()
  $teams = Get-Teams
  $progressCountTeam = 1;
  foreach ($team in $teams) {
    Write-Progress -Id 0 -Activity "Processing channels in Team : $($team.displayName)" -Status "Team $progressCountTeam of $($teams.length)" -PercentComplete (($progressCountTeam / $teams.length) * 100)
    $channelsCollection = [System.Collections.ArrayList]@()
    $channels = Get-Channels $team.id
    $progressCountChannel = 1;
    foreach ($channel in $channels) {
      Write-Progress -Id 1 -ParentId 0 -Activity "Processing messages in channel : $($channel.displayName)" -Status "Channel $progressCountChannel of $($channels.length)" -PercentComplete (($progressCountChannel / $channels.length) * 100)
      $messages = Get-Messages $team.id $channel.id
      $messagesCollection = [System.Collections.ArrayList]@()
      foreach ($message in $messages) {
        $messageReplies = Get-MessageReplies $team.id $channel.id $message.id
        $messageDetails = $message
        [void]$messageDetails.Add("replies", $messageReplies)
        [void]$messagesCollection.Add($messageDetails)
      }
      $channelDetails = $channel
      [void]$channelDetails.Add("messages", $messagesCollection)
      [void]$channelsCollection.Add($channelDetails)
      $progressCountChannel++
    }
    $teamDetails = $team
    [void]$teamDetails.Add("channels", $channelsCollection)
    [void]$teamsCollection.Add($teamDetails)
    $progressCountTeam++
  }
  Write-Progress -Id 0 -Activity " " -Status " " -Completed
  Write-Progress -Id 1 -Activity " " -Status " " -Completed
  $output = @{}
  [void]$output.Add("teams", $teamsCollection)
  $executionDir = $PSScriptRoot
  $outputFilePath = "$executionDir/$(get-date -f yyyyMMdd-HHmmss).json"
  # ConvertTo-Json cuts off data when exporting to JSON if it nests too deep. The default value of Depth parameter is 2. Set your -Depth parameter whatever depth you need to preserve your data.
  $output | ConvertTo-Json -Depth 100 | Out-File $outputFilePath
  Write-Host "Open $outputFilePath file to review your output" -F Green
}
Catch {
  $ErrorMessage = $_.Exception.Message
  Write-Error $ErrorMessage
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
\
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
