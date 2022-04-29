---
title: "PnP Batch versus Microsoft Graph Batch in PowerShell to add/delete 3k items"
date: 2021-09-13T08:40:00-04:00
author: "Reshmee Auckloo"
categories: ["Community post"]
images:

tags: ["PnP PowerShell", "Microsoft Graph"]
type: "regular"
---

Following on previous blog [PnP Batch Add or Delete items from very
large
list](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/pnp-batch-add-or-delete-items-from-very-large-list-i-e-more-than/ba-p/2739737)

and reading about the post [fastest way to create SharePoint List
Items](https://blog.mastykarz.nl/fastest-way-create-sharepoint-list-items/) by
Waldek Mastykarz, I decided to try using Microsoft Graph batch in
PowerShell. I found the article [Calling the Microsoft Graph with PnP
PowerShell](https://www.pkbullock.com/blog/2020/calling-the-microsoft-graph-with-pnp-powershell/)
by Paul Bullock useful to get started. Using PnP Batch with retry
mechanisms still took up to 4 hours to create 300k items and up to 8
hours to delete 300 k items. I thought [Microsoft
Graph](https://docs.microsoft.com/graph/throttling) can handle
huge volume of requests and could help with my scenario. Unfortunately,
at random intervals I was getting errors like 

\"Invoke-WebRequest : The underlying connection was closed: A connection
that was expected to be kept alive was closed by the server\"
![reshmeeauckloo_0-1631898450004.png](images/reshmeeauckloo_0-1631898450004.png)
and 
\"Invoke-webRequest : The remote server returned an error: (401)
Unauthorized\" 
![reshmeeauckloo_1-1631898461413.png](images/reshmeeauckloo_1-1631898461413.png)
I used a retry mechanism in case of failure to re-establish the
connection to continue the operation. To my dismay even if the script
completed looping the 300k times to either add or delete the items, not
all the 300k items were deleted or added compared to the script from
[PnP Batch Add or Delete items from very large
list](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/pnp-batch-add-or-delete-items-from-very-large-list-i-e-more-than/ba-p/2739737)
 making it impossible for me to do a fair comparison. I decided to do
the comparison on 3k items in both scenarios after trying decreasing
number of items, i.e. 200k, 100 k, 50 k and 10 k where the results were
not as expected with Microsoft Graph batch. For example I ran the script
to create 10k items in the SharePoint Online list but only around 4k
items were created despite the script completed successfully in around 2
minutes. 
Below is a screenshot of the results of running the script which resumed
the operation in case of errors like \"The underlying connection was
closed\".
![reshmeeauckloo_0-1631978767171.png](images/reshmeeauckloo_0-1631978767171.png)

Microsoft Graph batch script

```powershell
$action = Read-Host "Enter the action you want to perform, e.g. Add or Delete"
$siteUrl = "https://contoso.sharepoint.com/sites/Team1"
$listName = "TestDemo" 
$clientId = "00000000-0000-0000-0000-000000000000"
$thumbprint =  "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
#connect with application permissions
Connect-PnPOnline -ClientId $clientId  -Thumbprint $thumbprint -Tenant "contoso.onmicrosoft.com" -Url $siteUrl
write-host $("Start time " + (Get-Date)) 
$startTime = Get-Date
#site and list details
$siteID = (Get-PnPSite -Includes Id).Id
$listID = (Get-PnPList $listName).Id

$Total =  3000
$batchSize = 20
#bearer token for batch request
$token = Get-PnPGraphAccessToken

$Stoploop = $false
$Retrycount = 0 
$requests = @()
$header = @{ "Content-Type" = "application/json" }
do {
try {
if($action -eq "Add")
{   
   $lst = Get-PnPList -Identity $listName
    if($lst.ItemCount -lt $Total)
    {
      $startInc = $lst.ItemCount
      $itemsCountToCreate = $Total - $startInc
      for($i=$startInc;$i -lt ($Total);$i++)
        {
            $request = @{
              id      = $i
              method  = "POST"
              url     = "/sites/$siteID/lists/$listID/items/"
              body = @{ fields = @{ Title = "Test $i" } }
              headers = $header
            } 
            $requests += $request
       if($requests.count -eq $batchSize -or $requests.count -eq $itemsCountToCreate)
       { 
         $batchRequests = @{
         requests = $requests
        }
        #IMPORTANT: use -Deph parameter
        $batchBody = $batchRequests | ConvertTo-Json -Depth 4
        #send batch request
        $response = Invoke-WebRequest -Method Post -Uri 'https://graph.microsoft.com/v1.0/$batch' -Headers @{Authorization = "Bearer $($token)" } -ContentType "application/json" -Body $batchBody -ErrorAction Stop
        $StatusCode = $Response.StatusCode
       # This will only execute if the Invoke-WebRequest is successful.  
         #write-host $("$StatusCode response for adding 20")
         #reset batch item counter and requests array
         $requests = @()
         $itemsCountToCreate = $itemsCountToCreate - $batchSize
         }
        }
       }
    $lst = Get-PnPList -Identity $listName
    $Stoploop = $true   
}

if($action -eq "Delete")
{
   $requests = @()
   $listItems= Get-PnPListItem -List $listName -Fields "ID" -PageSize 1000  
   $itemCount = $listItems.Count
   for($i=$itemCount-1;$i -ge 0;$i--)
    {
          $itemId = $listItems[$i].Id 
            $request = @{
              id      = $i
              method  = "DELETE"
              url     = "/sites/$siteID/lists/$listID/items/$itemId"
              headers = $header
              }          
            $requests += $request 
       if($requests.count -eq $batchSize -or $requests.count -eq $itemCount)
       { 
          $batchRequests = @{
          requests = $requests
       }
         
        #IMPORTANT: use -Deph parameter
        $batchBody = $batchRequests | ConvertTo-Json -Depth 4
        #send batch request
        $response = Invoke-WebRequest -Method Post -Uri 'https://graph.microsoft.com/v1.0/$batch' -Headers @{Authorization = "Bearer $($token)" } -ContentType "application/json" -Body $batchBody
         #$StatusCode = $Response.StatusCode
       
         #write-host $("$StatusCode response for deleting 20")
         #reset batch item counter and requests array
         $requests = @()
         $itemCount = $itemCount - $batchSize
        }
      }
   }
 $Stoploop = $true
}
catch {
  if ($Retrycount -gt 3){
    Write-Host "Could not send Information after 3 retrys."
    $Stoploop = $true
}
else {
  Write-Host "Could not send Information retrying in 30 seconds..."
  write-host $("Time error happened " + (Get-Date)) 
  Write-host $("$_.Exception.Message") -ForegroundColor Red
  Start-Sleep -Seconds 30
   Connect-PnPOnline -ClientId $clientId -Thumbprint $thumbprint -Tenant "contoso.onmicrosoft.com" -Url $siteUrl
   $token = Get-PnPGraphAccessToken
   $Retrycount = $Retrycount + 1
  }
 }
}
While ($Stoploop -eq $false) 
$endTime = Get-Date
$totalTime = $endTime - $startTime
write-host "Total script run time: $($totalTime.Hours) hours, $($totalTime.Minutes) minutes, $($totalTime.Seconds) seconds" -ForegroundColor Cyan
```
 
 

PnP batch script
 

```powershell
$action = Read-Host "Enter the action you want to perform, e.g. Add or Delete"
$siteUrl = "https://contoso.sharepoint.com/sites/Team1"
$listName = "TestDemo" 
$ErrorActionPreference="Stop"
Connect-PnPOnline –Url $siteUrl -interactive
$Total =  30000
$Stoploop = $false

[int]$Retrycount = "0"

write-host $("Start time " + (Get-Date))
$startTime = Get-Date
do {
try {

if($action -eq "Add")
{   
  $lst = Get-PnPList -Identity $listName  
    if($lst.ItemCount -lt $Total)
    {
       $startInc = $lst.ItemCount
       while($lst.ItemCount -lt $Total)
       {    
        $batch = New-PnPBatch
        #perform in increment of 1000 until 300k is reached 
        if($startInc+1000 -gt $Total)
        {
         $endNu = $Total
        } 
        else
        {
         $endNu = $startInc+1000
        }
        for($i=$startInc;$i -lt ($endNu);$i++)
        {
           Add-PnPListItem -List $listName -Values @{"Title"="Test $i"} -Batch $batch
        }
        Invoke-PnPBatch -Batch $batch
         $lst = Get-PnPList -Identity $listName
       }
    }
}

if($action -eq "Delete")
{
 $listItems= Get-PnPListItem -List $listName -Fields "ID" -PageSize 1000  
 $itemIds = $lisItems | Foreach {$_.Id}
 $itemCount = $listItems.Count
 while($itemCount -gt 0)
 {
    $batch = New-PnPBatch
    #delete in batches of 1000, if itemcount is less than 1000 , all will be deleted 
    if($itemCount -lt 1000)
    {
     $noDeletions = 0
    }
    else
    {
     $noDeletions = $itemCount -1000
    }

    for($i=$itemCount-1;$i -ge $noDeletions;$i--)
    {
        Remove-PnPListItem -List $listName -Identity $listItems[$i].Id -Batch $batch 
    }
    Invoke-PnPBatch -Batch $batch
    $itemCount = $itemCount-1000
  }
}
 Write-Host "Job completed"
 $Stoploop = $true
}
catch {
if ($Retrycount -gt 3){
Write-Host "Could not send Information after 3 retrys."
$Stoploop = $true

}

else {
  Write-Host "Could not send Information retrying in 30 seconds..."
  Start-Sleep -Seconds 30
  Connect-PnPOnline –Url $siteUrl -interactive
  $Retrycount = $Retrycount + 1
  }
 }
}
While ($Stoploop -eq $false)
write-host $("End time " + (Get-Date))

$endTime = Get-Date
$totalTime = $endTime - $startTime
 
write-host "Total script run time: $($totalTime.Hours) hours, $($totalTime.Minutes) minutes, $($totalTime.Seconds) seconds" -ForegroundColor Cyan
```
 

I have run the scripts using Microsoft Graph batch and PnP Batch 3 times
to add and delete 3k items and below are the results.

![table](images/table.png)

Microsoft Graph batch is faster to add and delete than PnP batch for 3k
items.

However for a very large number of items, i.e. more than 10 k the
results can be sporadic with Microsoft Graph batch unless I added a
delay of few seconds after each batch operation which makes it less
performant than using PnP batch.
