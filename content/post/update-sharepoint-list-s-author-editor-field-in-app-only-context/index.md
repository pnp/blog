---
title: "Update SharePoint list's Author / Editor field in App-Only context"
date: 2021-08-09T08:40:00-04:00
author: "Michael Maillot"
categories: ["Community post"]
images:

tags: ["PnP PowerShell"]
type: "regular"
---

## Use Cases

-   You're migrating list items from a tenant to another using
    back-office app (console app or Azure SaaS resource) and want to
    keep existing fields, including author / editor ones
-   You're developing an API
    / Web App that will be used by employees which data is saved to a SharePoint List without 
    being in user context (because you want to make some background
    checks before saving)

When working with SharePoint in App-Only
context, every update made on list items are done with the user "SharePoint App".
But you can replace this by any user of the company!

One important thing to know is that the Azure AD Application that will be used must be granted to \"Sites.FullControl.All\", in order to update the Author / Editor field. Lower permissions won't let you update them.]{.underline}


## Summary


In this article, we'll cover the following steps:

-   Setup the AAD Application
    -   Generate self-signed certificate
    -   [Granting SharePoint app permission]
-   Connect to SharePoint in App-Only context
-   Update list item Author / Editor fields with any other user than
    "SharePoint App"

We'll use [PnP PowerShell](https://pnp.github.io/powershell/), [CLI for Microsoft 365](https://pnp.github.io/cli-microsoft365/) and [PnP Framework](https://github.com/pnp/pnpframework)!


## Setup the AAD Application

The first thing to do is to register an application in Azure AD. As we'll use the [client credential flow](https://learn.microsoft.com/azure/active-directory/develop/v2-oauth2-client-creds-grant-flow) with a certificate, we first need to create a certificate.


### Setup using PnP PowerShell

With PnP PowerShell, a simple command is enough to both declare
self-signed certificate and register AAD Application with permissions
using this certificate:

```powershell
# Beware to mention an existing path in the -OutPath parameter, otherwise you won't get your certificate available
Register-PnPAzureADApp -ApplicationName "PnP.SharePoint.AppOnly" -Tenant contoso.onmicrosoft.com -OutPath c:\temp -CertificatePassword (ConvertTo-SecureString -String "password" -AsPlainText -Force) -SharePointApplicationPermissions "Sites.FullControl.All" -Store CurrentUser -DeviceLogin
```



This command does the following:


-   Generate a self-signed certificate
    with a password and stores it in the current user Local Certificate Store
    (Personal, this parameter works only on Windows)
-   Register an AAD Application with a
    certificate as an authentication flow, and a SharePoint App-Only permission



You can find more info about the command [Register-PnPAzureADAp](https://pnp.github.io/powershell/cmdlets/Register-PnPAzureADApp.html).


### Setup using CLI for Microsoft 365



For now there's no option to: 


- generate both a self-signed certificate and register an AAD Application using it, in a single command. Requested [in issue 2170](https://github.com/pnp/cli-microsoft365/issues/2170)
- admin consent permissions when registering an AAD Application. Requested [in issue 2563](https://github.com/pnp/cli-microsoft365/issues/2563)

#### Generate the self-signed certificate



That said, we have two possibilities depending on the environment, to genereate the self-signed certificate.





With PnP PowerShell command [New-PnPAzureCertificate](https://pnp.github.io/powershell/cmdlets/New-PnPAzureCertificate.html):


```powershell
New-PnPAzureCertificate -OutCert "PnP.SharePoint.AppOnly.cer" -OutPfx "PnP.SharePoint.AppOnly.pfx" -ValidYears 1  -CertificatePassword (ConvertTo-SecureString -String "password" -AsPlainText -Force) -CommonName "PnP.SharePoint.AppOnly"
```



With [OpenSSL:](https://www.openssl.org/docs/manmaster/man1/)



```bash
# Replace the -nodes argument by -noenc if you're using OpenSSL 3.0, to disable encryption, since it will be done right after with the pfx file generation
openssl req -new -x509 -sha256 -newkey rsa:2048 -nodes -keyout PnP.SharePoint.AppOnly.key.pem -days 365 -out PnP.SharePoint.AppOnly.cert.pem -subj "/CN=contoso.com"


openssl pkcs12 -export -name "contoso.com" -out PnP.SharePoint.AppOnly.pfx -inkey PnP.SharePoint.AppOnly.key.pem -in PnP.SharePoint.AppOnly.cert.pem -password pass:password
```


 

The first command generates both certificate request and X.509
self-signed one (with private key RSA 2048 bits) which expires in 1
year.
The \".cer.pem\" exported file will be used for Azure AD Application registration.
The second command will generate the PFX file with a password, from both the private key input file (\".key.pem\") and the certificate request (\".cert.pem\") one. This one will be used for authentication,
we'll see about that later.

#### Register the AAD Application



Once the certificate generated, we'll setup the app registration with the following command:


```bash
m365 aad app add --name 'PnP.SharePoint.AppOnly' --apisApplication 'https://microsoft.sharepoint-df.com/Sites.FullControl.All'
```


Wait a couple of minutes before being enabled to admin consent the permission through the Azure Portal.

Once done, stay on the AAD Application page and go to **Certificates & Secrets** and click on "*Upload certificate*" to add the "*PnP.SharePoint.AppOnly.cert.pem*" file.



\
![aad-certificate.png](images/aad-certificate.png)\

## Authenticate to SharePoint & Update list item



Once everything's set for App-Only context, let's authenticate to SharePoint and update our list item!

### Update with PnP Framework



The simpliest way is to use the PFX file created before, to get a context.





Let's try with a simple Console App:


 

```csharp
static void Main(string[] args)
{
    string aadAppId = "[AAD_APP_ID]"; // Get Application ID / Client ID from the registration made before
    string pfxFilePath = "[PFX_FILE_PATH]"; // Like this: C:\\temp\\PnP.SharePoint.AppOnly.pfx
    string pfxPassword = "[PFX_PASSWORD]"; // For this example, it's "password"
    string tenant = "contoso.onmicrosoft.com";
    string spWeb = "htttps://contoso.sharepoint.com";


    var authManager = new AuthenticationManager(aadAppId, pfxFilePath, pfxPassword, tenant);


    using (var ctx = authManager.GetContext(spWeb))
    {
        Guid listId = new Guid("[LIST_ID]");
        int listItemId = 1;


        List lst = ctx.Web.GetListById(listId);
        ListItem itm = lst.GetItemById(listItemId);


        // Get Megan Bowen account
        User usr = ctx.Web.EnsureUser($"meganb@{tenant}");


        // Replace "Editor" by "Author" if you want
        itm["Editor"] = usr;
        itm.Update();


        ctx.ExecuteQuery();
    }
}
```


### Update with PNP PowerShell

```powershell
$aadAppId = "[AAD_APP_ID]" # Get Application ID / Client ID from the registration made before
$pfxFilePath = "[PFX_FILE_PATH]" # Like this: C:\\temp\\PnP.SharePoint.AppOnly.pfx
$pfxPassword = (ConvertTo-SecureString -String "[PFX_PASSWORD]" -AsPlainText -Force) # For this example, it's "password"
$tenant = "contoso.onmicrosoft.com"
$spWeb = "https://contoso.sharepoint.com"


Connect-PnPOnline -Url $spWeb -Tenant $tenant -ClientId $aadAppId -CertificatePath $pfxFilePath -CertificatePassword $pfxPassword


$listId = "53006cd2-871c-4683-aaf9-f67affa2de5b"
$lisItemId = 1


# Replace "Editor" by "Author" if you want
Set-PnPListItem -List $listId -Identity $lisItemId -Values @{"Editor"="meganb@" + $tenant}
```


### Update with CLI for Microsoft 365



```bash
aadAppId="[AAD_APP_ID]" # Get Application ID / Client ID from the registration made before
pfxFilePath="[PFX_FILE_PATH]" # Like this: /home/PnP.SharePoint.AppOnly.pfx
pfxPassword="[PFX_PASSWORD]" # For this example, it's "password"
tenant="contoso.onmicrosoft.com"
spWeb="https://contoso.sharepoint.com"


m365 login --authType certificate --certificateFile $pfxFilePath --password $pfxPassword --appId $aadAppId --tenant $tenant


listId="53006cd2-871c-4683-aaf9-f67affa2de5b"
lisItemId=1


# Replace "--Editor" by "--Author" if you want
m365 spo listitem set --listId $listId --id $lisItemId --webUrl $spWeb --Editor "[{'Key':'i:0#.f|membership|meganb@${tenant}'}]"
```



And that's
it! You should now be able to update those specific fields in any way !

Happy coding!
