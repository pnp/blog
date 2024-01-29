---
title: "Setting up https for Teams Tabs projects - without ngrok"
date: 2021-05-13T07:58:00-04:00
author: "Bob German"
githubname: BobGerman
categories: ["Community post"]
images:
- images/localhostcert.png
tags: ["Microsoft Teams"]
type: "regular"
---

I've started using the new Microsoft Teams toolkit, which is a Visual
Studio Code extension and generator for Teams applications. One thing I
noticed is a little challenge when creating tabs, and that's due to the
requirement to use SSL. The documentation is fine and [explains how to
trust your local
project](https://learn.microsoft.com/microsoftteams/platform/toolkit/visual-studio-code-overview?WT.mc_id=m365-blog-rogerman#add-a-trusted-certificate-for-localhost),
but I found it a little painful since the certificates only last 1 month
and there's a different one for each project, so I need repeat the
process frequently. Your teammates will need to do that as well.

\
![localhostcert.png](images/localhostcert.png)

[Here is an alternative approach in which you create your own
certificate authority and build certs from that so you can install just
one root certificate across all your projects! Each teammate can have
their own certs, so you can collaborate as much as you wish and nobody
has to go installing certs.]
> NOTE: Did you know that the Teams Toolkit uses [Create React App
> (CRA)](https://reactjs.org/docs/create-a-new-react-app.html) for tabs?
> Create React App is a toolchain from Facebook (who created React in
> the first place) it's very popular and well supported! If you need
> help, search on "Create React App" and you can find a plethora of
> helpful articles; [this
> one](https://dev.to/maximization/setup-https-in-development-with-create-react-app-3ien) helped
> me figure this out!

## Step 1: Create and trust a certificate authority (CA)

This step only needs to be done once for as many projects as you wish.
It assumes you already have Node.js installed, as required by the Teams
Toolkit.
**a.** Create a safe/private folder somewhere and go there in your
favorite command-line tool, and run these commands:

``` wp-block-preformatted
npm install -g mkcert
mkcert create-ca --organization "MyOrg" --validity 3650
mkcert create-cert --ca-key "ca.key" --ca-cert "ca.crt" --validity 3650
```

> NOTE: 3650 is the number of days your certs will be valid; feel free
> to change it. You can use `--help` on `mkcert` to reveal other
> options, such as setting an organization name and location (the
> default org is "Test CA") and customizing the domain names for your
> certificate (the default is "localhost,127.0.0.1").

This will create a new Certificate Authority and a certificate that was
issued from it. You should see 4 files:

  FILE       DESCRIPTION
  ---------- ---------------------------------
  ca.crt     Certificate for your new CA
  ca.key     Private key for your new CA
  cert.crt   Certificate for use in projects
  cert.key   Private key for use in projects

**b.** Now you need to trust the certificate for your new CA; by doing
that any cert you create will be trusted with no additional action on
your part.

### On Windows

-   Double select  the `ca.crt` file and select "Install Certificate".
    \
    ![ssl-01.png](images/ssl-01.png)

-   Choose Local Machine and select next.
    \
    ![ssl-02.png](images/ssl-02.png)

     

-   Select "Place all certificates in the following store" and then
    select the "Browse" button. Choose "Trusted Root Certification
    Authorities" select "OK" to close the dialog box, and then click
    "Next".
    \
    ![ssl-03.png](images/ssl-03.png)

-   Restart all instances of your browser to force it to re-read its
    trusted roots. If in doubt, reboot your computer.

### On Mac

-   Double select  the **ca.crt** file, which should be found
    under `/Users/[your-name]/`. It will launch Keychain Access app.
-   Enter your password or use Touch ID when prompted. \
    ![ssl-mac-01.png](images/ssl-mac-01.png)
-   The new certificate (in this case, "MyOrg") should be added.
    Double-select it. \
    ![ssl-mac-02.png](images/ssl-mac-02.png)
-   In a new window, expand the **Trust** section of the certificate
    details. Select "Always Trust" for every option. \
    ![ssl-mac-03.png](images/ssl-mac-03.png)
-   Close the window. Enter your password or use Touch ID again if you
    are asked. Now the certificate is trusted. \
    ![ssl-mac-04.png](images/ssl-mac-04.png)
-   Restart all instances of your browser to force it to re-read its
    trusted roots. If in doubt, reboot your computer.

### On Linux

There are more steps on Linux as most browsers don't use the operating
system's certificate store, and a tool called `certutil` is needed to
modify the browsers' `cert?.db` files. [This
article](https://thomas-leister.de/en/how-to-import-ca-root-certificate/) explains
how to install your new root certificate on Linux.

## Step 2 -- Add the certs to your project

This is what you need to do for each project.

**a.** Create a new folder in your project folder (the same level as the
package.json file) called `.cert`. Copy
the `cert.crt` and `cert.key` files into this folder

**b.** Modify your .env file to tell the local web server to use your
cert:

`HTTPS=true`{.plain .plain}


`SSL_CRT_FILE=./.cert/cert.crt`{.plain .plain}



`SSL_KEY_FILE=./.cert/cert.key`{.plain .plain}


**c.** Prevent saving the certs to your git repository by adding a line
to the `.gitignore` file.

`.cert`{.plain .plain}


## Azure Active Directory SSO Tabs

Tabs that implement Azure Active Directory Single Sign-On need to
implement more than just a web page; they need to implement a web
service to exchange the SSO token for an access token that the app can
use to call downstream services such as the Microsoft Graph. This is
explained in [this blog
article](https://blog.mastykarz.nl/securely-connect-microsoft-graph-teams-tabs-sso/),
or [this
one,](https://www.wictorwilen.se/blog/microsoft-teams-tabs-sso-and-microsoft-graph-the-on-behalf-of-blog-post/) more
clearly than in the documentation.

When `yo teams` generates an SSO tab, this web service is hosted using
the same web server as the page itself.

When the Teams Toolkit generates one, however, it creates a separate web
service for the web service so there really are two endpoints that need
to be SSL enabled. The web service is in a folder called `api-server`.
To enable SSL here, follow these steps:

1.  Add these lines to the `api-server\.env` file.

`HTTPS=trueSSL_CRT_FILE=../.cert/cert.crtSSL_KEY_FILE=../.cert/cert.keyCORS_ORIGIN=https://devappsforteams.local:3000`
2.  Immediately above the
line `app.get('/getGraphAccessToken')` in `server.ts` or `server.js`,
add these lines to allow the cross-origin call from the web page (port
3000) to the web service (port 5000):

`const cors = require('cors');app.use(cors({    origin: process.env.CORS_ORIGIN}));`
3.  Near the bottom of the same file, replace the line

`app.listen(port);`

with this code:


```js
const fs = require('fs');const https = require('https');var privateKey = fs.readFileSync(process.env.SSL_KEY_FILE );var certificate = fs.readFileSync(process.env.SSL_CRT_FILE);https.createServer({    key: privateKey,    cert: certificate}, app).listen(port);
```

## Working in a team

Each team member needs to do Step 1 on their computer just once. When a
developer starts working on a project they can simply copy their .cert
folder into their project and go to work.
\

Many thanks to my colleague [Tomomi Imura ](https://girliemac.com/)for
documenting the Mac instructions and providing screen shots.

Do you have ideas on how to do this better, especially in a project
team? Please chime in using the comments; thanks!
