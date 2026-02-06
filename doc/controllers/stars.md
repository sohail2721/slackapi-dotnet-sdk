# Stars

```csharp
StarsController starsController = client.StarsController;
```

## Class Name

`StarsController`

## Methods

* [Stars Add](../../doc/controllers/stars.md#stars-add)
* [Stars List](../../doc/controllers/stars.md#stars-list)
* [Stars Remove](../../doc/controllers/stars.md#stars-remove)


# Stars Add

Adds a star to an item.

API method documentation: [https://api.slack.com/methods/stars.add](https://api.slack.com/methods/stars.add)

```csharp
StarsAddAsync(
    string token,
    string channel = null,
    string file = null,
    string fileComment = null,
    string timestamp = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `stars:write` |
| `channel` | `string` | Form, Optional | Channel to add star to, or channel where the message to add star to was posted (used with `timestamp`). |
| `file` | `string` | Form, Optional | File to add star to. |
| `fileComment` | `string` | Form, Optional | File comment to add star to. |
| `timestamp` | `string` | Form, Optional | Timestamp of the message to add star to. |

## Requires scope

### slackAuth

`stars:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.StarsAddSchema](../../doc/models/stars-add-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<StarsAddSchema> result = await starsController.StarsAddAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is StarsAddErrorSchemaException)
    {
       // TODO: Handle StarsAddErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`StarsAddErrorSchemaException`](../../doc/models/stars-add-error-schema-exception.md) |


# Stars List

Lists stars for a user.

API method documentation: [https://api.slack.com/methods/stars.list](https://api.slack.com/methods/stars.list)

```csharp
StarsListAsync(
    string token = null,
    string count = null,
    string page = null,
    string cursor = null,
    int? limit = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `stars:read` |
| `count` | `string` | Query, Optional | - |
| `page` | `string` | Query, Optional | - |
| `cursor` | `string` | Query, Optional | Parameter for pagination. Set `cursor` equal to the `next_cursor` attribute returned by the previous request's `response_metadata`. This parameter is optional, but pagination is mandatory: the default value simply fetches the first "page" of the collection. See [pagination](/docs/pagination) for more details. |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. |

## Requires scope

### slackAuth

`stars:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.StarsListSchema](../../doc/models/stars-list-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<StarsListSchema> result = await starsController.StarsListAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is StarsListErrorSchemaException)
    {
       // TODO: Handle StarsListErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`StarsListErrorSchemaException`](../../doc/models/stars-list-error-schema-exception.md) |


# Stars Remove

Removes a star from an item.

API method documentation: [https://api.slack.com/methods/stars.remove](https://api.slack.com/methods/stars.remove)

```csharp
StarsRemoveAsync(
    string token,
    string channel = null,
    string file = null,
    string fileComment = null,
    string timestamp = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `stars:write` |
| `channel` | `string` | Form, Optional | Channel to remove star from, or channel where the message to remove star from was posted (used with `timestamp`). |
| `file` | `string` | Form, Optional | File to remove star from. |
| `fileComment` | `string` | Form, Optional | File comment to remove star from. |
| `timestamp` | `string` | Form, Optional | Timestamp of the message to remove star from. |

## Requires scope

### slackAuth

`stars:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.StarsRemoveSchema](../../doc/models/stars-remove-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<StarsRemoveSchema> result = await starsController.StarsRemoveAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is StarsRemoveErrorSchemaException)
    {
       // TODO: Handle StarsRemoveErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`StarsRemoveErrorSchemaException`](../../doc/models/stars-remove-error-schema-exception.md) |

