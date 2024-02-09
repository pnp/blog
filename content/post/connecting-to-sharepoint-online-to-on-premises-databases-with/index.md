---
title: "Connecting to SharePoint Online to On-Premises Databases with SharePoint Framework"
date: 2021-10-18T04:08:00-04:00
author: "Simon Doy"
githubname: SimonDoy
categories: ["Community post"]
tags: ["SharePoint Framework (SPFx)"]
type: "regular"
---

## Introduction

Recently we seem to be getting involved in projects after they have gone
awry. One of our partners reached out asking for help with an issue they
had whilst migrating a SharePoint 2010 environment to SharePoint Online.
The problem was that the customer made extensive use of Dataview Web
parts with their SharePoint 2010 environment. These web parts displayed
important information used by the business. The Dataview Web parts are
connected directly to a SQL server hosted within the customer database.
Of course, when the web parts were migrated into the cloud, they did not
work as they were unable to connect to the SQL Server. This ended up
stopping the migration until a solution was found.
The customer did not want to move the data into the cloud due to several
reasons but the most important one being all of the other systems
dependent on it.
Several options were discussed which will be covered in the next
section.
 
 
## The approach

So several options were looked at, and as moving the database was
quickly ruled out, we came up with these two:

-   Build a solution with Power Apps and use the On-Premise data gateway.
-   Build a solution with SharePoint Framework using a REST API using
    Azure Hybrid Connections
Whilst the Power Apps solution would take less time, the licensing cost
of the Power Apps solution ended up ruling it out due to its total cost
of ownership (TCO).
So, the SPFX solution was chosen. The architecture was to use SPFX web
parts that connected to a REST API hosted in Azure App Services. The
clever part was using [Azure App Service Hybrid
Connections](https://learn.microsoft.com/azure/app-service/app-service-hybrid-connections) which
allowed us to connect from Azure back into the customer network without
the need to reconfigure complex firewalls.
 
To help visualize the solution, let's take a look at the architecture.
![The architecture overview of the solution](images/image-5.png)

We ended up having two [Azure Hybrid Connection
Services](https://learn.microsoft.com/azure/app-service/app-service-hybrid-connections) running.
One for the active live environment and another for the disaster
recovery environment.
The data being accessed was sensitive so the REST API had to be secure.
It was configured so that it was backed by Azure AD using an Azure AD
Application, implemented with OAuth authentication using JWT Bearer
tokens. The SPFX connected to the REST API and authenticates using Open
Id Connect to ensure that only authenticated and authorized users can
access the API. Further protection was provided by setting the API
behind Azure API Management.
 
### Authentication

For the SharePoint Framework web parts to be able to authenticate with
the REST API there are a couple of steps that need to be performed:

-   Configure the SharePoint Framework solution to request permission to
    access the REST API
-   Authorize the request made by SharePoint Framework to access the
    REST API.
To configure the SharePoint Framework solution take a look at [this
Microsoft
post](https://learn.microsoft.com/sharepoint/dev/spfx/use-aad-tutorial#configure-the-api-permissions-requests) which
provides a good guide (see section Configure the API Permission
Requests).
The second part is performed by going into the SharePoint Admin centre
and approving the request. Now the point to make is that the user
accepting the request needs to be a SharePoint Administrator and also
grant admin consent to Azure AD Applications. Basically, a Global Admin
has this role, so we worked with the IT team to ensure a privileged user
did the authorization. Be mindful of this when deploying to the customer

![The steps to authorize accessing an API in SharePoint Online.](images/image-6.png)
 
The screen to authorize SharePoint Framework solutions.
 
Another point to make here is that the name of the Azure AD Application
configured in the SharePoint Framework needs to use the name of the
Azure AD Application configured in Azure AD. This is configured as
mentioned above in the SharePoint Framework solution. When I first
looked at this I set the resource to be the ***resourceid*** for the
Azure AD Application rather than the name of the application.
Hopefully mentioning this will mean you do not waste your time getting
this right.

``` wp-block-code
"webApiPermissionRequests": [
      {
        "resource": "HROnline Api",
        "scope": "user_impersonation"
      }
]
```

### Azure Hybrid Connections

The Azure Hybrid Connection is set up in two places.

-   Azure App Service hosted in the cloud
-   Hybrid Connection service -- running as a Windows server within the
    network.
The hybrid connection service establishes a connection to the Azure App
Service through Azure Relay which is built on top of Service Bus.

![Diagram explaining the architecture of Azure Hybrid Connections.](images/hybridconn-connectiondiagram.png)

 
To set up the Hybrid Connection in Azure App Service you must be running
at least the Basic Tier or above.
There are some limitations to the types of connections that the
technology supports. The transport mechanism needs to be TCP based and
does not support UCP. For this solution, a .NET SQL Client was used
which is supported and works really well.
For information on setting up the Azure Hybrid Connection see the
following [Microsoft article](https://learn.microsoft.com/azure/app-service/app-service-hybrid-connections).
 
### Performance

One of the areas that we wanted to ensure was the performance of the
application. So we put together a POC was put together to prove the
approach and also check performance. The performance has been very good
and provided that the REST API is developed with some thought, it
performed better than expected.
There was plenty of thought that went into the API. A few of the
optimizations we made were

-   making sure that we had support for paging and limiting the number
    of records retrieved at one time.
-   Using Dapper and performing filtering at the SQL layer rather than
    pulling the data down and filtering in the API

## Conclusion

This solution enables SharePoint Online solutions to access data hosted
On-Premises in a secure manner which is very effective. I was surprised
by how well the solution performed.
 
