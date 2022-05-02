---
title: "PnP Batch Add or Delete items from very large list, i.e. more than 300k items"
date: 2021-09-13T08:40:00-04:00
author: "Reshmee Auckloo"
categories: ["Community post"]
images:

tags: ["PnP PowerShell"]
type: "regular"
---

I was tasked to delete more than 300k items loaded as part of testing
from a very large SharePoint list, I used the script from the blog
post <https://vladilen.com/office-365/spo/fastest-way-to-delete-all-items-in-a-large-list/> describing
the difference of speed using batches, scriptblock and without batches.
The conclusion was batches and scriptblock were equally fast and faster
than without the use of batches. 

``` wp-block-preformatted
Get-PnPListItem -List $list -Fields "ID" -PageSize 100 -ScriptBlock { Param($items) $items | Sort-Object -Property Id -Descending | ForEach-Object{ $_.DeleteObject() } } 
```

Unfortunately the script kept producing errors like "The collection has
not been initialised" , "A task has been canceled" or "The operation
has timed out" at irregular intervals and had to manually restart the
script to resume deletion of remaining items.
 
``` {.lia-code-sample .language-applescript}
$action = Read-Host "Enter the action you want to perform, e.g. Add or Delete"
$siteUrl = "https://contoso.sharepoint.com/sites/Team1"
$listName = "TestDemo" 
$ErrorActionPreference="Stop"
Connect-PnPOnline –Url $siteUrl -interactive
$Stoploop = $false
[int]$Retrycount = "0"

write-host $("Start time " + (Get-Date))
do {
try {
if($action -eq "Add")
{   
  $lst = Get-PnPList -Identity $listName   
    if($lst.ItemCount -lt 300000)
    {
       $startInc = $lst.ItemCount
       while($lst.ItemCount -lt 300000)
       {    
         $batch = New-PnPBatch
        #perform in increment of 1000 until 300k is reached 
        if($startInc+1000 -gt 300000)
        {
         $endNu = 300000
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

```

The script took up to 4 hours to add 300k items. The script resumed
despite an error happening. 

![reshmeeauckloo_0-1631278209238.png](images/reshmeeauckloo_0-1631278209238.png)

The script took 7.5 hours to delete 300k items with a couple of
retries.  

![reshmeeauckloo_2-1631278372706.png](images/reshmeeauckloo_2-1631278372706.png)

