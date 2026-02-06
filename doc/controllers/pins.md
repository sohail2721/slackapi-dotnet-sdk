# Pins

```csharp
PinsController pinsController = client.PinsController;
```

## Class Name

`PinsController`

## Methods

* [Pins Add](../../doc/controllers/pins.md#pins-add)
* [Pins List](../../doc/controllers/pins.md#pins-list)
* [Pins Remove](../../doc/controllers/pins.md#pins-remove)


# Pins Add

Pins an item to a channel.

API method documentation: [https://api.slack.com/methods/pins.add](https://api.slack.com/methods/pins.add)

```csharp
PinsAddAsync(
    string token,
    string channel,
    string timestamp = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `pins:write` |
| `channel` | `string` | Form, Required | Channel to pin the item in. |
| `timestamp` | `string` | Form, Optional | Timestamp of the message to pin. |

## Requires scope

### slackAuth

`pins:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.PinsAddSchema](../../doc/models/pins-add-schema.md).

## Example Usage

```csharp
string token = "token6";
string channel = "channel4";
try
{
    ApiResponse<PinsAddSchema> result = await pinsController.PinsAddAsync(
        token,
        channel
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is PinsAddErrorSchemaException)
    {
       // TODO: Handle PinsAddErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`PinsAddErrorSchemaException`](../../doc/models/pins-add-error-schema-exception.md) |


# Pins List

Lists items pinned to a channel.

API method documentation: [https://api.slack.com/methods/pins.list](https://api.slack.com/methods/pins.list)

```csharp
PinsListAsync(
    string token,
    string channel)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `pins:read` |
| `channel` | `string` | Query, Required | Channel to get pinned items for. |

## Requires scope

### slackAuth

`pins:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type dynamic.

## Example Usage

```csharp
string token = "token6";
string channel = "channel4";
try
{
    ApiResponse<dynamic> result = await pinsController.PinsListAsync(
        token,
        channel
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is PinsListErrorSchemaException)
    {
       // TODO: Handle PinsListErrorSchemaException exception here
    }
}
```

## Example Response

```
{
  "items": [
    {
      "channel": "C2U86NC6H",
      "created": 1508881078,
      "created_by": "U2U85N1RZ",
      "message": {
        "permalink": "https://hitchhikers.slack.com/archives/C2U86NC6H/p1508197641000151",
        "pinned_to": [
          "C2U86NC6H"
        ],
        "text": "What is the meaning of life?",
        "ts": "1508197641.000151",
        "type": "message",
        "user": "U2U85N1RZ"
      },
      "type": "message"
    },
    {
      "channel": "C2U86NC6H",
      "created": 1508880991,
      "created_by": "U2U85N1RZ",
      "message": {
        "permalink": "https://hitchhikers.slack.com/archives/C2U86NC6H/p1508284197000015",
        "pinned_to": [
          "C2U86NC6H"
        ],
        "text": "The meaning of life, the universe, and everything is 42.",
        "ts": "1503289197.000015",
        "type": "message",
        "user": "U2U85N1RZ"
      },
      "type": "message"
    }
  ],
  "ok": true
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`PinsListErrorSchemaException`](../../doc/models/pins-list-error-schema-exception.md) |


# Pins Remove

Un-pins an item from a channel.

API method documentation: [https://api.slack.com/methods/pins.remove](https://api.slack.com/methods/pins.remove)

```csharp
PinsRemoveAsync(
    string token,
    string channel,
    string timestamp = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `pins:write` |
| `channel` | `string` | Form, Required | Channel where the item is pinned to. |
| `timestamp` | `string` | Form, Optional | Timestamp of the message to un-pin. |

## Requires scope

### slackAuth

`pins:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.PinsRemoveSchema](../../doc/models/pins-remove-schema.md).

## Example Usage

```csharp
string token = "token6";
string channel = "channel4";
try
{
    ApiResponse<PinsRemoveSchema> result = await pinsController.PinsRemoveAsync(
        token,
        channel
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is PinsRemoveErrorSchemaException)
    {
       // TODO: Handle PinsRemoveErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`PinsRemoveErrorSchemaException`](../../doc/models/pins-remove-error-schema-exception.md) |

