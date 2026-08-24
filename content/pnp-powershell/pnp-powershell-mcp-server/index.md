---
title: Introducing the PnP PowerShell MCP Server
summary: The PnP PowerShell MCP Server lets you manage Microsoft 365 with natural language by turning your favourite MCP client into a PnP PowerShell co-pilot - running cmdlets, authoring scripts, and searching the community PnP Script Samples library, all from a plain-English prompt.
date: 2026-08-24T19:09:00.000Z
author: Nishkalank Bezawada
githubname: NishkalankBezawada
categories:
  - PnP PowerShell
images:
  - images/pnp-powershell-mcp-hero.png

tags:
  - PnP PowerShell
  - PnP PowerShell MCP Server
  - Model Context Protocol
  - GitHub Copilot
  - SharePoint
  - Microsoft Teams
  - Microsoft 365
type: trending
---

## 🤖 Introducing the PnP PowerShell MCP Server

We are excited to introduce the **PnP PowerShell MCP Server** - a new way to work with [PnP PowerShell](https://pnp.github.io/powershell/) using **natural language**. 🎉

Instead of remembering the exact cmdlet, its parameter set, and the right syntax, you can now simply *describe* what you want to do, and let your MCP client (GitHub Copilot, Claude, Cursor, and more) translate that into the right chain of PnP PowerShell cmdlets - executed against your connected tenant.

Think of it as a **PnP PowerShell co-pilot**: it knows the 800+ cmdlets, it can look up their documentation, it can search the community's [PnP Script Samples](https://pnp.github.io/script-samples/) library, and it can run commands for you - safely and with confirmation for anything destructive.

![PnP PowerShell MCP Server](images/pnp-powershell-mcp-hero.png)

## 🧩 What is an MCP server?

The **Model Context Protocol (MCP)** is an open standard that lets AI assistants talk to external tools in a consistent way. An **MCP server** exposes a set of *tools* and *resources* that an AI client can discover and call on your behalf.

The PnP PowerShell MCP Server is a **local (stdio) MCP server**. It shells out to the PnP PowerShell module already installed on your machine - so it reuses *your* authentication and *your* connection context. It does **not** authenticate for you and it does **not** send your tenant data anywhere; it simply lets your AI client drive PnP PowerShell in a controlled way.

## ✨ Why it matters

With the PnP PowerShell MCP Server you can manage many different areas of Microsoft 365 straight from your MCP client:

* **SharePoint Online** - sites, lists, libraries, columns, items, pages
* **Microsoft Teams** - teams, channels, posts
* **Entra ID**, **OneDrive**, **Planner**, **Power Platform**, **Microsoft 365 Groups**
* **Taxonomy, search, and tenant administration**

Beyond running commands, it's a great **jump-start for writing your own automation**: ask it for a community script sample, and it will find the most relevant one and adapt it to your scenario.

## 📦 Prerequisites

Before you begin, make sure you have:

* [PowerShell 7.4 or above](https://aka.ms/powershell) (`pwsh`) installed and available on your `PATH`
* The [`PnP.PowerShell`](https://www.powershellgallery.com/packages/PnP.PowerShell) module installed:

  ```powershell
  Install-Module -Name PnP.PowerShell -Scope CurrentUser -Force
  ```

* A connection established with `Connect-PnPOnline` - the MCP server reuses this same connection context.

> The published tool releases are self-contained, so you only need the [.NET 10 SDK](https://dotnet.microsoft.com/download) if you want to build and run from source.

## 🚀 Installation

You can install the server in two ways: as a persistent .NET global tool, or on-demand through the `dnx` tool runner straight from your MCP client config.

### Option 1: Install as a .NET global tool

```bash
dotnet tool install --global PnP.PowerShell.MCPServer --prerelease
```

This installs a self-contained, native AOT executable named `pnp-powershell-mcp-server` on your `PATH`. It supports Windows (x64, arm64), macOS (arm64, x64), and Linux (x64, arm64, musl x64).

To update an existing install:

```bash
dotnet tool update --global PnP.PowerShell.MCPServer --prerelease
```

![Installing the PnP PowerShell MCP Server as a .NET global tool](images/install-dotnet-tool.png)

### Option 2: Run on-demand with `dnx`

If you're on the .NET 10 SDK, you don't need to install anything up front - you can point your MCP client at the NuGet package directly and let the [`dnx`](https://aka.ms/nuget/mcp/concepts) tool runner fetch and run it. Add this to your `.vscode/mcp.json`:

```json
{
  "servers": {
    "PnP.PowerShell.MCPServer": {
      "type": "stdio",
      "command": "dnx",
      "args": ["PnP.PowerShell.MCPServer@0.1.4-beta", "--yes"]
    }
  }
}
```

This is the configuration surfaced on the [NuGet package page](https://www.nuget.org/packages/PnP.PowerShell.MCPServer). Pin the version (`@0.1.4-beta`) to a specific release, or drop it to always pull the latest prerelease.

### Add to VS Code

If you installed the global tool (Option 1), register it with VS Code:

1. Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`) and type `MCP: Add Server`.
2. Select **Command (stdio)** as the server type.
3. Enter the command to run the MCP server:

   ```text
   pnp-powershell-mcp-server
   ```

4. Name the server (e.g., `PnP PowerShell MCP Server`).

You should end up with the following in your `.vscode/mcp.json` file:

```json
{
    "servers": {
        "PnP PowerShell MCP Server": {
            "type": "stdio",
            "command": "pnp-powershell-mcp-server"
        }
    }
}
```

![Registering the server in VS Code mcp.json](images/vscode-mcp-config.png)

Now open GitHub Copilot chat in Agent mode, and you'll be able to select the **PnP PowerShell MCP Server** tools. Start your prompt with something like *"Using PnP PowerShell, I want you to..."* and Copilot will use the MCP server to fulfil your request.

![PnP PowerShell MCP tools available in GitHub Copilot](images/copilot-tools-list.png)

The server can also be added to **GitHub Copilot CLI**, **Claude Code**, **Claude Desktop**, and **Cursor** - see the [project README](https://github.com/pnp/pnp-powershell-mcp-server) for the exact steps for each client.

## 🛠️ Capabilities & tools

Under the hood, the server exposes a focused set of tools. Your MCP client picks the right one automatically - you just describe what you want.

| Tool | What it does |
| --- | --- |
| `pnp_search_commands` | Finds which cmdlet does a job by keyword, with a link to each cmdlet's help. Works offline via a vendored cmdlet index. |
| `pnp_get_command_docs` | Returns the full reference docs for a cmdlet - syntax, parameters, parameter sets, and examples. |
| `pnp_run_command` | Runs PnP PowerShell against your connected tenant in a persistent session. Destructive commands require confirmation first. |
| `pnp_get_result_page` | Pages through a large result set that was summarised, without re-querying the tenant. |
| `pnp_get_connection_status` | Reports whether you're signed in, to which site, and as which account. |
| `pnp_diagnose_connection` | Checks everything needed before a command can run - `pwsh`, the module, and the connection - and names the exact fix for each failing check. |
| `pnp_reset_session` | Ends a session and its connection - to sign out, switch accounts, or recover a stuck session. |
| `pnp_get_best_practices` | Returns best practices for using PnP PowerShell through the MCP server. |
| `pnp_search_script_samples` | Lists community [PnP Script Samples](https://pnp.github.io/script-samples/) matching a keyword. |
| `pnp_get_script_sample` | Retrieves the full script code for a named community sample. |
| `pnp_suggest_script` | Finds the most relevant community samples for a task and returns their code plus adaptation guidance. |
| `pnp_ping` | Lightweight health check - server version, uptime, read-only status, and active session count. |
| `pnp_list_sessions` | Lists all active PowerShell sessions with their status and last activity time. |

Every tool declares its `readOnlyHint`, `idempotentHint`, and `openWorldHint` annotations, and the two that can change state also declare `destructiveHint` - so your client can decide what to auto-approve without guessing.

The same guidance and cmdlet documentation is also exposed as MCP **resources** (`pnp://best-practices`, `pnp://best-practices/{section}`, and `pnp://cmdlet/{name}`), so a client that supports resources can browse and cache the content instead of spending a tool call on it.

## 📷 Use cases

Here are a few examples of what you can do - these are just a starting point; feel free to experiment.

### Manage SharePoint Online

> Add a new list to this site with title 'awesome ducks'. Then add new columns to that list including them in the default view. The first should be a text description column and the second one should be a user column. Then add 3 items to this list with some funny jokes about ducks added in the description column and my user in the user column.


### Manage Microsoft Teams

> Create a new Team on Teams with name 'Awesome Ducks' and in the General channel add a welcome post.


### Bootstrap a script from a community sample

> I need a PnP PowerShell script that exports all SharePoint list items to a CSV file - find a community sample and adapt it for the 'Documents' list on my site.

### Report on tenant state

> Can you check if I have a Power Automate flow called 'HoursReportingReminder' and if so disable it?


## 🔐 Security & safety

Security was a first-class design goal:

* **You stay in control of authentication.** The server never signs in for you - it reuses the connection you made with `Connect-PnPOnline`.
* **Destructive commands require confirmation.** Anything that can change or delete state must be confirmed before it runs.
* **Everything is annotated.** Read-only, idempotent, and destructive hints let your client auto-approve safe operations while pausing on risky ones.

![A destructive command asking for confirmation before running](images/destructive-confirmation.png)

## 🔁 Working with multiple tenants

Commands run in a persistent `pwsh` session, so a connection made with `Connect-PnPOnline` stays alive across calls - you connect once rather than on every command.

For most work you never think about sessions. If you need to work against **two tenants (or two accounts) at the same time**, you can simply *say* so, and the agent will keep each connection in its own named session:

> Connect to contoso in a session called "contoso" and to fabrikam in a session called "fabrikam", then list the site count in each and tell me which is larger.

### Things worth knowing

A few practical notes that will save you time once you start using sessions:

* **Sign out or switch account** with `pnp_reset_session`. It ends that session and discards its connection and variables; the next call starts fresh.
* **Idle sessions end after 30 minutes.** A session busy running a command is never reclaimed, however long it takes - just reconnect if one does expire.
* **One command at a time per session.** A second call against a busy session waits, then reports the session is busy. To genuinely run two things at once, use two different session names.
* **Reuse the connection.** Don't re-run `Connect-PnPOnline` before every command; the agent checks `pnp_get_connection_status` first and reuses the existing connection.

## ⚙️ Configuration

The server reads a handful of environment variables that let you tune its behaviour - from locking it into read-only mode to extending the command timeout for long-running tenant reports. You set these wherever your MCP client launches the server (most commonly the `env` block of your `.vscode/mcp.json`).

| Environment variable | Default | Description |
| --- | --- | --- |
| `PNP_MCP_READONLY` | `false` | Set to `true` to refuse any command that would change Microsoft 365. Only read-style verbs (`Get-`, `Export-`, `Test-`, `Find-`, `Measure-`, ...) are allowed; change verbs (`Set-`, `Remove-`, `New-`, `Add-`, ...) are blocked. Great for letting an agent explore a production tenant safely. |
| `PNP_MCP_CONFIRM_DESTRUCTIVE` | `true` | Set to `false` to run destructive commands (`Remove-*`, `Clear-*`, ...) without asking for confirmation. Use only in reviewed, unattended automation. |
| `PNP_MCP_COMMAND_TIMEOUT_SECONDS` | `600` | Wall-clock limit for a single `pnp_run_command` call. On timeout the session is terminated and the connection is lost. |
| `PNP_MCP_MAX_OUTPUT_CHARS` | `50000` | Largest tool response returned, in characters. Oversized result sets are summarised and paged rather than blindly truncated. |
| `PNP_SCRIPT_SAMPLES_PATH` | _(unset)_ | Path to a local clone of [pnp/script-samples](https://github.com/pnp/script-samples), used when you want a catalogue newer than the one compiled into the server. |

Here's how you'd set two of them in VS Code:

```json
{
    "servers": {
        "PnP PowerShell MCP Server": {
            "type": "stdio",
            "command": "pnp-powershell-mcp-server",
            "env": {
                "PNP_MCP_READONLY": "true",
                "PNP_MCP_COMMAND_TIMEOUT_SECONDS": "1800"
            }
        }
    }
}
```

The client passes the environment in when it launches the server process, so after changing any of these, **restart the MCP server** (in most clients, reload the window or toggle the server off and on) - an already-running server keeps the old values.

### Worked examples

| Goal | Setting |
| --- | --- |
| Let an agent explore a production tenant without being able to change it | `PNP_MCP_READONLY=true` |
| Tenant-wide reports that take longer than 10 minutes | `PNP_MCP_COMMAND_TIMEOUT_SECONDS=3600` |
| Unattended automation where the commands are already reviewed | `PNP_MCP_CONFIRM_DESTRUCTIVE=false` |
| Work against a script-samples clone newer than the vendored index | `PNP_SCRIPT_SAMPLES_PATH=C:\src\script-samples` |

> ⚠️ Two cautions: `PNP_MCP_CONFIRM_DESTRUCTIVE=false` removes the only prompt standing between an agent and a command like `Remove-PnPTenantSite`, so set it only where the commands are reviewed some other way. And the booleans are matched exactly - `PNP_MCP_READONLY` enables only on the literal string `true`, and `PNP_MCP_CONFIRM_DESTRUCTIVE` disables only on `false`; anything else (including `1` and `yes`) leaves the default in place.

## 💬 Try it out and share feedback

The PnP PowerShell MCP Server is open source and community-driven. We'd love for you to:

* 👉 **Try it out** and manage Microsoft 365 using natural language
* 👉 **Report any issues or bugs** you encounter
* 👉 **Share feedback, suggestions, and feature requests**

You can find the project, full installation instructions for every client, and the source code on GitHub: [pnp/pnp-powershell-mcp-server](https://github.com/pnp/pnp-powershell-mcp-server).

## Need more information?

For more on PnP PowerShell itself - commands, architecture, and getting started - visit [aka.ms/pnppowershell](https://aka.ms/pnppowershell).

Happy scripting with natural language! 💙
