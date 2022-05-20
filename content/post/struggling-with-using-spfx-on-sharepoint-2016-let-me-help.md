---
title: "Struggling with using SPFx on SharePoint 2016? Let me help!"
date: 2021-07-02T03:20:00-04:00
author: "Kirk Liemohn"
categories: ["Community post"]
images: []
tags: []
type: "regular"
---

SharePoint has a lot of great out-of-the-box capabilities, but sometimes
you need to take it a step further.  For example, you need a custom user
interface to improve productivity.
The SharePoint Framework (aka
[SPFx](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview))
is a great way to customize SharePoint and Teams. There have been
various ways to customize SharePoint in the past, but SPFx is the
recommended option.  This is especially true for SharePoint Online, but
also for more recent versions of SharePoint on-prem.  What I like about
SPFx -- beyond the fact that it lets you customize SharePoint - is that
there are several [web
controls](https://developer.microsoft.com/fluentui#/controls/web)
that are ready to use and require very little effort to incorporate into
your customizations.  Not only do these components function well, they
also fit the look and feel of SharePoint today.
SPFx is supported with SharePoint 2019 and SharePoint 2016 (with feature
pack 2), but there are limitations to both.  This post focuses on the
limitations with SharePoint 2016 which are more restrictive than
SharePoint 2019.  In addition, some of the details I provide will be
specific to my development environment which runs on Windows 10.

## Confused Yet?

I think part of the confusion on developing with SPFx on SP2016 is
because SP2016 hasn't changed in years, but SPFx is constantly
changing.  The documentation on what to use with SP2016 is pretty old
and hasn't kept up. For example, to get started with SPFx on SharePoint
2016, this seems like the logical place: [SharePoint Framework
development with SharePoint Server 2016 Feature Pack
2](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-2016-support). 
The web page was updated within the last month of when I wrote this
post.  However, the video shown is from 2017.  In the video, Vesa
recommends version 1.0.2 as the SPFx version and the post mentions
version 1.1.0.  What worked for me (more details below) was version
1.9.1.
What made this more confusing to me is that there were other blog posts
indicating you can use *any* version of key dependencies:

-   [Build SharePoint Framework solutions for on-premises SharePoint
    with ANY version of React,
    TypeScrip\...](https://spblog.net/post/2019/08/08/build-sharepoint-framework-solutions-for-on-premises-sharepoint-with-any-version-of-react-typescript-or-office-ui-fabric-react)
-   [Yes, you can use Modern React on SharePoint
    2016](https://blog.pathtosharepoint.com/2021/01/28/yes-you-can-use-modern-react-on-sharepoint-2016/)
-   [SharePoint 2016, 2019 & SharePoint Online: Which Version of the
    SharePoint Framework Should You
    Inst\...](https://www.voitanos.io/blog/spfx-which-version-of-spfx-generator-to-install/)

That last post mentions version 1.9.1 of
@microsoft/generator-sharepoint,
which is what I used.  But it was the latest at the time of that post. 
I had trouble with later versions, which it recommended (but did caveat
that they may not work).  Your mileage may vary.

## Multiple Paths Forward and Limitations

I definitely recommend checking out the links above to see if they work
for you.  If they don't, then hopefully the steps I outline below will
work.  It's hard to sound too confident because others sounded confident
in the posts above.  They clearly worked for them, but didn't work for
me.  Maybe it was user error, but who knows what else will change going
forward that may somehow cause issues.
Whenever deciding on what versions to use, a good resource to use is:
[SPFx Compatibility
Matrix](https://tahoeninjas.blog/2019/12/30/spfx-compatibility-matrix/).
Depending on the path you take may change your limitations, but here are
some I know of:

-   You can only create [web
    parts](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/overview-client-side-web-parts),
    not
    [extensions](https://docs.microsoft.com/sharepoint/dev/spfx/extensions/overview-extensions).
-   You cannot bundle your assets with the package (sppkg) file.  You
    must host your assets (manifest JSON and JavaScript files) in a
    SharePoint document library, Azure, or somewhere else.  I discuss
    how to do this further below.
-   Some [Fluent UI
    Controls](https://developer.microsoft.com/fluentui#/controls/web)
    won't work.  Based on the path I took (described below), There was
    no ComboBox, no PeoplePicker, and the Dropdown did not allow
    multi-select.  There are probably several other controls that aren't
    available, but I didn't need them, so I didn't check.  Of those that
    are available, the documentation has properties/capabilities that
    are newer than what I was able to use.  Sometimes I went to the old
    [Office UI Fabric
    React](https://docs.microsoft.com/javascript/api/office-ui-fabric-react?view=office-ui-fabric-react-latest)
    documentation, but even then that was sometimes too new for what I
    was using.
-   I was unable to use [React
    Hooks](https://reactjs.org/docs/hooks-intro.html) and had to use the
    [React component
    class](https://reactjs.org/docs/react-component.html).  React hooks
    were introduced in React 16.8.  I'm using React 15.4.2.  This may be
    why some newer Fluent UI controls cannot be used.

## Prerequisites

Regardless of the approach you take, everyone appears to agree on the
prerequisites:

-   SharePoint Server 2016
-   Feature Pack 2 Installed

To check to see if Feature Pack 2 is installed, I went to [Feature Pack
2 Required to Install ShortPoint SPFx on SharePoint 2016
On-premise](https://support.shortpoint.com/support/solutions/articles/1000181281-shortpoint-farm-solution-installation-and-upgrade-sharepoint-on-premise-2013-and-2016). 
There may be better articles out there.  Two key parts of this that
helped me were:

-   If you don't see \"Manage Patch Status\", look for \"Check
    Production and Patch Installation Status\".
-   For \"Microsoft SharePoint Foundation 2016 Core\", you are looking
    to see if there is an item with a version number \>= 16.0.4744.1000
    with a status of Installed.  If not, you'll need to install Feature
    Pack 2 as the link above describes.

## Node v8.17.0 (Recommended: Install NVM for Windows)

If you're developing SPFx for SharePoint Online or SharePoint 2019 in
the same development environment, you'll need to maintain multiple
versions of node.  A great way to do that is with
[nvm-windows](https://github.com/coreybutler/nvm-windows).
After installing nvm-windows, you need to install and use node version
8.17.0: 
 
```bash
nvm install 8.17.0
nvm use 8.17.0
```
 
Then you can check the active version of node with: 
 
```bash
nvm list
```
 
Note: if you don't want to install nvm and just want to install node,
you can get version 8.17.0 from here: [Index of /dist/latest-v8.x/
(nodejs.org)](https://nodejs.org/dist/latest-v8.x/).  If you have
installed node directly, you can check the version using: 
 
```bash
node -v
```
 
## Install NPM Packages

Before installing other packages, I wanted to check on the version of
npm.  I did this with: 
 
 

```bash
npm -v
npm list g --depth 0
```
 
 

Both v3.10.10 and v6.13.4 of npm worked for me.
Then I installed a specific version of gulp, yeoman generator, and
generator-sharepoint: 
 
```bash
npm install -g gulp@3.9.1
npm install -g yo@1.8.5
npm install -g @microsoft/generator-sharepoint@1.9.1
```
 
 

Installing gulp may not be required, but it helps to have gulp at the
ready from the command line.  Otherwise you may need to play with the
path or add scripts to package.json to call gulp for you while you do
something like: npm run \<my-script>
Regarding v1.9.1 of generator-sharepoint, it could be that a later
version works for you.  This worked for me and v1.12.0 did not work for
me.  Maybe something in between is a better choice.

## Generate Your Project

This is old hat for many, but for those not used to it, I'll spell out
some details...
Create a directory for your web part project and cd into that
directory.  This could be the name of your solution or even just
"WebParts".  Think about how you want to organize your code.  Do you
want a separate solution per web part or do you want to be able to have
several web parts within one project in the future.  The former makes it
so a change to one web part does not require all to be re-deployed.  The
latter allows the web parts to have shared components.  You generate the
project with:
 
```bash
yo @microsoft/sharepoint
```
 
Then you answer several questions.  Here are some example answers:

|||
|--- |--- |
|What is your solution name?|Hello World SPFx 2016|
|Which baseline packages do you want to target for your component(s)?|SharePoint 2016 onwards, including 2019 and SharePoint Online|
|Where do you want to place the files?|Use current folder|
|Which type of client-side component to create?|WebPart|
|What is your Web part (on-prem) name?|HelloWorld|
|What is your Web part (on-prem) description?|A sample web part|
|Which framework would you like to use?|React|

## Test Your Project in the SharePoint Workbench

Even though you haven't done much yet, your project should run.  To run
the workbench you would normally do a "gulp serve", but since we're
stuck in version 8 of node, we need to [Run gulp serve with
'NODE_NO_HTTP2=1' when using SPFx on node
v8](https://github.com/SharePoint/sp-dev-docs/issues/1002):
 
```bash
set NODE_NO_HTTP2=1 && gulp serve
```
 
Note that the command above looks a little different when run on a Mac.
From the resulting web page that pops up, you should be able to see your
web part and edit the web part property.

## Minor Cleanup

The yeoman generator does a great job, but it does make some assumptions
that aren't ideal.  One is the solution name could be friendlier.  This
shows when you are adding the solution to App Catalog (discussed
below).  To fix this, go into config\\package-solution.json and change
the **solution** **name** to be a friendlier name.  You can use spaces
instead of dashes and feel free to capitalize the first letter of each
word.  You can't use a period in the solution name, however.
 
```json
{
    "$schema": "https://developer.microsoft.com/json-schemas/spfx-build/package-solution.schema.json",
    "solution": {
        "name": "Hello World SPFx 2016",
        "id": "5d88310e-6651-4dc3-a80a-be165e851e9b",
        "version": "1.0.0.0"
    },
    "paths": {
        "zippedPackage": "solution/hello-world-spfx-2016.sppkg"
    }
}
```
 
 

Consider updating the group that is shown when adding a web part to a
page.  By default this is "Other".  The group name is defined in the web
part json file found at
src\\webparts\\\<web-part-name>\\\<web-part-name>WebPart.manifest.json. 
Change "Other" to any name you like.  You don't need to change the
groupId.
 
```bash
"preconfiguredEntries": [
    {
        "groupId": "5c03119e-3074-46fd-976b-c60198311f70", // Other
        "group": { "default": "Other" },
```

## Dev Test / Deploy

If your dev environment has access to the SharePoint 2016 server, you
can use the following steps:

-   ```bash
    gulp bundle
    gulp package-solution
    ```

-   Create an App Catalog: [Manage the App Catalog in SharePoint
    Server](https://docs.microsoft.com/sharepoint/administration/manage-the-app-catalog#:~:text=Add%20Apps%20to%20the%20App%20Catalog%201%20Verify,that%20you%20want%20to%20upload.%20...%20See%20More.). 
    Note that SharePoint Online allows apps to be uploaded to just a
    site collection, but in SP2016 you must have an App Catalog for the
    entire web application.

-   Upload your package to the app catalog.  Go into your app catalog,
    choose Upload, and pick the sppkg file from your
    sharepoint\\solution folder.  Notice how the trust dialog mentions
    <https://localhost:4321> because this is a dev deploy (further below
    we do a non-dev deploy with the \--ship flag).

-   select the Deploy button.  Notice that there is no tenant wide
    deployment of apps like there is in SharePoint Online.

-   Add the App to your site.  Go to the site where you want to deploy
    your app.  Go to Site Contents \> add an app.  Pick the name of your
    solution and wat for it to be enabled (no longer grayed out).

-   ```bash
    set NODE_NO_HTTP2=1 && gulp serve --nobrowser
    ```

-   Add your web part to a page.  Go to Site Contents \> Site Pages. 
    Add a page then go to Insert \> Web Part and pick the Other category
    (or whatever you renamed it to above) to find your web part.

-   Verify that your web part works.

## Test a Minor Change

With all of the potential problems around versioning of dependencies,
it's a good idea to take small steps.  Let's start with a small
change...
In your editor (you are using [VSCode](https://code.visualstudio.com/),
right?), edit
src\\webparts\\\<web-part-name>\\components\\\<web-part-name>.tsx and
make a simple change to the title text and save your changes.  If your
terminal is still running "gulp serve" as mentioned above, then you just
need to wait a few seconds and refresh your web page from the previous
section.  There is no need to re-deploy the sppkg file for simple code
changes.

## Incorporate Office Fabric

The yeoman generator does not have Office Fabric as part of it.  Here we
add that and do a small test that uses it:

-   Kill the "gulp serve" in your terminal window (CTRL-C)

-   ```bash
    npm install office-ui-fabric-rect@2.34.2​
    ```



    -   This is a critical step.  The new Fluent UI will not work -- we
        *must* use this version.
    -   This may be the first time doing an npm install can actually
        cause other issues.  See the section further below entitled:
        [Check package-lock.json On Every npm install]{.underline}.  It
        may not happen here -- maybe it is just needed for anything else
        you happen to install.

-   Edit
    src\\webparts\\\<web-part-name>\\components\\\<web-part-name>.tsx as
    follows:

    -   Add near the top of the file:

```javascript
            import { TextField } from 'office-ui-fabric-react';
```

- Add just inside the innermost div (maybe before the anchor tag):

 ```javascript
            <TextField label='Test Office UI Fabric React' />
 ```

- Test the updates:

```bash
            set NODE_NO_HTTP2=1 && gulp serve --nobrowser
```

- Refresh your page with the web part on it
- If the above fails, try a redeploy.  Whenever we do an npm
        install, I feel that you *may* need to redeploy your package. 
        Here are the steps:
- Update config\\package-solution.json and increment the
            version (to 1.0.0.1)

```bash
    gulp bundle
    gulp package-solution
```

- Upload your sppkg file into your App Catalog and deploy it

```bash
    set NODE_NO_HTTP2=1 && gulp serve --nobrowser
```

- Refresh your page with the web part on it

## Test a Production (Ship) Build -- First Time

So far the only tests we have done above are running from localhost and
not running from SharePoint.  To have them run from SharePoint, you need
to create package that runs from SharePoint.
Since SharePoint 2016 can't read the assets (manifest and JavaScript
files) from with the package, we need to deploy the assets to another
location.  This can be any website, but I'll cover two options: a
SharePoint Library or an Azure storage account.  Since you are already
using SharePoint, that may be the best option for you.

-   SharePoint Library
    -   The files include not only JavaScript, but also a JSON
        manifest.  By default, SharePoint 2016 does not allow JSON files
        in a document library.  This article describes how to fix this:
         [HOW TO ALLOW JSON FILE FORMAT ON SHAREPOINT 2016 ON
        PREMISE](https://njrathod.wordpress.com/2018/06/15/how-to-allow-json-file-format-on-sharepoint-2016-on-premise/)

    -   I consider JSON files pretty harmless, but here is a discussion
        on that you may find useful if you are unsure: [Why is upload of
        JSON files
        prohibited?](https://sharepoint.stackexchange.com/questions/114540/why-is-upload-of-json-files-prohibited)

    -   The only other part of this is to create a folder in a library
        somewhere.  You might want to create a folder in the Site Assets
        library in the site where the web part will reside or in a
        common site if the web part will be across site collections. 
        The end users need access to the library, of course.

    -   Open config\\write-manifest.json and update the cdnBasePath to
        point to the folder you created.  For example: 

        ```json
        {
          "$schema": "https://developer.microsoft.com/json-schemas/spfx-build/write-manifests.schema.json",
          "cdnBasePath": "https://sp2016.mycorp.com/sites/somesite/SiteAssets/helloworld-webpart-assets"
        }​
        ```

-   Azure Storage Account
    -   First you'll need to [create an Azure storage
        account](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal).

    -   Create a blob container within the storage account.

    -   Set the Public Access Level to Public read access for blobs
        only.

    -   It's not required, but if you like you can [create a CDN for the
        Azure storage
        account](https://docs.microsoft.com/azure/cdn/cdn-create-a-storage-account-with-cdn).

    -   Open config\\write-manifest.json and update the cdnBasePath to
        point to the container (or Azure CDN) you created.  For
        example: 

        ```json
        {
          "$schema": "https://developer.microsoft.com/json-schemas/spfx-build/write-manifests.schema.json",
          "cdnBasePath": "https://mytestcdn.azureedge.net/helloworld-webpart-assets"
        }​
        ```

Your asset deployment location is ready.  Let's build and package the
solution.  We use \--ship to indicate that we are running from
SharePoint and not localhost:

-   Update config\\package-solution.json to increment your version
    number

-   ```bash
    gulp bundle --ship
    ```

-   Copy temp\\deploy folder contents to the appropriate location
    configured above

-   ```bash
    gulp package-solution --ship
    ```

-   Upload your sppkg file into your App Catalog

-   Refresh your page with the web part on it.  There is no need to run
    gulp serve as this is running completely with SharePoint now. If you
    get errors, try using dev tools in your browser to see if there are
    network errors accessing the files from the CDN.

-   Note: to go back to a dev build, you don't have to change
    write-manifest.json again (see the next two sections for what to do)

## Subsequent Production (Ship) Build Tests

The section above described what to do the first time you deploy
everything to SharePoint.  Here are the steps for any other times you
deploy to SharePoint:

-   Update config\\package-solution.json to increment your version
    number

-   Delete all files in your temp\\deploy folder

-   ```bash
    gulp bundle --ship
    ```

-   Delete all files in your Azure blob container or Site Assets folder

-   Copy temp\\deploy folder contents to the appropriate location
    (SharePoint library or Azure blob container)

-   ```bash
    gulp package-solution --ship
    ```

-   Upload your sppkg file into your App Catalog

-   Refresh your page with the web part on it (no need to run gulp serve
    as this is running totally in SharePoint now).  If you get errors,
    try using dev tools in your browser to see if there are network
    errors accessing files from the CDN

## Subsequent Dev Tests

For most dev changes, the process is simple.  If you are already running
gulp serve and didn't do a production/ship build recently, the process
is as simple as:

-   Make sure you are still running: 

    ```bash
    set NODE_NO_HTTP2=1 && gulp serve --nobrowser​
    ```

-   Refresh your web page with the web part on it after saving your
    changes and waiting a few seconds

If you were just doing a production (ship) build, did an npm install, or
otherwise changed package.json, you probably need to do these steps
instead:

-   increment your version number in package-solution.json

-   ```bash
    gulp bundle
    gulp package-solution
    ```

-   Upload your sppkg file to the App Catalog

-   ```bash
    set NODE_NO_HTTP2=1 && gulp serve --nobrowser
    ```

-   Refresh your page with the web part on it

## Check package-lock.json On Every npm install

Unfortunately, there is an issue with the SPFx TypeScript version which
requires you to do something you aren't supposed to do: manually update
package-lock.json.  The process is described here: [Workaround for SPFx
TypeScript
Version](https://pnp.github.io/pnpjs/v1/documentation/SPFx-On-Premesis-2016/).
I got in the habit of searching package-lock.json for "typescript" (with
the quotes) **[every]{.underline}** time I did an npm install to change
2.2.2 back to 2.4.2.  You'll be glad you did.
In addition, you don't want to wait too long to test a production/ship
version of your build after doing an npm install.  Make sure you are
using version control for your code and review your package-lock.json
for changes every time you checkin changes.

## Don't Be Tempted to Use a Later Version of Microsoft or PnP

If you look at your package.json file, the dependencies section, might
look like this:
 
```json
"dependencies": {
    "@microsoft/sp-core-library": "~1.1.0",
    "@microsoft/sp-lodash-subset": "~1.1.0",
    "@microsoft/sp-office-ui-fabric-core": "~1.4.0-0",
    "@microsoft/sp-webpart-base": "~1.1.0",
    "@pnp/common": "1.1.0",
    "@pnp/logging": "1.1.0",
    "@pnp/odata": "1.1.0",
    "@pnp/sp": "1.1.0",
    "@types/es6-promise": "0.0.33",
    "@types/react": "0.14.46",
    "@types/react-addons-shallow-compare": "0.14.17",
    "@types/react-addons-test-utils": "0.14.15",
    "@types/react-addons-update": "0.14.14",
    "@types/react-dom": "0.14.18",
    "@types/webpack-env": "1.13.1",
    "office-ui-fabric-react": "2.34.2",
    "react": "15.4.2",
    "react-dom": "15.4.2"
},
```
 
 

You might be tempted, as I was, to maybe bump those @microsoft/sp-\*
and @pnp/\* packages to 1.4.1 or some other version by doing an npm
install of them to a specific version.  I highly recommend against
this.  If you do, make sure you are prepared to revert both package.json
and package-lock.json.  Also test with a production/ship build as you
will likely find, as I did, that it works with a dev build, but not a
production build.
More details can be found here: [Duplicate of issue #985](https://github.com/SharePoint/sp-dev-docs/issues/1100) (deployed web
part says "Manifest not found", after updating from 1.1.0 to 1.

Note that you might want to remove the "\~" and "" from some of those
versions to make sure the version matches exactly (and doesn't use an
[approximate equivalent
version](https://docs.npmjs.com/about-semantic-versioning)
or compatible with
version.
If you ever have to revert package.json and package-lock.json, the
easiest way to get back where you were after you revert is to delete
your node_modules folder, do an npm install, and then fix your
package-lock.json as discussed in the previous section.

## No SharePoint Server Access from Dev?

If this is the case for you, I'd like to say this is not really a
problem, but it will be pretty painful.  If possible, I recommend
developing where your machine has access to the SharePoint server. 
Maybe even a Dev/Test SharePoint server, if there is one.  Otherwise,
you may want to use an Azure storage account / CDN to store your assets
instead of a SharePoint library, as it may be quicker to transfer them
for every minor change you make.  You won't be able to run gulp serve
and run things from localhost.
I recommend you check out this blog post for generating a source map for
the release build: [Easily debug production version of your SharePoint
Framework
solution](https://blog.mastykarz.nl/debug-production-version-sharepoint-framework-solution/). 
If you put the source map with the rest of the source (in Azure blob or
SharePoint Site Assets) you won't need to manually add the source map
to your browser.

## TSLint Changes

As you start adding more of your own code, you may start seeing
[TSLint](https://www.npmjs.com/package/tslint) warnings.  It can be
quite annoying as you may miss real warnings, so you want a clean
build.  I had trouble configuring TSLint via tsling.json, so I used
[prettier within VS
code](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
and configured it by creating a prettier.config.js file at the root of
my project.  Its contents are the following.  The trailingComma and
singleQuote values are important to minimize prettier and TSLint from
fighting each other.
 
```json
module.exports = {
    trailingComma: 'es5',
    tabWidth: 4,
    singleQuote: true,
    printWidth: 120,
};
```
 
Even with the above, I was still getting a lot of TSLint errors, so I
reviewed [TSLint rule
flags](https://palantir.github.io/tslint/usage/rule-flags/) and had to
enact several rules within my code including:

-   Immediately before I exported something where the filename had more
    than one period in it: 

    ```javascript
    /* tslint:disable-next-line:export-name */​
    ```

-   Immediately before I used the type \"any\" for a variable.  This
    seemed necessary when I couldn't find a type that PnP was using
    (maybe I didn't look hard enough): 

    ```javascript
    /* tslint:disable-next-line:no-any */​
    ```

-   Immediately before any line that just didn't fit TSLint's max line
    length (I think it is 120, but my configuration is ignored, so I am
    not sure what it is): 

    ```javascript
    /* tslint:disable-next-line:max-line-length */​
    ```

-   This problem occurred when prettier insisted on ending an arrow
    function with a semicolon, but TSLint complained, so I put it right
    before the closing of the arrow function: 

    ```javascript
    /* tslint:disable-next-line:semicolon */​
    ```

## Summary

Well, if you made it this far, I applaud you -- and am a little
surprised.  I don't tend to write blog posts that are this long, but I
really needed to get this off of my chest.
Many companies are still on older versions of SharePoint and the effort
to upgrade is sometimes daunting ([but ThreeWill can
help](https://threewill.com/services/transform/cloud-migrations/)!)  If
you are working with SharePoint 2016 and want to build custom web parts
with SPFx I hope the steps above (and the pain I went through) saves you
some time.


