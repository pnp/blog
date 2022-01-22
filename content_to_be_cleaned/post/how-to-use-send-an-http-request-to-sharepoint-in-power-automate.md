# How to use Send an HTTP request to SharePoint in Power Automate?

## Introduction 
Send an HTTP request to SharePoint action is used to execute REST
queries. As we know when we want to perform any operations in SharePoint
then we are using APIs so in the flow, we can use fro the same
requirements.
For more details refer to
[this](https://docs.microsoft.com/en-us/sharepoint/dev/business-apps/power-automate/guidance/working-with-send-sp-http-request).

## Implementation 
We will create a SharePoint list and we will perform Create, Read,
Update and Delete operations. we will create an instant flow. let\'s see
step-by-step implementation.
 

**1. Go to Power Automate \> My flows \> Click on New flow \> Select
instant cloud flow**
![STep
1.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/288069i322382E6EFAFEC13/image-size/large?v=v2&px=999 "STep 1.png")
 
**2. Read items from To Do list. (Read Operation)**
So to perform the read operation we will use the **GET** method.
Add Send an HTTP request to SharePoint action from **+** icon and here
we need Site address, Method, and URI.
**Site Address:** Select the Site URL in which we want to perform
actions

**Method:** *GET*

**Uri:** *\_api/web/lists/getbytitle(\'To Do\')/items*

**Headers*****:** Not required*
You can also add URI in a variable because this we will need for all the
actions.
![Read
Items.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/288070iC415BF2E9258F5C0/image-size/large?v=v2&px=999 "Read Items.png")
If it will successfully execute it returns statusCode 200 and records in
the body if records are available.
![Read Items
OP.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/288083iA55015B4873A2108/image-size/large?v=v2&px=999 "Read Items OP.png")
 

**3. Create item in To Do list (Create Operation)**
**Site Address:** Select the Site URL in which we want to perform
actions

**Method:** *POST*

**Uri:** *\_api/web/lists/getbytitle(\'To Do\')/items*

**Headers*****:** Need JSON object*

*  {\
       \"content-type\": \"application/json;odata=verbose\",\
       \"accept\": \"application/json;odata=verbose\"\
  }*

**Body :** *RequestBody*

*     {\
         \"\_\_metadata\": {\
               \"type\": \"SP.Data.To_x0020_DoListItem\"\
        },\
       \"Title\": \"Demo Task1\",\
       \"Status\": \"Started\"\
   }*
In the request body, we need type so now the question is how to get
type? It is ***SP.Data.{ListName}ListItem*** (replace {*ListName*} with
list name. if space in between list name then it will be separated with
***\_x0020\_***).
![Create
item.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/288073i920EFE8CE6406947/image-size/large?v=v2&px=999 "Create item.png")
If it will successfully execute it returns statusCode 201.
![Create item
op.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/288082i98AD4FD9BF6B56E7/image-size/large?v=v2&px=999 "Create item op.png")
 
**4. Update item in To Do list (Update Operation)**
**Site Address:** Select the Site URL in which we want to perform
actions

**Method:** PATCH

**Uri:** *\_api/web/lists/getbytitle(\'To Do\')/items(itemID) *

**Headers*****: ***

*  {\
      \"content-type\": \"application/json;odata=verbose\",\
      \"IF-MATCH\": \"\*\"\
}*

**Body :** *RequestBody*

*     {\
         \"\_\_metadata\": {\
               \"type\": \"SP.Data.To_x0020_DoListItem\"\
        },\
       \"Title\": \"Task1\",\
   }*

**  **

**![Update
Item.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/288076i791D97200BD29A67/image-size/large?v=v2&px=999 "Update Item.png")
 

**5. Delete item in To Do list (Delete Operation)**
**Site Address:** Select the Site URL in which we want to perform
actions

**Method:** DELETE

**Uri:** *\_api/web/lists/getbytitle(\'To Do\')/items(itemID) *

**Headers**

```
{     \
      \"content-type\": \"application/json;odata=verbose\",\
      \"IF-MATCH\": \"\*\",\
      \"X-HTTP-Method\": \"DELETE \"\
}
```

**Body:** *Not required*
*![Delete
ietm.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/288078i11A2FD5057908D2D/image-size/large?v=v2&px=999 "Delete ietm.png")

## Summary 

In this article, we have seen the step-by-step implementation of CRUD
operation of SharePoint list items using Send an HTTP request to
SharePoint in Power automate.
Hope this helps!
Sharing is caring!
