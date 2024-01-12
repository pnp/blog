---
title: "Getting started with PnP Script Samples"
date: 2021-08-10T06:10:00-04:00
author: "Paul Bullock"
githubname: pkbullock
categories: ["Community post"]
tags: ["SharePoint"]
type: "regular"
---

Ever wanted to share your PowerShell or Bash scripts that you use to
automate, deploy or manage Microsoft 365, those written with:

-   [PnP PowerShell](https://pnp.github.io/powershell/)
-   [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/)
-   [SPO Management
    shell](https://learn.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?WT.mc_id=M365-MVP-5003816)
-   [Graph
    PowerShell](https://learn.microsoft.com/graph/powershell/get-started?WT.mc_id=M365-MVP-5003816)
-   [Graph
    CLI ](https://developer.microsoft.com/graph/blogs/access-microsoft-graph-through-a-new-preview-cli/)
-   other Microsoft 365 related scripts\...

Our intention is simply to make it easier for people to share and find
automation samples for the Microsoft 365 - got scripts you've built? -
share them with others!  Well now you can, **introducing PnP Script
Samples!**

This is a site used for hosting contributions of your PowerShell or Bash
scripts, allowing you to reduce the time to perform script based tasks
with the Microsoft 365 services. Like other PnP resources, you can refer
to this resource to leverage existing scripts to achieve your goals
quicker and easier.
![Script Samples - Homepage](images/script-samples-home.png)

## Scenarios and Scripts

When working with Microsoft 365 using scripts, there is a scenario that
you are trying to achieve, e.g. "Install a site design into the
tenant" or "Report on Teams Private Channels".
In the community and from those provided by Microsoft, there are a
variety of tools that you can use for the scenarios. The sample pages
are designed to first describe the scenario and then provide one or more
scripts across the tools to achieve the goals of the scenario.
Each script is represented as tabs, giving you the option to choose the
preferred tool and learn about how the same goal can be achieved by
different tools.

## Search and Filtering

Each of the scenario samples are bundled with metadata to allow for
identification of authors - crediting you on your contributions, the
type of operation e.g. reporting, provision, data, which tools the
sample refers to and which Microsoft products the script targets.
Using the metadata, we can provide filters and search capabilities on
the listing pages enabling you to search for the scenario and script.
![Searching Script Samples](images/script-samples-search.png)

## Copy to Clipboard

We have introduced a feature within each of the script to copy to
clipboard allowing you to quickly grab the sample to use in your
preferred authoring tool. This is located top right-hand side of the
script blocks:
![Copy to Clipboard feature](images/copt-to-clipboard.png)


## Clickable commands

In the scripts, there will be example usage of commands that each tool
provides for the scenario. We have made it easier for you to learn about
these commands, by automatically linking to the relevant documentation
site.
![Clickable Help for commands](images/script-clickable-help.png)

Few points about this feature:

-   if you use the Copy To Clipboard feature the links are NOT
    included - this is by design.
-   the commands are linked to the latest docs, this will not make
    clickable any retired commands.

If you are think a command should be highlighted and linked to the
documentation [please raise an issue in the GitHub
repo](https://github.com/pnp/script-samples/issues).

## Contributing

If you would like to contribute to the samples, you are absolutely
welcomed to do so, we have created [guidance to help
you](https://pnp.github.io/script-samples/contributing/index.html). We
are looking for contributions in the following areas:

-   Create a new scenario with a script
-   Update a scenario with an alternative script using another tool e.g.
    Adding a PnP PowerShell script to a scenario that only has CLI for
    Microsoft 365.
-   Feedback on the usability of the site, we are always looking to
    improve the experience.

In the repo, we are created a template submission folder and files,
complete the readme, add any screenshots and submit your GitHub Pull
Request, please contact us via issues list to communicate what your
planning.
If you need any support or want to know how to use GitHub then we have a
great program to [support new contributors | sharing is
caring](https://pnp.github.io/sharing-is-caring/).
So check out <https://aka.ms/script-samples> today!
