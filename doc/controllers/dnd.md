# Dnd

```csharp
DndController dndController = client.DndController;
```

## Class Name

`DndController`

## Methods

* [Dnd End Dnd](../../doc/controllers/dnd.md#dnd-end-dnd)
* [Dnd End Snooze](../../doc/controllers/dnd.md#dnd-end-snooze)
* [Dnd Info](../../doc/controllers/dnd.md#dnd-info)
* [Dnd Set Snooze](../../doc/controllers/dnd.md#dnd-set-snooze)
* [Dnd Team Info](../../doc/controllers/dnd.md#dnd-team-info)


# Dnd End Dnd

Ends the current user's Do Not Disturb session immediately.

API method documentation: [https://api.slack.com/methods/dnd.endDnd](https://api.slack.com/methods/dnd.endDnd)

```csharp
DndEndDndAsync(
    string token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `dnd:write` |

## Requires scope

### slackAuth

`dnd:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DndEndDndSchema](../../doc/models/dnd-end-dnd-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<DndEndDndSchema> result = await dndController.DndEndDndAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is DndEndDndErrorSchemaException)
    {
       // TODO: Handle DndEndDndErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DndEndDndErrorSchemaException`](../../doc/models/dnd-end-dnd-error-schema-exception.md) |


# Dnd End Snooze

Ends the current user's snooze mode immediately.

API method documentation: [https://api.slack.com/methods/dnd.endSnooze](https://api.slack.com/methods/dnd.endSnooze)

```csharp
DndEndSnoozeAsync(
    string token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `dnd:write` |

## Requires scope

### slackAuth

`dnd:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DndEndSnoozeSchema](../../doc/models/dnd-end-snooze-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<DndEndSnoozeSchema> result = await dndController.DndEndSnoozeAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is DndEndSnoozeErrorSchemaException)
    {
       // TODO: Handle DndEndSnoozeErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DndEndSnoozeErrorSchemaException`](../../doc/models/dnd-end-snooze-error-schema-exception.md) |


# Dnd Info

Retrieves a user's current Do Not Disturb status.

API method documentation: [https://api.slack.com/methods/dnd.info](https://api.slack.com/methods/dnd.info)

```csharp
DndInfoAsync(
    string token = null,
    string user = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `dnd:read` |
| `user` | `string` | Query, Optional | User to fetch status for (defaults to current user) |

## Requires scope

### slackAuth

`dnd:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DndInfoSchema](../../doc/models/dnd-info-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<DndInfoSchema> result = await dndController.DndInfoAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is DndInfoErrorSchemaException)
    {
       // TODO: Handle DndInfoErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DndInfoErrorSchemaException`](../../doc/models/dnd-info-error-schema-exception.md) |


# Dnd Set Snooze

Turns on Do Not Disturb mode for the current user, or changes its duration.

API method documentation: [https://api.slack.com/methods/dnd.setSnooze](https://api.slack.com/methods/dnd.setSnooze)

```csharp
DndSetSnoozeAsync(
    string token,
    string numMinutes)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `dnd:write` |
| `numMinutes` | `string` | Form, Required | Number of minutes, from now, to snooze until. |

## Requires scope

### slackAuth

`dnd:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DndSetSnoozeSchema](../../doc/models/dnd-set-snooze-schema.md).

## Example Usage

```csharp
string token = "token6";
string numMinutes = "num_minutes0";
try
{
    ApiResponse<DndSetSnoozeSchema> result = await dndController.DndSetSnoozeAsync(
        token,
        numMinutes
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is DndSetSnoozeErrorSchemaException)
    {
       // TODO: Handle DndSetSnoozeErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DndSetSnoozeErrorSchemaException`](../../doc/models/dnd-set-snooze-error-schema-exception.md) |


# Dnd Team Info

Retrieves the Do Not Disturb status for up to 50 users on a team.

API method documentation: [https://api.slack.com/methods/dnd.teamInfo](https://api.slack.com/methods/dnd.teamInfo)

```csharp
DndTeamInfoAsync(
    string token = null,
    string users = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `dnd:read` |
| `users` | `string` | Query, Optional | Comma-separated list of users to fetch Do Not Disturb status for |

## Requires scope

### slackAuth

`dnd:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
try
{
    ApiResponse<DefaultSuccessTemplate> result = await dndController.DndTeamInfoAsync();
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

