# Rtm

```csharp
RtmController rtmController = client.RtmController;
```

## Class Name

`RtmController`


# Rtm Connect

Starts a Real Time Messaging session.

API method documentation: [https://api.slack.com/methods/rtm.connect](https://api.slack.com/methods/rtm.connect)

```csharp
RtmConnectAsync(
    string token,
    bool? batchPresenceAware = null,
    bool? presenceSub = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `rtm:stream` |
| `batchPresenceAware` | `bool?` | Query, Optional | Batch presence deliveries via subscription. Enabling changes the shape of `presence_change` events. See [batch presence](/docs/presence-and-status#batching). |
| `presenceSub` | `bool?` | Query, Optional | Only deliver presence events when requested by subscription. See [presence subscriptions](/docs/presence-and-status#subscriptions). |

## Requires scope

### slackAuth

`rtm:stream`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.RtmConnectSchema](../../doc/models/rtm-connect-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<RtmConnectSchema> result = await rtmController.RtmConnectAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is RtmConnectErrorSchemaException)
    {
       // TODO: Handle RtmConnectErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RtmConnectErrorSchemaException`](../../doc/models/rtm-connect-error-schema-exception.md) |

