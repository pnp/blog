---
title: "How to use oh-my-posh with PnPPowerShell"
date: 2022-04-14T09:08:00-05:00
author: "Luise Freese"
githubname:  luisefreese
categories: ["Community post"]
images:
- images/oh-my-posh.png
tags: ["PnP PowerShell", "SharePoint"]
type: "regular"
draft: false
---

## What is oh my posh?

[Oh-my-posh](https://ohmyposh.dev/) is an amazing prompt engine that does not only pretty up the terminal you use, but it will ease your work. By using an [established theme](https://ohmyposh.dev/docs/themes) or creating a new one, you get important information directly in the context of your work, highlighted in the way that works best for you. For example:

* In which repository am I working in?
* Which branch?
* When did I execute a command?
* On which node.js version am I working?

### the M365Princess theme by Luise plus environment variables by Anoop

Making good things even better: A while ago, [Luise](https://twitter.com/LuiseFreese) created her own theme and now [Anoop](https://twitter.com/anooptells) had the idea to level it up:

When interacting with Microsoft 365, most of the times we use the Microsoft 365 platform community driven PowerShell module called [**PnP PowerShell**](https://pnp.github.io/powershell/). One of the first commands we execute while using PnP PowerShell, is `Connect-PnPOnline` to connect to a SharePoint site. We can now see right in the terminal which SharePoint site we are connected to and which Microsoft 365 tenant the SharePoint site lives in.

These are displayed with the help of a couple of environment variables that are set by PnP PowerShell after running the `Connect-PnPOnline` command.

In the preview below, the connected SharePoint site is  `/sites/yoursite` which is in the tenant named `yourtenant.sharepoint.com`

![oh my posh M365Princess theme PnP](images/oh-my-posh.png)

The original idea to show these values comes from [Erwin van Hunen](https://twitter.com/erwinvnhunen), the father of PnP PowerShell.

## How to install oh-my-posh and the theme

To have this experience in Visual Studio Code, complete the following steps:

1. Install oh-my-posh and posh-git
   - Open the the terminal and run
        - `winget install JanDeDobbeleer.OhMyPosh --scope user`
        - `Install-Module posh-git -Scope CurrentUser`

      > If you are unable to use `winget` then please install oh-my-posh using the `install-amd64.exe` file under the oh-my-posh reopsitory's [latest release](https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest).

2. Edit your PowerShell profile in VS Code
   - Open it with `code $PROFILE`
   - Insert this:

```ps1
Import-Module posh-git
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\M365Princess.omp.json" | Invoke-Expression
```

3. Install a font
   - Download a font of your choice from [Nerdfonts](https://www.nerdfonts.com/font-downloads)
   - Install a monospace version of that font
   - Open settings in VS Code with CTRL + SHIFT + P and select **Preferences: Open settings (JSON)**
   - Add (for example) `"terminal.integrated.fontFamily": "CaskaydiaCove Nerd Font"`
   - Save settings and restart VS Code

## How does the site information get displayed

oh-my-posh has the capability to display environment variables in the prompt. We use this capability to show the site information.

When we run the `Connect-PnPOnline` cmdlet, a couple of environment variables are set. They are `PNPPSHOST` and `PNPPSSITE`. This can be seen in the PnP PowerShell code [here](https://github.com/pnp/powershell/blob/dev/src/Commands/Base/ConnectOnline.cs#L305). `PNPPSHOST` contains the host name e.g. `yourtenant.sharepoint.com` and `PNPPSSITE` contains the URL of the connected site e.g. `yoursite.sharepoint.com`.

To display environment variables in an oh-my-posh theme we need to use the syntax `{{ .Env.variablename }}`.

In the oh-my-posh M365Princess theme, we are displaying the values of `PNPPSHOST` and `PNPPSSITE` using `{{ .Env.PNPPSHOST }}` and `{{ .Env.PNPPSSITE }}`. The same be seen in the following lines of the code for theme:
   - [Displaying the host name](https://github.com/JanDeDobbeleer/oh-my-posh/blob/main/themes/M365Princess.omp.json#L13)
   - [Displaying the site URL](https://github.com/JanDeDobbeleer/oh-my-posh/blob/main/themes/M365Princess.omp.json#L21)

The above lines of code check if the corresponding variables have a value and if they do then, the value is shown.

These values can be shown in any other oh-my-posh theme if needed. To customise any other on-my-posh theme, please follow the guide [here](https://ohmyposh.dev/docs/installation/customize). As part of the customisation, the block between lines [4](https://github.com/JanDeDobbeleer/oh-my-posh/blob/main/themes/M365Princess.omp.json#L4) and [33](https://github.com/JanDeDobbeleer/oh-my-posh/blob/main/themes/M365Princess.omp.json#L33) of the M365Princess theme to the custom theme.

### Slow prompt?

In case the prompt is responding slow on Windows OS, then one of the reasons might be the oh-my-posh process being blocked by Windows defender. To overcome that, please run PowerShell with elevated permissions (Run as administrator) and execute the following command:

```ps1
Add-MpPreference -ExclusionProcess "oh-my-posh.exe"
```

If that doesn't solve the problem then, execute the following command

```ps1
Add-MpPreference -ExclusionPath "$env:POSH_PATH\oh-my-posh.exe"
```

For more information see the comments [this issue](https://github.com/JanDeDobbeleer/oh-my-posh/issues/1904).

## Conclusion

It's the little things! Of course this is just one puzzle tile, but better overview, crucial information presented in a minimal but nerdy and compelling way helps people to ease their workloads. When working with PnP PowerShell, it's a game changer to know to which of your tenants and sites you are connected to.

If you like the oh-my-posh and can afford it, go buy Jan, who builds and maintains this awesome open source project, a coffee ☕: [oh-my-posh repository](https://github.com/JanDeDobbeleer/oh-my-posh)

*sharing is caring*

*This post was written by Luise Freese and Anoop Tatti - we are working on having a co-author field.*

