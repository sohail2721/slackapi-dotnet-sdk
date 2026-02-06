# Reactions

```csharp
ReactionsController reactionsController = client.ReactionsController;
```

## Class Name

`ReactionsController`

## Methods

* [Reactions Add](../../doc/controllers/reactions.md#reactions-add)
* [Reactions Get](../../doc/controllers/reactions.md#reactions-get)
* [Reactions List](../../doc/controllers/reactions.md#reactions-list)
* [Reactions Remove](../../doc/controllers/reactions.md#reactions-remove)


# Reactions Add

Adds a reaction to an item.

API method documentation: [https://api.slack.com/methods/reactions.add](https://api.slack.com/methods/reactions.add)

```csharp
ReactionsAddAsync(
    string channel,
    string name,
    string timestamp,
    string token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channel` | `string` | Form, Required | Channel where the message to add reaction to was posted. |
| `name` | `string` | Form, Required | Reaction (emoji) name. |
| `timestamp` | `string` | Form, Required | Timestamp of the message to add reaction to. |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `reactions:write` |

## Requires scope

### slackAuth

`reactions:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ReactionsAddSchema](../../doc/models/reactions-add-schema.md).

## Example Usage

```csharp
string channel = "channel4";
string name = "name0";
string timestamp = "timestamp2";
string token = "token6";
try
{
    ApiResponse<ReactionsAddSchema> result = await reactionsController.ReactionsAddAsync(
        channel,
        name,
        timestamp,
        token
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ReactionsAddErrorSchemaException)
    {
       // TODO: Handle ReactionsAddErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ReactionsAddErrorSchemaException`](../../doc/models/reactions-add-error-schema-exception.md) |


# Reactions Get

Gets reactions for an item.

API method documentation: [https://api.slack.com/methods/reactions.get](https://api.slack.com/methods/reactions.get)

```csharp
ReactionsGetAsync(
    string token,
    string channel = null,
    string file = null,
    string fileComment = null,
    bool? full = null,
    string timestamp = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `reactions:read` |
| `channel` | `string` | Query, Optional | Channel where the message to get reactions for was posted. |
| `file` | `string` | Query, Optional | File to get reactions for. |
| `fileComment` | `string` | Query, Optional | File comment to get reactions for. |
| `full` | `bool?` | Query, Optional | If true always return the complete reaction list. |
| `timestamp` | `string` | Query, Optional | Timestamp of the message to get reactions for. |

## Requires scope

### slackAuth

`reactions:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type object.

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<object> result = await reactionsController.ReactionsGetAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ReactionsGetErrorSchemaException)
    {
       // TODO: Handle ReactionsGetErrorSchemaException exception here
    }
}
```

## Example Response

```
{
  "file": {
    "channels": [
      "C2U7V2YA2"
    ],
    "comments_count": 1,
    "created": 1507850315,
    "groups": [],
    "id": "F7H0D7ZA4",
    "ims": [],
    "name": "computer.gif",
    "reactions": [
      {
        "count": 1,
        "name": "stuck_out_tongue_winking_eye",
        "users": [
          "U2U85N1RV"
        ]
      }
    ],
    "timestamp": 1507850315,
    "title": "computer.gif",
    "user": "U2U85N1RV"
  },
  "ok": true,
  "type": "file"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ReactionsGetErrorSchemaException`](../../doc/models/reactions-get-error-schema-exception.md) |


# Reactions List

Lists reactions made by a user.

API method documentation: [https://api.slack.com/methods/reactions.list](https://api.slack.com/methods/reactions.list)

```csharp
ReactionsListAsync(
    string token,
    string user = null,
    bool? full = null,
    int? count = null,
    int? page = null,
    string cursor = null,
    int? limit = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `reactions:read` |
| `user` | `string` | Query, Optional | Show reactions made by this user. Defaults to the authed user. |
| `full` | `bool?` | Query, Optional | If true always return the complete reaction list. |
| `count` | `int?` | Query, Optional | - |
| `page` | `int?` | Query, Optional | - |
| `cursor` | `string` | Query, Optional | Parameter for pagination. Set `cursor` equal to the `next_cursor` attribute returned by the previous request's `response_metadata`. This parameter is optional, but pagination is mandatory: the default value simply fetches the first "page" of the collection. See [pagination](/docs/pagination) for more details. |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. |

## Requires scope

### slackAuth

`reactions:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ReactionsListSchema](../../doc/models/reactions-list-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<ReactionsListSchema> result = await reactionsController.ReactionsListAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ReactionsListErrorSchemaException)
    {
       // TODO: Handle ReactionsListErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ReactionsListErrorSchemaException`](../../doc/models/reactions-list-error-schema-exception.md) |


# Reactions Remove

Removes a reaction from an item.

API method documentation: [https://api.slack.com/methods/reactions.remove](https://api.slack.com/methods/reactions.remove)

```csharp
ReactionsRemoveAsync(
    string token,
    string name,
    string file = null,
    string fileComment = null,
    string channel = null,
    string timestamp = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `reactions:write` |
| `name` | `string` | Form, Required | Reaction (emoji) name. |
| `file` | `string` | Form, Optional | File to remove reaction from. |
| `fileComment` | `string` | Form, Optional | File comment to remove reaction from. |
| `channel` | `string` | Form, Optional | Channel where the message to remove reaction from was posted. |
| `timestamp` | `string` | Form, Optional | Timestamp of the message to remove reaction from. |

## Requires scope

### slackAuth

`reactions:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ReactionsRemoveSchema](../../doc/models/reactions-remove-schema.md).

## Example Usage

```csharp
string token = "token6";
string name = "name0";
try
{
    ApiResponse<ReactionsRemoveSchema> result = await reactionsController.ReactionsRemoveAsync(
        token,
        name
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ReactionsRemoveErrorSchemaException)
    {
       // TODO: Handle ReactionsRemoveErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ReactionsRemoveErrorSchemaException`](../../doc/models/reactions-remove-error-schema-exception.md) |

