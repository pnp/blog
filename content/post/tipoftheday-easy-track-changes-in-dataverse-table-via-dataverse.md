# TipOfTheDay - Easy Track changes in dataverse table via dataverse API

Note: I am using [PostMan](https://www.postman.com/downloads/) in my
example. 

1\. First  - use \"GET\" http request  to get details of dataverse table
\"**Accounts**\": 
 

``` {.lia-code-sample .language-markup}
{{webapiurl}}/accounts?$select=name,accountnumber,telephone1,websiteurl
```
 

*{{webapiurl}} - variable from the postman, contains a link to your
environment API.*

\
**Accounts** table data retrieved: (image 1)

![ValerasNarbutas_0-1633418328122.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/315182iB0F9C764E4940B50/image-size/large?v=v2&px=999 "ValerasNarbutas_0-1633418328122.png")

1. Now add a new header in postman call:
``` {.lia-code-sample .language-markup}
"Prefer odata.track-changes"
```
 http request call will return additional information:\
**deltalink** with **deltatoken** in body area (image 2)\

![ValerasNarbutas_0-1633418806793.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/315184i95C9713EA849BC2D/image-size/large?v=v2&px=999 "ValerasNarbutas_0-1633418806793.png")

3\. Use delta token in as GET request (image 3 )

![ValerasNarbutas_1-1633418877623.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/315185i374C0ED6A3EC6B15/image-size/large?v=v2&px=999 "ValerasNarbutas_1-1633418877623.png")

Were are no changes that happen last time we did
request to **accounts** table, this is why under \"**value**\" it shows
empty array\
If I do changes like: add **new** details, **edit** and **delete** in
**accounts**  table I would get result: (image 4)\

![ValerasNarbutas_2-1633419038732.png](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/315186i465EC2B05840A7C0/image-size/large?v=v2&px=999 "ValerasNarbutas_2-1633419038732.png")

Now \"value\" contain 3 additional results for **new**, **edit**, and
**delete** records.

Such updates checking method would be very useful when implementing
solutions to synchronize data with external systems using Logic Apps or
Power Automate or any other tool or approach you are most comfortable
with.

Hope this is useful :) have a great day

[#dataverse](https://web.yammer.com/main/search/threads?search=%23dataverse)
[#dataverseAPI](https://web.yammer.com/main/search/threads?search=%23dataverseAPI)
[#tip](https://web.yammer.com/main/search/threads?search=%23tip)
[#postman ](https://web.yammer.com/main/search/threads?search=%23postman)[#tipoftheday](https://web.yammer.com/main/search/threads?search=%23postman)

