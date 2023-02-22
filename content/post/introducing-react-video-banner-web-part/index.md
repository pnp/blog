---
title: "Introducing React Video Banner Web Part"
date: 2021-05-06T04:18:00-04:00
author: "Mohamed Derhalli"
githubname: derhallim
categories: ["Community post"]
images:
- images/derhallim_0-1620249069072.png
tags: ["SharePoint Framework (SPFx)"]
type: "regular"
---

In this post, we will see how easy it is to build a cool looking video
banner web part using SPFx with the help of PnP reusable property pane
controls. First of all, the requirements: 

-   The web part should look like a banner on top of pages, with a video
    playing
-   Ability to change the overlay text on this video
-   Control the banner area size

This is what the [PnP React Video Banner web
part](https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-video-banner "PnP React Video Banner web part")
offers, once you add the web part to your page, you will be able to
select a video (using the file picker control from the PnP Reusable
Property Pane Controls), you will be able to modify the text overlay and
its color, control the height of the video area and lastly (at least for
now) modify the brightness: 
  ![derhallim_0-1620249069072.png](images/derhallim_0-1620249069072.png)

 These settings would provide you with a web part that looks like this: 
 ![derhallim_4-1620249695924.png](images/derhallim_4-1620249695924.png)
 

Now let's have a look at the code itself which is pretty simple. The
file structure can be seen below:


 ![derhallim_1-1620252146944.png](images/derhallim_1-1620252146944.png)
 
The web part has only one functional component named: `VideoBackground`
that accepts the following properties as defined in the
IVideoBackgroundProps.ts file: wpTitle (string), videoUrl (string),
labelColor (string), brightness (number), height (number).
 ![derhallim_2-1620252225550.png](images/derhallim_2-1620252225550.png)
The video url and the label color are set with the help of PnP Property
Pane Controls as shown below: 
 ![derhallim_0-1620252048668.png](images/derhallim_0-1620252048668.png)


Once the properties are setup on the VideoBackgroundWebPart.ts file, we
pass them to the VideoBackground.tsx component. 


 ![derhallim_6-1620252844193.png](images/derhallim_6-1620252844193.png)


All good so far? Now in our functional component, we have an HTML video
control where the source of the video is set to the videoUrl prop we
pass and we play with the CSS filter prop to set the brightness by
adding the value concatenated with % as we need a brightness
percentage: 

![derhallim_3-1620252272134.png](images/derhallim_3-1620252272134.png)

Notice the ref attribute on the video control? The reason we have it is
that we want to refresh the video whenever we change the video url. By
default, when changing the properties, all values will be reflected
except for the video url, it needs to be explicitly refreshed on the
video control. So we get a reference to the video control using React's
ref, where we define the \"vRef\" value on the functional component
itself. 
We then use React's useEffect to check if the video url has changed or
not, if it has changed, we call the load() function on the video
reference itself: 

 ![derhallim_4-1620252332115.png](images/derhallim_4-1620252332115.png)

 
Some notable points about the CSS used is the div that's available just
before the video control, it's aligned using an absolute position with
a display of flex to position the h1 element inside of it. The video
element itself has a CSS property *object-fit: cover.*


As demonstrated, with SPFx and the help of PnP Reusable Property Pane
controls, building web parts using modern development techniques is very
easy and isn't time consuming as some may think! Source code is
available on GitHub along with other awesome web parts by the community,
for more information about all the PnP offerings,
checkout <https://aka.ms/m365pnp> \
\
*#SharingIsCaring*
