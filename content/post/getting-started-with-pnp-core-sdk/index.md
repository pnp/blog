---
title: "Getting started with PnP Core SDK"
date: 2021-03-15T01:55:00-04:00
author: "Paul Bullock"
githubname: pkbullock
categories: ["Community post"]
tags: ["PnP Core SDK"]
type: "regular"
---


## Introduction

PnP Core SDK is a library designed to help you work with Microsoft 365
services in your .NET projects, this currently focuses on SharePoint and
Teams as part of the V1.0 GA release. The PnP Core SDK is the successor
to the PnP-Sites-Core project - the library that underpins well known
tools such as the PnP Provisioning Engine and PnP PowerShell, and is
designed to use the latest development techniques and standards such as:

-   **.Net 5 and .Net Standard 2.0 support** -- this has cross-platform
    support allowing you to build solutions for a wider range of
    platforms, greater performance, and a larger range of APIs.
-   **Unified object model** - obscures the underlying API used to
    retrieve the data, so from a developer point of view, the SDK
    handles determining the best API to use e.g., Graph, SharePoint,
    REST or CSOM meaning *you can focus on writing your business logic*
    rather than dealing with working with the various APIs to access the
    features you need to consume. This yields a significantly faster
    response and huge performance benefits over the older CSOM method
    accessing SharePoint.
-   **Batching support** at the API level to reduce the calls to the
    service with retry logic to handle cases such as service throttling.

## Improved Quality

The PnP Core SDK has a strong focus on quality, to help reduce bugs and
issues, provide developers with better support working with the SDK,
concentrating, and building on the following points:

-   **Unit testing** -- with a project goal to maintain over **80% of
    the SDK covered by unit tests**, we also as part use a new mocking
    framework that allows us to perform rapid tests without the
    dependency of the underlying services.
-   **Improved documentation** -- we have built [a portal that contains
    all the API documentation](https://aka.ms/pnp/coresdk/docs), how to
    use the SDK and perform common operations with sample code to help
    developers use the SDK in their business logic.
-   **Samples** -- a [range of
    samples](https://pnp.github.io/pnpcore/demos/README.html) initially
    focusing on, Console App, Web App, Azure Functions, Blazor, WPF and
    even an example on a Raspberry Pi -- each demonstrating a working
    example using the SDK interacting with Microsoft 365 services.
-   **Contributor guidance** -- we have included [support documentation
    for
    contributors](https://pnp.github.io/pnpcore/contributing/readme.html)
    to explain, how to get setup, how to extend the models that work
    with SharePoint and the Graph, writing unit tests and supporting
    documentation.
This is a starting point, and we are actively working on better ways of
supporting developers with the use of the SDK and testing to ensure that
SDK maintains a high standard of quality -- of course, we welcome any
feedback, issues, suggestions from the community, ***all are
welcome***.

## Getting started building an app

We are next going to show you, the simplest method of creating a console
app that interacts with Microsoft 365, provides you with a login window,
and creates a page in SharePoint using the awesome support for working
with Modern Pages in the PnP Core SDK.
 
But before we start writing the application, we are going to need to
setup a few things in Azure and SharePoint:

### SharePoint Site

For the purposes of this example, we will use a Microsoft 365 Group
connected team, please sure that you set one up for the application to
connect to.

### Azure AD App

The application uses Azure AD app to authenticate into the services
required, for this you we recommend creating your own Azure AD app, and
there are tools that can assist with this either the [Microsoft 365
CLI](https://pnp.github.io/cli-microsoft365/user-guide/using-own-identity/#register-azure-ad-application-in-your-tenant),
[PnP
PowerShell](https://learn.microsoft.com/powershell/module/sharepoint-pnp/register-pnpazureadapp?view=sharepoint-ps)
are great at making it easy to setup your own Azure AD Apps --
additionally, [we also have documentation to help set up the
app](https://pnp.github.io/pnpcore/using-the-sdk/configuring%20authentication.html).
Make sure you take a note of the Azure AD app - Application Id, you will
need this later.
 
If you want to test the app first, we recommend setup of a "dev" tenant
to test the application in a non-production environment -- check out
[this article to understand on how to get a free developer tenant from
Microsoft](https://techcommunity.microsoft.com/t5/microsoft-365-pnp-blog/what-is-a-dev-tenant-and-why-would-you-want-one/ba-p/2036610).

### Building the Application

So, let's get going with using the SDK, so for this next section, we
will show you how to get going in Visual Studio (btw, Visual Studio Code
supported as well), to get the packages and connect to the Microsoft 365
Services using a C# Console Application.
 
Note: If you do not have visual studio, and you are using this for
academic, open-source, or personal usage, you can [download Visual
Studio Community edition](https://visualstudio.microsoft.com/vs/) to get
going, this blog is using Visual Studio 2019, version V16.9.
 
In Visual Studio, create a new C# Console Application (.NET core),
 
![Create a new visual studio project](images/Create a new project.png)

(Note: I have filtered the list using the dropdowns to find the project
type quickly)

Select Next, and Enter Project Name, Location and Solution Name as your
discretion,

Under additional information, please select .NET 5.0 as the Target
Framework
![Visual studio - select .NET version](images/additional information.png)


Visual Studio will create a hello world project for you, as a starting
place.
Next we, want to get the NuGet package for the PnP Core SDK, [NuGet is a
package manager tool](https://www.nuget.org/) that by Microsoft is an
essential tool in modern development that allows you to download,
create, share, useful libraries and packages to use in your .NET
projects -- [this is where the PnP Core SDK packages are published
to](https://www.nuget.org/packages?q=PnP+Core+SDK).
Continuing in Visual Studio, right select  the solution and find the
"Manage NuGet Packages for Solution" option.

![Option to manage NuGet packages in the solution right-select menu](images/Manage Nuget.png)

When the package manager opens, Select to Browse for Packages and Enter
"PnP Core SDK" in the search bar, to show the two packages described
earlier.

![Find the PnP Core SDK NuGet packages](images/Nuget Packages.png)

### About the versions and libraries

When searching for the NuGet packages you will see two options, these
options are:

-   **PnP.Core** -- this includes the core library that interacts with
    the Microsoft 365 workloads such as SharePoint and Microsoft Graph.
-   **PnP.Core.Auth** -- includes the authentication library providing
    multiple methods in which to securely connect to Microsoft 365 using
    Azure Active Directory - this *includes PnP.Core as a dependency*.
    In most cases, you will only need to use this one to get started.

You will need an additional NuGet Package called
"Microsoft.Extensions.Hosting" -- this allows us to manage the services
in the lifetime of running the app. For further information, [please
refer the documentation around the generic host
library](https://learn.microsoft.com/dotnet/core/extensions/generic-host).
With regards to the way versioning is done for the SDK, there are major
releases which currently is v1.0.0 and nightly releases e.g.,
v1.0.1-nightly which are the prerelease versions allowing you to use the
very latest build this would include any fixes and new features.

![PnP Core SDK release versions](images/SDK Release versions.png)

### Let's start writing some code

Once you have added the NuGet packages, open the ***program.cs*** file,
this is the entry point that the application runs calling on the Main
method, we need to add code to this to configure the connection to
Microsoft 365 services and perform the page operations.
Change the ***program.cs*** file using the following code:
 

```csharp
using System;

// Add the relevant using statements for PnP Core
using Microsoft.Extensions.DependencyInjection;
using Microsoft.Extensions.Hosting;
using PnP.Core.Model.SharePoint;
using PnP.Core.Services;
using System.Threading.Tasks;
using PnP.Core.Auth;

// Ensure you have added the NuGet packages
//  - PnP.Core.Auth
//  - Microsoft.Extensions.Hosting

namespace GettingStartedConsoleApp
{
    class Program
    {
        // Update main method for asynchronous
        static async Task Main(string[] args)
        {
            // Setup the host
            // This app uses interactive login

            var host = Host.CreateDefaultBuilder()

            .ConfigureServices((hostingContext, services) =>
            {
                //    Add the PnP Core SDK library services
                services.AddPnPCore(options => {

                    options.DefaultAuthenticationProvider = new InteractiveAuthenticationProvider(
                            "f8023692-08de-48ea-8bef-d987f10e08d2", // Client Id
                            "contoso.onmicrosoft.com", // Tenant Id
                            new Uri("http://localhost"));  // Redirect Id
                });
            })

            // Let the builder know we're running in a console
            .UseConsoleLifetime()
            // Add services to the container
            .Build();

            // Start console host
            await host.StartAsync();

            // Connect to SharePoint
            using (var scope = host.Services.CreateScope())
            {
                // Obtain a PnP Context factory
                var pnpContextFactory = scope.ServiceProvider.GetRequiredService<IPnPContextFactory>();
                // Use the PnP Context factory to get a PnPContext for the given configuration
                using (var context = await pnpContextFactory.CreateAsync(new Uri("https://contoso.sharepoint.com/sites/pnpcoresdktestgroup")))
                {
                    var web = await context.Web.GetAsync();
                    Console.WriteLine($"Title: {web.Title}");

                    // Create the page
                    var page = await context.Web.NewPageAsync();

                    // Configure the page header
                    // Check out for more detail https://pnp.github.io/pnpcore/using-the-sdk/pages-header.html
                    page.SetDefaultPageHeader();
                    page.PageHeader.LayoutType = PageHeaderLayoutType.CutInShape;
                    page.PageHeader.ShowTopicHeader = true;
                    page.PageHeader.TopicHeader = "Welcome";
                    page.PageHeader.TextAlignment = PageHeaderTitleAlignment.Center;

                    // adding sections to the page
                    page.AddSection(CanvasSectionTemplate.OneColumn, 1);

                    // Adding text control to the first section, first column
                    // Check out for more detail https://pnp.github.io/pnpcore/using-the-sdk/pages-webparts.html#working-with-text-parts
                    page.AddControl(page.NewTextPart("<p style="text-align:center">" +
                                                        "<span class="fontSizeSuper">" +
                                                            "<span class="fontColorRed">" +
                                                                "<strong>PnP Core SDK Rocks!</strong>" +
                                                            "</span>" +
                                                        "</span>" +
                                                     "</p>"), page.Sections[0].Columns[0]);

                    // Save the page
                    await page.SaveAsync("Awesomeness.aspx");

                    // Publish the page
                    await page.PublishAsync();
                }
            }

            // Cleanup console host
            host.Dispose();
        }
    }
}
```
 

In the above sample, we look through the sections of the code:
**Async** -- the PnP Core SDK is designed to work asynchronously, so we
need to update the main method to include the "async" keyword and "Task"
return type to allow the code inside to run.
 

```csharp
 // Update main method for asynchronous
 static async Task Main(string[] args)
```
 

**\
Configure Host ­**-- This block creates and configures the host to run
the application, this adds references to the PnP Core SDK, configures
the default authentication method, as the simplest method of connecting
to Microsoft 365 services, there are other ways to implement this, such
as using an *appsettings.json* file or inline code, if you want more
information about this - [the PnP Core SDK documentation site contains
the additional
instructions](https://pnp.github.io/pnpcore/using-the-sdk/configuring%20authentication.html#configuring-pnp-core-sdk-to-use-the-configured-application).
 

```csharp
// Setup the host
// This app uses interactive login

var host = Host.CreateDefaultBuilder()

.ConfigureServices((hostingContext, services) =>
{
  //    Add the PnP Core SDK library services
 services.AddPnPCore(options => {

    options.DefaultAuthenticationProvider = new InteractiveAuthenticationProvider(
        "f8023692-08de-48ea-8bef-d987f10e08d2", // Client Id
        "contoso..onmicrosoft.com", // Tenant Id
        new Uri("http://localhost"));  // Redirect Id
    });
 })

 // Let the builder know we're running in a console
 .UseConsoleLifetime()
 // Add services to the container
 .Build();

 // Start console host
 await host.StartAsync();
```
 

Note, the client ID shown above is the same as the ID as the Azure AD
app, you set up earlier.

**\
Setup Context** -- This block will create a context to connect to
SharePoint supplying the URL to the site this will use the default
authentication provider specified earlier -- on running the app, this
will open a window or tab to allow you to interactively log into your
tenant. When authenticated, you are returned a context to perform
further options using the connection.
 

```csharp
// Connect to SharePoint
using (var scope = host.Services.CreateScope())
{
   // Obtain a PnP Context factory
   var pnpContextFactory = scope.ServiceProvider.GetRequiredService<IPnPContextFactory>();

  // Use the PnP Context factory to get a PnPContext for the given configuration
  using (var context = await pnpContextFactory.CreateAsync(new Uri("https://contoso.sharepoint.com/sites/pnpcoresdktestgroup")))
  {
```
 

**\
Make a page** -- Now that you have connected and you have a context
object, you can set to write code that interacts with the service.
 

```csharp
// Create the page
var page = await context.Web.NewPageAsync();

// Configure the page header
// Check out for more detail https://pnp.github.io/pnpcore/using-the-sdk/pages-header.html
page.SetDefaultPageHeader();
page.PageHeader.LayoutType = PageHeaderLayoutType.CutInShape;
page.PageHeader.ShowTopicHeader = true;
page.PageHeader.TopicHeader = "Welcome";
page.PageHeader.TextAlignment = PageHeaderTitleAlignment.Center;

// adding sections to the page
page.AddSection(CanvasSectionTemplate.OneColumn, 1);

// Adding text control to the first section, first column
// Check out for more detail https://pnp.github.io/pnpcore/using-the-sdk/pages-webparts.html#working-with-text-parts
page.AddControl(page.NewTextPart("<p style="text-align:center">" +
                                   "<span class="fontSizeSuper">" +
                                      "<span class="fontColorRed">" +
                                         "<strong>PnP Core SDK Rocks!</strong>" +
                                      "</span>" +
                                   "</span>" +
                                "</p>"), page.Sections[0].Columns[0]);

// Save the page
await page.SaveAsync("Awesomeness.aspx");

// Publish the page
await page.PublishAsync();
```
 

The code fragment is a simple example of using the Modern Pages support,
by doing the following:

-   Creating a modern page
-   Setting the header of the page
-   Adds a one column section to the page
-   Adds a text web part to the page with some simple formatting, to the
    new section in the first column.
-   Saving the page
-   Publishing the page

If you want to dive deeper into [how to use the SDK when working with
Modern
Pages](https://pnp.github.io/pnpcore/using-the-sdk/pages-intro.html),
there is documentation on the site that covers adding web parts,
configuring the header, publishing and promoting pages and multi-lingual
support.
Once written, Hit F5, log in and see the result:

![Resulting page creation by the console app](images/result.png)

## What's Next

So, you have written the app, what's next, if you want a further
examples and a video walkthrough, checkout the short video by Paolo
Pialorsi (one of the major authors of the SDK) on PiaSys Tech Bites, 
"Welcome PnP Core SDK" with a fantastic demo (no spoilers here) -
<https://www.youtube.com/watch?v=ozqN5-Yh5cM>

**Check out these great resources to help you build your solutions:**

-   For understanding how the PnP Core SDK fits in the picture of the
    wave of uplifts by the team check out - [How the new wave of
    libraries from Microsoft 365 PnP will change the way you modernize
    SharePoint
    (p\...](https://practical365.com/blog/how-the-new-wave-of-libraries-from-microsoft-365-pnp-will-change-the-way-you-modernize-sharepoint/)
-   The PnP Core SDK site with guidance on using the SDK, API level
    documentation, how to contribute and samples - [Getting started with
    the PnP Core SDK | PnP Core SDK](https://aka.ms/pnp/coresdk/docs)
-   Want to contribute, have an issue, bug, feature suggestion -- please
    engage with using the project site on GitHub - [pnp/pnpcore |
    github.com](https://github.com/pnp/pnpcore)

There is still plenty to do in the SDK, if you want to contribute to
this open source repository, you are most welcome to, [we have tagged
areas in the issues
list](https://github.com/pnp/pnpcore/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22)
for areas we are looking for help with, please reach out either on
social media, via GitHub to connect and support you getting started.

**Enjoy!**
