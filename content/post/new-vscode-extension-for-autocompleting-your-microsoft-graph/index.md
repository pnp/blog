---
title: "New VSCode extension for autocompleting your Microsoft Graph APIs"
date: 2021-05-07T05:38:00-05:00
author: "Elio Struyf"
githubname: estruyf

categories: ["Community post"]
images:
- images/how-it-works.gif
tags: ["Microsoft Graph"]
type: "regular"
---

While working on a project which uses Microsoft Graph APIs, I found
myself opening the Microsoft Graph Explorer a lot to check which
paths/parameters were available. The Microsoft Graph Explorer is a great
tool, but I love not to change context too much.
As I like to create Visual Studio Code extensions, I did not have to
think long to start building a new extension.

## Background info

The good news for me was that Microsoft Graph Explorer has an API for
retrieving the Open API information. This API returns all the available
endpoints and their parameters per path. All I had to do, was create the
logic to know when you are writing a Microsoft Graph URL and call the
API to provide the suggestions.

## The extension 

> **Info**: The Visual Studio Code extension can be found on the
marketplace: [MS Graph
Completion](https://marketplace.visualstudio.com/items?itemName=eliostruyf.vscode-msgraph-autocomplete "MS Graph Completion").
The initial version of the extension supports the **GET** API paths,
query string parameters, and their values.

![how-it-works.gif](images/how-it-works.gif)

The **/users/** API completion allows you to add a **{user-id}** token.
![Screenshot 2021-03-23 at 21.04.10.png](images/Screenshot 2021-03-23 at 21.04.10.png)

When providing your user-ID or username, it will automatically tokenize
it.
![Screenshot 2021-03-23 at 21.04.25.png](images/Screenshot 2021-03-23 at 21.04.25.png)

## When would you use it?

There are various reasons for this. My reasoning, as mentioned, was to
know which parameters are available for selecting and expanding
quickly
Another option could be to use it in combination with the popular [REST
Client - Visual Studio
Marketplace](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)

![Screenshot 2021-03-24 at 08.30.52.png](images/Screenshot 2021-03-24 at 08.30.52.png)
Let me know how you would use it and feel free to contribute to the
project [MS Graph Completion - GitHub
Repository](https://github.com/estruyf/vscode-msgraph-autocomplete "MS Graph Completion - GitHub Repository")

*Thanks to the Microsoft Graph team for the API and Graph explorer*
