
# Export Power Apps and Power Automate user licenses]

## Context 

During a Power Platform audit for a customer, I was looking for
exporting all user licenses data into a single file to analyze it with
Power BI. In this article, I'll show you the easy way to export Power
Apps and Power Automate user licenses with PowerShell!
 
## Download user licenses 

To do this, we are using [PowerApps
PowerShell](https://docs.microsoft.com/en-us/powershell/powerapps/overview)
and more particular, the Power Apps admin module.
 
To install this module, execute the following command as a
**local administrator**:
 
``` {.lia-code-sample .language-powershell}
Install-Module -Name Microsoft.PowerApps.Administration.PowerShell
```
 
**Note:** if this module is already installed on your machine, you can
use the
[Update-Module](https://docs.microsoft.com/en-us/powershell/module/powershellget/update-module)
command to update it to the latest version available.
 
Then to export user licenses data, you just need to execute the
following command and replace the target file path to use:
 
``` {.lia-code-sample .language-powershell}
Get-AdminPowerAppLicenses -OutputFilePath <PATH-TO-CSV-FILE>
```
 
**Note:** you will be prompted for your Microsoft 365 tenant
credentials, you need to sign-in as **Power Platform Administrator or
Global Administrator** to execute this command successfully.
 
After this, you can easily use the generated CSV file in Power BI
Desktop for further data analysis:
 
![power-platform-licenses.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/274789iE9950278D1A7DBFC/image-size/large?v=v2&px=999 "power-platform-licenses.png")


Happy reporting everyone!
 
You can read this article on my blog
[here](https://yhabersaat.ch/2021/04/18/get-power-apps-power-automate-user-licenses/).
 
## Resources 

<https://docs.microsoft.com/en-us/powershell/powerapps/get-started-powerapps-admin>
[https://docs.microsoft.com/en-us/powershell/module/microsoft.powerapps.administration.powershell/get\...](https://docs.microsoft.com/en-us/powershell/module/microsoft.powerapps.administration.powershell/get-adminpowerapplicenses)
