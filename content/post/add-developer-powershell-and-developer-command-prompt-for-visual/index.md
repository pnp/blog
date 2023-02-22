---
title: "Add Developer PowerShell and Developer Command Prompt for Visual Studio to Windows Terminal"
date: 2021-03-29T01:29:00-04:00
author: "Yannick Reekmans"
githubname: YannickRe
categories: ["Community post"]
images:
- images/image.png

tags: ["PowerShell"]
type: "regular"
---

[Windows
Terminal](https://www.microsoft.com/p/windows-terminal/9n0dx20hk701)
is great, I use it for all my command line work. It automatically
detects new shells that are installed on your system, like the shell for
Ubuntu or PowerShell Core 7. Unfortunately, it doesn't detect the
Developer Command Prompt and Developer PowerShell for Visual Studio.
Luckily, you can add them yourself!

![image.png](images/image.png)

The steps are rather simple:

-   Open Windows Terminal
-   Open the Settings through the UI (see screenshot) or with Ctrl+,
-   In the `settings.json` file that opens in your favorite code editor,
    locate the `lists` array inside the `profiles` object

![image-1.png](images/image-1.png){

Inside that `lists` array, you can add your additional profiles. In this
case, for the Visual Studio command prompts, just use the following
snippet:

```json
            {
                "name": "Developer PowerShell for VS 2019",
                "commandline": "powershell.exe -noe -c "&{$vsPath = &(Join-Path ${env:ProgramFiles(x86)} '\\Microsoft Visual Studio\\Installer\\vswhere.exe') -property installationpath; Import-Module (Join-Path $vsPath 'Common7\\Tools\\Microsoft.VisualStudio.DevShell.dll'); Enter-VsDevShell -VsInstallPath $vsPath -SkipAutomaticLocation}"",
                "icon": "%ProgramFiles(x86)%\\Microsoft Visual Studio\\2019\\Enterprise\\Common7\\IDE\\Assets\\VisualStudio.70x70.contrast-standard_scale-180.png"
            },
            {
                "name": "Developer Command Prompt for VS 2019",
                "commandline": "%comspec%  /k "%ProgramFiles(x86)%\\Microsoft Visual Studio\\2019\\Enterprise\\Common7\\Tools\\VsDevCmd.bat"",
                "icon": "%ProgramFiles(x86)%\\Microsoft Visual Studio\\2019\\Enterprise\\Common7\\IDE\\Assets\\VisualStudio.70x70.contrast-standard_scale-180.png"
            },
```

Save the `settings.json` file, and now the new options show when opening
a new tab:

![image-2.png](images/image-2.png)

Time to do your Visual Studio command line work in the fancy new Windows
Terminal!
