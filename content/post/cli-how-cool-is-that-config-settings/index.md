---
title: "CLI for Microsoft 365 - how cool is that? - Configuring settings"
date: 2022-08-21T02:44:24+06:00
# post thumb
images:
  - images/main.png
#author
author: "Adam Wójcik"
githubname: Adam-it
# description
description: "CLI for Microsoft 365 is a cross platform command line tool based on Node.js that helps you manage many things around Microsoft 365 and your SPFx project (yes, that as well 🤩. rename, upgrade ... you name it). You may manage OneDrive, Planner, Power Apps and Automate, Teams, Yammer, SharePoint (of course). The list keeps on growing and growing. Lets check CLI for Microsoft 365 settings and how to configure them."
summary: "CLI for Microsoft 365 is a cross platform command line tool based on Node.js that helps you manage many things around Microsoft 365 and your SPFx project (yes, that as well 🤩. rename, upgrade ... you name it). You may manage OneDrive, Planner, Power Apps and Automate, Teams, Yammer, SharePoint (of course). The list keeps on growing and growing. Lets check CLI for Microsoft 365 settings and how to configure them."
# Taxonomies
categories: ["Community post"]
tags: ["CLI for Microsoft 365"]
type: "regular" 
---

## 🤔 But first of all what is CLI for Microsoft 365? Quick intro 

If your already know what CLI for M365 is then I suppose you may skip this part😀. CLI for Microsoft 365 is a cross platform command line tool based on Node.js that helps you manage many things around Microsoft 365 and your SPFx project (yes, that as well 🤩. rename, upgrade ... you name it). To name a few, you may manage OneDrive, Planner, Power Apps and Automate, Teams, Yammer, SharePoint (of course). The list keeps on growing and growing, [check out the CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/). But it's not only about managing Microsoft 365. The CLI helps you also manage your own SPFx environment (check out the [doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor/)) or projects (rename, upgrade etc.). This is very unique that many similar command line tools don't have. Some commands do simple things but some actually are ready to use scenarios all done under a single command. Check out the full list of [commands](https://pnp.github.io/cli-microsoft365/cmd/login/#usage)


## ⚙️ Configure CLI for Microsoft 365 for the way you need

Did you know that you can configure CLI for Microsoft 365 in a few different ways? Thats right, CLI gives you the opportunity to adjust the way it will behave to meet your personalized needs or specific scenario. 

Ok, so where is that config.json file I need to modify to change the settings? Well, at start there is non 😅, and it's not the way we should actually modify CLI settings. Instead there are ready to use `m365 cli config` commands which will help you configure CLI for Microsoft 365 properly. We have three commands which will allow us to modify CLI settings: `get`, `set` and `reset`. Let's check them out. 

The first one is `m365 cli config get` command, which will show you the specified setting. For example we may check what is the default output format for a command:

```sh
m365 cli config get --key output
```

If the output of the above command is empty then it means that the setting was not changed and the default is used. CLI provides the following settings along with it's default values: 

Setting name | Definition | Default value
-------------|------------|--------------
autoOpenBrowserOnLogin | Automatically open the browser to the Azure AD login page after running m365 login command in device code mode. This setting will be replaced by autoOpenLinksInBrowser in the next major release. | false
autoOpenLinksInBrowser | Automatically open the browser for all commands which return a url and expect the user to copy paste this to the browser. For example when logging in, using m365 login in device code mode. This setting will replace autoOpenBrowserOnLogin in the next major release. | false
copyDeviceCodeToClipboard | Automatically copy the device code to the clipboard when running m365 login command in device code mode | false
csvEscape | Single character used for escaping; only apply to characters matching the quote and the escape options | "
csvHeader | Display the column names on the first line | true
csvQuote | The quote characters surrounding a field. An empty quote value will preserve the original field, whether it contains quotation marks or not. | 
csvQuoted | Quote all the non-empty fields even if not required | false
csvQuotedEmpty | Quote empty strings and overrides quoted_string on empty strings when defined | false
errorOutput | Defines if errors should be written to stdout or stderr | stderr
output | Defines the default output when issuing a command | json
printErrorsAsPlainText | When output mode is set to json, print error messages as plain-text rather than JSON | true
prompt | Prompts for missing values in required options | false
showHelpOnFailure | Automatically display help when executing a command failed | true

In order to change some config, lets say the command output format, we may just use:

```sh
m365 cli config set --key output --value text
```

Now we changed the default output format for every CLI command from `json` to `text`.

So we changed something, it got saved, but where? Well, the answer is, as always, it depends 😉. The moment we change some default setting a new cli-m365-config.json file is created and it's location depends from the OS we are using. On Windows the config file may be found in folder 'C:\Users\\<YouUserHere\>\\.config\configstore\' and for macOS it's '/Users/\<YouUserHere\>/.config/configstore'. 

If we play to much with the setting and we would like to revet back to the default state we may use the `m365 cli config reset` command.

For more information of course you may check [CLI for Microsoft 365 docs configuration page](https://pnp.github.io/cli-microsoft365/user-guide/configuring-cli/). Everything is always in the docs, but instead you may follow along this article and let me guide you through each setting in a bit more detail and (I hope) funny way 😉, as work and knowledge should always be a bit of fun 👍. 

## ✂️ AutoOpen & autoCopy

Remember when first time you ran `m365 login` command and you had to copy past the url and the code to authenticate? CLI provides config setting which will improve and speed up that process. 

First lets set:

```sh
m365 cli config set --key autoOpenBrowserOnLogin --value true
```

Which will automatically open the login page in your default browser after running the `m365 login` command. Now lets set:

```sh
m365 cli config set --key copyDeviceCodeToClipboard --value true
```

By setting that your autogenerated device code used for login will be automatically copied to the clipboard. 

How cool is that 😎? If only there was a setting which will the the full login for you right 😜.
 
👉 One thing that is important to mention is that we have a similar setting `autoOpenLinksInBrowser` which will open any url output from command in browser, not only the login url. This setting for example might be useful for the `m365 app open` command to automatically open the link to the Azure Portal in the browser from the .m365rc.json file for our current app. Even more worth mentioning is that setting `autoOpenBrowserOnLogin` will be removed in the next major release (v6) and replaced by `autoOpenLinksInBrowser`. For more info please check the related issue [Remove the setting autoOpenBrowserOnLogin to follow new settings autoOpenLinksInBrowser](https://github.com/pnp/cli-microsoft365/issues/3163)

## 📅 Csv master

## 🐞 Error handling

## 📎 Don't mis that required option ever again

Ever executed some command and forgot to specify that required option and got the help response together with the failure message? No ... WoW😮... well I did (and I still do 😅), lucky for me, there as a CLI config property we may set which will help me not to forget about that required option ever again 😉. When setting `prompt` to `true` CLI will ask for missing values for required options before executing a command. I know, pretty sweet 😎.

![m365 command options prompt](images/prompt.png)

👉 One thing that is important to mention is that CLI for Microsoft 365 will not prompt for options where at least one is required. So for example in `m365 spo list get` command we may either use `--id` or `--title` to specify which list we want and we need to specify at least one of them. Currently CLI for Microsoft 365 will not prompt for neither of them and at the time of writing this article this feature is still open and waiting to be implemented.

## 🤷 Is that all? 

I hope this article explained everything you were looking regarding CLI for Microsoft 365 settings and now you will use them freely in order to adjust the CLI to you needs and your projects. If you haven't already, make sure you give [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) a try 👍

## 🙋 Wanna help out?

CLI for Microsoft 365 is a great tool to use and also great place to learn git best practices, how to use SharePoint or Graph or other APIs. We are constantly improving and are always opened for any contributions that want to help out 💪. Don't worry if you don't know how to start or what you could do. Just check out the [contributing guide](https://github.com/pnp/cli-microsoft365/blob/main/CONTRIBUTING.md) and [issues list](https://github.com/pnp/cli-microsoft365/issues) and give it a shot. If I still didn't convince you, check out the the [7 reasons to contribute to the community](https://pnp.github.io/blog/post/7-reasons-to-contribute-to-the-community/) by [Martin Lingstuyl](https://github.com/martinlingstuyl/). I will be waiting for your PRs. Let me know if you need any help to start 👍
