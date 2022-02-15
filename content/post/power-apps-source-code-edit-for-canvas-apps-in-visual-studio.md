---
title: "Power Apps: source code edit for Canvas Apps in Visual Studio Code"
date: 2021-04-28T08:40:00-04:00
author: "Django Lohn"
categories: ["Power Apps", "Tooling"]
images:

tags: []
type: "regular"
draft: false

---

## Why?

In April, I showed how to unpack and repack Power Apps .msapp files of
Canvas Apps in the blog post [Power Apps Source Code file editing for
Canvas Apps
(microsoft.com)](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/power-apps-source-code-editing-for-canvas-apps/ba-p/2256476) Using
this functionality, we can view and edit the source code of Canvas Apps.
In a recent announcement ([Canvas source code tool integrated with Power
Platform CLI \| Microsoft Power
Apps](https://powerapps.microsoft.com/en-us/blog/canvas-source-code-tool-integrated-with-power-platform-cli/)),
Microsoft announced that the same functionalities are now available
within the Power Platform VS Code Extension of Visual Studio Code!

![PowerApps_VisualStudio_PowerPlatform_Extension](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/290863i14A33878984C6534/image-size/large?v=v2&px=999 "PowerApps_VisualStudio_PowerPlatform_Extension")

This means that after installing this extension, we can do the same
unpacking and packing without leaving Visual Studio Code.

## What?

This posts will show how easy it is to use Visual Studio Code so we can
unpack and (re)pack .msapp files of Canvas Apps:

![PowerApps_VisualStudio_PowerPlatform_Extension_msapp_compare](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/290864iD98446B52D0C5FCC/image-size/large?v=v2&px=999 "PowerApps_VisualStudio_PowerPlatform_Extension_msapp_compare")

## How?

1\) First install the Power Platform VS Code Extension in your Visual
Studio Code Client using the Visual Studio Marketplace ([Power Platform
VS Code Extension - Visual Studio
Marketplace](https://marketplace.visualstudio.com/items?itemName=microsoft-IsvExpTools.powerplatform-vscode)).

![PowerApps_VisualStudio_PowerPlatform_Extension_Installed](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/290865iCF5BD2477E301F09/image-size/large?v=v2&px=999 "PowerApps_VisualStudio_PowerPlatform_Extension_Installed")

2\) After installing the extension a computer restart may be required.
We can from this moment on, run commands from within Visual Studio using
the built-in Terminal.\
In my example I saved the text file with commands as a Power Shell file
(.ps1). In this type of files, short cuts like F8 can be used to run
selected commands:

![PowerApps_VisualStudio_PowerPlatform_Extension_run_command](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/290866i20403B3FDD20D31C/image-size/large?v=v2&px=999 "PowerApps_VisualStudio_PowerPlatform_Extension_run_command")

Notice the improved commands where referencing (input and output) files
is much easier now!

![PowerApps_VisualStudio_PowerPlatform_Extension_run_command_result](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/290867i4B95B843B1911155/image-size/large?v=v2&px=999 "PowerApps_VisualStudio_PowerPlatform_Extension_run_command_result")

In the Marketplace screenshot above, you can see that the extension is
in Preview at the moment.\
Please be aware of this and read the announcement link above on how to
report issues.
Originally published at [Power Apps: source code edit for Canvas Apps in
Visual Studio Code »
Knowhere365](https://knowhere365.space/power-apps-source-code-edit-for-canvas-apps-in-visual-studio-code/)
