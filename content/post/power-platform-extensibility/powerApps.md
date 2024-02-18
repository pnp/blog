## Power Apps

### Contents

1. [Power Platform? I'm a developer!](index.md)
1. **Power Apps**
1. [Power Automate](./PowerAutomate.md)
1. [Dataverse](Dataverse.md)


**In Power Apps, the execution of components can be both synchronous and asynchronous, depending on the specific functions and scenarios.**

**There is no built-in transaction support in Power Apps itself. However, you can use stored procedures called from a Power Automate flow to achieve transaction-like behavior.**

Placing business logic in the low-code application is simpler to build, test, and has a lower maintenance cost, but it provides **limited options for reuse or to enforce consistency** across apps and automations.
Generally, you should limit this approach to **non–mission-critical, simple logic** that other applications or automations **don’t need** to use. Evaluate canvas components first and then use code components only if there is a need for more complex and advanced customization.

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

In **Canvas app formulas, model-driven form script, business rules, and Power Apps component framework**, logic happens **in the user interface (cient-side)** and the user will see the result immediately.

|||Canvas Apps|Model-driven Apps|[Custom Pages](https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/design-page-for-model-app)|Power Pages|
|-|-|-|-|-|-|
|[Formulas - Power Apps](https://learn.microsoft.com/en-us/power-platform/power-fx/formula-reference) |Power Fx|✅|✅|✅|❌|
|[Script web resources](https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/webpage-html-web-resources) |JavaScript |❌|✅|❌|❌|
|[Low-code canvas components](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/create-component) with [behavior formulas](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/component-behavior)<sup>*</sup> and [component properties](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/component-properties)|Power Fx|✅|👉|✅|❌|
|[Low-code plugins](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant) <sup>Preview</sup>|Power Fx, Connectors|✅|👉|✅|❌|
|[PowerApps component framework](https://learn.microsoft.com/en-us/power-apps/developer/component-framework/overview) (PCF)|Typescript |✅|✅|✅|✅|
|[React controls & platform libraries](https://learn.microsoft.com/en-us/power-apps/developer/component-framework/react-controls-platform-libraries) <sup>Preview</sup>|TypeScript |✅|✅|✅|❌|
|[Custom connectors](https://learn.microsoft.com/en-us/connectors/custom-connectors/) |openAPI  |✅|👉|✅|❌|
|[Custom webpage templates](https://learn.microsoft.com/en-us/power-pages/configure/web-templates)|HTML, CSS, Liquid  |❌|❌|❌|✅|

<sup> *Behavior formulas for components (experimental): The feature to create custom behavioral properties is currently experimental. However, you can use the default OnReset property that is available on all components in your production environment.</sup>

<table >
 <tbody><tr>
  <td >
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Approach</p>
  </td>
  <td >
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Programming
  language</p>
  </td>
  <td >
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Description</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Constraints and limitations</p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/power-platform/power-fx/formula-reference-overview">Formulas</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >PowerFx</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Formulas combine many elements, for example:</p>
  <ul type="disc" style="direction:ltr;unicode-bidi:embed;margin-top:0in;margin-bottom:0in">
   <li ><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">Functions:</span><span style="font-family:Calibri;font-size:11.0pt"> take parameters, perform an operation, and return a value. Functions are modeled after Microsoft Excel functions. Some functions have side effects, such as SubmitForm, which are appropriate only in a </span><a href="https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/working-with-formulas-in-depth"><span style="font-family:Calibri;font-size:11.0pt">behavior formula</span></a><span style="font-family:Calibri;font-size:11.0pt"> such as Button.OnSelect.</span></li>
   <li ><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">Signals</span><span style="font-family:Calibri;font-size:11.0pt"> return information </span><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">about the environment</span><span style="font-family:Calibri;font-size:11.0pt">.For example, </span><a href="https://learn.microsoft.com/en-us/power-platform/power-fx/reference/signals"><span style="font-family:Calibri;font-size:11.0pt">Location</span></a><span style="font-family:Calibri;font-size:11.0pt"> returns the device's current GPS coordinates. Signals don't take parameters or have side effects.</span></li>
   <li ><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">Enumerations</span><span style="font-family:Calibri;font-size:11.0pt"> return a pre-defined constant value. For example, </span><a href="https://learn.microsoft.com/en-us/power-platform/power-fx/reference/function-colors"><span style="font-family:Calibri;font-size:11.0pt">Color</span></a><span style="font-family:Calibri;font-size:11.0pt"> is an enumeration that has pre-defined values for Color.Red, Color.Blue, and so forth. </span></li>
   <li ><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">Named
       operators</span><span style="font-family:Calibri;font-size:11.0pt">, such as </span><a href="https://learn.microsoft.com/en-us/power-platform/power-fx/reference/operators#thisitem-thisrecord-and-as-operators"><span style="font-family:Calibri;font-size:11.0pt">ThisItem</span></a><span style="font-family:Calibri;font-size:11.0pt"> and </span><a href="https://learn.microsoft.com/en-us/power-platform/power-fx/reference/operators#self-and-parent-operators"><span style="font-family:Calibri;font-size:11.0pt">Self</span></a><span style="font-family:Calibri;font-size:11.0pt">, provide access to information from within a container.</span></li>
  </ul>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Not all functions area available in all Power Platform components. See <a href="https://learn.microsoft.com/en-us/power-platform/power-fx/formula-reference">Formula reference - Power Apps - Power Platform | Microsoft Learn</a> for a list of formulas available in Power Apps.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >In model-driven apps, Power Fx can be <a href="https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/page-powerfx-in-model-app">used in custom pages</a> to add notifications and navigate between pages. However,
  <span style="font-weight:bold">some</span> Power Fx <span style="font-weight: bold">functions are </span><a href="https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/commanding-use-powerfx#functions-not-supported"><span style="font-weight:bold">not supported</span> with commanding</a> in model-driven apps. </p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/web-resources">Web resources</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >JavaScript</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >You can use JavaScript in the following areas of <span style="font-weight:bold">Model-driven apps:</span></p>
  <ul>
   <li ><span style="font-family:Calibri;font-size:11.0pt">Form Script event handlers: a form loads, data is changed in a column or an item within the form,
       data is saved in a form</span></li>
   <li ><span style="font-family:Calibri;font-size:11.0pt">Command bar (ribbon) commands</span></li>
   <li ><span style="font-family:Calibri;font-size:11.0pt">Table view/card view customization</span></li>
   <li ><span style="font-family:Calibri;font-size:11.0pt">Web resources and IFRAMEs</span></li>
   <li ><span style="font-family:Calibri;font-size:11.0pt">Sitemap</span></li>
  </ul>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/client-scripting">Client scripting</a> should <b>NOT</b> be your first choice for applying custom business process logic in model-driven app forms. Consider using Business rules (described later in the <b>Dataverse</b> section) first because they are easy to understand and implement for a non-developer, and they can be included as part of a Dataverse solution for deployment in production.</p>

  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Like all web resources, JavaScript web resources <a href="https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/script-jscript-web-resources">use the model-driven apps security context</a>. Only licensed users who have the
  necessary privileges can access them.</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >There is <span style="font-weight:bold">no</span> type of<span style="font-weight:
  bold"> web resource</span> that <span style="font-weight:bold">supports</span>  the capabilities of an <span style="font-weight:bold">ASP.NET(.aspx)</span>
  page to execute<span style="font-weight:bold"> code on the server</span>. Web resources are<span style="font-weight:bold"> limited to static files</span>
  or files that are <span style="font-weight:bold">processed in the browser</span>.
  A web resource <span style="font-weight:bold">can contain code</span> that is  <span style="font-weight:bold">processed in the browser</span> to<span style="font-weight:bold"> execute web service calls</span> to interact with  Dataverse data.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >The maximum size of files that can be uploaded is determined by the
  Organization.MaxUploadFileSize property. The default setting is 5 MB.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Source:
  <a href="https://learn.microsoft.com/en-us/power-apps/developer/model-driven-apps/web-resources#limitations-of-web-resources">Limitations
  of web resources</a></p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/create-component">Low-code canvas components</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >PowerFx</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Components are reusable building blocks for canvas apps so that app makers can create
  custom controls to use inside an app, or across apps using a <a href="https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/component-library">component library</a>. Components can use advanced features such as custom properties
  and enable complex capabilities. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Canvas components can also be used in model-driven apps using custom pages and
  component library: <a href="https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/page-canvas-components">Add
  canvas components to a custom page in a model-driven app</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/create-component#known-limitations">Known limitations</a></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Nested support: you can't add a low-code component inside another low-code component, even when using different types of components.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/component-properties">Component properties</a> like Function, Action and Event are still experimental at the time of writing.</p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant">Low-code Plug-ins</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >PowerFx</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >With the low-code plug-ins, you can create plug-ins with minimal or no coding
  required, and without the need for compiling solution and manual registration.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Low-code   plug-ins are stored within a Dataverse database and can be seamlessly
  integrated into Power Apps and Power Automate. They are defined using the Power Fx expression language and can directly connect   with Dataverse business data and external data sources through Power Platform connectors. </p>
   <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Running server-side, they reduce client-side workload</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant#benefits-of-server-side-logic">Benefits of server-side logic</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Low-code plug-ins are stored within a Dataverse database and are created using <a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant#prerequisites-for-creating-a-low-code-plug-in">Dataverse accelerator app</a>, which must be installed in the environment. All new environments have the Dataverse accelerator app automatically installed as of October 1st 2023.</p>
   <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Use of low-code plugins in your solution requires Premium licenses.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant#limitations">Limitations</a></p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/power-apps/developer/component-framework/overview">PowerApps component framework (PCF)</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >TypeScript</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Used to <span style="font-weight:bold">enhance the user experience</span> in <span style="font-weight:bold">forms, views, dashboards, and canvas app</span>
  screens. For example:</p>
  <ul>
   <li ><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">replace a column on a form</span><span style="font-family:Calibri;font-size:11.0pt"> that displays a numeric text value with a dial or slider code component. (FIELD)</span></li>
   <li ><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">transform a list into</span><span style="font-family:Calibri;font-size:11.0pt"> an entirely </span><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">different visua</span><span style="font-family:Calibri;
       font-size:11.0pt">l experience bound to the dataset, like a Calendar or Map. (DATASET)</span></li>
  </ul>
<p style="margin:0in;font-family:Calibri;font-size:11.0pt" >The definition and implementation of code components using Power Apps component
  framework is same for both model-driven and canvas apps. The only difference between both is the configuration part.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Unlike HTML web resources, code components are <span style="font-weight:bold">rendered
  as part of the same context and loaded at the same time</span> as any other components, providing a seamless experience for the user.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Developers can<span style="font-weight:bold"> bundle all the HTML, CSS, and TypeScript</span>
  files into a single <a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/solutions-overview">solution</a> package file and move across environments, and also make it available via <a href="https://appsource.microsoft.com/marketplace/apps?page=1&amp;product=dynamics-365">AppSource</a>.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Code components can be classified into two types:</p>
  <ul type="disc" style="direction:ltr;unicode-bidi:embed;margin-top:0in;margin-bottom:0in">
   <li ><span style="font-family:Calibri;font-size:11.0pt">Code components that connect to external services or data directly via the user's browser
       client and not through connectors are considered as premium. When these components are used in an app, </span><span style="font-weight:bold;
       font-family:Calibri;font-size:11.0pt">the app becomes premium</span><span style="font-family:Calibri;font-size:11.0pt">, and end-users are
       required to have Power Apps licenses.</span></li><li ><span style="font-family:Calibri;font-size:11.0pt">Code components that don't
       connect to external services or data are standard. When these components are used in an app that uses standard features, the app remains
       standard, and end- users are required to be licensed at minimum for Office 365. </span></li>
   <li ><span style="font-family:Calibri;font-size:11.0pt">Code components can be declared as premium components by adding
       a `&lt;external-service-usage&gt;` node to the component's manifest file with all the external service domains this component is
       connecting to.</span></li>
  </ul>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/power-apps/developer/component-framework/code-components-best-practices">Best practices and guidance for code components created using Power Apps component
  framework</a></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/powerapps/maker/model-driven-apps/page-code-components">add  code components to a custom page for your model-driven app.</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Microsoft  <span style="font-weight:bold">Dataverse dependent APIs, including WebAPI,</span>
  are <a href="https://learn.microsoft.com/en-us/power-apps/developer/component-framework/reference/"><span style="font-weight:bold">not available</span></a><span style="font-weight:bold"> for</span> Power Apps <span style="font-weight:bold">canvas  applications </span><span style="font-weight:bold;text-decoration:underline">yet</span><span style="font-weight:bold">. </span></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Code  components should <span style="font-weight:bold">bundle all the code
  including external library</span> content into the primary code bundle.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Code  components should not use the HTML web storage objects,</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Data  stored locally on the user's browser or mobile client is not secure and not
  guaranteed to be available reliably.</p>
  <p style="margin:0in;margin-left:.375in;font-family:Calibri;font-size:11.0pt" > </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Source:  <a href="https://learn.microsoft.com/en-us/power-apps/developer/component-framework/limitations">Limitations  of Power Apps component framework - Power Apps | Microsoft Learn</a></p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/power-apps/developer/component-framework/react-controls-platform-libraries">React  controls &amp; platform libraries</a> (Preview)</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >TypeScript + React</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >React  controls use the same infrastructure as the Power Apps platform. This means
  you do not have to package React and platform libraries individually for each   control. All controls share a common library instance and version to provide  a <span style="font-weight:bold">seamless and consistent experience</span>.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >By  re-using the existing platform React and Fluent libraries, you can expect the
  following benefits:</p>
  <ul >
   <li ><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">Reduced</span><span style="font-family:Calibri;font-size:11.0pt"> control bundle </span><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">size</span></li>
   <li ><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">Optimized</span><span style="font-family:Calibri;font-size:11.0pt"> solution </span><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">packaging</span></li>
   <li ><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">Faster runtime</span><span style="font-family:Calibri;font-size:11.0pt">
       transfer, scripting and control rendering</span></li>
  </ul>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Microsoft  expects this approach to <span style="font-weight:bold">become the preferred
  way</span>, with all Power Apps code components being created this way after  this feature reaches general availability. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/power-apps/developer/component-framework/implementing-controls-using-typescript">Create  your first component</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >React  controls &amp; platform libraries are <a href="https://learn.microsoft.com/en-us/power-apps/developer/component-framework/react-controls-platform-libraries#faq"><span style="font-weight:bold">currently</span> only available</a> for canvas and  model-driven apps.</p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/connectors/custom-connectors/">Custom
  connectors</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >REST API</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" >Use to  communicate to your external data sources and services. A custom connector is
  a wrapper around a REST API and can be created using tools like Azure
  Functions and Azure API Management</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt"><span >New  connectors</span>, both Mirosoft and third party, are
  added constantly, and as an administrator you should be aware of new  connectors and ensure they are classified accordingly in your </span><a href="https://learn.microsoft.com/en-us/power-platform/admin/wp-data-loss-prevention"><span >Data loss prevention (DLP) policies</span></a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><span style="font-weight:bold">Power Platform only supports REST API,
  while </span>Logic Apps also supports SOAP APIs.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" > </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><span style="font-weight:bold">Custom connectors are not supported</span>
  in Power Pages. However, you can use <span style="font-weight:bold">Dataverse  Dataflows</span> to render data from a REST API to Power Pages. That data
  will then need to either be replicated to Dataverse, or presented as a  Virtual Table.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" > </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/connectors/custom-connectors/faq">Custom
  connector FAQ for Azure Logic Apps, Power Automate, and Power Apps</a></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" ><a href="https://learn.microsoft.com/en-us/connectors/custom-connectors/customconnectorssolutions#known-limitations">Known  limitations</a></p>
  </td>
 </tr>
</tbody></table>


