---
title: "Running a Power App as Edge Extension"
date: 2021-10-12T02:53:00-04:00
author: "Albert-Jan Schot"
githubname: appieschot
categories: ["Community post"]
images:
- images/edge-plugin.gif
tags: ["Power Apps"]
type: "regular"
---

To get started you do need a sample, the demo used to get you started is
a solution to capture interesting pages in your browser to read later. I
am aware that there are dedicated solutions for that, but sometimes I
suffer from the not invented here syndrome and want to build something
myself...
The final result will look as follows: 

![edge-plugin.gif](images/edge-plugin.gif)
There are three building blocks that make up the logic: 

1.  Edge Extension
2.  Power App 
3.  Flow 

If you count the ToDo there is a fourth one, but we are only using a
ToDo list to store data from the Flow so there is no real logic required
on that side.  The goal is thus to run our Power App as an Edge
Extension.

## Edge Extension 

Up until this scenario I never had build an Edge Extension so I resorted
to Google to figure out the steps required. As it turns out there are
quite a few tutorials and the process itself is straightforward. You
have a `manifest.json` that describes the extension and a set of files
like icons, html and JavaScript. You can walk through the [Create an
extension
tutorial](https://docs.microsoft.com/microsoft-edge/extensions-chromium/getting-started/part1-simple-extension)
to get a feeling of all the components. 
Our Manifest itself is straight forward. We will be using two
files `frame.html` and `frame.js`, those must be in
the `web_accessible_resources`. We also will use
a `contentscript.js` file that is added as a `content_scripts`. Since we
will be authenticating users, we need to have access to the cookies from
our extension. Adding the `"permissions": ["cookies"]` fixes that for
us. The full `manifest.json` would look something like this:
 

```json
{
    "name": "Power App",
    "version": "0.0.0.3",
    "manifest_version": 2,
    "description": "Loading your custom Power App into the browser.",
    "content_scripts": [{
        "js": ["contentscript.js"],
        "matches": ["*://*/*"],
        "all_frames": true
    }],
    "web_accessible_resources": [
        "frame.html",
        "frame.js"
    ],
    "permissions": [
        "cookies"
    ]
}
```
 
The `contentscript.js` will load our `frame.html` as an iframe. There is
some logic to make sure recursive frame insertion will not happen and
will only load if the iFrame is not redirecting us
to `https://login.microsoftonline.com`.
The `login.microsoftonline.com` page will fail to render if you are
injecting an Iframe due to security concerns so make sure this is in
place. Finally we add some query
string parameters `origin` and `title` to our loaded `frame.html`. That
way we can capture the page we inject our iframe on. This captured data
can be used by our Power App later on. The full `contentscript.js` looks
as follows:
 
```javascript
// Avoid recursive frame insertion...
var extensionOrigin = 'chrome-extension://' + chrome.runtime.id;

if (!location.ancestorOrigins.contains(extensionOrigin) && !location.origin.startsWith("https://login.microsoftonline.com")) {

    var iframe = document.createElement('iframe');
    // Must be declared at web_accessible_resources in manifest.json
    iframe.src=chrome.runtime.getURL('frame.html?origin=' + encodeURI(location.href) + "&title=" + encodeURI(document.title));

    // Some styles for a fancy sidebar
    iframe.style.cssText = 'position:fixed;top:0;left:10;display:block;' +
        'width:300px;height:530px;overflow=hidden;z-index:1000;';
    document.body.appendChild(iframe);
}
```
 
The `frame.html` file can be an almost empty HTML file or contain as
much styling as you want. I opted for a clean html file with the magic
happening here. 


``` {.lia-code-sample .language-markup}
<body>
    <div id="iframeplaceholder"></div>
    <script src="frame.js"></script>
</body>
```

I opted for a `frame.js` file as inline JavaScript is not allowed in an
extension. By adding the  `frame.html`  and  `frame.js` to the
`web_accessible_resources` this no longer is an
issue.  The `frame.js` is used to get the query string parameters, add
them to our Power App play URL and set that URL as the Iframe. Make sure
to update the `iframe.src` URL to reflect your Power App ID.



```javascript
const params = new URLSearchParams(window.location.search)

var iframe = document.createElement('iframe');
iframe.src="https://apps.powerapps.com/play/xxxxxxx?source=iframe&title=" + encodeURI(params.get('title')) + "&url=" + encodeURI(params.get('origin'))

var myFrame = document.getElementById('iframeplaceholder');
myFrame.appendChild(iframe);
```

This are all the steps required to run a Power App in your Edge Browser.
However, make sure to reload your extension when side loading. Changes
might not always trickle down as some of the content is cached. My best
experience was to reload the extension each time I changed something in
the JS or HTML.

## Power Apps 

Once you have your Edge Extension working the Power App can be running
whatever you like. There is a bit of a chicken and egg issue as you need
the Power App ID for your Edge Extension to work, so you could start
with creating an empty app and save it to get the ID you need. Or you
could update the Edge Extension once the App is ready. To create an
application that can create something in To Do I picked a canvas app.
There are no 'real' requirements on the app side of things, but keep in
mind the sizing of your iframe when designing parts the app itself.
There is a To-Do connector you can use, but that is slightly limited. I
picked the Power Automate connector to have more control over the
options passed on. 
The Power App itself only uses the two parameters that are passed on,
and in return passes those on to the Flow. Passing on parameters can be
done using the `Param` option in the function window. My call to the
Flow is linked to the `OnSelect` and runs as follows:

``` {.lia-code-sample .language-applescript}
'PowerApp-ToDo'.Run(Param("title"), Param("url"));
```

That is all there is to our app; a single button that calls our Flow. 

## Flow 

The last component is the Flow, it uses the `Power App` trigger and a
single action to create a new ToDo. Since we are passing the title and
URL we can use those in the Flow as input parameters for our action
using the following
expression: `@{triggerBody()['Addato-do(V3)_Title']}`. The full flow
looks like this:
![flow-todo.png](images/flow-todo.png)

## Fusion Development 

Now I understand that some of these steps could have been done writing
actual code instead of using the Power Platform. However the fact that I
could select together a few components and have them interact with my
Edge browser really appealed to me :rocket:. Building a plugin to
capture specific data from your browser has become way easier. Something
that fits within the fusion development approach you hear a lot about.
So instead of diving head first into complex code I decided to play
around with the Power App approach and I must admit I am not
disappointed. The next version should have a little more logic in place
to prevent the plugin itself opening in multiple iframes on a page, but
other then that I had this demo working quicker then expected. 
