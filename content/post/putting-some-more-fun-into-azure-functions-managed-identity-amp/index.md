---
title: "Putting some more FUN into Azure Functions, Managed Identity & Microsoft Graph"
date: 2021-08-11T08:40:00-04:00
author: "Luise Freese"
githubname: LuiseFreese
categories: ["Community post"]
images:

tags: ["Microsoft Graph", "Azure"]
type: "regular"

---

## Use case & purpose of this blog post

I want to show, how you can use a Managed Identity in Azure Functions to
get an access token for Microsoft Graph API.
![image-8.png](images/image-8.png)

## Prerequisites to benefit from this article

To get the most out of this post, you should understand the following
concepts -- I included some links that should help you getting started.

## Managed Identity -- What is that and why would I want one?

Managed Identities are the state-of-the-art way to get Azure Active
Directory access tokens, because you won't need to handle credentials,
which is of course a security benefit

\>...where there are credentials, there are leaks ¯\\\_(ツ)\_/¯

If you are unfamiliar with tokens, [this article by Lee
Ford](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/introduction-to-tokens/ba-p/2267853)
will help. This is not a full tutorial on Managed Identities, for more
information please start to read here. Also, [Yannick
Reekmans](https://twitter.com/YannickReekmans) posted an entire [series
on Managed
Identities](https://blog.yannickreekmans.be/secretless-applications-managed-identities/),
highly recommended to read this -- helped me a lot to understand.

## Azure Functions

If you'd like to deploy and execute code without needing to THINK about
server infrastructure or VMs, you may like Azure Functions. Azure
Functions can be written in a lot of languages and you can deploy and
execute Azure Functions on any platform that can run .NET Core. Azure
functions are scalable, as they use compute-on-demand: More resources
are allocated automagically, when the demand of execution increases. If
the demand decreases again, you don't need to worry about the extra
resources anymore as they drop off again. This way, you only pay what
you need. For more info please start to read here: [Azure Functions
Overview | Microsoft
Docs](https://learn.microsoft.com/azure/azure-functions/functions-overview)

I will use PowerShell for my Azure Functions, so that IT-Pros can
benefit from this post as well. But please do choose [your poison
]{style="text-decoration: line-through;"}your favourite language, the
concept stays the same. Use whatever you are familiar with or what makes
you happy.

## Microsoft Graph

Microsoft Graph is THE API to access Microsoft 365 resources, in our
case we will want to read all Microsoft 365 groups -- for more
information see also the [Microsoft Graph permissions reference --
Microsoft Graph | Microsoft
Docs.](https://learn.microsoft.com/graph/permissions-reference#group-permissions)

Our challenge will be to access the Graph API with a Managed Identity. I
will show how to do this entirely in Azure CLI & [VS
Code](https://code.visualstudio.com/). Creating and assigning Managed
Identities has been shown often before in the Azure portal, but a script
would allow for automation, it is usually faster than working in a
visual environment and you can use the tool of your choice. I highly
recommend VS Code as editor (and I like the built-in terminal as well).

### Create your Azure Functions locally

You still may create your first Azure Functions in the Azure Portal (I
did as well), which demoes really nicely, but as we want to go for real
world, I will show how to develop your Azure Functions in Visual Studio
code. This has some great advantages:

-   you develop locally using the tools that you are already familiar
    with
-   you don't need to adjust to ever changing UI in Azure portal
-   you can benefit from source control
-   you can collaborate with others

I covered how to do this also in a previous post, but for the sake of a
start-to-end scenario, here we go again:

-   Install the Core Tools package with `npm install -g
    azure-functions-core-tools@3 \--unsafe-perm true`
-   Install the Azure Functions extension for VS Code
-   Select New Project
-   Select a folder for your project
-   Select a language -- I will use PowerShell
-   Select HTTP trigger as a template
-   Type in a better name like GetGraphToken
-   Select Authorization level Function
-   Select how you want to open your project -- I prefer Add to
    workspace
-   You will now see your Local Project in the pane.
(yes, my pane is on the right hand side so that my code doesn't "jump"
all the time when I am expanding or collapsing the pane)

We will now write the code for our Azure Functions. Replace the default
code of run.ps1 in VS Code by this:

```bash
using namespace System.Net

# Input bindings are passed in via param block
param($Request, $TriggerMetadata)

# Write to the Azure Functions log stream.
Write-Host "PowerShell HTTP trigger function processed a request."

# Interact with query parameters or the body of the request
.$Scope = $Request.Query.Scope
if (-not $Scope) {
$Scope = $Request.Body.Scope
}
#If parameter "Scope" has not been provided, we assume that graph.microsoft.com is the target resource
If (!$Scope) {
$Scope = "https://graph.microsoft.com/"
}

$tokenAuthUri = $env:IDENTITY_ENDPOINT + "?resource=$Scope&amp;api-version=2019-08-01"
$response = Invoke-RestMethod -Method Get -Headers @{"X-IDENTITY-HEADER"="$env:IDENTITY_HEADER"} -Uri $tokenAuthUri -UseBasicParsing

$accessToken = $response.access_token

#Invoke REST call to Graph API
$uri = 'https://graph.microsoft.com/v1.0/groups'
$authHeader = @{
'Content-Type'='application/json'
'Authorization'='Bearer ' + $accessToken
}

$result = (Invoke-RestMethod -Uri $uri -Headers $authHeader -Method Get -ResponseHeadersVariable RES).value

If ($result) {
$body = $result
$StatusCode = '200'
}
Else {
$body = $RES
$StatusCode = '400'}

# Associate values to output bindings by calling 'Push-OutputBinding'
Push-OutputBinding -Name Response -Value ([HttpResponseContext]@{
StatusCode = $StatusCode
Body = $body
})
```

Take a moment to understand what the code does:

-   log that a request was received
-   define the scope (if not stated, it's Microsoft Graph)
-   obtain the token from the environment variables
    \`IDENTITY_ENDPOINT\` and \`IDENTITY_HEADER\` which come from the
    Managed Identity (thanks [Yannick
    Reekmans](https://twitter.com/yannickreekmans) for this hint) --
    learn more here: [Managed identities -- Azure App Service |
    Microsoft
    Docs](https://learn.microsoft.com/azure/app-service/overview-managed-identity?tabs=powershell&WT.mc_id=M365-MVP-5003400#obtain-tokens-for-azure-resources)
    -- you can also see your environment variables here, the mentioned
    ones will show after you assigned the system assigned Managed
    Identity:
    [https://\<YOUR-FUNCTIONAPPNAME-HERE>.scm.azurewebsites.net/ENV.cshtml#envVariables](https://%3cYOUR-FUNCTIONAPPNAME-HERE%3e.scm.azurewebsites.net/ENV.cshtml#envVariables))
-   pass that token in the header of the REST call towards the group
    endpoint of Microsoft Graph
-   get the status code (hopefully 200)

Watch out -- the Graph API will this way return up to 100 groups --
Please adjust with [query
parameters](https://learn.microsoft.com/graph/query-parameters) as
needed like [https://graph.microsoft.com/v1.0/groups?\$top=42
or](https://graph.microsoft.com/v1.0/groups?$top=42&nbsp;or) use paging,
which is described here: [Paging Microsoft Graph data in your app --
Microsoft Graph | Microsoft
Docs](https://learn.microsoft.com/graph/paging)


## Resources in Azure

We will now create the Functions App in Azure -- You can either install
the CLI or use Cloud shell (available on shell.azure.com -- no
installation is needed then and it works in any browser!)

### Variables & names

For testing purposes, I pseudo-randomized a number to not always need to
come up with new names:

```bash
#Get a random number between 100 and 300 to more easily be able to distinguish between several trials
$rand = Get-Random -Minimum 100 -Maximum 300
```

We will now set some variables, this reduces risk of typos and makes our
code better readable -- also we can reuse it better -- this is a
courtesy to future-self

```bash
#Set values
$resourceGroup = "DemoPlay$rand"
$location = "westeurope"
$storage = "luisedemostorage$rand"
$functionapp = "LuiseDemo-functionapp$rand"
```

### Resource group

Let's create a resource-group that will later hold our Azure Functions
App

```bash
#create group
az group create -n $resourceGroup -l $location
```

### Storage Account

As our Functions App will need a storage account, we will create this as
well:

```bash
#create storage account
az storage account create `
-n $storage `
-l $location `
-g $resourceGroup `
--sku Standard_LRS
```

### Functions App

Now create the Azure Functions app which later holds our functions
(remember we created that earlier locally, but will later deploy it to
Azure)

```bash
#create function
az functionapp create `
-n $functionapp `
--storage-account $storage `
--consumption-plan-location $location `
--runtime powershell `
-g $resourceGroup `
--functions-version 3
```

It will take a few moments for everything to be set, once this step is
completed, you will be prompted with a message, that you also can
benefit from Application Insights.

### Managed Identity

We want things to be super secure -- this is why we want to enable a
system assigned Managed Identity for our new Functions:

```bash
az functionapp identity assign -n $functionapp -g $resourceGroup
```

 Our Managed Identity shall have the right permission scope to access
Graph API for Group.Read.All, and to eventually be able to make the
required REST call, we will need

-   the Graph API service Provider
-   permission scope, expressed as App role\
    Let's do this:

```bash
#Get Graph Api service provider (that's later needed for --api)
az ad sp list --query "[?appDisplayName=='Microsoft Graph'].{Name:appDisplayName, Id:appId}" --output table --all

#Save that service provider
$graphId = az ad sp list --query "[?appDisplayName=='Microsoft Graph'].appId | [0]" --all

# Get permission scope for "Group.Read.All"
$appRoleId = az ad sp show --id $graphId --query "appRoles[?value=='Group.Read.All'].id | [0]"
```

Time to make the REST call to assign the permissions as shown above to
the Managed Identity:

```bash
#Set values
$webAppName="LuiseDemo-functionapp$rand"
$principalId=$(az resource list -n $webAppName --query [*].identity.principalId --out tsv)
$graphResourceId=$(az ad sp list --display-name "Microsoft Graph" --query [0].objectId --out tsv)
$appRoleId=$(az ad sp list --display-name "Microsoft Graph" --query "[0].appRoles[?value=='Group.Read.All' &amp;&amp; contains(allowedMemberTypes, 'Application')].id" --out tsv)
$body="{'principalId':'$principalId','resourceId':'$graphResourceId','appRoleId':'$appRoleId'}"

#the actual REST call

az rest --method post --uri https://graph.microsoft.com/v1.0/servicePrincipals/$principalId/appRoleAssignments --body $body --headers Content-Type=application/json
```

If you like to, you may now have a look at our Managed Identity
permissions in the Azure portal -- for everyone who loves to be assured
in a UI that things have worked:\
\
![image-10-2048x664.png](images/image-10-2048x664.png)

-   Open [portal.azure.com](https://portal.azure.com/)
-   Select Azure Active Directory
-   Select Enterprise applications
-   Select Managed Identity from the Applications dropdown
-   Note the app level permission Read all groups for Microsoft Graph

### Deploy to Azure

Let's now deploy our Function to our Functions App. Go back to Visual
Studio Code:

-   Select the Azure extension
-   Select deploy to Functions App -- its that little cloud icon
-   Select the Functions App you already created in Azure
-   Confirm the Pop up window by selecting Deploy
-   Check progress results in the output window

Time to test!
Please note, that due to our Managed Identity, we can't test locally.
You can trigger your Functions with Postman or similar or run a test in
the Azure portal

-   Open portal.azure.com
-   Select **Resource groups**
-   Select the resource group you worked in
-   Select the Azure Functions App you worked in
-   Select **Functions**
-   Select **Code + Test**
-   Select **Test/Run**
-   Select **Run**

You should see a status code 200 -- and a list of all your Microsoft 365
groups. YAY!

![groups (1).png](images/groups (1).png)

## Conclusion and FusionDev scenario

As developers, we could build a robust, scalable and secure solution,
developed with familiar tools like VS Code, PowerShell or Azure CLI. But
what if we want to make this available to makers/citizen developers?
What if we want to make sure, that this could be used in Power Apps and
Power Automate? One way to achieve this, is creating a Power Platform
custom connector. This way, makers can use the connector which calls our
Azure Functions in a canvas app and display for example the groups in a
gallery or table.
\
Please note, that there are of course more fancy use cases, I will focus
in this blog post on the code -- If you have a good story, please reach
out.
\
Sample script is available at [Script Samples | PnP
Samples](https://pnp.github.io/script-samples/)

## More Resources to learn

\
Get started with Microsoft 365 development by signing up for a [free
Developer
tenant](https://developer.microsoft.com/microsoft-365/dev-program)\
Join the [Microsoft 365 PnP Community](https://pnp.github.io/) -- join
our calls and benefit from guidance, tools, sample\
 \
Originally published at [Putting some more FUN into Azure Functions, Managed Identity & Microsoft Graph -- M365 Princess](https://m365princess.com/putting-some-fun-into-azure-functions-managed-identity-and-microsoft-graph/)
