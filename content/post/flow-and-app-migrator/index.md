---
title: "Migrate Cloud Flows and Canvas Apps across tenants"
date: 2022-03-10T22:29:00-04:00
author: "Denis Molodtsov"
githubname: zerg00s
categories: ["Community post"]
images:
- images/flow-migrator.jpg
tags: ["Power Apps", "Power Automate",  "SharePoint", "DataVerse"]
type: "regular"
---

## Introduction

If you are a Power App or Power Automate developer, chances are you had to move your creations between SharePoint sites or even Microsoft 365 tenants. At the very least, you were probably wondering about the easiest ways of doing it. Perhaps, you were trying to establish separate development, staging and production environments. Or you wanted to share your solution with a client or a friendly department within your organization.

If you are using [Solutions](https://docs.microsoft.com/powerapps/maker/data-platform/solutions-overview) and [Dataverse](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro) for your development, chances are these migrations are not very difficult. A combination of [environment variables](https://docs.microsoft.com/powerapps/maker/data-platform/environmentvariables) and the **Dataverse** tables, takes care of most complexities including packaging data sources and parametrization

This is why it is recommended to always develop apps and flows as part of a **solution** as opposed to standalone ones. **Solutions** allow us to expose all configurations via environment variables.

However, **solutions** are not used every time for one reason or another. On top of it, the majority of apps and flows are still using SharePoint lists and libraries as a data source instead of **Dataverse** tables. 

As a result, you will still face a few challenges when migrating:

- SharePoint lists need to be migrated separately since they are not packaged within a Power Platform solution.
- Site and list URLs need to be replaced manually after migration.

## About Flow and App Migrator

**[Flows and Power Apps Migrator](https://github.com/Zerg00s/FlowPowerAppsMigrator)** is an open-source portable tool that lets you migrate apps and flows that primarily use **SharePoint** as a data source. With it:

- You can continue developing with or without solutions and environment variables. 
- Don't have to worry about hardcoded SharePoint URLs.
- Don't have to migrate SharePoint lists, libraries and content types. The tool does it for you.

## Using Flow and App Migrator

- Navigate to [https://github.com/Zerg00s/FlowPowerAppsMigrator](https://github.com/Zerg00s/FlowPowerAppsMigrator)
- Download the [latest release](https://github.com/Zerg00s/FlowPowerAppsMigrator/releases)
- Extract the ZIP package
- Export your flows, apps and solutions to the `src` folder:

    ![Exporting a Package as .ZIP](images/export.png)
     
    ![Exporting Apps](images/export-apps.png)
    
    ![The source](images/src.png)
    
    ![Migrate Packages.bat](images/contents.png)


- Launch on `Migrate-Packages.bat` file.

    ![The Flow and Power App Migrator splash screen](images/app.png)

- Enter source site URL and target site URL.

    ![Enter source and target site](images/dialog.png)

- Select **OK**.
- Select lists and libraries to migrate. These are dependencies used by your flows and apps.

    ![Select lists and libraries to migrate](images/lists.png)

- Select **OK**. Sit back and wait for the lists and libraries to be migrated and the conversion process to finish.

- Navigate to the `dist` folder and collect converted flows, apps and solutions

    ![The dist folder containing converted flows, apps, and solutions](images/dist.png)

- Now go ahead and import your flows and apps to the destination tenant or environment. All SharePoint actions are now be converted and point to the new SharePoint location. You will also notice that SharePoint dependencies were migrated.

    ![All SharePoint data sources converted with a smiley](images/converted.png)

## Bonus: Preparing a deployment package for your clients and partners

### On your end

- Run `Prepare-Deployment-Package-for-Client.bat` to create a **deployment package** that you can share with your clients or partners. This script will generate a `package` folder on disk.

- Export your solutions, apps and flows and save them to the `package\src` folder.

    ![Exported solutions, apps, and flows to the package/src folder](images/client-package.png)

- Send the `package` folder to your client or partner.

### On the client's side

- If not already exists, create a SharePoint Online site. It will contain SharePoint Lists and Libraries that Power Apps/Flows require.
- Open the `package` directory.
- Run the `Convert-Packages.bat` script. 
- Provide a target site URL.
- Import all solutions, flows and apps from the `dist` directory.

## Credits to the PnP PowerShell team

Behind the scenes, Flow and Power Apps migrator uses a [PowerShell PnP module](https://pnp.github.io/powershell) for exporting and importing provisioning templates.

## Conclusion

As you can see, Flow and Power Apps Migrator makes your  migration process simpler. Likewise, a deployment process for your clients is significantly simplified.
