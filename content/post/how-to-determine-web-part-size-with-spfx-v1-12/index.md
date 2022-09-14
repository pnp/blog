---
title: "How to determine web part size with SPFx v1.12"
date: 2021-03-23T03:55:00-04:00
author: "Yves Habersaat"
githubname: yhabersaat
categories: ["Community post"]
images:
- images/web-part-width.png
tags: ["SharePoint Framework (SPFx)"]
type: "regular"
---

## Context

You might know that this new SPFx v1.12 feature has an old story behind
it. In the past, developers were getting web part's width by
unsupported ways like DOM classes or attributes. It was working pretty
well until Microsoft decided to update SharePoint Online DOM in October
last year and broke a lot of custom developments. As Microsoft says, DOM
is not and API and you should avoid taking any dependencies in it but
until now, nothing was officially released to solve this issue
correctly. It's now done, SPFx v1.12 adds a **width** property and
an **onAfterResize()** event to determine the width of your web part.
**Note:** In this article, I'm using a web part project with SPFx
v.1.12 and React framework.

## Determine web part size

In your web part TS file, you can add the **onAfterResize()** method to
get notified when the web part is resized (for example when you resize
your window):

```javascript
  protected onAfterResize(newWidth: number) {
    console.log("New web part width: " + newWidth);
  }
```

This new method is documented as below:

```javascript

This API is invoked when the web part container dom element width is changed, e.g. when the browser window is resized and when the property pane is toggled open/closed.

@param newWidth — Width (in pixels) of the container for the web part after the resize event.

@remarks
Web parts should utilize this method to perform operations such as potentially re-rendering components based on the new available width for the web part.

@virtual
```

Then you can use the **width** property as a prop for your React
component:

```javascript
  public render(): void {
    const element: React.ReactElement<IDemoWebPartWidthProps> = React.createElement(
      DemoWebPartWidth,
      {
        description: this.properties.description,
        webPartWidth: this.width
      }
    );

    ReactDom.render(element, this.domElement);
  }
```

This new property is documented as below:

```javascript
This propery returns the width of the container for the web part.

@returns — Width (in pixels) of the container for the web part.

@remarks
Web parts should utilize this property to perform operations such as any conditional styling of components based on the initial available width for the web part.

@internalRemarks
This function retrieves web part's key to get stored section width from cache. If cache key does not exist in cache it will calculate and store the width before returning.

In the case where getWebPartCacheKey is not passed down, it will go through the original workflow to caculate web part width.
```

And you can display it in your component render() method:

```javascript
<p className={ styles.description }>Web part width = { this.props.webPartWidth }</p>
```

Final result of this demo web part:


![web-part-width.png](images/web-part-width.png)

This a great add to SPFx and allows developers to re-render components
when the web part is resized
Happy coding everyone!


## Resources

[Determine the rendered web part width | Microsoft
Docs](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/basics/determine-web-part-width)

[SharePoint Framework enterprise guidance | Microsoft
Docs](https://docs.microsoft.com/sharepoint/dev/spfx/enterprise-guidance#in-perspective-sharepoint-framework-in-the-broader-sharepoint-platform)
