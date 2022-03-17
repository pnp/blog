---
title: "CLI for Microsoft 365 on your mobile"
date: 2022-01-11T02:44:24+06:00
# post thumb
images:
  - "images/blog/cli-for-microsoft-365-on-your-mobile/Prezentacja1.png"
#author
author: "Adam Wójcik"
githubname: Adam-it
# description
description: "CLI for Microsoft 365 is a cross platform command line tool you may use to manage many things. To name a few, you may manage OneDrive, Planner, Power Apps and Automate, Teams, Yammer, SharePoint (of course), now there is even a dedicated command to help you set up Viva. The list keeps on growing and growing"
summary: "CLI for Microsoft 365 is a cross platform command line tool you may use to manage many things. To name a few, you may manage OneDrive, Planner, Power Apps and Automate, Teams, Yammer, SharePoint (of course), now there is even a dedicated command to help you set up Viva. The list keeps on growing and growing"
# Taxonomies
categories: ["Community post"]
tags: []
type: "regular" # available type (epic, trending, popular, or regular)

---
> *"Hey, do you have 5 min?"*\
> *"Could you check one simple thing and let me know asap?"*
>
> *"I see you are available, could you
do..."* 😒

Ever got one of those message on Teams? Now when working 'home office'
I noticed this trend and I usually get one of those over the phone
during shopping and usually couple of lines in CLI for Microsoft 365 may
do the trick but I don't always carry my laptop with me (I know...
strange). I always considered CLI for M365 as an ace up my sleeve but I
never found any cards in my pocket... but a mobile phone
🤩, now that's a different story. So lets see if we may
use CLI on Android.

## But first of all what is CLI for Microsoft 365? Quick introduction

if your already know... skip this part😀
CLI for Microsoft 365 is a cross platform command line tool you may use
to manage many things. To name a few, you may manage OneDrive, Planner,
Power Apps and Automate, Teams, Yammer, SharePoint (of course), now
there is even a dedicated command to help you set up Viva. The list
keeps on growing and growing, [check out the CLI for Microsoft
365](https://pnp.github.io/cli-microsoft365/).
But it's not only about managing Microsoft 365. The CLI helps you also
manage your own spfx environment (check out
the [doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor/))
or projects (rename, upgrade etc.). This is very unique that many
similar command line tools don't have.
Some commands do simple things but some actually are ready to use
scenarios all done under a single command. Check out the full list
of[commands](https://pnp.github.io/cli-microsoft365/cmd/login/#usage)
That's nice right. But how does it work. Well CLI for M365 is given as a
npm package, that's right you need Node.js (that's why it's cross
platform). How cool is that. If only we could use Node on Android right
😀.

## CLI everywhere, why not on mobile?

So let's check how we may use CLI for Microsoft 365 on Andriod.

1.  First we need a terminal to install Node. For this we may use
  
    [Termux
    on play
    store](https://play.google.com/store/apps/details?id=com.termux&hl=pl&gl=US).
    We just go to the play store, search for the app install. Done. Lets
    move
    on
2.  Next we need to usually update the
    terminal

    ```bash
    apt update && apt upgrade
    ```

3.  Now we need to install
    Node

    ```bash
    apt install nodejs
    ```

4.  Now we need to install CLI for
    M365

    ```bash
    npm i -g @pnp/cli-microsoft365
    ```

... done.
Lets check what we have using bash

```bash
m365
```

{{< image alt="2.png" src="images/blog/cli-for-microsoft-365-on-your-mobile/2.png" >}}

CLI for Microsoft 365 is up and running... Nice.
Now to manage the tenant we only need to login. This is done like
always

```bash
m365 login
```

{{< image alt="5.png" src="images/blog/cli-for-microsoft-365-on-your-mobile/5.png" >}}
After successful login we may check the connection status running

```bash
m365 status
```

{{< image alt="3.png" src="images/blog/cli-for-microsoft-365-on-your-mobile/3.png" >}}

Now lets try any command. Lets check my sites on tenant running

```bash
m365 spo site list
```

{{< image alt="1.png" src="images/blog/cli-for-microsoft-365-on-your-mobile/1.png" >}}

Or lets check my ToDo tasks

```bash
m365 todo task list --listName 'Test list
```

{{< image alt="7.png" src="images/blog/cli-for-microsoft-365-on-your-mobile/7.png" >}}

I think I may mark the 'Try to write something close to an article' as
done 🤩
So there you have it. CLI for Microsoft 365 running everywhere you need,
also on your mobile. Now you may also do the simple request during
shopping. The question is, if you should? Maybe it's better to focus on
the shopping list and respond to the message during working
hours😀
I hope you liked the article. Please leave a comment if you tried it out
and/or if you think it may be helpful.
BTW if you didn't try CLI for Microsoft 365 yet I strongly encourage
you to do so [CLI for Microsoft
365](https://pnp.github.io/cli-microsoft365/). Check out the PnP script
samples gallery to see in what cases other people already use the CLI
[Script Samples | PnP Samples](https://pnp.github.io/script-samples/).
Something not working and should? Or maybe you see something missing in
the CLI. No worries, open an issue and let the maintainers (or a
friendly contributor) know
[Issues ·
pnp/cli-microsoft365](https://github.com/pnp/cli-microsoft365/issues)
