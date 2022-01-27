# QuickBooks API Integration With Power Automate Using Custom Connectors


In this article, we will be exploring the below concepts,
-   Understand QuickBooks Online APIs
-   Trying QuickBooks API from the postman
-   Create MS flow custom connectors.
-   Integrating QuickBooks API from Power automate(MS flow) using Custom
    connectors.

Suppose you have some business process working in SharePoint/Power
automate where employees are filling timesheets and after approval, you
want to generate invoices in Quick books online (QBO). Or you want to
record expense(bill) in QBO once your vendor has submitted his invoice
due to you, maybe via power apps forms or SharePoint online list. Office
365 products like SharePoint, Power Automate, Power apps will allow us
to automate a business process like approval, review, etc. And once this
process is completed, we wanted to do accounting entries in our
accounting software (in this case Quick books online).

So Let's get started.

## What do you need? 

-   Quick book online account.
-   Intuit developer account.
-   Postman
-   Power automate (MS flow) license.

## Quick book online account 

Create a Quickbook online account (if not already) by subscribing to the
plan as per your requirement. For this sample, I have created a 30 days
trial account. You can check different pricing available at
this [link](https://quickbooks.intuit.com/in/pricing/), based on your
country different pricing and subscription are available.

## Intuit developer account 

You would need to create Intuit (company owning Quickbook) developer
account.

1.  Go [here](https://developer.intuit.com/app/developer/homepage)

On the top menu, follow the last link to sign up. The below screen will
open, fill in the below details.

![SiddharthVaghasia_0-1628135161016.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300618i1EFDB5B13192F6CF/image-dimensions/331x646?v=v2 "SiddharthVaghasia_0-1628135161016.png")
1.  Once sign in, you can follow
    this [link](https://developer.intuit.com/app/developer/qbo/docs/get-started) to
    create an APP. Ignore Steps 3 and 4 for now from this link. Make
    note of client id and client secret, Please note that your sandbox
    client id and client secret will be different. For this demo, we
    will create production keys so that we can make the actual calls to
    our live environment.
2.  Below is how my developer dashboard looks like,

![SiddharthVaghasia_1-1628135161497.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300619i7265A9B17131091F/image-dimensions/615x220?v=v2 "SiddharthVaghasia_1-1628135161497.png"){.lia-media-image
width="615" height="220" role="button"
li-image-url="https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300619i7265A9B17131091F?v=v2"
li-image-display-id="'300619i7265A9B17131091F'"
li-message-uid="'2613452'" li-messages-message-image="true"
li-bindable="" tabindex="0" li-bypass-lightbox-when-linked="true"
li-use-hover-links="false"}]{.lia-inline-image-display-wrapper
.lia-image-align-inline
image-alt="SiddharthVaghasia_1-1628135161497.png" style="width: 615px;"}
So we have all the things required from the QBO side of integration,
let\'s move ahead. 

Assuming now you already have Postman and MS flow license, let us go
ahead and see the overall approach we will follow for this integration.

1.  Import postman collection,
2.  Create a new collection and copy/try the API calls from postman for
    required endpoints (web service we want to integrate)
3.  Setup authorization in postman to get access token.
4.  Call a simple web service.
5.  Export the collection.
6.  Create custom connector in Powerautomate
7.  Create Power automate(flow) and use actions to call Quickbooks API

**Step 1**

Import Postman collection of All APIs available in Quick book online.
This export of collections is provided by Quickbooks at
this [link](https://developer.intuit.com/app/developer/qbo/docs/develop/postman)(refer
to screenshot below).

![SiddharthVaghasia_2-1628135161255.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300620i519BF63C19571672/image-dimensions/565x319?v=v2 "SiddharthVaghasia_2-1628135161255.png")
This will directly ask to open postman and it will open collection like
in the below screenshot.

![SiddharthVaghasia_3-1628135161604.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300621i60B4D9A8EDB2CF0A/image-dimensions/410x575?v=v2 "SiddharthVaghasia_3-1628135161604.png")
**Step 2 - Create a new empty collection**

![SiddharthVaghasia_4-1628135161655.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300623i51C1AFD34D2B01D7/image-dimensions/756x501?v=v2 "SiddharthVaghasia_4-1628135161655.png")
Now go to Imported postman collection and expand the Invoice.

![SiddharthVaghasia_5-1628135161514.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300622iA2B762F1DAEDB572/image-size/medium?v=v2&px=400 "SiddharthVaghasia_5-1628135161514.png")
We will use 2 API(invoice read by Id and create an invoice). Open one by
one and click on Save as to save in our custom-created
collection(QBOMSflowIntegration).

![SiddharthVaghasia_6-1628135161650.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300624i844703A1DA873A73/image-dimensions/630x359?v=v2 "SiddharthVaghasia_6-1628135161650.png")
![SiddharthVaghasia_7-1628135161752.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300625i7D33B5FB274FF75F/image-dimensions/471x578?v=v2 "SiddharthVaghasia_7-1628135161752.png")
Please follow the same step for API 'Create Invoice'.

Now, Let set up an environment variable for dynamic values to be passed
in URL.

Follow the below screenshot,

![SiddharthVaghasia_8-1628135161722.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300626iFCB19C41F1EED836/image-dimensions/903x388?v=v2 "SiddharthVaghasia_8-1628135161722.png")
Create 3 URLs,

**Base URL**

Sandbox Base URL - sandbox-quickbooks.api.intuit.com

Product Base URL - quickbooks.api.intuit.com (Production)

Company ID -- You can find company ID by following
this [link](https://quickbooks.intuit.com/learn-support/en-us/customer-company-settings/find-your-quickbooks-online-company-id/00/185551)

Invoice Id -- Set is 1(we will query invoiced Id 1 in one Get Invoice
Webservice)

**Step 3 -- Setup authorization**

Now let us set up authorization details to get the access token and pass
it to the actual API call.

Please follow along with the below screenshot.

![SiddharthVaghasia_9-1628135161520.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300629i02052262C2C1BA1E/image-dimensions/854x413?v=v2 "SiddharthVaghasia_9-1628135161520.png")

It should open the below popup box, enter the below details here.

-   Token Name - Enter your preferred name
-   Grant Type -- Select Authorization Code
-   Call Back URL - <https://app.getpostman.com/oauth2/callback> (this
    URL should be in Allowed redirect URL in Intuit developer dashboard,
    we will see how to do this later)
-   Auth URL - <https://appcenter.intuit.com/connect/oauth2>
-   Access Token URL -
    <https://oauth.platform.intuit.com/oauth2/v1/tokens/bearer>
-   Client ID -- This needs to be copied from intuit developer
    dashboard(use according to the environment)
-   Client Secret - This needs to be copied from intuit developer
    dashboard(use according to the environment)
-   Scope - com.intuit.quickbooks.accounting OpenID email profile
-   State -- mydemostateobject123213(this can be anything)

Client Authentication -- Select. Send client credentials in the body.

Before clicking on Request Token, we need to add a call-back URL to in
developer dashboard.

Login to the developer dashboard at
this [link](https://developer.intuit.com/app/developer/homepage).

Click on My Apps, select targeted app, and refer to the below screenshot
to add.

![SiddharthVaghasia_10-1628135161610.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300627i4A69657631CD0B87/image-dimensions/856x462?v=v2 "SiddharthVaghasia_10-1628135161610.png")

Once this is done, come back to Postman and Click on Request token, it
will ask you to authenticate with your Quickbook account, login with a
valid account, and follow along. Once you are logged in you should see
the below popup, rename the token name with your preference and click on
use token.

![SiddharthVaghasia_11-1628135161603.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300628iAA932967F2CC9A95/image-dimensions/894x502?v=v2 "SiddharthVaghasia_11-1628135161603.png"){.lia-media-image
width="894" height="502" role="button"
li-image-url="https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300628iAA932967F2CC9A95?v=v2"
li-image-display-id="'300628iAA932967F2CC9A95'"
li-message-uid="'2613452'" li-messages-message-image="true"
li-bindable="" tabindex="0" li-bypass-lightbox-when-linked="true"
li-use-hover-links="false"}]{.lia-inline-image-display-wrapper
.lia-image-align-inline
image-alt="SiddharthVaghasia_11-1628135161603.png"
style="width: 894px;"}
Select that token name in the available tokens dropdown.

![SiddharthVaghasia_12-1628135161649.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300630i93B4B26E5AE8847C/image-dimensions/893x241?v=v2 "SiddharthVaghasia_12-1628135161649.png"){.lia-media-image
width="893" height="241" role="button"
li-image-url="https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300630i93B4B26E5AE8847C?v=v2"
li-image-display-id="'300630i93B4B26E5AE8847C'"
li-message-uid="'2613452'" li-messages-message-image="true"
li-bindable="" tabindex="0" li-bypass-lightbox-when-linked="true"
li-use-hover-links="false"}]{.lia-inline-image-display-wrapper
.lia-image-align-inline
image-alt="SiddharthVaghasia_12-1628135161649.png"
style="width: 893px;"}
Now make sure, you match the environment variable name in the URL and
what we used while created in the above step.

![SiddharthVaghasia_13-1628135161644.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300631i0874B70B6DEE96AC/image-dimensions/896x354?v=v2 "SiddharthVaghasia_13-1628135161644.png")
**Step 4 -- Call a simple web service**

Now we are ready to test, click on the send button. If everything is set
up correctly, we can see the below output.

![SiddharthVaghasia_14-1628135161638.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300632i017539C2AFEF5F17/image-dimensions/901x462?v=v2 "SiddharthVaghasia_14-1628135161638.png")

In the same way, you can test Create invoice method. Make sure in the
authorization tab you have selected the newly generated token. Follow
the below screenshot, if you notice, there is already a JSON object in
the body which is the bare minimum thing required to create an invoice.
Click on send.

![SiddharthVaghasia_15-1628135161634.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300635i9D576ACC8DC7517C/image-dimensions/904x479?v=v2 "SiddharthVaghasia_15-1628135161634.png")

In your real case, you would have to pass many more things, for that you
can always refer to Quick Book API documentation at
this [link](https://developer.intuit.com/app/developer/qbo/docs/api/accounting/most-commonly-used/invoice).

**Step 5 -- Export collection**

Now we are done with the postman and it\'s time to export this
collection, which will be used in Power automate to create the custom
connector.

![SiddharthVaghasia_16-1628135161616.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300633iE81D37DF9DE17ABC/image-dimensions/913x438?v=v2 "SiddharthVaghasia_16-1628135161616.png")
Once you click one export, it will ask you to save the exported file,
save it at your preferred location.

**Step 6 -- Create a custom connector**

Now it\'s time to go to Power automate and create a custom connector.

Go [here](https://flow.microsoft.com/).

Follow the below screenshot,

![SiddharthVaghasia_17-1628135161596.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300634i70CA3CB61BB65A1F/image-dimensions/887x528?v=v2 "SiddharthVaghasia_17-1628135161596.png")
It will open below popup, select the JSON file which was imported in
step 5. Give your preferred name. Click on Continue.

![SiddharthVaghasia_18-1628135160901.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300636iC6F9C15F58435F06/image-dimensions/748x505?v=v2 "SiddharthVaghasia_18-1628135160901.png")
We will now be taken into a wizard where we have to setup our connector,
In first (below screenshot) enter details are per your preference, we
will keep default but enter the base URL.

![SiddharthVaghasia_19-1628135161522.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300637i1049616C0BF6888A/image-dimensions/814x596?v=v2 "SiddharthVaghasia_19-1628135161522.png")
Click on Security Tab and select oAuth 2.0 in Authentication Type.

![SiddharthVaghasia_20-1628135161374.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300638i847094C1A345F09A/image-dimensions/838x725?v=v2 "SiddharthVaghasia_20-1628135161374.png")
Below is for your quick reference, most of them are the same as we did
in postman in Step 3.

-   Identity Provider - Generic OAuth 2
-   Client ID -- Our App Client ID
-   Client Secret -- Our App Client Secret
-   Authorization URL- <https://appcenter.intuit.com/connect/oauth2>
-   Token URL -
    <https://oauth.platform.intuit.com/oauth2/v1/tokens/bearer>
-   Refresh URL -
    <https://oauth.platform.intuit.com/oauth2/v1/tokens/bearer> (Same as
    Token URL)
-   Scope - com.intuit.quickbooks.accounting
-   Redirect URL -- Leave it blank.

Note - Leave Redirect URL blank, for now, this will be auto-generated.
We need to come back here and then copy this URL to add this in Intuit
developer dashboard in Allowed Redirect URL, the way we did it for the
postman.

Click on Definition --Here we will see below screen,

![SiddharthVaghasia_21-1628135161481.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300639iEF6F0B7CCB83740F/image-dimensions/889x349?v=v2 "SiddharthVaghasia_21-1628135161481.png")
Now comes the tricky part, By default the definition we imported using
the swagger file does not understand the dynamic variables like BaseURL,
CompanyId, and InvoiceId. This is because the syntax of the postman to
pass dynamic variable is different than the swagger for Flow. So what we
will do here is modify the swagger file manually so that we can pass
company id, base URL, and Invoice id dynamically while configuring
action in actual Flow implementation. Please note this is to demonstrate
how to make your URLs dynamic (because in real use cases, we won't call
webservice via hardcoded data).

Enable Swagger Editor(as in the above screenshot)

We will need to change the path both webservice url and add parameters
definition


``` {.line-numbers .language-javascript tabindex="0"}
Get Invoice webservice path
/v3/company/%7B%7Bcompanyid%7D%7D/invoice/147:
TO
/v3/company/{companyid}/invoice/{invoiceId}:
Create invoice webservice Path
/v3/company/%7B%7Bcompanyid%7D%7D/invoice:
TO
/v3/company/{companyid}/invoice:
```

For Get Invoice parameters we added

\- {name: companyid, default: \'{{companyid}}\', in: path, type: string,
required: true}

\- {name: invoiceId, default: \'{{invoiceId}}\', in: path, type: string,
required: true}

For Create Invoice parameters we added.

\- {name: companyid, default: \'{{companyid}}\', in: path, type: string,
required: true}

This is how it will look after the change.

![SiddharthVaghasia_22-1628135161636.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300641i8070FD5AFA871791/image-dimensions/850x703?v=v2 "SiddharthVaghasia_22-1628135161636.png"){.lia-media-image
width="850" height="703" role="button"
li-image-url="https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300641i8070FD5AFA871791?v=v2"
li-image-display-id="'300641i8070FD5AFA871791'"
li-message-uid="'2613452'" li-messages-message-image="true"
li-bindable="" tabindex="0" li-bypass-lightbox-when-linked="true"
li-use-hover-links="false"}]{.lia-inline-image-display-wrapper
.lia-image-align-inline
image-alt="SiddharthVaghasia_22-1628135161636.png"
style="width: 850px;"}
Please make sure there is no error while making this change, space is
very important, for e.g if you missed a space as in the below screenshot
it will give you a parser error.

![SiddharthVaghasia_23-1628135161733.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300640i7E4D61175685DC37/image-dimensions/873x228?v=v2 "SiddharthVaghasia_23-1628135161733.png"){.lia-media-image
width="873" height="228" role="button"
li-image-url="https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300640i7E4D61175685DC37?v=v2"
li-image-display-id="'300640i7E4D61175685DC37'"
li-message-uid="'2613452'" li-messages-message-image="true"
li-bindable="" tabindex="0" li-bypass-lightbox-when-linked="true"
li-use-hover-links="false"}]{.lia-inline-image-display-wrapper
.lia-image-align-inline
image-alt="SiddharthVaghasia_23-1628135161733.png"
style="width: 873px;"}
Below is have it will look like if you made all entries correct.

![SiddharthVaghasia_24-1628135161735.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300642iA40DBCFEF885BF33/image-dimensions/897x506?v=v2 "SiddharthVaghasia_24-1628135161735.png"){.lia-media-image
width="897" height="506" role="button"
li-image-url="https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300642iA40DBCFEF885BF33?v=v2"
li-image-display-id="'300642iA40DBCFEF885BF33'"
li-message-uid="'2613452'" li-messages-message-image="true"
li-bindable="" tabindex="0" li-bypass-lightbox-when-linked="true"
li-use-hover-links="false"}]{.lia-inline-image-display-wrapper
.lia-image-align-inline
image-alt="SiddharthVaghasia_24-1628135161735.png"
style="width: 897px;"}
You can Toggle Enable Swagger and click on create connector button.

It will validate and save your connector.

Now before moving forward, let us go back to the security tab and copy
the redirect URL. Go to Intuit developer dashboard and add this in the
Allowed redirect URL(as we did for postman).

In most cases, it would be below,

<https://global.consent.azure-apim.net/redirect>

Now let's test. Click on the Test tab, Click on New connection. It will
ask us to login to Quickbooks, follow all steps as required. Enter
companyid, invoice id as in below screenshot and click on Test
operation, If you got output as marked as no.5, we are good.
:smiling_face_with_smiling_eyes:

![SiddharthVaghasia_25-1628135161760.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300644iB81E7837A7592602/image-dimensions/875x770?v=v2 "SiddharthVaghasia_25-1628135161760.png")
Congratulation our custom connector is created successfully, now it\'s
time to create a sample flow to use this connector and its methods. For
sake of simplicity, I am creating a flow with Manual Trigger.

![SiddharthVaghasia_26-1628135161718.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300643iE875AA113BEF834D/image-dimensions/882x551?v=v2 "SiddharthVaghasia_26-1628135161718.png")
Now add a new step, in action, select the custom tab, select our custom
connector,

![SiddharthVaghasia_27-1628135160899.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300645iEC70100160270AA8/image-dimensions/900x513?v=v2 "SiddharthVaghasia_27-1628135160899.png")
It will ask us to choose from 2 actions, first, add the Get invoice.
Repeat this step and add Create Invoice also as the next step.

Configure both actions as in below,

![SiddharthVaghasia_28-1628135161719.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300646i8CC8909BC75C4C0B/image-dimensions/606x803?v=v2 "SiddharthVaghasia_28-1628135161719.png")
Please note that for Create invoice, we need to pass Line as an array of
the JSON objects. Copy it from the postman, below is for quick
reference.


``` {.line-numbers .language-javascript tabindex="0"}
[{
    "Amount": 100.00,
    "DetailType": "SalesItemLineDetail",
    "SalesItemLineDetail": {
        "ItemRef": {
            "value": "1",
            "name": "From MS Flow demo"
        },
        "TaxCodeRef": {
            "value": "2"
        }
    }
}]
```


Value is customer Id on whose account we need to generate Invoice, so
adding 1 here, make sure you have customer created with that Id.

We are done with setting up our actions, let us run it. Save flow,

Click on Test,

Select I'll perform the trigger action. Click on Save and test.

![SiddharthVaghasia_29-1628135161013.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300647iEED04B517F3ED6F9/image-dimensions/819x731?v=v2 "SiddharthVaghasia_29-1628135161013.png")
**Click continue -\> Run Flow. **Wait for some time. If everything goes
well, you see the below message.

![SiddharthVaghasia_30-1628135161134.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300648i3FFCED149F04941D/image-dimensions/807x341?v=v2 "SiddharthVaghasia_30-1628135161134.png")
You can expand actions and check responses returned in both actions.

Login to Quick book, From left navigation Go to Sales-\>Invoices and you
will see a new invoice generated. In my case, below are some generated
invoices that I created from flow(except the first one) while testing
flow.

![SiddharthVaghasia_31-1628135161766.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/300649i0B3602C0A4E36852/image-dimensions/838x329?v=v2 "SiddharthVaghasia_31-1628135161766.png")

So that's come to end to the long article. To conclude, Please note we
can create any operations available in quick books API from flow, we
have to use first use postman to add the required API endpoint and then
configure while creating custom connectors. Hope this helps and gives
you a basic idea on getting started.
