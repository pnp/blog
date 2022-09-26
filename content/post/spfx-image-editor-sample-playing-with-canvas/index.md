---
title: "SPFx Image Editor Sample - Playing with Canvas"
date: 2021-03-31T09:49:00-04:00
author: "Peter Paul Kirschner"
categories: ["Community post"]
images:
- images/Screenshot 2021-03-22 at 21.42.06.png
tags: ["SharePoint Framework (SPFx)"]
type: "regular"
---

In the year 2020, Microsoft added a new capability to the Image Viewer
Web part Resize and Crop. These are excellent features, but I want to
try to give the End User more Manipulation Options. I was thinking about
Flip and Rotate. First, I tried with CSS it worked, but for me, an
Image-Editor should work in every combination of applied manipulations.

So, I started to play with canvas.

![Screenshot 2021-03-22 at 21.42.06.png](images/Screenshot 2021-03-22 at 21.42.06.png)

## How HTML canvas  works

 ![Screenshot 2021-03-22 at 20.29.22.png](images/Screenshot 2021-03-22 at 20.29.22.png)
![Screenshot 2021-03-22 at 20.29.33.png](images/Screenshot 2021-03-22 at 20.29.33.png)

 
The next step is to draw an image to our HTML canvas
 

``` {.lia-code-sample .language-html}
<canvas id="myCanvas" width="200" height="100" style="border:1px solid #d3d3d3;"></canvas>
<script>
  const img= new Image()
  img.crossOrigin = "Anonymous";
  img.addEventListener("load", imageReceived, false);
  img.src='https://pnp.github.io/images/hero-parker-p-800.png';

  function imageReceived() {
  const c = document.getElementById("myCanvas");
  const ctx = c.getContext("2d");
  c.width = img.width;
  c.height = img.height;
  ctx.drawImage(img, 0, 0);
  ctx.font = "30px Arial";
  ctx.strokeText("Hello PnP-Community",10,50);
}
</script>
```
 

![Parker draw on canvas](images/Screenshot 2021-03-23 at 14.38.34.png)

How to Flip such thing

FlipY
 

```javascript
ctx.translate(c.width, 0);
ctx.scale(-1, 1);
```
 

![Flip Parker Y](images/Screenshot 2021-03-23 at 14.47.53.png)

FlipX
 

```javascript
ctx.translate(0, c.height);
ctx.scale(1, -1);
```
 

![Flip Parker X](images/Screenshot 2021-03-23 at 14.47.07.png)

Rotate:

To explain rotation, I start with a straightforward Sample

I draw only a Rectangle on a canvas

![Screenshot 2021-03-22 at 21.48.21.png](images/Screenshot 2021-03-22 at 21.48.21.png)

 

Then I rotate this thing for 20 Degree

![Screenshot 2021-03-22 at 21.48.51.png](images/Screenshot 2021-03-22 at 21.48.51.png)

 

As you can see the rotation Point is not in the Center of the Canvas.
The Rotation Point is at Position 0,0

![Screenshot 2021-03-22 at 21.54.42.png](images/Screenshot 2021-03-22 at 21.54.42.png)

For this sample I want to rotate the Rectangle from the center of the
Black box. So we have to move center to position 0,0 than the rotation
and than move it back to original position. 
 Now it looks good, but the edges are out of the canvas. Due to the
rotation, the height and width has to be changed. Welcome back to maths
class.

To i Combine the previous knowledge with the basic Parker Sample here it
is
 

```javascript
const img= new Image()
  img.crossOrigin = "Anonymous";
  img.addEventListener("load", imageReceived, false);
  img.src='https://pnp.github.io/images/hero-parker-p-800.png';

  function imageReceived() {
  const c = document.getElementById("myCanvas");
  const ctx = c.getContext("2d");
  const oldwidth =c.width = img.width;
  const oldheight =c.height = img.height;
  const degree=20;
  const radian=degree*Math.PI/180 //Radian

  const a = oldwidth * Math.abs(Math.cos(radian));
  const b =  oldheight * Math.abs(Math.sin(radian));
  const p = oldwidth * Math.abs(Math.sin(radian));
  const q =  oldheight * Math.abs(Math.cos(radian));
  const newwidth = a + b;
  const newheight = p + q;

   const offsetwidth = (newwidth - oldwidth) / 2;
   const offsetheight = (newheight - oldheight) / 2;
    c.width = newwidth;
    c.height = newheight;

  ctx.translate(newwidth/2,newheight/2);
  ctx.rotate(radian);
  ctx.translate(-newwidth/2,-newheight/2);

  ctx.fillStyle = "#0078d4";
  ctx.fillRect(offsetwidth,offsetheight,oldwidth,oldheight);

  ctx.drawImage(img, offsetwidth, offsetheight);
   ctx.font = "30px Arial";
  ctx.strokeText("Hello PnP-Community",offsetwidth+10,offsetheight+50);

}
```

![Screenshot 2021-03-23 at 15.18.24.png](images/Screenshot 2021-03-23 at 15.18.24.png)

 

Thank's, Parker to be my Top-Model

Try it [sp-dev-fx-webparts/samples/react-image-editor at master ·
pnp/sp-dev-fx-webparts
(github.com)](https://github.com/pnp/sp-dev-fx-webparts/tree/master/samples/react-image-editor)
 
