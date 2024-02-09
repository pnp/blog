# Dataverse

Because Dataverse includes many capabilities for people to configure custom business logic without writing code, the most common scenarios for developers to contribute involve filling spaces in-between where existing features may not provide functionality you need to meet a requirement. Fortunately, Dataverse provides many points for developers to extend the common functionality using code. Each of these options are typically invoked based on events that occur on the server, so understanding of the [Event Framework](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/event-framework) will be valuable.

A best practice recommendation is that [long running operations should be executed outside of Dataverse](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/workflow-custom-actions#watch-out-for-long-running-actions) using Power Automate, Logic Apps, or other capabilities offered by Azure.

**All operations in a synchronous transaction are limited to a total of two minutes. An exception thrown by your code at any synchronous stage within the database transaction will cause the entire transaction to be rolled back.**

Tables in Dataverse can use rich server-side logic and validation to ensure data quality and reduce repetitive code in each app that creates and uses data in a table.

- [Business rules](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/data-platform-create-business-rule): Validate data across multiple columns and tables, and provide warning and error messages, regardless of the app used to create the data.
-[Business process flows](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/data-platform-create-business-rule): Guide users to ensure that they enter data consistently and follow the same steps every time. Business process flows are currently only supported for model-driven apps.
- [Classic workflows](https://learn.microsoft.com/en-us/power-automate/business-process-flows-overview): Automate business processes without user interaction.
    - Background workflows.
    - Real-time workflows.
- [Business logic with code](https://learn.microsoft.com/en-us/power-apps/developer/data-platform/apply-business-logic-with-code): Supports advanced developer scenarios to extend the app directly through code.
    - Plug-in
    - Workflow extension

>Key developer extensibility points
>
>- Create plug-ins, similar to event handlers, that customize or extend Dataverse data processing with custom business logic (code)
>- Use webhooks and Azure Service Bus to integrate with external systems
>- Extend the Dataverse API with your own custom API that implements your business logic
>- Use virtual tables to integrate data stored in external systems into Dataverse without replicating the data
>
>Source: [Introduction to Microsoft Power Platform for developers](https://learn.microsoft.com/en-us/power-platform/developer/get-started#power-apps)


## Summary of extensibility options in Dataverse

![Extensibility options in Dataverse](./images/Dataverse.png)
<table border="1" cellpadding="0" cellspacing="0" valign="top" style="direction:ltr;
 border-collapse:collapse;border-style:solid;border-color:#A3A3A3;border-width:
 1pt" title="" summary="">
 <tbody><tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.7611in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Approach</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.2506in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Programming
  language</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.7409in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Description</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.4152in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Constraints
  and Limitations</p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.7611in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/training/modules/create-define-calculation-rollup-fields/1-intro">Rollup
  column</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.2506in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Power
  Fx</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.7409in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Contains
  an aggregate value computed over the rows related to a specified row,
  can<span style="mso-spacerun:yes">&nbsp; </span>aggregates data from relate
  records in another table</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">In more
  complex scenarios, you can aggregate data over the hierarchy of rows.&nbsp;</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.5326in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">The
  rollups are calculated by scheduled system jobs that run asynchronously in
  the background.&nbsp;Rollup columns are <span style="font-weight:bold">only
  recalculated every hour </span>by default, but can be scheduled to run daily
  every x hours.<span style="font-weight:bold">.</span></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/define-rollup-fields#rollup-columns-benefits-and-capabilities">Rollup
  columns benefits and capabilities</a> and <a href="https://learn.microsoft.com/en-us/training/modules/create-define-calculation-rollup-fields/2-rollup">key
  considerations</a></p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.7611in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/formula-columns">Formula
  columns</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.2506in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Power
  Fx</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.7604in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Formula
  column is a column that derives its value from a formula using other columns
  in the same table. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">The
  formula can be defined using the Power Apps editor and can reference other
  calculated columns, but not rollup columns. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Calculated
  columns are read-only and their values are calculated at runtime when the
  record is retrieved</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.5263in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">The <span style="font-weight:bold">Calculated behavior</span> will eventually be
  discontinued. It's recommend to use the Formula data type for calculations
  instead.</p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.7611in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/training/modules/define-create-business-rules/">Business
  rules</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.2506in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">declarative</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.7409in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Business
  logic to ensure that columns in a model-driven app are shown, hidden, or set
  with the correct values without writing JavaScript code or creating plug-ins.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Define&nbsp;business
  rules&nbsp;for a table that apply to all the table forms and at the server
  level. Business rules defined for a table apply to both&nbsp;canvas
  apps&nbsp;and&nbsp;model-driven apps&nbsp;if the table is used in the
  app.&nbsp;</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.5263in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Not all
  business rule actions are available on canvas apps at this time: <a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/data-platform-create-business-rule#differences-between-canvas-and-model-driven-apps">Differences
  between canvas and model-driven apps</a></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form">Create
  business rules to apply logic in a model-driven app form</a></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/data-platform-create-business-rule">Differences
  between canvas and model-driven apps</a></p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.7611in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant">Low-code
  Plug-ins</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.2506in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Power
  Fx</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.7604in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Traditionally,
  plug-ins were created as custom classes compiled into a .NET Framework
  assembly, which were then uploaded and registered within Dataverse. However,
  with the introduction of low-code plug-ins, users can create these event
  handlers with minimal or no coding required, and without the need for manual
  registration.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Low-code
  plug-ins are stored within a Dataverse database and can be seamlessly
  integrated into Power Apps and Power Automate. The behavior of the workflow
  is defined using the <span style="font-weight:bold">Power Fx</span>
  expression language and can directly connect with Dataverse business data and
  external data sources through Power Platform connectors. With low-code
  plug-ins, makers can rapidly construct complex workflows with minimal coding
  expertise, resulting in a more streamlined and efficient data architecture.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US">There are <span style="font-weight:bold">two types of low-code
  plug-ins</span> supported in Dataverse:</p>
  <div style="direction:ltr">
  <table border="1" cellpadding="0" cellspacing="0" valign="top" style="direction:ltr;
   border-collapse:collapse;border-style:solid;border-color:#A3A3A3;border-width:
   1pt" title="" summary="">
   <tbody><tr>
    <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
    vertical-align:top;width:.9048in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
    <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><span style="font-weight:bold">Type</span></p>
    </td>
    <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
    vertical-align:top;width:1.5652in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
    <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><span style="font-weight:bold">Trigger</span></p>
    </td>
    <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
    vertical-align:top;width:1.5576in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
    <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><span style="font-weight:bold">Supports parameters</span></p>
    </td>
    <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
    vertical-align:top;width:1.2048in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
    <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><span style="font-weight:bold">Supported&nbsp;</span><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/custom-api#select-a-binding-type"><span style="font-weight:bold">scope</span></a></p>
    </td>
   </tr>
   <tr>
    <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
    vertical-align:top;width:.9048in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
    <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Instant</p>
    </td>
    <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
    vertical-align:top;width:1.5652in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
    <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Manually
    run</p>
    </td>
    <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
    vertical-align:top;width:1.5388in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
    <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Yes</p>
    </td>
    <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
    vertical-align:top;width:1.175in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
    <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Global
    and table</p>
    </td>
   </tr>
   <tr>
    <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
    vertical-align:top;width:.9243in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
    <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Automated</p>
    </td>
    <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
    vertical-align:top;width:1.584in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
    <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Dataverse
    table event</p>
    </td>
    <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
    vertical-align:top;width:1.5388in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
    <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">No</p>
    </td>
    <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
    vertical-align:top;width:.9506in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
    <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Table</p>
    </td>
   </tr>
  </tbody></table>
  </div>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.5263in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Low-code
  plug-ins are stored within a Dataverse database and are created using <a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant#prerequisites-for-creating-a-low-code-plug-in">Dataverse
  accelerator app</a>, which must be installed in the environment.&nbsp;</p>
  <p><cite style="margin:0in;font-family:Calibri;font-size:9.0pt;color:#595959" lang="en-US">&nbsp;</cite></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant#limitations">Limitations</a></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins-powerfx">Formulas
  not currently supported</a> | <a href="https://learn.microsoft.com/en-us/power-platform/power-fx/formula-reference">Formula
  reference</a> </p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.7611in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/plug-ins">Dataverse
  plugins</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.2506in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">.NET</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.7548in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">A&nbsp;plug-in&nbsp;is
  a custom event handler that executes in response to a specific event raised
  during processing of a Microsoft Dataverse data operation. It <span style="font-weight:bold;color:#161616">sits between the API and the data</span><span style="color:#161616">. </span></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">When
  the target event occurs during a data processing operation, the code within
  the registered plug-in class executes. It can create, read, modify, or delete
  data being processed during the current database transaction. <span style="font-weight:bold">Logic is transactional and either all complete or
  all roll back</span>. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Plug-in
  code should be very focused, execute quickly and minimize blocking to avoid
  exceeding timeout thresholds and ensure a responsive system for synchronous
  scenarios. Simply submit each request directly <a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/best-practices/business-logic/avoid-batch-requests-plugin">instead
  of batching</a> them and submitting as a single request</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">They
  can perform logic with <span style="font-weight:bold">elevated permissions</span>
  that the user might not normally have. This approach also allows for
  minimizing the permissions the app user might require. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><span style="color:#161616">Plug-ins can be synchronous or asynchronous. </span><span style="mso-spacerun:yes">&nbsp;</span>A <span style="font-weight:bold">sy
nchronous</span>
  plug-in will cause the data <span style="font-weight:bold">operation to wait</span>
  until the code in the plug-in completes. This has an impact on end-user
  perceived performance of the system, which is why<span style="font-weight:
  bold"> synchronous plug-ins must execute and complete quickly</span>. <span style="font-weight:bold">Asynchronous</span> plug-in execution is <span style="font-weight:bold">queued</span> and later executed after the data
  operation has completed.</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.6305in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Plug-ins
  on events a<span style="font-weight:bold">ren’t the best approach if
you must
  listen to events on multiple tables</span> to complete a single business
  event like Close Inspection. Consider a <span style="font-weight:bold">Dataverse
  custom API instead of having plug-ins on multiple tables.</span></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/plug-ins#disadvantages-of-plug-ins"><span style="font-weight:bold">Disadvantages</span></a> of plug-ins</p>
  <ul type="disc" style="direction:ltr;unicode-bidi:embed;margin-top:0in;
   margin-bottom:0in">
   <li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:#161616" lang="en-US"><span style="font-family:Calibri;font-size:11.0pt">Plug-ins</span><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt"> require
       the special skills</span><span style="font-family:Calibri;font-size:
       11.0pt"> of a software developer to create and maintain the plug-in
       code. Smaller businesses may not have access to a developer with the
       needed skills. Business processes can change rapidly and providing
       options to enable change without requiring a developer can allow the
       system to adapt more rapidly.</span></li>
   <li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:#161616" lang="en-US"><span style="font-family:Calibri;font-size:11.0pt">Plug-ins </span><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">can be
       abused.</span><span style="font-family:Calibri;font-size:11.0pt"> A </span><span style="font-weight:bold;font-family:Calibri;font-size:11.0pt">poorly
       written</span><span style="font-family:Calibri;font-size:11.0pt">
       plug-in can cause </span><span style="font-weight:bold;font-family:Calibri;
       font-size:11.0pt">significant impact on the performance</span><span style="font-family:Calibri;font-size:11.0pt"> of the data processing
       pipeline and ultimately the environment. The great power of plug-ins
       needs to be applied with some restraint and consideration for the impact
       it has on the system as a whole.</span></li>
  </ul>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.7611in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/create-actions">Custom
  process action</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.2506in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">declarative</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.7604in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/workflow-custom-actions"><span style="font-weight:bold">Custom process actions</span></a> provide the
  ability to <span style="font-weight:bold">define a single verb (or message)</span>
  that <span style="font-weight:bold">matches an operation</span> you need to
  perform for your <span style="font-weight:bold">business</span>. These new
  messages are <span style="font-weight:bold">driven by a process or behavior</span>
  rather than what can be done with a table. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">They
  can <span style="font-weight:bold">perform operations</span>, such as Create,
  Update, Delete, Assign (record), SendEmail, Start/Stop Workflow or Perform
  Action</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/create-actions#:~:text=Enable-,rollback,-Generally%2C%20processes%20that">Rollback</a>:
  Custom process actions have always been synchronous 'real-time' workflows. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US"><span style="font-weight:bold">Everything you</span> can <span style="font-weight:bold">do</span> just with the <span style="font-weight:
  bold">user interface of the action will support transactions</span>. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Some
  actions developers might do in code initiated by the custom process action
  might not support transactions. For example, if the code perform actions in
  other systems that are beyond the scope of the transaction.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US"><span style="font-weight:bold">All the actions</span> that are
  part <span style="font-weight:bold">of a real-time workflow are </span>considered
  in<span style="font-weight:bold"> transaction</span>, but with <span style="font-weight:bold">actions</span> you have the option to <span style="font-weight:bold">opt out</span> of this.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">If one
  of the <span style="font-weight:bold">steps in the action's real-time
  workflow</span> is a <span style="font-weight:bold">custom workflow activit</span>y,
  that custom workflow activity is subject to the <span style="font-weight:
  bold">two-minute timeout limit.</span> However, there are <span style="font-weight:bold">no specific restrictions</span> on the amount of <span style="font-weight:bold">overall time the action itself</span> can take. This
  absence of restriction isn't an advantage; workflows can't run indefinitely
  and will eventually fail.&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">There
  are two ways t<span style="font-weight:bold">o extend Custom Process Actions</span>
  using code:<span style="font-weight:bold"> with custom workflow activities</span>
  or by r<span style="font-weight:bold">egistering plug-ins on stages.</span></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.6131in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">A best
  practice recommendation is that <span style="font-weight:bold">long running
  operations</span> should be executed <span style="font-weight:bold">outside
  of Dataverse</span> using Power Automate, Logic Apps, or other capabilities
  offered by Azure.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt"><span lang="en-US">You
  can</span><span lang="en-CH">’</span><span lang="en-US">t enable rollb
ck if a
  custom process action is invoked directly from within a workflow. You can
  enable rollback if an action is triggered by a Power Apps web services
  message.</span></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Unlike
  Microsoft Dataverse workflows or plug-ins, an custom process action doesn�
  have to be associated with a specific table. You can define global custom
  process actions that can be called on their own.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/business-events#:~:text=custom%20process%20actions%20have%20the%20following%20limitations%3A">Custom
  Process Actions limitations</a></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.7611in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/workflow/workflow-extensions">workflow
  activities/assemblies</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.2506in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">.NET</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.7604in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt"><span lang="en-US">If
  you don</span><span lang="en-CH">’</span><span lang="en-US">t find t
  functionality you require using the default process activities, you can </span><span style="font-weight:bold" lang="en-US">add custom activities</span><span lang="en-US"> so that they're available </span><span style="font-weight:bold" lang="en-US">in the editor used to compose workflow, dialog, and action </span><span lang="en-US">processes</span><span style="font-weight:bold" lang="en-US">. </span></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt;color:#161616" lang="en-US">The new actions will be available in the workflow designer for
  users to apply - <span style="font-weight:bold">for example a condition or
  some new operation.</span> In this way you can add new custom actions in the
  process designer for users of your environment.</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.6305in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Unlike
  an ordinary plug-in, with workflow extensions you don't have the opportunity
  to explicitly register your code for a specific step. This means you don't
  control whether the code in your workflow extension will run synchronously or
  asynchronously.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">When
  your <span style="font-weight:bold">workflow extension is used</span> in a <span style="font-weight:bold">synchronous workflow or a custom action</span> the
  time spent running the code directly impacts the user's experience. For this
  reason, workflow extensions should require <span style="font-weight:bold;
  text-decoration:underline">no more than two seconds</span> to complete when
  used <span style="font-weight:bold;text-decoration:underline">synchronously</span>.
  If your extension requires <span style="font-weight:bold">more time</span>
  than this, you should <span style="font-weight:bold">document this and
  discourage</span> use of the extension <span style="font-weight:bold">in
  synchronous workflows or custom actions.</span></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.7611in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/custom-api">Custom
  API</a> </p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.2506in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">.NET</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.7604in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Custom
  API is a <span style="font-weight:bold">newer </span>way to define custom
  messages, offering developers better capabilities to create their own
  messages. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Using
  Microsoft Dataverse <a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/business-events">business
  events</a>, you can create a custom API without a plug-in to pass data about
  an event that other subscribers respond to. In other cases you'll combine a
  custom API with a plug-in to define some operation that is delegated to
  Dataverse to compute and return the result.<span style="mso-spacerun:yes">�
  </span>A <span style="font-weight:bold">plug-in that implements</span> the
  main operation for a custom API is subject to the <span style="font-weight:
  bold">2 minute time limit</span> to complete execution. </p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">They
  can be used <span style="font-weight:bold">on demand by the apps and flows</span>,
  the data changes done in the<span style="font-weight:bold"> custom API
  plug-in</span> are <span style="font-weight:bold">transactional</span>.<span style="mso-spacerun:yes">&nbsp; </span>See &lt;
  href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/custom-api#select-a-custom-processing-step-type"&gt;Custom
  Processing Step Type for guidance on defining how can your custom API be
  executed.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Custom
  API is the <span style="font-weight:bold">best</span> choice when the <span style="font-weight:bold">only</span> service it uses is the <span style="font-weight:bold">Dataverse API for other data work</span>. </p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.5673in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Custom
  APIs use plug-ins to perform data operations. Like all Dataverse plug-ins,
  these plug-ins have a <span style="font-weight:bold">two-minute execution
  time-out</span>. Sending the request asynchronously doesn't provide more
  execution time.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Set
  "Enabled for Workflow"&nbsp;to true when you need to enable calling
  a custom API as a workflow action. However, when this option is selected some
  <a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/custom-api#use-a-custom-api-in-a-workflow">limitations</a>
  are imposed&nbsp;.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p><cite style="margin:0in;font-family:Calibri;font-size:9.0pt;color:#595959" lang="en-US">&nbsp;</cite></p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.7611in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/background-operations">Background
  operations</a> (preview)</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.2506in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.7409in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Use <a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/background-operations">background
  operations</a> to send requests that Dataverse processes asynchronously,
  without maintaining connection while a request runs. Even when executing
  request asynchronously, the <span style="font-weight:bold">two-minute
  execution time-out</span> still applies to the plug-in.</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.5263in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">If an
  error occurs during execution of the request, it's retried up to three times,
  using <a href="https://wikipedia.org/wiki/Exponential_backoff">exponential
  backoff strategy</a>.</p>
  </td>
 </tr>
 <tr>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.7611in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US"><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/business-events">Business
  events</a></p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:1.2506in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.7604in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Automation
  of business logic and integration with other systems are driven by events.
  Using&nbsp;Microsoft Dataverse <span style="font-weight:bold">business events</span>,
  you can create a <span style="font-weight:bold">custom API without a plug-in</span>,
  to pass data <span style="font-weight:bold">about an event</span> that other
  subscribers respond to asynchronously.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">You can
  use custom APIs without any&nbsp;synchronous logic that exist to only to
  notify listeners that an event of interest occurred. You emit the event by
  calling the custom action.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
  <td style="border-style:solid;border-color:#A3A3A3;border-width:1pt;
  vertical-align:top;width:6.6243in;padding:2.0pt 3.0pt 2.0pt 3.0pt">
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Custom
  process actions can also be cataloged as business events. This is for
  backward compatibility, and custom API is the recommended approach for
  exposing events.</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">Custom
  events can represent events that occur in external systems. See <a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/business-events#external-events">External
  Events</a> for additional considerations</p>
  <p style="margin:0in;font-family:Calibri;font-size:11.0pt" lang="en-US">&nbsp;</p>
  </td>
 </tr>
</tbody></table>
