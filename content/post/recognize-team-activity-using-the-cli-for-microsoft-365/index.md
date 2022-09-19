---
title: "Recognize team activity using the CLI for Microsoft 365"
date: 2021-08-09T08:41:00-04:00
author: "Albert-Jan Schot"
githubname: appieschot
categories: ["CLI for Microsoft 365"]
images:
- images/team-champion-script.png
tags: ["CLI for Microsoft 365", "Microsoft Teams"]
type: "regular"
---

## The scenario

Not unlike the previous scenario the goal of this blog post is to
identify the activities per team. We want to capture how active each
team member is based on their actions within that specific team. We can
use those activities to score each member and share the top active users
to team. Potentially we could also consider out to other services like
SharePoint as they might be active on files rather than using the chat
functionality. Given that we want to identify those users within a
timeframe the script should be able to handle activity within a
timeslot.

## Available metrics

The CLI for Microsoft offers a range of commands to work with teams,
channels, and the data within Teams. As well as information for other
services. So, the first step is to identify what data we need. For demo
purposes we start with the following:

1.  Retrieve a single team
2.  Retrieve all channels
3.  Retrieve messages within a timeframe
4.  Get all Likes & replies, and of course likes per reply as well

If we do have that information, we score each interaction and group the
results per team member. We can even add additional points if the
initial post has a subject to promote the use of best practices in
working with Teams. Once we have all that information, we can post to
Teams using an adaptive card.

## Microsoft 365 CLI Commands

Interacting with the CLI for Microsoft will be done using a set of basic
commands:

-   m365 teams channel list to list all teams channels
-   m365 teams message list to list all messages within a channel. We
    will use a filter to get only messages in our desired time frame.
-   m365 teams message reply list to list all replies per message as the
    the message list or message get do not provide you the reply list.
-   m365 aad user get to get the display name for each user.
-   m365 adaptivecard send to send our results to Teams and present a
    score card for all team members.

## The scripts

The script itself list all channels, loops through those channels and
retrieves all replies. It constructs a new object that saves the UserID
and per message type some additional details. Once that information is
processed the results are group per user and sorted by the scores. Those
results are then posted to Teams using an adaptive card.
For scoring the scenario uses the following 'ranking':

-   Each new posts is worth 2 points.
-   Each new post with a subject scores an additional 1 pointer.
-   Each reply counts as 1 point.
-   Each reaction (using the :thumbs_up: or ♥ icons) scores 0.5 points.

You can tweak those scores yourself if you like on line 77 to 80. Future
samples might add SharePoint interactions as well.
 
 
```bash
$teamId = "<PUTYOURTEAMIDHERE>"
$webhookUrl = "<PUTYOURURLHERE>"
# You can get a delta of messages since the last 'n' days. Currently set to seven. You can go back a maximum of 8 months.
$date = (get-date).AddDays(-7).ToString("yyyy-MM-ddTHH:mm:ssZ")

$channels = m365 teams channel list --teamId $teamId --output json | ConvertFrom-Json
$results = @()
$scoreResults = @()

$channelCounter = 0;

foreach ($channel in $channels) {

    $channelCounter++;
    Write-Output "Processing channel... $channelCounter/$($channels.Length)"

    $messages = m365 teams message list --teamId $teamId --channelId $channel.id --since $date --output json | ConvertFrom-Json

    $messageCounter = 0;

    foreach ($message in $messages) {
        $messageCounter++
        Write-Output "Processing message ... $messageCounter/$($messages.Length)"

        # Skip messages that are created with an application (bots / adaptive cards)
        if ($null -ne $message.from.user.id) {
            $results += [pscustomobject][ordered]@{
                Type       = "Post"
                Details    = $message.reactionType
                UserId     = $message.from.user.id
                HasSubject = $($null -ne $message.subject)
            }
        }

        # Process all likes and comments on the initial message
        foreach ($reaction in $message.reactions) {
            $results += [pscustomobject][ordered]@{
                Type    = "Reaction"
                Details = $reaction.reactionType
                UserId  = $reaction.user.user.id
            }
        }

        $replies = m365 teams message reply list --teamId $teamId --channelId $channel.id --messageId $message.Id --output json | ConvertFrom-Json

        foreach ($reply in $replies) {
            # Skip replies that are created with an application (bots)
            if ($null -ne $message.from.user.id) {
                $results += [pscustomobject][ordered]@{
                    Type   = "Reply"
                    UserId = $reply.from.user.id
                }
            }

            # Process all likes and comments on the reply message
            foreach ($reaction in $reply.reactions) {
                $results += [pscustomobject][ordered]@{
                    Type    = "Reaction"
                    Details = $reaction.reactionType
                    UserId  = $reaction.user.user.id
                }
            }

        }
    }
}

# Group the results per user
$resultsGrouped = $results | Group-Object -Property UserId

#Score per user
foreach ($teamsUser in $resultsGrouped) {
    $user = m365 aad user get --id $teamsUser.Name --output json | ConvertFrom-Json

    # Count points
    # Each  post is two points, 1 extra point awarded for each Post with Subject
    # Each reply 1 and each reaction 0.5
    $score = (($teamsUser.Group | Where-Object { $_.Type -eq "Post" }).Count * 2)
    $score += (($teamsUser.Group | Where-Object { $_.HasSubject }).Count)
    $score += ($teamsUser.Group | Where-Object { $_.Type -eq "Reply" }).Count
    $score += (($teamsUser.Group | Where-Object { $_.Type -eq "Reaction" }).Count / 2)

    $scoreResults += [pscustomobject][ordered]@{
        DisplayName       = $user.displayName
        UserPrincipalName = $user.userPrincipalName
        Score             = $score;
    }
}

# Sort our score report based on the score
$scoreResults = $scoreResults | Sort-Object { $_.score } -Descending

#Construct adaptive card
$title = "‌‌ Most active team members"
$scoreJson = '{   "title": "‌‌ '+$($scoreResults[0].DisplayName)+'",   "value": "' + $($scoreResults[0].score) + '"   }'

if($scoreResults[1]){
    $scoreJson += ',{   "title": "‌‌ '+$($scoreResults[1].DisplayName)+'",   "value": "' + $($scoreResults[1].score) + '"   }'
}
if($scoreResults[2]){
    $scoreJson += ',{   "title": "‌‌ '+$($scoreResults[2].DisplayName)+'",   "value": "' + $($scoreResults[2].score) + '"   }'
}

$card = '{ "type": "AdaptiveCard", "$schema": "http://adaptivecards.io/schemas/adaptive-card.json", "version": "1.2", "body": [  {  "type": "TextBlock",  "text": "' + $($title) + '",  "wrap": true,  "size": "Medium",  "weight": "Bolder",  "color": "Attention"  },  {  "type": "TextBlock",  "wrap": true,  "text": "Week ' + $(get-date -UFormat %V) + '",  "fontType": "Default",  "size": "Small",  "weight": "Lighter",  "isSubtle": true  },  {  "type": "FactSet",  "facts": [   ' + $scoreJson + '  ]  } ] }'

m365 adaptivecard send --url $webhookUrl --card $card
```
 

Executing the script will tell you the progress as it can take a while
to process all channels and messages depending the size of your team.

 

![team-champion-script.png](images/team-champion-script.png)

Once the script is finished you can expect an adaptive card showing the
score for that team. If no top 3 can be constructed it will only show
the top 1 or 2, and their score.
![team-champion-result.png](images/team-champion-result.png)

Hopefully this sample provides some insights in how you can track
activity and recognize the contributions team members make per team. I
love playing around with samples like this as its a great way to learn
the commands and see what value you can add based off data and
information already present in your Microsoft 365 tenant.
