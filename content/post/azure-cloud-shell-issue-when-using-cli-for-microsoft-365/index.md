---
title: "Azure Cloud Shell issue when using CLI for Microsoft 365 - Workaround"
date: 2021-10-18T04:24:00-04:00
author: "Arjun Menon"
githubname: arjunumenon
categories: ["CLI For Microsoft 365"]
images:
- images/ArjunMenon_0-1634207520847.jpeg
tags: ["CLI for Microsoft 365", "Azure"]
type: "regular"
---

[Azure Cloud
Shell](https://docs.microsoft.com/azure/cloud-shell/overview) is
one of the cool Azure features which will help you to execute Bash /
PowerShell script from the browser. The best part is that Azure Cloud
shell even supports [CLI for Microsoft
365](https://aka.ms/cli-m365) without you need to explicitly install
anything in the shell.

When you try to execute CLI for Microsoft 365 after creating a [new
Cloud
Shell](https://docs.microsoft.com/azure/cloud-shell/quickstart#start-cloud-shell),
we will get an error which is something like below,

```Shell
/usr/local/lib/node_modules/@pnp/cli-microsoft365/node_modules/update-notifier/index.js:58
                        } catch {
                                ^
SyntaxError: Unexpected token {
    at createScript (vm.js:80:10)
    at Object.runInThisContext (vm.js:139:10)
    at Module._compile (module.js:617:28)
    at Object.Module._extensions..js (module.js:664:10)
    at Module.load (module.js:566:32)
    at tryModuleLoad (module.js:506:12)
    at Function.Module._load (module.js:498:3)
    at Module.require (module.js:597:17)
    at require (internal/module.js:11:18)
    at Object.<anonymous> (/usr/local/lib/node_modules/@pnp/cli-microsoft365/dist/index.js:17:28)
```

![ArjunMenon_0-1634207520847.jpeg](images/ArjunMenon_0-1634207520847.jpeg)
It was identified by the expert team that this was because of the case
where Azure Cloud Shell uses node version 8.16 as the base image. But
CLI for Microsoft 365 uses later Node version which is causing the issue
in Azure Cloud Shell. Due to this Node version mismatch, CLI for
Microsoft 365 is unable to work as expected. The conversation related to
this already [initiated as an
Issue](https://github.com/Azure/CloudShell/issues/63#issuecomment-746877238) in
GitHub.

But till the time upgrade is complete, we have a workaround which could
be implemented so that you can execute CLI for Microsoft 365 in Azure
Cloud Shell seamlessly.

## Workaround

Though the team is actively working on updating the node version, we
will not be able to use Azure shell for CLI for M365 till the upgrade is
complete. We do have a workaround for the same using the node on top
of [Node Version Manager aka NVM](https://github.com/nvm-sh/nvm#intro).
You can follow the below steps if you want to know the complete steps

1.  [Install
    NVM](https://github.com/nvm-sh/nvm#install--update-script) in the
    cloud shell
2.  [Install the Node
    version](https://github.com/nvm-sh/nvm#intro) required for CLI for
    Microsoft 365. As of writing this blog, CLI for Microsoft 365
    supports any node version>14.0.0
    1.  `nvm install 14.0.0`{.language-plaintext .highlighter-rouge}
    2.  *Made sure you are making this [version as
        default](https://github.com/nvm-sh/nvm#set-default-node-version)*
3.  After that [install CLI for Microsoft
    365](https://pnp.github.io/cli-microsoft365/user-guide/installing-cli/#install-the-cli-for-microsoft-365) in
    the node version which you have set as the default
4.  Once the CLI package is installed, you can see that CLI works
    perfectly well in Azure Shell

![ArjunMenon_1-1634207520863.jpeg](images/ArjunMenon_1-1634207520863.jpeg)


This is just a workaround till we have a permanent solution from Azure
Shell team for the same.
