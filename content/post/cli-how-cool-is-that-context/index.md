---
title: "CLI for Microsoft 365 - how cool is that? - Context"
date: 2023-02-27T02:44:24+06:00
# post thumb
images:
  - images/main.png
#author
author: "Adam Wójcik"
githubname: Adam-it
# description
description: "CLI for Microsoft 365 is a cross platform command line tool based on Node.js that helps you manage many things around Microsoft 365 and your SPFx project (yes, that as well 🤩. rename, upgrade ... you name it). You may manage OneDrive, Planner, Power Apps and Automate, Teams, Yammer, SharePoint (of course). The list keeps on growing and growing. Lets check some tips and tricks which may improve your experience with CLI for Microsoft 365."
summary: "CLI for Microsoft 365 is a cross platform command line tool based on Node.js that helps you manage many things around Microsoft 365 and your SPFx project (yes, that as well 🤩. rename, upgrade ... you name it). You may manage OneDrive, Planner, Power Apps and Automate, Teams, Yammer, SharePoint (of course). The list keeps on growing and growing. Lets check some tips and tricks which may improve your experience with CLI for Microsoft 365."
# Taxonomies
categories: ["Community post"]
tags: ["CLI for Microsoft 365"]
type: "regular" 
---

Are you regularly using CLI for Microsoft 365 and looking for a way to be more productive? Or is this totally new for you and you are looking for something 'special' which will make CLI for M365 stand out when compared with other command line tools? Well, you are in the right place. Did you ever write a script using a bunch of different commands and for each you passed almost always the same options? Or you maybe had some scripts which you just needed to execute in a loop providing different set of options every time? Or you just needed some 'place' to keep all of your options in single place to create a kind of a context. Well CLI for Micorosft 365 now has exactly that 🤩.

## 🤔 But first of all what is CLI for Microsoft 365? Quick intro

If your already know what CLI for M365 is then I suppose you may skip this part😀. CLI for Microsoft 365 is a cross platform command line tool based on Node.js that helps you manage many things around Microsoft 365 and your SPFx project (yes, that as well 🤩. rename, upgrade ... you name it). To name a few, you may manage OneDrive, Planner, Power Apps and Automate, Teams, Yammer, SharePoint (of course). The list keeps on growing and growing, [check out the CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/). But it's not only about managing Microsoft 365. The CLI helps you also manage your own SPFx environment (check out the [doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor/)) or projects (rename, upgrade etc.). This is very unique that many similar command line tools don't have. Some commands do simple things but some actually are ready to use scenarios all done under a single command. Check out the full list of [commands](https://pnp.github.io/cli-microsoft365/cmd/login/#usage)

## 💡 What is it all about?

Remember when you executed a couple of CLI for Microsoft 365 commands one after another and almost every time you passed the same options. The same site url, file, folder relative path, list title ect ect. Wouldn't it be great if you could just keep all options related to your current work or SharePoint site, or current planner plan, or whatever you may imagine 🧠 in a single place? Well, now it is possible. The CLI for Microsoft 365 context gives you the possibility to save any kind of option and its value and then before any command is executed the CLI for Microsoft 365 will first check if any option of the current command may be populated based on what you currently have in the context. Cool right 😎?

## 👉 How to get started?

Before we start adding anything to the context we may first insure it is created using the following command:

```powershell
m365 context init
```

This will create a file `.m365rc.json` in the current location, with a `context` section in it, yep this is the same file used by the `m365 aad app` commands that will store your app registration ID and name when `--save` option will be used.

At the begining the context will be empty so, of course, what we want to do first is adding (saving) new options in it. This is may be done by using the `context option set` command. For example:

```powershell
m365 context option set --name 'listTitle' --value 'issue list'
```

From that moment on every command you will execute that has the `--listTitle` option, for which you did not provide any value, will be automatically filled with the value saved in the context. If you do however execute some command providing the list title, then the context will not overwrite the given value. In other words, the provided options inline with the commands will have higher priority than those saved in the context file. So now when we would execute:

```powershell
m365 spo listitem list --webUrl "https://contoso.sharepoint.com/sites/sales"
```

Instead of getting a failure (which should as we did not provide any option to identify the list, like `--listTitle`), we will get all list items from list 'issue list' from the 'sites/sales' site.


## ⚙️ How does it work?



For more details check the [guidance provided in the CLI for Micorosft 365 docs](URL)

## 🙋 Wanna help out?

CLI for Microsoft 365 is a great tool to use and also great place to learn git best practices, how to use SharePoint or MS Graph or other APIs. We are constantly improving and are always opened for any contributions that want to help out 💪. Don't worry if you don't know how to start or what you could do. Just check out the [contributing guide](https://github.com/pnp/cli-microsoft365/blob/main/CONTRIBUTING.md) and [issues list](https://github.com/pnp/cli-microsoft365/issues) and give it a shot. If I still didn't convince you, check out the the [7 reasons to contribute to the community](https://pnp.github.io/blog/post/7-reasons-to-contribute-to-the-community/) by [Martin Lingstuyl](https://github.com/martinlingstuyl/). I will be waiting for your PRs. Let me know if you need any help to start 👍
