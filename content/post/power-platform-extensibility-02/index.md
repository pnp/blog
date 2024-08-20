---
title: "Power Platform extensibility options in Power Apps"
date: 2024-03-20T08:50:00-04:00
author: "Kinga Kazala"
githubname: kkazala
categories: ["Community post"]
images:
- images/thumbnail2.png
tags: ["Power Platform", "Power Apps", "Power Automate", "Dataverse"]
type: "regular"
---

## Power Platform extensibility options series

1. [Power Platform extensibility options](./../power-platform-extensibility-01)
1. Power Apps - this article
1. [Power Automate](./../power-platform-extensibility-03)
1. [Dataverse](./../power-platform-extensibility-04)


## Where to place logic

>**In Power Apps, the execution of components can be both synchronous and asynchronous, depending on the specific functions and scenarios.**
>
>**There is no built-in transaction support in Power Apps itself. However, you can use stored procedures called from a Power Automate flow to achieve transaction-like behavior.**

Whenever possible, you should first consider applying one of the several declarative process options to define or apply business logic.

>You set logic in **canvas apps** by using formulas. All the formula logic is processed on the device the app is run on. The more complex the logic is, the more processing power the device will require to be able to handle all the logic.
To keep the app performant, you should consider the following when placing logic in canvas apps:
>
>-  Use it in situations where you must make any changes immediately visible on the screen
>-  Use only simple logic, and avoid complex formulas with dozens of lines
>-  Limit it to a few data connectors in a formula
>-  Avoid using logic to manipulate or transform data
>-  Avoid processing multiple records at a time (for example, avoid using the `ForAll` function)
>
>**Model-driven** apps provide several ways to run logic and all of these options run on the device that runs the apps. Consider placing logic in model-driven apps if:

>- Logic needs to be run on the device.
>- The logic requires multiple entities (tables).
>- You need sophisticated logic that isn't available with out-of-the-box features.
>
>In general, if you're making apps with **complex logic, consider using model-driven apps instead** of trying to do everything by using **canvas apps**.
>
>Source: [Where to place logic: Canvas apps, model-driven apps, Microsoft Dataverse, or Power Automate flows?](https://learn.microsoft.com/en-us/power-apps/guidance/planning/logic#power-apps-canvas-apps)

Placing business logic directly in low-code applications is simpler to build, test, and has a lower maintenance cost, but it provides **limited options for reuse or to enforce consistency** across apps and automations.

Generally, you should limit this approach to **non–mission-critical, simple logic** that other applications or automations **don’t need** to use. Evaluate existing components first and then use code components only if there is a need for more complex and advanced customization.

>Key developer extensibility points: Canvas Apps
>
>- Build custom UI components using Power Apps component framework
>- Create custom connectors to communicate to your external data sources and services. A custom connector is a wrapper around a REST API and can be created using tools like Azure Functions and Azure API Management
>
>Key developer extensibility points: Model-driven apps
>
>- Build custom UI components using Power Apps component framework
>- Implement client business logic using JavaScript and the client API
>- Build HTML web resources
>
>Key developer extensibility points: Power Pages
>
>- Custom web page templates built with HTML, CSS, and Liquid
>- Extend site integration with Dataverse with the portals Web API
>- Use Visual Studio Code and the Power Platform CLI to enable metadata editing and CI/CD (Continuous Integration/Continuous Deployment) of site configurations
>
>Source: [Introduction to Microsoft Power Platform for developers](https://learn.microsoft.com/en-us/power-platform/developer/get-started#power-apps)

## Summary of extensibility options in Power Apps

![Extensibility options in Power Apps](./images/PowerApps.png)

See full resolution [here](https://gist.github.com/kkazala/9e83d5e7ad5e2cccf87586adf4523e0f)

In **Canvas app formulas, model-driven form script, business rules, and Power Apps component framework**, logic happens **in the user interface (client-side)** and the user will see the result immediately. When the operations are performed synchronously, the user's screen is blocked until all operations are completed.

|||Canvas Apps|Model-driven Apps|[Custom Pages](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/design-page-for-model-app)|Power Pages|
|-|-|-|-|-|-|
|[Formulas - Power Apps](#formulas-using-power-fx) |Power Fx|✅|✅|✅|❌|
|[Script web resources](#web-resources-with-javascript) |JavaScript |❌|✅|❌|❌|
|[Low-code canvas components](#low-code-canvas-components-using-power-fx) with [behavior formulas](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/component-behavior)* and [component properties](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/component-properties)|Power Fx|✅|👉|✅|❌|
|[Low-code plugins](#low-code-plug-ins-using-power-fx) |Power Fx, Connectors|✅|👉|✅|❌|
|[PowerApps component framework](#powerapps-component-framework-pcf-using-typescript) (PCF)|Typescript |✅|✅|✅|✅|
|[React controls & platform libraries](#react-controls-using-typescript--react) |TypeScript |✅|✅|✅|❌|
|[Custom connectors](#custom-connectors-with-rest-api) |openAPI  |✅|👉|✅|❌|
|[Custom webpage templates](https://learn.microsoft.com/en-us/power-pages/configure/web-templates)|HTML, CSS, Liquid  |❌|❌|❌|✅|

\* Behavior formulas for components (experimental): The feature to create custom behavioral properties is currently experimental. However, you can use the default OnReset property that is available on all components in your production environment.

## Formulas using Power Fx

Read more: [Formulas](https://learn.microsoft.com/en-us/power-platform/power-fx/formula-reference-overview)

Formulas combine many elements, for example:

- **Functions:** take parameters, perform an operation, and return a value. Functions are modeled after Microsoft Excel functions. Some functions have side effects, such as `SubmitForm`, which are appropriate only in a [behavior formula](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/working-with-formulas-in-depth) such as `Button.OnSelect`.
- **Signals** return information about the environment. For example, [Location](https://learn.microsoft.com/en-us/power-platform/power-fx/reference/signals) returns the device's current GPS coordinates. Signals don't take parameters or have side effects.
- **Enumerations** return a pre-defined constant value. For example, [Color](https://learn.microsoft.com/en-us/power-platform/power-fx/reference/function-colors) is an enumeration that has pre-defined values for `Color.Red`, `Color.Blue`, and so forth.
- **Named operators**, such as [ThisItem](https://learn.microsoft.com/en-us/power-platform/power-fx/reference/operators#thisitem-thisrecord-and-as-operators) and [Self](https://learn.microsoft.com/en-us/power-platform/power-fx/reference/operators#self-and-parent-operator), provide access to information from within a container.

### Constraints and limitations

Not all functions area available in all Power Platform components. See [Formula reference - Power Apps - Power Platform | Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/power-fx/formula-reference) for a list of formulas available in Power Apps.

In model-driven apps, Power Fx can be [used in custom pages](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/page-powerfx-in-model-app) to add notifications and navigate between pages. Custom pages are a new feature with significant product changes. Refer to [Known issues with custom pages in a model-driven app](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/model-app-page-issues) for information on current limitations.

## Web resources with JavaScript

Read more: [Web resources](https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/web-resources)

You can use JavaScript in the following areas of **model-driven apps:**

- Form Script event handlers: a form loads, data is changed in a column or an item within the form, data is saved in a form
- Command bar (ribbon) commands
- Table view/card view customization
- Web resources and IFRAMEs
- Sitemap

>[Client scripting](https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/client-scripting) should **NOT** be your first choice for applying custom business process logic in model-driven app forms. Consider using **business rules** first (described later in the [Dataverse](./../power-platform-extensibility-04) section), because they are easy to understand and implement for a non-developer, and they can be included as part of a Dataverse solution for deployment in production.
Like all web resources, JavaScript web resources [use the model-driven apps security context](https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/script-jscript-web-resources). Only licensed users who have the necessary privileges can access them.

### Constraints and limitations

 **Web resource do not support capabilities of an ASP.NET(.aspx)** pages to execute **code on the server**. They are **limited to static files**  or files that are **processed in the browser**.
A web resource **can contain code** that is  **processed in the browser** to **execute web service calls** to interact with  Dataverse data.
The maximum size of files that can be uploaded is determined by the `Organization.MaxUploadFileSize` property. The default setting is `5 MB`.

Source: [Limitations of web resources](https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/web-resources#limitations-of-web-resources)

## Low-code canvas components using Power Fx

Read more: [Low-code canvas components](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/create-component)

 Components are reusable building blocks for canvas apps so that app makers can create custom controls to use inside an app, or across apps using a [component library](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/component-library). Components can use advanced features such as custom properties  and enable complex capabilities.
Canvas components can also be used in model-driven apps using custom pages and  component library: [Add  canvas components to a custom page in a model-driven app](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/page-canvas-components).

### Constraints and limitations

You can't add a low-code component inside another low-code component, even when using different types of components. [Component properties](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/component-properties) like Function, Action and Event are still experimental at the time of writing.

[Known limitations](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/create-component#known-limitations)

## Low-code Plug-ins using Power Fx

Read more: [Low-code Plug-ins](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant)

 With the low-code plug-ins, you can create plug-ins with minimal or no coding  required, and without the need for compiling solution and manual registration.

Low-code  plug-ins are stored within a Dataverse database and can be seamlessly  integrated into Power Apps and Power Automate. They are defined using the Power Fx expression language and can directly connect   with Dataverse business data and external data sources through Power Platform connectors.
Running **server-side, they reduce client-side workload**. [Benefits of server-side logic](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant#benefits-of-server-side-logic)

### Constraints and limitations

  Low-code plug-ins are stored within a Dataverse database and are created using [Dataverse accelerator app](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant#prerequisites-for-creating-a-low-code-plug-in), which must be installed in the environment. All new environments have the Dataverse accelerator app automatically installed as of October 1st 2023.

Use of low-code plugins in your solution requires Premium licenses.

[Limitations](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant#limitations)

## PowerApps component framework (PCF) using TypeScript

Read more: [PowerApps component framework (PCF)](https://learn.microsoft.com/en-us/power-apps/developer/component-framework/overview)

Used to **enhance the user experience** in **forms, views, dashboards, and canvas app**  screens. For example:

- replace a column on a form that displays a numeric text value with a dial or slider code component. (`FIELD`)
- transform a list into an entirely different visual experience bound to the dataset, like a Calendar or Map. (`DATASET`)

The definition and implementation of code components using Power Apps component framework is same for both model-driven and canvas apps. The only difference between both is the configuration part.

Unlike HTML web resources, code components are **rendered as part of the same context and loaded at the same time** as any other components, providing a seamless experience for the user. Developers can **bundle all the HTML, CSS, and TypeScript** files into a single [solution](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/solutions-overview) package file and move across environments, and also make it available via [AppSource](https://appsource.microsoft.com/marketplace/apps?page=1&amp;product=dynamics-365).

Code components can be classified into two types:

- Code components that connect to external services or data directly via the user's browser client and not through connectors are considered as **premium**. When these components are used in an app, **the app becomes premium**, and end-users are required to have Power Apps licenses.
- Code components that don't connect to external services or data are **standard**. When these components are used in an app that uses standard features, the app remains standard, and end- users are required to be licensed at minimum for Office 365.
- Code components can be declared as premium components by adding a `external-service-usage` node to the component's manifest file with all the external service domains this component is connecting to.

[Best practices and guidance for code components created using Power Apps component  framework](https://learn.microsoft.com/en-us/power-apps/developer/component-framework/code-components-best-practices)

[Add  code components to a custom page for your model-driven app](https://learn.microsoft.com/en-us/powerapps/maker/model-driven-apps/page-code-components)

### Constraints and limitations

Microsoft **Dataverse dependent APIs, including WebAPI,**  are [not available](https://learn.microsoft.com/en-us/power-apps/developer/component-framework/reference) for Power Apps **canvas  applications** **_yet_**.

Code  components should **bundle all the code  including external library** content into the primary code bundle. They should not use the HTML web storage objects, Data  stored locally on the user's browser or mobile client is not secure and not  guaranteed to be available reliably.
Source: [Limitations  of Power Apps component framework - Power Apps | Microsoft Learn](https://learn.microsoft.com/en-us/power-apps/developer/component-framework/limitations)

## React controls using TypeScript + React

Read more: [React  controls & platform libraries](https://learn.microsoft.com/en-us/power-apps/developer/component-framework/react-controls-platform-libraries)

React controls use the same infrastructure as the Power Apps platform. This means  you do not have to package React and platform libraries individually for each control. All controls share a common library instance and version to provide  a **seamless and consistent experience**.
By  re-using the existing platform React and Fluent libraries, you can expect the  following benefits:

- Reduced control bundle size
- Optimized solution packaging
- Faster runtime transfer, scripting and control rendering

Microsoft  expects this approach to **become the preferred way**⭐, with all Power Apps code components being created this way after  this feature reaches general availability. [Create  your first component](https://learn.microsoft.com/en-us/power-apps/developer/component-framework/implementing-controls-using-typescript)

### Constraints and limitations

 React controls & platform libraries are **currently** [not supported for Power Pages](https://learn.microsoft.com/en-us/power-apps/developer/component-framework/react-controls-platform-libraries#faq)

## Custom connectors with REST API

Read more: [Custom  connectors](https://learn.microsoft.com/en-us/connectors/custom-connectors/)

 Use to  communicate to your external data sources and services. A custom connector is  a wrapper around a REST API and can be created using tools like Azure Functions or Azure API Management.

New  connectors, both Microsoft and third party, are  added constantly, and as an administrator you should be aware of new  connectors and ensure they are classified accordingly in your [Data loss prevention (DLP) policies](https://learn.microsoft.com/en-us/power-platform/admin/wp-data-loss-prevention)

### Constraints and limitations

 Power Platform **only supports REST API**,  while Logic Apps also supports SOAP APIs.

Custom connectors are **not supported in Power Pages**. However, you can use **Dataverse  Dataflows** to render data from a REST API to Power Pages. That data  will then need to either be replicated to Dataverse, or presented as a  Virtual Table.

[Custom  connector FAQ for Azure Logic Apps, Power Automate, and Power Apps](https://learn.microsoft.com/en-us/connectors/custom-connectors/faq)

[Known  limitations](https://learn.microsoft.com/en-us/connectors/custom-connectors/customconnectorssolutions#known-limitations)
