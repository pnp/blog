## Dataverse

### Contents

1. [Power Platform? I'm a developer!](index.md)
1. [Power Apps](powerApps.md)
1. [Power Automate](./PowerAutomate.md)
1. **Dataverse**


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
<table>
 <tbody><tr>
  <td><p>Approach</p></td>
  <td><p>Programming  language</p></td>
  <td>  <p>Description</p>  </td>
  <td><p>Constraints  and Limitations</p></td>
 </tr>
 <tr>
  <td><p><a href="https://learn.microsoft.com/en-us/training/modules/create-define-calculation-rollup-fields/1-intro">Rollup  column</a></p>
  </td>
  <td>  <p>Power Fx</p>
  </td>
  <td>
  <p>Contains  an aggregate value computed over the rows related to a specified row,  can aggregates data from relate  records in another table</p>
  <p>In more  complex scenarios, you can aggregate data over the hierarchy of rows. </p>
  </td>
  <td>
  <p>The  rollups are calculated by scheduled system jobs that run asynchronously in
  the background. Rollup columns are <b>only  recalculated every hour </b>by default, but can be scheduled to run daily
  every x hours.</p>
  <p><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/define-rollup-fields#rollup-columns-benefits-and-capabilities">Rollup
  columns benefits and capabilities</a> and <a href="https://learn.microsoft.com/en-us/training/modules/create-define-calculation-rollup-fields/2-rollup">key
  considerations</a></p>
  </td>
 </tr>
 <tr>
  <td><p><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/formula-columns">Formula  columns</a></p></td>
  <td><p>Power Fx</p></td>
  <td>
  <p>Formula  column is a column that derives its value from a formula using other columns  in the same table. </p>
  <p>The  formula can be defined using the Power Apps editor and can reference other  calculated columns, but not rollup columns. </p>
  <p>Calculated  columns are read-only and their values are calculated at runtime when the  record is retrieved</p>
  </td>
  <td>
  <p>The <b>Calculated behavior</b> will eventually be  discontinued. It's recommend to use the Formula data type for calculations
  instead.</p>
  </td>
 </tr>
 <tr>
  <td>
  <p><a href="https://learn.microsoft.com/en-us/training/modules/define-create-business-rules/">Business  rules</a></p>
  </td>
  <td>
  <p>declarative</p>
  </td>
  <td>
  <p>Business  logic to ensure that columns in a model-driven app are shown, hidden, or set  with the correct values without writing JavaScript code or creating plug-ins.</p>
  <p>Define business  rules for a table that apply to all the table forms and at the server  level. Business rules defined for a table apply to both canvas
  apps and model-driven apps if the table is used in the  app. </p>
  </td>
  <td>
  <p>Not all  business rule actions are available on canvas apps at this time: <a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/data-platform-create-business-rule#differences-between-canvas-and-model-driven-apps">Differences  between canvas and model-driven apps</a></p>
  <p><a href="https://learn.microsoft.com/en-us/power-apps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form">Create
  business rules to apply logic in a model-driven app form</a></p>
  <p><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/data-platform-create-business-rule">Differences  between canvas and model-driven apps</a></p>
  </td>
 </tr>
 <tr>
  <td>
  <p><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant">Low-code  Plug-ins</a></p>
  </td>
  <td>
  <p>Power  Fx</p>
  </td>
  <td>
  <p>Traditionally,  plug-ins were created as custom classes compiled into a .NET Framework  assembly, which were then uploaded and registered within Dataverse. However,  with the introduction of low-code plug-ins, users can create these event  handlers with minimal or no coding required, and without the need for manual  registration.</p>

  <p>Low-code  plug-ins are stored within a Dataverse database and can be seamlessly  integrated into Power Apps and Power Automate. The behavior of the workflow  is defined using the <b>Power Fx</b>
  expression language and can directly connect with Dataverse business data and  external data sources through Power Platform connectors. With low-code
  plug-ins, makers can rapidly construct complex workflows with minimal coding  expertise, resulting in a more streamlined and efficient data architecture.</p>
  </td>
  <td>
  <p>Low-code  plug-ins are stored within a Dataverse database and are created using <a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant#prerequisites-for-creating-a-low-code-plug-in">Dataverse  accelerator app</a>, which must be installed in the environment. </p>
  <p><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins?tabs=instant#limitations">Limitations</a></p>
  <p><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/low-code-plug-ins-powerfx">Formulas  not currently supported</a> |
  <a href="https://learn.microsoft.com/en-us/power-platform/power-fx/formula-reference">Formula  reference</a> </p>
  </td>
 </tr>
 <tr>
  <td><p><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/plug-ins">Dataverse  plugins</a></p></td>
  <td><p>.NET</p></td>
  <td>
  <p>A plug-in is  a custom event handler that executes in response to a specific event raised  during processing of a Microsoft Dataverse data operation. It sits between the API and the data. </p>
  <p>When  the target event occurs during a data processing operation, the code within  the registered plug-in class executes. It can create, read, modify, or delete  data being processed during the current database transaction. <b>Logic is transactional and either all complete or  all roll back</b>. </p>
  <p>Plug-in  code should be very focused, execute quickly and minimize blocking to avoid  exceeding timeout thresholds and ensure a responsive system for synchronous  scenarios. Simply submit each request directly <a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/best-practices/business-logic/avoid-batch-requests-plugin">instead  of batching</a> them and submitting as a single request</p>
  <p>They  can perform logic with <b>elevated permissions</b>  that the user might not normally have. This approach also allows for  minimizing the permissions the app user might require. </p>
  <p>Plug-ins can be synchronous or asynchronous. <b>Asynchronous</b>  plug-in will cause the data <b>operation to wait</b>
  until the code in the plug-in completes. This has an impact on end-user  perceived performance of the system, which is why <b> synchronous plug-ins must execute and complete quickly</b>. <b>Asynchronous</b> plug-in execution is <b>queued</b> and later executed after the data  operation has completed.</p>
  </td>
  <td>
  <p>Plug-ins  on events <b>aren’t the best approach ifyou must  listen to events on multiple tables</b> to complete a single business
  event like Close Inspection. Consider a <b>Dataverse  custom API instead of having plug-ins on multiple tables.</b></p>
  <p><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/plug-ins#disadvantages-of-plug-ins"><b>Disadvantages</b></a> of plug-ins</p>
  <ul>
   <li>Plug-ins<b> require the special skills</b> of a software developer to create and maintain the plug-in
 code. Smaller businesses may not have access to a developer with the needed skills. Business processes can change rapidly and providing options to enable change without requiring a developer can allow the system to adapt more rapidly.</li>
   <li>Plug-ins <b>can be abused.</b> A <b>poorly written</b> plug-in can cause significant impact on the performance of the data processing
 pipeline and ultimately the environment. The great power of plug-ins needs to be applied with some restraint and consideration for the impact
 it has on the system as a whole.</li>
  </ul>
  </td>
 </tr>
 <tr>
  <td>
  <p><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/create-actions">Custom  process action</a></p>
  </td>
  <td><p>declarative</p></td>
  <td>
  <p><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/workflow-custom-actions"><b>Custom process actions</b></a> provide the
  ability to <b>define a single verb (or message)</b>  that <b>matches an operation</b> you need to  perform for your <b>business</b>. These new  messages are <b>driven by a process or behavior</b>  rather than what can be done with a table. </p>
  <p>They  can <b>perform operations</b>, such as Create,  Update, Delete, Assign (record), SendEmail, Start/Stop Workflow or Perform  Action</p>
  <p><a href="https://learn.microsoft.com/en-us/power-apps/maker/data-platform/create-actions#:~:text=Enable-,rollback,-Generally%2C%20processes%20that">Rollback</a>:  Custom process actions have always been synchronous 'real-time' workflows. </p>
  <p><b>Everything you</b> can <b>do</b> just with the <b>user interface of the action will support transactions</b>. </p>
  <p>Some  actions developers might do in code initiated by the custom process action  might not support transactions. For example, if the code perform actions in  other systems that are beyond the scope of the transaction.</p>
  <p><b>All the actions</b> that are  part <b>of a real-time workflow are </b>considered  in<b> transaction</b>, but with <b>actions</b> you have the option to <b>opt out</b> of this.</p>
  <p>If one  of the <b>steps in the action's real-time  workflow</b> is a <b>custom workflow activity</b>,  that custom workflow activity is subject to the <b>two-minute timeout limit.</b> However, there are <b>no specific restrictions</b> on the amount of <b>overall time the action itself</b> can take. This
  absence of restriction isn't an advantage; workflows can't run indefinitely  and will eventually fail. </p>
  <p>There  are two ways to<b> extend Custom Process Actions</b>  using code:<b> with custom workflow activities</b>  or by <b>registering plug-ins on stages.</b></p>
  </td>
  <td>
  <p>A best  practice recommendation is that <b>long running  operations</b> should be executed <b>outside  of Dataverse</b> using Power Automate, Logic Apps, or other capabilities  offered by Azure.</p>
  <p>You  cannot enable rollback if a  custom process action is invoked directly from within a workflow. You can  enable rollback if an action is triggered by a Power Apps web services  message.</p>
  <p>Unlike  Microsoft Dataverse workflows or plug-ins, an custom process action doesn't  have to be associated with a specific table. You can define global custom  process actions that can be called on their own.</p>
  <p><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/business-events#:~:text=custom%20process%20actions%20have%20the%20following%20limitations%3A">Custom  Process Actions limitations</a></p>
  </td>
 </tr>
 <tr>
  <td>
  <p><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/workflow/workflow-extensions">workflow  activities/assemblies</a></p>
  </td>
  <td>
  <p>.NET</p>
  </td>
  <td>
  <p >If  you don't find the  functionality you require using the default process activities, you can <b>add custom activities</b> so that they're available in the editor used to compose workflow, dialog, and action processes.</p>
  <p>The new actions will be available in the workflow designer for  users to apply - <b>for example a condition or  some new operation.</b> In this way you can add new custom actions in the  process designer for users of your environment.</p>
  </td>
  <td>
  <p>Unlike  an ordinary plug-in, with workflow extensions you don't have the opportunity  to explicitly register your code for a specific step. This means you don't  control whether the code in your workflow extension will run synchronously or  asynchronously.</p>
  <p>When  your <b>workflow extension is used</b> in a <b>synchronous workflow or a custom action</b> the
  time spent running the code directly impacts the user's experience. For this  reason, workflow extensions should require <b>no more than two seconds</b> to complete when  used <b>synchronously</b>.  If your extension requires <b>more time</b>  than this, you should <b>document this and
  discourage</b> use of the extension <b>in  synchronous workflows or custom actions.</b></p>
  </td>
 </tr>
 <tr>
  <td>
  <p><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/custom-api"> Custom  API </a> </p>
  </td>
  <td>
  <p>.NET</p>
  </td>
  <td>
  <p>Custom  API is a <b>newer </b>way to define custom  messages, offering developers better capabilities to create their own  messages. </p>
  <p>Using  Microsoft Dataverse <a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/business-events">business
  events</a>, you can create a custom API without a plug-in to pass data about  an event that other subscribers respond to. In other cases you'll combine a
  custom API with a plug-in to define some operation that is delegated to  Dataverse to compute and return the result.A <b>plug-in that implements</b> the
  main operation for a custom API is subject to the <b>2 minute time limit</b> to complete execution. </p>
  <p>They  can be used <b>on demand by the apps and flows</b>,  the data changes done in the<b> custom API  plug-in</b> are <b>transactional</b>.
  See <a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/custom-api#select-a-custom-processing-step-type">Custom
  Processing Step Type</a> for guidance on defining how can your custom API be  executed.</p>
  <p>Custom  API is the <b>best</b> choice when the <b>only</b> service it uses is the <b>Dataverse API for other data work</b>. </p>
  </td>
  <td>
  <p>Custom  APIs use plug-ins to perform data operations. Like all Dataverse plug-ins,  these plug-ins have a <b>two-minute execution time-out</b>.
  Sending the request asynchronously doesn't provide more  execution time.</p>

  <p>Set  "Enabled for Workflow" to true when you need to enable calling  a custom API as a workflow action. However, when this option is selected some
  <a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/custom-api#use-a-custom-api-in-a-workflow">limitations</a>  are imposed .</p>
  </td>
 </tr>
 <tr>
  <td>
  <p><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/background-operations">Background  operations</a> (preview)</p>
  </td>
  <td>

  </td>
  <td>
  <p>Use <a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/background-operations">background  operations</a> to send requests that Dataverse processes asynchronously,  without maintaining connection while a request runs. Even when executing  request asynchronously, the <b>two-minute  execution time-out</b> still applies to the plug-in.</p>
  </td>
  <td>
  <p>If an  error occurs during execution of the request, it's retried up to three times,  using <a href="https://wikipedia.org/wiki/Exponential_backoff">exponential  backoff strategy</a>.</p>
  </td>
 </tr>
 <tr>
  <td>
  <p><a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/business-events">Business  events</a></p>
  </td>
  <td>
  </td>
  <td>
  <p>Automation  of business logic and integration with other systems are driven by events.  Using Microsoft Dataverse <b>business events</b>,
  you can create a <b>custom API without a plug-in</b>,  to pass data <b>about an event</b> that other  subscribers respond to asynchronously.</p>
  <p>You can  use custom APIs without any synchronous logic that exist to only to  notify listeners that an event of interest occurred. You emit the event by
  calling the custom action.</p>
  </td>
  <td>
  <p>Custom  process actions can also be cataloged as business events. This is for  backward compatibility, and custom API is the recommended approach for
  exposing events.</p>
  <p>Custom  events can represent events that occur in external systems. See <a href="https://learn.microsoft.com/en-us/power-apps/developer/data-platform/business-events#external-events">External  Events</a> for additional considerations</p>
  </td>
 </tr>
</tbody></table>
