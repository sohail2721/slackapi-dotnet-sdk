# Workflows

```csharp
WorkflowsController workflowsController = client.WorkflowsController;
```

## Class Name

`WorkflowsController`

## Methods

* [Workflows Step Completed](../../doc/controllers/workflows.md#workflows-step-completed)
* [Workflows Step Failed](../../doc/controllers/workflows.md#workflows-step-failed)
* [Workflows Update Step](../../doc/controllers/workflows.md#workflows-update-step)


# Workflows Step Completed

Indicate that an app's step in a workflow completed execution.

API method documentation: [https://api.slack.com/methods/workflows.stepCompleted](https://api.slack.com/methods/workflows.stepCompleted)

```csharp
WorkflowsStepCompletedAsync(
    string token,
    string workflowStepExecuteId,
    string outputs = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `workflow.steps:execute` |
| `workflowStepExecuteId` | `string` | Query, Required | Context identifier that maps to the correct workflow step execution. |
| `outputs` | `string` | Query, Optional | Key-value object of outputs from your step. Keys of this object reflect the configured `key` properties of your [`outputs`](/reference/workflows/workflow_step#output) array from your `workflow_step` object. |

## Requires scope

### slackAuth

`workflow.steps:execute`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string workflowStepExecuteId = "workflow_step_execute_id2";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await workflowsController.WorkflowsStepCompletedAsync(
        token,
        workflowStepExecuteId
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is DefaultErrorTemplateException)
    {
       // TODO: Handle DefaultErrorTemplateException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Workflows Step Failed

Indicate that an app's step in a workflow failed to execute.

API method documentation: [https://api.slack.com/methods/workflows.stepFailed](https://api.slack.com/methods/workflows.stepFailed)

```csharp
WorkflowsStepFailedAsync(
    string token,
    string workflowStepExecuteId,
    string error)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `workflow.steps:execute` |
| `workflowStepExecuteId` | `string` | Query, Required | Context identifier that maps to the correct workflow step execution. |
| `error` | `string` | Query, Required | A JSON-based object with a `message` property that should contain a human readable error message. |

## Requires scope

### slackAuth

`workflow.steps:execute`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string workflowStepExecuteId = "workflow_step_execute_id2";
string error = "error4";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await workflowsController.WorkflowsStepFailedAsync(
        token,
        workflowStepExecuteId,
        error
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is DefaultErrorTemplateException)
    {
       // TODO: Handle DefaultErrorTemplateException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Workflows Update Step

Update the configuration for a workflow extension step.

API method documentation: [https://api.slack.com/methods/workflows.updateStep](https://api.slack.com/methods/workflows.updateStep)

```csharp
WorkflowsUpdateStepAsync(
    string token,
    string workflowStepEditId,
    string inputs = null,
    string outputs = null,
    string stepName = null,
    string stepImageUrl = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `workflow.steps:execute` |
| `workflowStepEditId` | `string` | Query, Required | A context identifier provided with `view_submission` payloads used to call back to `workflows.updateStep`. |
| `inputs` | `string` | Query, Optional | A JSON key-value map of inputs required from a user during configuration. This is the data your app expects to receive when the workflow step starts. **Please note**: the embedded variable format is set and replaced by the workflow system. You cannot create custom variables that will be replaced at runtime. [Read more about variables in workflow steps here](/workflows/steps#variables). |
| `outputs` | `string` | Query, Optional | An JSON array of output objects used during step execution. This is the data your app agrees to provide when your workflow step was executed. |
| `stepName` | `string` | Query, Optional | An optional field that can be used to override the step name that is shown in the Workflow Builder. |
| `stepImageUrl` | `string` | Query, Optional | An optional field that can be used to override app image that is shown in the Workflow Builder. |

## Requires scope

### slackAuth

`workflow.steps:execute`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string workflowStepEditId = "workflow_step_edit_id0";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await workflowsController.WorkflowsUpdateStepAsync(
        token,
        workflowStepEditId
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is DefaultErrorTemplateException)
    {
       // TODO: Handle DefaultErrorTemplateException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

