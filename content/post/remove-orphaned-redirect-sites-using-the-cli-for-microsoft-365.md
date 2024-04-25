---
title: "Remove orphaned redirect sites using the CLI for Microsoft 365"
date: 2021-11-18T02:20:00-05:00
author: "Patrick Lamber"
githubname: plamber
categories: ["CLI for Microsoft 365"]
images: []
tags: []
type: "regular"
---

Changing the URL of a site results in a new site type: a Redirect Site.
However this redirect site does not get removed if you delete the newly
renamed site. This could result in orphaned redirect site collections
that redirect to nothing. This script provides you with an overview of
all orphaned redirect sites and allows you to quickly delete them.
This post will show you one of the most popular [sample
scripts](https://pnp.github.io/cli-microsoft365/sample-scripts/spo/remove-orphaned-redirect-sites/)
created  for the CLI for Microsoft 365. The original script was created
by our community member [Albert-Jan
Schot.](https://www.cloudappie.nl/remove-orphaned-redirectsites/)

```powershell
$sites = m365 spo site classic list --t "REDIRECTSITE#0" --output json | ConvertFrom-Json

$sites | ForEach-Object {
  Write-Host -f Green "Processing redirect site: " $_.Url
  $siteUrl = $_.Url

  $redirectSite = Invoke-WebRequest -Uri $_.Url -MaximumRedirection 0 -SkipHttpErrorCheck
  $body = $null
  $siteUrl = $_.Url

  if($redirectSite.StatusCode -eq 308) {
    Try {
      [string]$newUrl = $redirectSite.Headers.Location;
      Write-Host -f Green " Redirects to: " $newUrl
      $body = Invoke-WebRequest -Uri $newUrl -SkipHttpErrorCheck
    }
    Catch{
    Write-Host $_.Exception
    }
    Finally {
      If($body.StatusCode -eq "200"){
      Write-host -f Yellow "  Target location still exists"
      }
      If($body.StatusCode -eq "404"){
        Write-Host -f Red "  Target location no longer exists, should be removed"
        m365 spo site remove --url $siteUrl
      }
    }
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
