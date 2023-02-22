---
title: "How to get Source Code files for Power Apps Canvas apps"
date: 2021-04-29T03:07:00-04:00
author: "Luise Freese"
githubname: LuiseFreese
categories: ["Community post"]
images:
- images/PASopa-folder.png
tags: ["Power Apps"]
type: "regular"
---

This post will guide you through the process of how to use the Power
Apps Language Toolkit to extract a Power Apps .msapp file. 

## Why would you want to have the source code files?  

To make your app reusable, so that more people can benefit from it, you
will want to share the source code files. Unfortunately, when you save
your Canvas App from Power Apps Studio, it is saved in one opaque .msapp
file. To be able to get the source files, you will need to use the Power
Apps Language Toolkit to extract all files from the .msapp file. This
way,

-   developers can not only open the source code in their code editor of
    choice but can effectively manage the code of a Canvas app in GitHub
    or Azure DevOps. This makes a huge difference as we can't look into
    .msapp files.
-   makers can still open the .msapp file to easily import an app sample
    into their environment

## Prerequisites 

To be able to use the Power Apps Language Toolkit, you will need to

-   install [Visual Studio Code](https://code.visualstudio.com) 
-   install [.NET Core 3.1.x
    (x64)](https://dotnet.microsoft.com/download/dotnet-core/3.1) 
-   download the Power Apps Language Toolkit
    -   go to
        [github.com/microsoft/PowerApps-Language-Tooling](https://github.com/microsoft/PowerApps-Language-Tooling) 
    -   select **Code**
    -   select **Download ZIP**
-    extract the Power Apps Language Toolkit to a local folder
-    open that local folder
-   locate the build.cmd file
-   rightclick, **Run as Administrator**
-   in the Pop up Window, select **more info**
-   select **Run anyway**

Please note, that command Prompt will open, show a few lines and then
close automatically again.
Please also not, that you can now find a **bin** folder in the local
folder you extracted the Power Apps Language Toolkit to. In this
**bin** folder, you will find a **Debug** folder and inside of the
**Debug** folder you will find a **PASopa** folder.
![PASopa-folder.png](images/PASopa-folder.png)

## **Download the .msapp file** 

-   go to <https://make.powerapps.com>)
-   log in
-   open your app in edit mode
-   select **File**
-   select **Save as**
-   select **This Computer**
-   select **Download**
-   move the downloaded .msapp file to your folder in which you
    extracted the Power Apps Language Toolkit as well

## unpack .msapp file 

-   Now that we have the .msapp file of the app:
-   press the WINDOWS key on your keyboard and search for **Command
    Prompt** (first few letters should do)
-   run as an Administrator
-   copy the path of the **PASopa** folder
-    type in Command Prompt \`cd \<your PASopa path>\`
-   copy the path of the .msapp file
-   create a new folder in your app folder
-   copy the path of that new folder
-   type in Command Prompt \`pasopa -unpack \<your msappfile path> \<new
    folder path>\`

Please note that you will now find all source code files in that new
folder. You can open the folder in a code Editor of your choice, for
example Visual Studio Code.

## submit as a sample 

Well done! If you like to contribute with your app to the [PnP Power
Apps sample gallery](https://pnp.github.io/powerplatform-samples/) , you
can submit your app with these source code files here. To do so, follow
these steps: 
Now you can submit these source code files as a sample. Please

-   fork the [PnP PowerApps
    repository](https://github.com/pnp/powerapps-samples) 
-   commit your files
-   Pull Request by filling out the PR template
Please do not forget to provide as well a \`README.md\` file which
explains what your sample is about.

If this all sounds confusing to you and you are new on GitHub - you are
more than welcome to attend the [Sharing Is
Caring](https://pnp.github.io/sharing-is-caring) sessions, where we
guide you through using GitHub and making your first PR. 
*Sharing Is Caring*
