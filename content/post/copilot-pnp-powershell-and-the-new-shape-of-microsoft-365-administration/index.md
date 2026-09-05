---
title: "Copilot, PnP PowerShell, and the New Shape of Microsoft 365 Administration"
date: 2026-09-05T00:00:00-00:00
author: "Josiah Opiyo"
githubname: ojopiyo
categories: ["Community post"]
images:
  - images/cover.png
tags: ["Microsoft 365"]
type: "regular"
draft: false
---

The Power Platform community call I attended on 25th August 2026 delivered many strong sessions, but one presentation immediately stood out to me - **Setup and use PnP Powershell with Copilot to manage your tenant without knowing it by Adam Wójick**. It wasn't because of a new feature announcement or a dramatic architectural shift. Instead, it was the way the presenter connected Copilot, PnP PowerShell, and Microsoft 365 administration into a single, practical workflow. The idea was deceptively simple: give Copilot a dedicated agent with skills for working directly with PnP PowerShell. With that, natural language becomes a legitimate administrative entry point. The moment I saw this demonstrated, the implications were hard to ignore.

Behind this approach sits a familiar challenge. Administrators often know what they want to achieve, but translating intent into the correct command syntax is where friction appears. Even experienced engineers occasionally pause to check parameters or authentication patterns. For newer administrators, the command layer can become a barrier entirely. The presentation didn't try to hide this complexity. Instead, it reframed Copilot as an interface that sits on top of established administrative capabilities, reducing the distance between intent and action without removing the underlying technology.

The PnP PowerShell Copilot agent is built around a set of skills that make this possible. The Setup skill handles installation, configuration, authentication, and sign-in. It supports interactive login or app registration, with certificate or secret-based authentication. This matters because authentication choices define the security posture of any automation. The Manage Microsoft 365 skill focuses on practical tasks: creating sites, managing lists and libraries, updating pages, and handling permissions. These are the operations administrators perform daily, and the agent turns them into natural-language requests that still map to real PnP PowerShell commands.

The presentation also highlighted planned skills for script creation, evaluation, and updating. These remain works in progress, but their inclusion signals a future where Copilot can help generate and refine automation rather than simply execute it. The demonstration covered installation paths for both VS Code and GitHub Copilot CLI. In each case, users install the plugin, switch to the PnP PowerShell agent, and begin issuing requests conversationally.

The examples were where the concept truly came alive. A simple setup request triggered a guided conversation about tenant details, authentication method, and required permissions. Once configured, the agent handled a multi-step workflow: creating a site, configuring content, building a page, and generating test data. This wasn't a single command; it was a sequence of operations stitched together through natural language. Another example asked Copilot to create a backup script, hinting at how the planned script skills could evolve into meaningful automation support.

For organisations exploring Copilot-led administration, the appeal is clear. Intent becomes the starting point, and the agent handles translation into PnP PowerShell operations. Experienced engineers gain speed for repetitive tasks. Less experienced administrators gain a gentler learning curve. But none of this removes the need for strong governance. Natural language does not make administrative actions safe by default. Permissions, authentication, and oversight still matter. The Setup skill's explicit handling of tenant details and authentication is a reminder that governance must remain central.

Before treating the agent as operational tooling, organisations should consider who is allowed to use it, how generated actions are reviewed, and how maintainability will be preserved as the plugin evolves. Script creation and evaluation remain under development, making this a technology worth testing rather than assuming. The evaluation approach, which scores and improves the agent over time, is also worth watching.

As the community explores this together, one question feels especially relevant: how should natural-language administration be governed when it has the power to change tenant configuration?

## Resources

- Repo: **[https://github.com/Adam-it/pnp-powershell-copilot-plugin](https://github.com/Adam-it/pnp-powershell-copilot-plugin)**
- PnP PowerShell: **[https://pnp.github.io/powershell/index.html](https://pnp.github.io/powershell/index.html)**
- PnP PowerShell MCP server: **[https://github.com/pnp/pnp-powershell-mcp-server](https://github.com/pnp/pnp-powershell-mcp-server)**
- PnP PowerShell Copilot Plugin: **[https://github.com/Adam-it/pnp-powershell-copilot-plugin/tree/main](https://github.com/Adam-it/pnp-powershell-copilot-plugin/tree/main)**
- CLI for Microsoft 365: **[https://pnp.github.io/cli-microsoft365](https://pnp.github.io/cli-microsoft365)**
- CLI for Microsoft 365 MCP server: **[https://github.com/pnp/cli-microsoft365-mcp-server](https://github.com/pnp/cli-microsoft365-mcp-server)**
- PnP PowerShell VS Code extension: **[https://marketplace.visualstudio.com/items?itemName=adamwojcikit.pnp-powershell-extension](https://marketplace.visualstudio.com/items?itemName=adamwojcikit.pnp-powershell-extension)**
