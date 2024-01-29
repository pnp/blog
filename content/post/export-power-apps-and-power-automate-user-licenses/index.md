---
title: "Export Power Apps and Power Automate user licenses"
date: 2021-04-23T05:48:00-04:00
author: "Yves Habersaat"
githubname: yhabersaat
categories: ["Community post"]
images:
- images/power-platform-licenses.png
tags: ["Power Apps", "Power Automate"]
type: "regular"
---

## Context

During a Power Platform audit for a customer, I was looking for
exporting all user licenses data into a single file to analyze it with
Power BI. In this article, I'll show you the easy way to export Power
Apps and Power Automate user licenses with PowerShell!
 
## Download user licenses

To do this, we are using [PowerApps
PowerShell](https://learn.microsoft.com/powershell/powerapps/overview)
and more particular, the Power Apps admin module.
 
To install this module, execute the following command as a
**local administrator**:
 
```powershell
Install-Module -Name Microsoft.PowerApps.Administration.PowerShell
```
 
**Note:** if this module is already installed on your machine, you can
use the
[Update-Module](https://learn.microsoft.com/powershell/module/powershellget/update-module)
command to update it to the latest version available.
 
Then to export user licenses data, you just need to execute the
following command and replace the target file path to use:
 
```powershell
Get-AdminPowerAppLicenses -OutputFilePath <PATH-TO-CSV-FILE>
```
 
**Note:** you will be prompted for your Microsoft 365 tenant
credentials, you need to sign-in as **Power Platform Administrator or
Global Administrator** to execute this command successfully.
 
After this, you can easily use the generated CSV file in Power BI
Desktop for further data analysis:
 
![power-platform-licenses.png](images/power-platform-licenses.png)


Happy reporting everyone!
 
You can read this article [on my blog](https://yhabersaat.ch/2021/04/18/get-power-apps-power-automate-user-licenses/).
 

## Resources

<https://learn.microsoft.com/powershell/powerapps/get-started-powerapps-admin>
[https://learn.microsoft.com/powershell/module/microsoft.powerapps.administration.powershell/get-adminpowerapplicenses](https://learn.microsoft.com/powershell/module/microsoft.powerapps.administration.powershell/get-adminpowerapplicenses)
