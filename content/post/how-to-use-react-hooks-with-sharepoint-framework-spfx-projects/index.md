---
title: How to use React hooks with the SharePoint Framework (SPFx)

# Add a summary to convince readers to read your article (recommended). It will display on the homepage.
summary: Learn how to convert a default class-based React component to a functional component, and then see how to implement React hooks in the web part!
date: 2022-10-19T15:12:25.011Z

# Author. Your own name
author: "Andrew Connell"

# GitHub username.
githubname: "andrewconnell"

# Featured image
# To use, add an image named `thumbnail.jpg/png` to your page's images folder. Make sure to replace the placeholder image
images:
- images/thumbnail.png

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
# Community posts should always use "Community post" as the categories
tags: ["SharePoint Framework (SPFx)"]
categories: ["Community post"]
canonicalURL: https://www.voitanos.io/blog/how-to-use-react-hooks-with-sharepoint-framework-spfx-projects/
---
> This article originally appeared on Andrew Connell's site, **[How to use React hooks with the SharePoint Framework (SPFx)](https://www.voitanos.io/blog/how-to-use-react-hooks-with-sharepoint-framework-spfx-projects/?utm_medium=website&utm_source=pnpblog&utm_campaign=blog&utm_content=How%20to%20use%20React%20hooks%20with%20the%20SharePoint%20Framework%20(SPFx))**, where it's [also available as a video](https://youtu.be/EzI-k5lqIng) and podcast episode. You can also download the code from the project used in this article from the original article

The current version of the Yeoman generator for the SPFx still uses the older-style React class components. Because that’s what you get by default, that’s what most developers end up using.

But functional components enabled by React hooks have become widely popular... and I get a lot of questions on how to use React hooks in your SharePoint projects!

So... until Microsoft updates the Yeoman generator, I’m going to show you how you change your new projects to React hooks in just a few minutes. And then, I’ll show the basics of React hooks with a simple example.

## Introduction

Let’s start by looking at the current state of React in SPFx projects.

Hooks were added to React v16.8 and they let you use the component’s state and other React features without writing classes. I love them because I find I write less code and the code that I do write is more expressive of what I want to happen when other things happen on the page.

The SharePoint Framework has supported React v16.8 since the SPFx v1.9.1 was released in August 2019, but we still can’t easily use them!

**Why?** Because even today, in 2022, with SPFx v1.15.2, the Yeoman generator for the SharePoint Framework is *still* creating React class-based controls:

```typescript
export default class SpFxReactHooksWebPart
  extends BaseClientSideWebPart<ISpFxReactHooksWebPartProps> {

  public render(): void {
    const element: React.ReactElement<ISpFxReactHooksProps> =
      React.createElement(SpFxReactHooks, { .. });
    ReactDom.render(element, this.domElement);
  }

  protected onInit(): Promise<void> {
    return super.onInit();
  }
}
```

> **What is a React hook?**
>
> A hook is a function that allows you to “hook into” React state & lifecycle events from function components, meaning you don’t have to use classes. They’re 100% backward compatible & entirely opt-in. React includes a few hooks, but you can create your own if you wanted to. In this video, I’m only going to cover two popular and most commonly used hooks: `useState` & `useEffect`.
>
> ▶ [Reactjs.org: Hooks at a Glance](https://reactjs.org/docs/hooks-overview.html)

While there’s nothing wrong with these class components, let’s look at how to convert this project to a functional component that leverages React hooks.

## Convert a class component to a functional component

There’s nothing to change with the web part because it's just a React component as far as SPFx is concerned. All the changes you need to implement to switch to functional components happen in the  React component.

Converting the default class component to a functional component is pretty simple. The following code shows the core things you need to change to the component. *To keep things simple, I removed a lot of the boilerplate HTML in the default component’s `render()` method.*

The steps include:

- change the declaration from a class to an object
- export the object
- remove the `render()` method
- change the reference to the component’s `props` to not use the `this` keyword because it's not a class

```diff
  import * as React from 'react';
  import styles from './SpFxReactHooks.module.scss';
  import { ISpFxReactHooksProps } from './ISpFxReactHooksProps';
  import { escape } from '@microsoft/sp-lodash-subset';

- export default class SpFxReactHooks extends React.Component<ISpFxReactHooksProps, {}> {
+ const SpFxReactHooks: React.FC<ISpFxReactHooksProps> = (props) => {
-   public render(): React.ReactElement<ISpFxReactHooksProps> {
    const {
      hasTeamsContext,
      userDisplayName
-   } = this.props;
+   } = props;

    return (
      <section className={`${styles.SpFxReactHooks} ${hasTeamsContext ? styles.teams : ''}`}>
        <div className={styles.welcome}>
          <h2>Well done, {escape(userDisplayName)}!</h2>
        </div>
      </section>
    );
  }

+ export default SpFxReactHooks;
```

**That's it!** Your class component is now a functional component.

Now let’s see how we can use React hooks in this component.

## Implement state & refresh the web part

One of the most common things we do in React components is work with the state. Let’s see how can do this with the React hook `useState`.

Let’s do this by adding a new state property `counter` and add it to our rendering:

```diff
  import * as React from 'react';
+ import { useState } from 'react';
  import styles from './SpFxReactHooks.module.scss';
  import { ISpFxReactHooksProps } from './ISpFxReactHooksProps';
  import { escape } from '@microsoft/sp-lodash-subset';

  const SpFxReactHooks: React.FC<ISpFxReactHooksProps> = (props) => {
    const {
      hasTeamsContext,
      userDisplayName
    } = props;

+   const [counter, setCounter] = useState<number>(1);

    return (
      <section className={`${styles.SpFxReactHooks} ${hasTeamsContext ? styles.teams : ''}`}>
        <div className={styles.welcome}>
          <h2>Well done, {escape(userDisplayName)}!</h2>
+         <div>Counter: <strong>{counter}</strong></div>
        </div>
      </section>
    );
  }

  export default SpFxReactHooks;
```

Notice when I create the `counter` property, I’m also defining the *setter* method I can use to update the counter:

```typescript
const [counter, setCounter] = useState<number>(1);
```

This replaces the `this.setState();` method we use with React class components. I’m also setting the initial value of the `counter` to `1` by passing it into the constructor.

## Add button & event handler

With a state property created and showing up in our component, let’s tackle two more common things: event handlers when something happens on the page and update the state property which triggers the repainting of the component on the page.

In this case, let’s add a button that increments the counter when the button is clicked:

```diff
  import * as React from 'react';
  import { useState } from 'react';
  import styles from './SpFxReactHooks.module.scss';
  import { ISpFxReactHooksProps } from './ISpFxReactHooksProps';
  import { escape } from '@microsoft/sp-lodash-subset';

  const SpFxReactHooks: React.FC<ISpFxReactHooksProps> = (props) => {
    const {
      hasTeamsContext,
      userDisplayName
    } = props;

    const [counter, setCounter] = useState<number>(1);

+   const onButtonClick = (): void => {
+     setCounter(counter + 1);
+   }

    return (
      <section className={`${styles.SpFxReactHooks} ${hasTeamsContext ? styles.teams : ''}`}>
        <div className={styles.welcome}>
          <h2>Well done, {escape(userDisplayName)}!</h2>
          <div>Counter: <strong>{counter}</strong></div>
+         <button onClick={ () => onButtonClick() }>+</button>
        </div>
      </section>
    );
  }

  export default SpFxReactHooks;
```

Notice how much cleaner that code is compared to setting the state value with a class component?

Before, when using the `setState()` method, when I wanted to use the previous state value, like in my case where I need to increment the counter, I’d have to write a lot more code to keep track of the state and then set it as an immutable object, like the following:

```typescript
this.setState((prevState) => ({
  ...prevState,
  counter: prevState.counter + 1
}));
```

## Add event handler when state property changes

Now, let’s see how to add a side effect to *hook* into other things happening in our component. This is done with the hook `useEffect`.

In this example, I’ll add a new state property to indicate if the counter value is even or odd. It needs to change whenever the counter value changes. Sure, I could have implemented this directly in the rendering of the component, but it’s a simple example to show how side effects work.

```diff
import * as React from 'react';
- import { useState } from 'react';
+ import { useState, useEffect } from 'react';
  import styles from './SpFxReactHooks.module.scss';
  import { ISpFxReactHooksProps } from './ISpFxReactHooksProps';
  import { escape } from '@microsoft/sp-lodash-subset';

  const SpFxReactHooks: React.FC<ISpFxReactHooksProps> = (props) => {
    const {
      hasTeamsContext,
      userDisplayName
    } = props;

    const [counter, setCounter] = useState<number>(1);
+   const [evenOdd, setEvenOdd] = useState<string>('');

+   useEffect(() => {
+     setEvenOdd((counter % 2 === 0) ? 'even' : 'odd');
+   }, [counter]);

    const onButtonClick = (): void => {
      setCounter(counter + 1);
    }

    return (
      <section className={`${styles.SpFxReactHooks} ${hasTeamsContext ? styles.teams : ''}`}>
        <div className={styles.welcome}>
          <h2>Well done, {escape(userDisplayName)}!</h2>
-         <div>Counter: <strong>{counter}</strong></div>
+         <div>Counter: <strong>{counter}</strong> is <strong>{evenOdd}</strong></div>
          <button onClick={ () => onButtonClick() }>+</button>
        </div>
      </section>
    );
  }

  export default SpFxReactHooks;
```

The introduction of the `useEffect()` method allows me to *hook into* whenever the `counter` state property changes. You do that by passing it in as the second argument. Now, whenever that property changes, my *side effect* will run and set the value of another state property `evenOdd`. By changing the state, that triggers React to re-render the component to display the new values.

## Initialize the component with `useEffect`

Now let’s see how we tackle a common requirement: initiating the component. In class components, we’re used the `componentDidMount` and `componentDidUpdate` lifecycle methods to handle this scenario.

The way you do this same thing with hooks is to add a `useEffect` method with an empty array of dependencies. So, let’s add some SPFx sauce to this and get some data from the SharePoint REST API when this component loads:

```diff
  import * as React from 'react';
  import { useState } from 'react';
  import { useState, useEffect } from 'react';
  import styles from './SpFxReactHooks.module.scss';
  import { ISpFxReactHooksProps } from './ISpFxReactHooksProps';
  import { escape } from '@microsoft/sp-lodash-subset';
+ import { SPHttpClient, SPHttpClientResponse } from '@microsoft/sp-http';

  const SpFxReactHooks: React.FC<ISpFxReactHooksProps> = (props) => {
    const {
      hasTeamsContext,
      userDisplayName,
+     // update prop interface & add as input prop in web part (not shown)
+     spHttpClient
    } = props;

    const [counter, setCounter] = useState<number>(1);
    const [evenOdd, setEvenOdd] = useState<string>('');
+   const [siteLists, setSiteLists] = useState<string[]>([]);

+   useEffect(() => {
+     (async () => {
+       // line wrapping added for readability
+       const endpoint: string = `${currentSiteUrl}/_api/web/lists
+                         ?$select=Title
+                         &$filter=Hidden eq false
+                         &$orderby=Title
+                         &$top=10`;
+       const rawResponse: SPHttpClientResponse = await spHttpClient.get(
+                                    endpoint, SPHttpClient.configurations.v1);
+       setSiteLists(
+         (await rawResponse.json()).value.map((list: { Title: string }) => {
+           return list.Title;
+         })
+       );
+     })();
+   }, []);

    useEffect(() => {
      setEvenOdd((counter % 2 === 0) ? 'even' : 'odd');
    }, [counter]);

    const onButtonClick = (): void => {
      setCounter(counter + 1);
    }

    return (
      <section className={`${styles.SpFxReactHooks} ${hasTeamsContext ? styles.teams : ''}`}>
        <div className={styles.welcome}>
          <h2>Well done, {escape(userDisplayName)}!</h2>
          <div>Counter: <strong>{counter}</strong> is <strong>{evenOdd}</strong></div>
          <button onClick={() => onButtonClick()}>+</button>
+         <ul>
+         {
+           siteLists.map((list: string) => (
+             <li>{list}</li>
+           ))
+         }
+         </ul>
        </div>
      </section>
    );
  }

  export default SpFxReactHooks;
```

One thing I do want to mention here about using the `useEffect` for initialization of the component. If I don't include a second parameter, like `useEffect(())`, the effect will run *after every single render of the component*.

That’s clearly not what we want in this case... I don’t want to query the SharePoint REST API for the lists every time the component is repainted on the screen.

So, to tell React that I only want it to run when the component is mounted & unmounted, I give it an empty array, `useEffect((), [])`, to tell React that it doesn’t depend on anything and therefore, only run when the component is initially mounted.

## Get the code

Pretty easy right? It’s a simple project, but if you want a copy of the code, head over to my site to request a copy: **[How to use React hooks with the SharePoint Framework (SPFx)](https://www.voitanos.io/blog/how-to-use-react-hooks-with-sharepoint-framework-spfx-projects?dst=pnpblog&utm_medium=website&utm_source=pnpblog&utm_campaign=blog&utm_content=How+to+use+React+hooks+with+the+SharePoint+Framework+(SPFx))**

## What do you think about React hooks?

I much prefer using React hooks and functional components over using the traditional class-based approach. And after showing you how little work is required to switch my new components over to functional components to leverage hooks, I think it’s worth it!

What do you think about using React hooks in your SPFx projects? Do you prefer them and functional components over class components? Or not? [I’d like to know what you think!](https://www.twitter.com/andrewconnell)

## Want to see it in action? Watch the video!

If you're the type who prefers to watch the demonstration, check out the video demo of this article, published to my YouTube channel:

{{< youtube "EzI-k5lqIng" >}}
