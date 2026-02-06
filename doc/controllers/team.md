# Team

```csharp
TeamController teamController = client.TeamController;
```

## Class Name

`TeamController`

## Methods

* [Team Access Logs](../../doc/controllers/team.md#team-access-logs)
* [Team Billable Info](../../doc/controllers/team.md#team-billable-info)
* [Team Info](../../doc/controllers/team.md#team-info)
* [Team Integration Logs](../../doc/controllers/team.md#team-integration-logs)


# Team Access Logs

Gets the access logs for the current team.

API method documentation: [https://api.slack.com/methods/team.accessLogs](https://api.slack.com/methods/team.accessLogs)

```csharp
TeamAccessLogsAsync(
    string token,
    string before = null,
    string count = null,
    string page = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `admin` |
| `before` | `string` | Query, Optional | End of time range of logs to include in results (inclusive). |
| `count` | `string` | Query, Optional | - |
| `page` | `string` | Query, Optional | - |

## Requires scope

### slackAuth

`admin`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.TeamAccessLogsSchema](../../doc/models/team-access-logs-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<TeamAccessLogsSchema> result = await teamController.TeamAccessLogsAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is TeamAccessLogsErrorSchemaException)
    {
       // TODO: Handle TeamAccessLogsErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | A workspace must be on a paid plan to use this method, otherwise the `paid_only` error is thrown: | [`TeamAccessLogsErrorSchemaException`](../../doc/models/team-access-logs-error-schema-exception.md) |


# Team Billable Info

Gets billable users information for the current team.

API method documentation: [https://api.slack.com/methods/team.billableInfo](https://api.slack.com/methods/team.billableInfo)

```csharp
TeamBillableInfoAsync(
    string token,
    string user = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `admin` |
| `user` | `string` | Query, Optional | A user to retrieve the billable information for. Defaults to all users. |

## Requires scope

### slackAuth

`admin`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await teamController.TeamBillableInfoAsync(token);
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


# Team Info

Gets information about the current team.

API method documentation: [https://api.slack.com/methods/team.info](https://api.slack.com/methods/team.info)

```csharp
TeamInfoAsync(
    string token,
    string team = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `team:read` |
| `team` | `string` | Query, Optional | Team to get info on, if omitted, will return information about the current team. Will only return team that the authenticated token is allowed to see through external shared channels |

## Requires scope

### slackAuth

`team:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.TeamInfoSchema](../../doc/models/team-info-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<TeamInfoSchema> result = await teamController.TeamInfoAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is TeamInfoErrorSchemaException)
    {
       // TODO: Handle TeamInfoErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`TeamInfoErrorSchemaException`](../../doc/models/team-info-error-schema-exception.md) |


# Team Integration Logs

Gets the integration logs for the current team.

API method documentation: [https://api.slack.com/methods/team.integrationLogs](https://api.slack.com/methods/team.integrationLogs)

```csharp
TeamIntegrationLogsAsync(
    string token,
    string appId = null,
    string changeType = null,
    string count = null,
    string page = null,
    string serviceId = null,
    string user = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `admin` |
| `appId` | `string` | Query, Optional | Filter logs to this Slack app. Defaults to all logs. |
| `changeType` | `string` | Query, Optional | Filter logs with this change type. Defaults to all logs. |
| `count` | `string` | Query, Optional | - |
| `page` | `string` | Query, Optional | - |
| `serviceId` | `string` | Query, Optional | Filter logs to this service. Defaults to all logs. |
| `user` | `string` | Query, Optional | Filter logs generated by this user’s actions. Defaults to all logs. |

## Requires scope

### slackAuth

`admin`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.TeamIntegrationLogsSchema](../../doc/models/team-integration-logs-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<TeamIntegrationLogsSchema> result = await teamController.TeamIntegrationLogsAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is TeamIntegrationLogsErrorSchemaException)
    {
       // TODO: Handle TeamIntegrationLogsErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`TeamIntegrationLogsErrorSchemaException`](../../doc/models/team-integration-logs-error-schema-exception.md) |

