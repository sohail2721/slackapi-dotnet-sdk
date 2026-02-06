# Calls

```csharp
CallsController callsController = client.CallsController;
```

## Class Name

`CallsController`

## Methods

* [Calls Add](../../doc/controllers/calls.md#calls-add)
* [Calls End](../../doc/controllers/calls.md#calls-end)
* [Calls Info](../../doc/controllers/calls.md#calls-info)
* [Calls Update](../../doc/controllers/calls.md#calls-update)


# Calls Add

Registers a new Call.

API method documentation: [https://api.slack.com/methods/calls.add](https://api.slack.com/methods/calls.add)

```csharp
CallsAddAsync(
    string token,
    string externalUniqueId,
    string joinUrl,
    string externalDisplayId = null,
    string desktopAppJoinUrl = null,
    int? dateStart = null,
    string title = null,
    string createdBy = null,
    string users = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `externalUniqueId` | `string` | Form, Required | An ID supplied by the 3rd-party Call provider. It must be unique across all Calls from that service. |
| `joinUrl` | `string` | Form, Required | The URL required for a client to join the Call. |
| `externalDisplayId` | `string` | Form, Optional | An optional, human-readable ID supplied by the 3rd-party Call provider. If supplied, this ID will be displayed in the Call object. |
| `desktopAppJoinUrl` | `string` | Form, Optional | When supplied, available Slack clients will attempt to directly launch the 3rd-party Call with this URL. |
| `dateStart` | `int?` | Form, Optional | Call start time in UTC UNIX timestamp format |
| `title` | `string` | Form, Optional | The name of the Call. |
| `createdBy` | `string` | Form, Optional | The valid Slack user ID of the user who created this Call. When this method is called with a user token, the `created_by` field is optional and defaults to the authed user of the token. Otherwise, the field is required. |
| `users` | `string` | Form, Optional | The list of users to register as participants in the Call. [Read more on how to specify users here](/apis/calls#users). |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string externalUniqueId = "external_unique_id0";
string joinUrl = "join_url6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await callsController.CallsAddAsync(
        token,
        externalUniqueId,
        joinUrl
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


# Calls End

Ends a Call.

API method documentation: [https://api.slack.com/methods/calls.end](https://api.slack.com/methods/calls.end)

```csharp
CallsEndAsync(
    string token,
    string id,
    int? duration = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `string` | Form, Required | `id` returned when registering the call using the [`calls.add`](/methods/calls.add) method. |
| `duration` | `int?` | Form, Optional | Call duration in seconds |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string id = "id0";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await callsController.CallsEndAsync(
        token,
        id
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


# Calls Info

Returns information about a Call.

API method documentation: [https://api.slack.com/methods/calls.info](https://api.slack.com/methods/calls.info)

```csharp
CallsInfoAsync(
    string token,
    string id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `calls:read` |
| `id` | `string` | Query, Required | `id` of the Call returned by the [`calls.add`](/methods/calls.add) method. |

## Requires scope

### slackAuth

`calls:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string id = "id0";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await callsController.CallsInfoAsync(
        token,
        id
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


# Calls Update

Updates information about a Call.

API method documentation: [https://api.slack.com/methods/calls.update](https://api.slack.com/methods/calls.update)

```csharp
CallsUpdateAsync(
    string token,
    string id,
    string title = null,
    string joinUrl = null,
    string desktopAppJoinUrl = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `string` | Form, Required | `id` returned by the [`calls.add`](/methods/calls.add) method. |
| `title` | `string` | Form, Optional | The name of the Call. |
| `joinUrl` | `string` | Form, Optional | The URL required for a client to join the Call. |
| `desktopAppJoinUrl` | `string` | Form, Optional | When supplied, available Slack clients will attempt to directly launch the 3rd-party Call with this URL. |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string id = "id0";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await callsController.CallsUpdateAsync(
        token,
        id
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

