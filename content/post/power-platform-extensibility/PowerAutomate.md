
## Power Automate

### Contents

1. [Power Platform? I'm a developer!](index.md)
1. [Power Apps](powerApps.md)
1. **Power Automate**
1. [Dataverse](Dataverse.md)

Power Automate **[Cloud flows](https://powerautomate.microsoft.com/en-us/digital-process-automation/) are always asynchronous**, while **Classic workflows** may be **either background (asynchronous) or real-time (synchronous)** workflows. Microsoft recommends to use Cloud Flows instead of classic background workflows.

Power Automate supports **transactions through ChangeSets** which can be used with the **Dataverse** connector to perform atomic transactions. For transactions not related to Dataverse, custom rollback logic must be implemented.

Power Automate is great for [use cases](https://learn.microsoft.com/en-us/power-apps/guidance/planning/logic#power-automate-flows) where you need to run complex logic, need multiple connectors, or you don't want the user to wait for the action to finish. Consider it if:

- Logic needs to run across multiple connectors.
- You're creating an approval process.
Output is being produced in another format.
- You want to reduce dependency on device-side processing power.
- The process is well understood and consistent, runs frequently and there's a potential ROI
- High risk and/or impact of a failure could be mitigated through automation.

It's [recommended to build separate flows](https://learn.microsoft.com/en-us/power-automate/guidance/planning/separate-flows) instead of a single automation that covers the entire process.

> Key developer extensibility points
>
> - Create custom connectors to communicate to your external data sources and services. A custom connector is a wrapper around a REST API and can be created using tools like Azure Functions and Azure API Management
> - Use workflow definition functions to build complex expressions
>
>Source: [Introduction to Microsoft Power Platform for developers](https://learn.microsoft.com/en-us/power-platform/developer/get-started#power-apps)

## Summary of extensibility options in Power Automate

![Extensibility options in Power Automate](./images/PowerAutomate.png)

|||Cloud Flows|Desktop Flows|Business Process Flow|Classic workflows|
|-|-|-|-|-|-|
|[Formulas - Power Apps](https://learn.microsoft.com/en-us/power-platform/power-fx/formula-reference) |Power Fx|✅|✅<sup>Preview</sup>|❌|❌|
|[Low-code plugins](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant) <sup>Preview</sup>|Power Fx, Connectors |✅|❌|❌|❌|
|[Custom process action](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/create-actions)|declarative|✅|❌|✅*|✅|
|[Custom API](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/custom-actions#compare-custom-process-action-and-custom-api) |.NET|✅|❌|❌|✅|
|[workflow activities/assemblies](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/workflow/workflow-extensions)|.NET|✅|❌|✅|✅|
|[Custom connectors](https://learn.microsoft.com/en-us/connectors/custom-connectors/) |REST API|✅|✅|✅**|❌|
|[Office Scripts in Excel](https://learn.microsoft.com/en-us/office/dev/scripts/overview/excel)|TypeScript|✅|❌|❌|❌|
|[Custom actions for Power Automate for Desktop](https://learn.microsoft.com/en-us/power-automate/desktop-flows/create-custom-actions)|.NET|❌|✅|❌|❌|
|[Custom script](https://learn.microsoft.com/en-us/power-automate/desktop-flows/actions-reference/scripting) in Desktop flows|DOS command<br/>VBScript***<br/>JavaScript<br/>PowerShell<br/>Python<br/>.NET<br/>|❌|✅|❌|❌|


<sup>* To allow business process flow execute the custom process action, define table entity and enable "As a Business Process Flow" in action properties</sup><br/>
<sup>** By using custom process action that uses custom connector</sup><br/>
<sup>*** VBScript is deprecated from Windows</sup>

<table border="1" cellpadding="0" cellspacing="0" valign="top" style="
 border-collapse:collapse;border-style:solid;border-color:#A3A3A3;border-width:
 1pt" >
 <tbody><tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Approach</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Programming
  language</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Description</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Constraints
  and Limitations</p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-platform/power-fx/formula-reference-overview">Formulas</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">PowerFx</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Formulas
  combine many elements, for example:</p>
  <ul type="disc" style="direction:ltr;unicode-bidi:embed;margin-top:0in;
   margin-bottom:0in">
   <li style="margin-top:0;margin-bottom:0;vertical-align:middle" lang="en-US"><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">Functions:</span><span style="font-family:Calibri;font-size:11.0pt">&nbsp;take parameters,
       perform an operation, and return a value. Functions are modeled after
       Microsoft Excel functions. Some functions have side effects, such
       as&nbsp;SubmitForm, which are appropriate only in a&nbsp;</span><a href="https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/working-with-formulas-in-depth"><span style="font-family:Calibri;font-size:11.0pt">behavior formula</span></a><span style="font-family:Calibri;font-size:11.0pt">&nbsp;such
       as&nbsp;Button.OnSelect.</span></li>
   <li style="margin-top:0;margin-bottom:0;vertical-align:middle" lang="en-US"><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">Signals</span><span style="font-family:Calibri;font-size:11.0pt">&nbsp;return information </span><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">about the
       environment</span><span style="font-family:Calibri;font-size:11.0pt">.
       For example,&nbsp;</span><a href="https://learn.microsoft.com/en-us/power-platform/power-fx/reference/signals"><span style="font-family:Calibri;font-size:11.0pt">Location</span></a><span style="font-family:Calibri;font-size:11.0pt">&nbsp;returns the device's
       current GPS coordinates. Signals don't take parameters or have side
       effects.</span></li>
   <li style="margin-top:0;margin-bottom:0;vertical-align:middle" lang="en-US"><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">Enumerations</span><span style="font-family:Calibri;font-size:11.0pt">&nbsp;return a pre-defined
       constant value. For example,&nbsp;</span><a href="https://learn.microsoft.com/en-us/power-platform/power-fx/reference/function-colors"><span style="font-family:Calibri;font-size:11.0pt">Color</span></a><span style="font-family:Calibri;font-size:11.0pt">&nbsp;is an enumeration
       that has pre-defined values for&nbsp;Color.Red,&nbsp;Color.Blue, and so
       forth. </span></li>
   <li style="margin-top:0;margin-bottom:0;vertical-align:middle" lang="en-US"><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">Named
       operators</span><span style="font-family:Calibri;font-size:11.0pt">,
       such as&nbsp;</span><a href="https://learn.microsoft.com/en-us/power-platform/power-fx/reference/operators#thisitem-thisrecord-and-as-operators"><span style="font-family:Calibri;font-size:11.0pt">ThisItem</span></a><span style="font-family:Calibri;font-size:11.0pt">&nbsp;and&nbsp;</span><a href="https://learn.microsoft.com/en-us/power-platform/power-fx/reference/operators#self-and-parent-operators"><span style="font-family:Calibri;font-size:11.0pt">Self</span></a><span style="font-family:Calibri;font-size:11.0pt">, provide access to
       information from within a container.</span></li>
  </ul>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Not all
  functions area available in all Power Platform components. For example <a href="https://learn.microsoft.com/en-us/power-platform/power-fx/reference/function-ismatch">regular
  expressions</a> like <span style="font-weight:bold">IsMatch</span>, <span style="font-weight:bold">Match</span>, and <span style="font-weight:bold">MatchAll</span>
  are available in both, Canvas and Model-driven apps but <span style="font-weight:bold">not in Power Automate.</span></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant">Low-code
  Plug-ins</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">PowerFx</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">With
  the low-code plug-ins, users can create plug-ins with minimal or no coding
  required, and without the need for compiling solution and manual
  registration.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Low-code
  plug-ins are stored within a Dataverse database and can be seamlessly
  integrated into Power Apps and Power Automate. The behavior of the workflow
  is defined using the Power Fx expression language and can directly connect
  with Dataverse business data and external data sources through Power Platform
  connectors</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><span style="font-weight:bold">Idea</span>: You may use low-code plugins as a way
  to execute <a href="https://learn.microsoft.com/en-us/power-platform/power-fx/reference/function-ismatch">regular
  expressions</a> in Power Automate.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-automate/desktop-flows/power-fx">Power
  Fx in desktop flows</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Low-code
  plug-ins are stored within a Dataverse database and are created using <a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant#prerequisites-for-creating-a-low-code-plug-in">Dataverse
  accelerator app</a>, which must be installed in the environment.&nbsp;</p>
  <p><cite style="margin:0in;font-family:Calibri;font-size:9.0pt;color:#595959" lang="en-US">&nbsp;</cite></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant#limitations">Limitations</a></p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/create-actions">Custom
  process action</a></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">declarative</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/workflow-custom-actions">Custom
  process actions</a>, also known as Custom actions, allow creating&nbsp;custom
  reusable actions&nbsp;that encapsulate specific business logic, and may be
  invoked directly from a workflow. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">The
  business logic of a custom process action is implemented using a workflow.
  When you create a custom process action, the associated real-time workflow is
  automatically registered to execute in the main operation stage of the
  message execution pipeline.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">They
  are stored in Dataverse and may use a context of a table, or be defined as
  global.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">See
  Dataverse section for a more detailed description</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.5368in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">To
  allow business process flow execute the custom process action, define table
  entity and enable "As a Business Process Flow"&nbsp;in action
  properties </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/custom-api">Custom
  API</a> </p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">.NET</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Custom
  API is a newer way to define custom messages with many advantages for
  developers. If you do not intend to use the no-code capabilities that custom
  process actions provide to configure business logic, custom API provides
  better capabilities for developers to create their own messages. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">See
  Dataverse section for a more detailed description</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/custom-actions#compare-custom-process-action-and-custom-api">Compare
  Custom Process Action and custom API</a></p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/workflow/workflow-extensions">workflow
  activities/assemblies</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">.NET</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">As
  reusable components, workflow extensions can be added to any workflow or
  custom action.&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">See
  Dataverse section for a more detailed description</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/connectors/custom-connectors/">Custom
  connectors</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">REST
  API</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Use to
  communicate to your external data sources and services. A custom connector is
  a wrapper around a REST API and can be created using tools like Azure
  Functions and Azure API Management</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt"><span lang="en-US">New
  connectors</span><span lang="en-CH">—</span><span lang="en-US">both Mi
rosoft
  first party and third party</span><span lang="en-CH">—</span><span lan="en-US">are
  added constantly, and as an administrator you should be aware of new
  connectors and ensure they are classified accordingly in your&nbsp;</span><a href="https://learn.microsoft.com/en-us/power-platform/admin/wp-data-loss-prevention"><span lang="en-US">Data loss prevention (DLP) policies</span></a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><span style="font-weight:bold;color:#161616">Power Platform only supports REST API,
  while </span>Logic Apps also supports SOAP APIs.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US"><span style="font-weight:bold">Custom connectors are not supported</span>
  in Power Pages. However, you can use <span style="font-weight:bold">Dataverse
  Dataflows</span> to render data from a REST API to Power Pages. That data
  will then need to either be replicated to Dataverse, or presented as a
  Virtual Table.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US"><a href="https://learn.microsoft.com/en-us/connectors/custom-connectors/faq">Custom
  connector FAQ for Azure Logic Apps, Power Automate, and Power Apps</a></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US"><a href="https://learn.microsoft.com/en-us/connectors/custom-connectors/customconnectorssolutions#known-limitations">Known
  limitations</a></p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/office/dev/scripts/develop/power-automate-integration?tabs=run-script">Office
  Script in Excel</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">TypeScript</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Office
  Scripts in Excel let you automate your day-to-day tasks. You may record
  manual steps, or write your script on your own. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Although
  it's meant for editing workbook, you don't have to access Excel contents at
  all. Instead, you may use Office Script in Excel to execute your TypeScript
  functions, to execute any logic that is not available using Power Fx.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US">To use&nbsp;<a href="https://learn.microsoft.com/en-us/connectors/excelonlinebusiness">Excel
  Online (Business) connector</a> (standard) in Power Automate you must have a <a href="https://learn.microsoft.com/en-us/office/dev/scripts/develop/power-automate-integration?tabs=run-script#:~:text=on%20workbook%20comments.-,Important,-To%20use%20Office">business
  license of Microsoft 365</a>. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US">Excel Scripts may be saved either in <a href="https://learn.microsoft.com/en-us/office/dev/scripts/overview/script-storage">OneDrive
  or in a SharePoint</a> site.</p>
  <p style="margin-top:1pt;margin-bottom:1pt;font-family:Calibri;font-size:
  11.0pt;color:#161616" lang="en-US">Requests and responses in Excel are limited
  to <span style="font-weight:bold">5MB, </span>and the maximum size of
  parameters passed to the Run script action is 30,000,000 bytes<span style="font-weight:bold"> (28.6MB).</span></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US"><span style="font-weight:bold">No external calls from a script</span></p>
  <p style="margin-top:1pt;margin-bottom:1pt;font-family:Calibri;font-size:
  11.0pt;color:#161616" lang="en-US">&nbsp;</p>
  <p style="margin-top:1pt;margin-bottom:1pt;font-family:Calibri;font-size:
  11.0pt;color:#161616" lang="en-US">&nbsp;</p>
  <p style="margin-top:1pt;margin-bottom:1pt;font-family:Calibri;font-size:
  11.0pt;color:#161616" lang="en-US">&nbsp;</p>
  <p style="margin-top:1pt;margin-bottom:1pt;font-family:Calibri;font-size:
  11.0pt;color:#161616" lang="en-US"><a href="https://learn.microsoft.com/en-us/office/dev/scripts/develop/power-automate-integration?tabs=run-script#data-security-in-office-scripts-with-power-automate">Data
  security in Office Scripts with Power Automate</a></p>
  <p style="margin-top:1pt;margin-bottom:1pt;font-family:Calibri;font-size:
  11.0pt;color:#161616" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-automate/limits-and-config">Limits
  and configuration in Power Automate</a></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/connectors/excelonlinebusiness/#known-issues-and-limitations">Known
  issues and limitations for the Excel Online (Business) connector</a></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/office/dev/scripts/testing/platform-limits?tabs=business#power-automate-specific-restrictions">Power
  Automate specific restrictions</a></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US"><a href="https://learn.microsoft.com/en-us/office/dev/scripts/develop/typescript-restrictions">TypeScript
  restrictions in Office Scripts</a></p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-automate/desktop-flows/custom-actions">Custom
  actions for Power Automate for Desktop</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">.NET</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Custom
  actions exist at the environment level.&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Custom
  actions developed by your organization and uploaded to the respective
  environments can be included in desktop flows and utilized like actions that
  belong in the standard library of automation actions.</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">.dll
  files describing Custom actions, their dependency .dll files, and the .cab
  files are properly signed with a digital certificate trusted by your
  organization. The certificate should also be installed on the device under
  the trusted root certificate authority where the desktop flow with custom
  action dependencies is modified and/or executed.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-automate/desktop-flows/custom-actions#known-limitations">Known
  limitations</a></p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-automate/desktop-flows/actions-reference/scripting">Custom
  script</a> in Desktop flows</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">DOS
  command</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US">VBScript *</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">JavaScript</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">PowerShell</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Python</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">.NET</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Scripting
  actions enable you to run blocks of code and implement custom behavior in
  your desktop flows.</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US">To prevent unauthorized access, Windows require administrator
  rights to access protected resources. To access protected resources (such as
  files) using the scripting actions, run Power Automate with administrator
  rights. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US">VBScript is deprecated from Windows</p>
  </td>
 </tr>
</tbody></table>



