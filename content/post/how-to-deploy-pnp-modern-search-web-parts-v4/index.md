---
title: "How to Deploy PnP Modern Search Web Parts v4"
date: 2021-07-27T08:19:00-04:00
author: "Agnes Molnar"
githubname: aghyyy
categories: ["Community post"]
images:
- images/pnp-modern-search-sharepoint-app-catalog-01-1024x834.png
tags: ["PnP Modern Search", "SharePoint"]
type: "regular"
---

If you use Microsoft 365 (Office 365), you probably have been using
[Microsoft Search](https://searchexplained.com/microsoft-search/), too.
But there might be use cases, when it's not enough - for example, when
you need a customized Search Application. If this is the case, your
number one option might be to deploy [PnP Modern Search Web
Parts](https://github.com/microsoft-search/pnp-modern-search). This is
an open source solution that helps you to build customized search
applications in SharePoint Online modern experience.
[However, this solution has to be deployed manually to your tenant.
Let's see how.]

## 1 - Download the PnP package


You can download the [latest releases](https://github.com/microsoft-search/pnp-modern-search/releases/).


You'll see there are two major versions: v3 and v4. Important notes:


-   **The v4 version uses a brand new code architecture and replaces the
    older v3 codebase**. There will be no new features added to v3.x
    anymore, but bug fixes will be provided as needed.
-   Because v4.x is not at feature parity yet with v3.x, you can still
    use the v3.x packages to meet your requirements.
-   Also, **there is not an auto-upgrade path from v3 to v4** due to the
    new architecture.
-   New search functionality backed by the Microsoft Graph Search API
    will be v4 only.

**If this is the first time you install PnP Modern Search, always go for
v4.**
On the Releases page, scroll down to Assets, and then select  the
.sppkg file:



**Note**: *If you've installed the 2021 Jan release of v4, you had to
deploy two packages, because the extensibility library was a separate
.sppkg file. With the 2021 March release, there's only one package, the
team has replaced the extensibility library dependency by an [npm
package](https://www.npmjs.com/package/@pnp/modern-search-extensibility).
Now you only need to deploy one SPFx solution in you app catalog.*

## 2 - Deploy the PnP Modern Search package to your tenant's App Catalog 

App Catalog is a special site collection in SharePoint, that stores the
apps for your organization' use. If you have an existing App Catalog,
you can [deploy the PnP Modern Search package
there](https://searchexplained.com/deploy-pnp-modern-search-web-parts-sharepoint-online/#deploy-pnp).
Otherwise, you have to create a new App Catalog.

### 2.1 - Create a new App Catalog 

You have to be a tenant administrator to create a new App Catalog.

Go to Microsoft 365 Admin / SharePoint Admin Center. On the left menu,
select  "More features", and the select "Apps":
![pnp-modern-search-sharepoint-app-catalog-01-1024x834](images/pnp-modern-search-sharepoint-app-catalog-01-1024x834.png)
Once here, select  New App Catalog, then fill in the form, so that the
new site collection will be created:
 

![pnp-modern-search-sharepoint-app-catalog-02-1024x535](images/pnp-modern-search-sharepoint-app-catalog-02-1024x535.png)

### 2.2 - Deploy the PnP Modern Search Package 

Once your App Catalog is done, or you have one that has been created
earlier, open its URL and then select  "Apps for SharePoint":

![pnp-modern-search-sharepoint-app-catalog-03-1024x553](images/pnp-modern-search-sharepoint-app-catalog-03-1024x553.png)

On this screen, select  Upload, then choose the PnP Modern Search
package file which you downloaded above.


![pnp-modern-search-sharepoint-app-catalog-04-1024x652](images/pnp-modern-search-sharepoint-app-catalog-04-1024x652.png)

When you're asked if you trust PnP Modern Search Web Parts, select the
checkbox if you want to deploy it to all site collections, otherwise
leave it unchecked if you need it on a few selected sites only. Then
select Deploy:

![pnp-modern-search-sharepoint-app-catalog-05](images/pnp-modern-search-sharepoint-app-catalog-05.png)

Once done, you should see the PnP Modern Search Web Parts in the App
Catalog:

![pnp-modern-search-sharepoint-app-catalog-06-1024x274](images/pnp-modern-search-sharepoint-app-catalog-06-1024x274.png)

## 3 - Enjoy

Now, go to any (modern) site on your tenant (in a site collection where
you've deployed PnP Modern Search above), and edit the page. In the web
parts list, search for "PnP", and you'll see the PnP Modern Search Web
Parts there:

![pnp-modern-search-v4-webparts](images/pnp-modern-search-v4-webparts.png)


*This article was originally posted on [Search Explained
Blog](https://searchexplained.com/deploy-pnp-modern-search-web-parts-sharepoint-online/).*
