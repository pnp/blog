---
title: "Export/Backup all your flows from an environment using the CLI for Microsoft 365"
date: 2021-11-08T04:16:00-05:00
author: "Patrick Lamber"
githubname: plamber
categories: ["CLI For Microsoft 365"]
tags: []
type: "regular"
---

When was the last time you backed up all the flows in your environment?

By combining the CLI for Microsoft 365 and PowerShell we can make this
task easy and repeatable.
 
This script will get all flows in your default environment and export
them as both a ZIP file for importing back into Power Automate and as a
JSON file for importing into Azure as an Azure Logic App. This post will
show you one of the most popular [sample
scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/flow/export-all-flows-in-environment/)
created  for the CLI for Microsoft 365. The original script was created
by our community member [Garry
Trinder.](https://twitter.com/garrytrinder)
 
```powershell
Write-Output "Getting environment info..."
$environment = m365 flow environment list --query '[?contains(displayName,`default`)] .name'
Write-Output "Getting Flows info..."
$flows = m365 flow list --environment $environment --asAdmin --output json | ConvertFrom-JSON
Write-Output "Found $($flows.Count) Flows to export..."
$flows | ForEach-Object {
    Write-Output "Exporting as ZIP & JSON... $($_.displayName)"
    $filename = $_.displayName.Replace(" ","")
    $timestamp = Get-Date -Format "yyyymmddhhmmss"
    $exportPath = "$($filename)_$($timestamp)"
    $flowId = $_.Name
    m365 flow export --id $flowId --environment $environment --packageDisplayName $_.displayName --path "$exportPath.zip"
    m365 flow export --id $flowId --environment $environment --format json --path "$exportPath.json"
}
Write-Output "Complete"
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
