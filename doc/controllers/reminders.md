# Reminders

```csharp
RemindersController remindersController = client.RemindersController;
```

## Class Name

`RemindersController`

## Methods

* [Reminders Add](../../doc/controllers/reminders.md#reminders-add)
* [Reminders Complete](../../doc/controllers/reminders.md#reminders-complete)
* [Reminders Delete](../../doc/controllers/reminders.md#reminders-delete)
* [Reminders Info](../../doc/controllers/reminders.md#reminders-info)
* [Reminders List](../../doc/controllers/reminders.md#reminders-list)


# Reminders Add

Creates a reminder.

API method documentation: [https://api.slack.com/methods/reminders.add](https://api.slack.com/methods/reminders.add)

```csharp
RemindersAddAsync(
    string token,
    string text,
    string time,
    string user = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `reminders:write` |
| `text` | `string` | Form, Required | The content of the reminder |
| `time` | `string` | Form, Required | When this reminder should happen: the Unix timestamp (up to five years from now), the number of seconds until the reminder (if within 24 hours), or a natural language description (Ex. "in 15 minutes," or "every Thursday") |
| `user` | `string` | Form, Optional | The user who will receive the reminder. If no user is specified, the reminder will go to user who created it. |

## Requires scope

### slackAuth

`reminders:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.RemindersAddSchema](../../doc/models/reminders-add-schema.md).

## Example Usage

```csharp
string token = "token6";
string text = "text0";
string time = "time0";
try
{
    ApiResponse<RemindersAddSchema> result = await remindersController.RemindersAddAsync(
        token,
        text,
        time
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is RemindersAddErrorSchemaException)
    {
       // TODO: Handle RemindersAddErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RemindersAddErrorSchemaException`](../../doc/models/reminders-add-error-schema-exception.md) |


# Reminders Complete

Marks a reminder as complete.

API method documentation: [https://api.slack.com/methods/reminders.complete](https://api.slack.com/methods/reminders.complete)

```csharp
RemindersCompleteAsync(
    string token = null,
    string reminder = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `reminders:write` |
| `reminder` | `string` | Form, Optional | The ID of the reminder to be marked as complete |

## Requires scope

### slackAuth

`reminders:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.RemindersCompleteSchema](../../doc/models/reminders-complete-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<RemindersCompleteSchema> result = await remindersController.RemindersCompleteAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is RemindersCompleteErrorSchemaException)
    {
       // TODO: Handle RemindersCompleteErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RemindersCompleteErrorSchemaException`](../../doc/models/reminders-complete-error-schema-exception.md) |


# Reminders Delete

Deletes a reminder.

API method documentation: [https://api.slack.com/methods/reminders.delete](https://api.slack.com/methods/reminders.delete)

```csharp
RemindersDeleteAsync(
    string token = null,
    string reminder = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `reminders:write` |
| `reminder` | `string` | Form, Optional | The ID of the reminder |

## Requires scope

### slackAuth

`reminders:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.RemindersDeleteSchema](../../doc/models/reminders-delete-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<RemindersDeleteSchema> result = await remindersController.RemindersDeleteAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is RemindersDeleteErrorSchemaException)
    {
       // TODO: Handle RemindersDeleteErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RemindersDeleteErrorSchemaException`](../../doc/models/reminders-delete-error-schema-exception.md) |


# Reminders Info

Gets information about a reminder.

API method documentation: [https://api.slack.com/methods/reminders.info](https://api.slack.com/methods/reminders.info)

```csharp
RemindersInfoAsync(
    string token = null,
    string reminder = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `reminders:read` |
| `reminder` | `string` | Query, Optional | The ID of the reminder |

## Requires scope

### slackAuth

`reminders:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.RemindersInfoSchema](../../doc/models/reminders-info-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<RemindersInfoSchema> result = await remindersController.RemindersInfoAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is RemindersInfoErrorSchemaException)
    {
       // TODO: Handle RemindersInfoErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RemindersInfoErrorSchemaException`](../../doc/models/reminders-info-error-schema-exception.md) |


# Reminders List

Lists all reminders created by or for a given user.

API method documentation: [https://api.slack.com/methods/reminders.list](https://api.slack.com/methods/reminders.list)

```csharp
RemindersListAsync(
    string token = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `reminders:read` |

## Requires scope

### slackAuth

`reminders:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.RemindersListSchema](../../doc/models/reminders-list-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<RemindersListSchema> result = await remindersController.RemindersListAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is RemindersListErrorSchemaException)
    {
       // TODO: Handle RemindersListErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RemindersListErrorSchemaException`](../../doc/models/reminders-list-error-schema-exception.md) |

