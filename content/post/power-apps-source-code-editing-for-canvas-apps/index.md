---
title: "Source code editing for Canvas Apps"
date: 2021-07-01T08:40:00-04:00
author: "Django Lohn"
githubname: m3ngi3
categories: ["Community post"]
images:
- images/PowerApps_Page_Unresponsive.png
tags: ["Power Apps"]
type: "regular"
---

## Why? 

Ever since I saw the post [Source code files for Canvas
apps](https://powerapps.microsoft.com/blog/source-code-files-for-canvas-apps/) from
Microsoft, I thought this might come in handy for some of my Canvas
Apps. As a non-coding Citizen Developer, I just thought that day would
be more in the future. A day when this feature would not be experimental
anymore but general available. 
One of my customers created a Power App with too many screens, too many
data sources and too many controls referencing each other. The result
was a Power Apps Studio with a *Page Unresponsive *error when when
opening specific screens:

![PowerApps_Page_Unresponsive](images/PowerApps_Page_Unresponsive.png)

This left us with no way to clean up the latest version of the Canvas
App through the Studio anymore

## What? 

This post adds information on how to edit Power Apps source code for
Canvas Apps. It will also show you that GitHub it is not per se needed.

## How? 

I still recommend to read the Microsoft post first. There is a lot of
potential in using GitHub as your code repository. There are also some
YouTube video's on how to perform most of the steps explained in further
detail. This post just focuses on how to use the tooling without a
GitHub setup.

**1)** First step is to download the .msapp file of your Canvas App. The
.msapp file is like a bundled package of multiple kind of files (.json,
.xml and .yaml), making up your whole Power App :woman_technologist:.

You can download your .msapp file by opening the Power App in the online
Studio. Then select **Save as** and select **This computer** as your
destination. A popup should appear that offers you to download the
.msapp file:\
![Save your .msapp file to a local destination](images/PowerApps_Studio_SaveAs.png)


![](images/PowerApps_ExportPackage.png)


2)  I then move the .msapp file to a folder within my Downloads
folder making the file path:

``` wp-block-code
C:\Users\DjangoLohn\Downloads\PowerApps-Language-Tooling-master\ConfigScreen.msapp
```

3) Make sure that you install the required .NET Core SDK version as
mentioned in the Microsoft post. Then download the Power Apps Language
Tooling locally to your Downloads folder:

![Download the Power Apps Language Tooling tool from GitHub locally](images/PowerApps_LanguageTooling_DownloadZIP.png)


Unzip this file and save the unzipped folder in a local place of your
computer. I chose to store it next to my .msapp file so the directories
would be near each other:

`C:\Users\DjangoLohn\Downloads\PowerApps-Language-Tooling-master`

4) Then just run the build.cmd file of the unzipped folder as
Administrator to be sure:

![Run the build.cmd as an Administrator](images/PowerApps_LanguageTooling_BuildCMD.png)


After a successful run, the bin folder will have a number of files in
the directory. The following path is the one to remember for



`C:\Users\DjangoLohn\Downloads\PowerApps-Language-Tooling-master\PowerApps-Language-Tooling-master\bin\Debug\PASopa`

Please note that your directory path may be different at the beginning,
but from the last \\PowerApps-Language-Tooling-master\\ section it
should be the same. The PASopa file is where the magic happens.

5) Now open the default Windows Command Prompt and Run as
adminisrator:

![CommanPromptAsAdministrator](images/CommanPromptAsAdministrator.png)


1) Have a folder prepared where you want to store the unpacked
.msapp files. I chose a folder next to the .msapp file again:

``` wp-block-code
C:\Users\DjangoLohn\Downloads\PowerApps-Language-Tooling-master\ConfigScreenSourceFiles
```

**7)** Change the directory path in the Command Prompt to the directory
where the PASopa file is located using this command

``` wp-block-code
cd C:\Users\DjangoLohn\Downloads\PowerApps-Language-Tooling-master\PowerApps-Language-Tooling-master\bin\Debug\PASopa
```


![](images/CommanPromptAsAdministrator_ChangeDirectory.png)


**8)** Execute the following command to unpack the .msapp files to the
desired folder:

```PowerShell
pasopa -unpack C:\Users\DjangoLohn\Downloads\PowerApps-Language-Tooling-master\ConfigScreen.msapp C:\Users\DjangoLohn\Downloads\PowerApps-Language-Tooling-master\ConfigScreenSourceFiles
```

Note that the first directory is that of the .msapp file. The second
directory is that of the folder where we want to unpack the separate
files. Warnings may occur because of checksums built in by the
developers. However in the end, the folder with the unpacked .msapp file
will have a default content structure:

![FileExplorer_Unpacked_msapp_File](images/FileExplorer_Unpacked_msapp_File.png)

With a tool like Notepad++ or my personal favorite Visual Studio Code,
you can edit the individual files. This is how you edit Power Apps
source code of Canvas Apps. I prefer Visual Studio Code because you can
open up a whole folder in one go:

![Visual Studio Code opening a whole Folder and Sub Folders to edit individual files](images/VisualStudioCode_Unpacked_msapp.png) 

1) Now you can remove frozen screens, rename controls in bulk,
update variables in bulk or any other action which in Power Apps Studio
would be a
hassle

When this is all done, you can just repack the files with a command
like:

```PowerShell
pasopa -pack  ConfigScreen.msapp C:\Users\DjangoLohn\Downloads\PowerApps-Language-Tooling-master\ConfigScreenSourceFiles 
```

If you are more observant than I was, you will have noticed that this
command does not give an output directory... so where did the new
repacked .msapp file go?? It gives you the new .msapp file in the PASopa
directory:

![FileExplorer_Repacked_msapp_Files](images/FileExplorer_Repacked_msapp_Files.png)

The repacked ZIP file can be imported in the online Studio. This import
will then update the existing Power App to a new version. Never thought
I would say this as if I know how to develop code but --> happy coding

[Originally published
at <https://knowhere365.space/power-apps-source-code-edit-for-canvas-apps/>
