# Chat Scheduled Messages

```csharp
ChatScheduledMessagesController chatScheduledMessagesController = client.ChatScheduledMessagesController;
```

## Class Name

`ChatScheduledMessagesController`


# Chat Scheduled Messages List

Returns a list of scheduled messages.

API method documentation: [https://api.slack.com/methods/chat.scheduledMessages.list](https://api.slack.com/methods/chat.scheduledMessages.list)

```csharp
ChatScheduledMessagesListAsync(
    string token = null,
    string channel = null,
    double? latest = null,
    double? oldest = null,
    int? limit = null,
    string cursor = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `none` |
| `channel` | `string` | Query, Optional | The channel of the scheduled messages |
| `latest` | `double?` | Query, Optional | A UNIX timestamp of the latest value in the time range |
| `oldest` | `double?` | Query, Optional | A UNIX timestamp of the oldest value in the time range |
| `limit` | `int?` | Query, Optional | Maximum number of original entries to return. |
| `cursor` | `string` | Query, Optional | For pagination purposes, this is the `cursor` value returned from a previous call to `chat.scheduledmessages.list` indicating where you want to start this call from. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ChatScheduledMessagesListSchema](../../doc/models/chat-scheduled-messages-list-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ChatScheduledMessagesListSchema> result = await chatScheduledMessagesController.ChatScheduledMessagesListAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ChatScheduledMessagesListErrorSchemaException)
    {
       // TODO: Handle ChatScheduledMessagesListErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response if the channel passed is invalid | [`ChatScheduledMessagesListErrorSchemaException`](../../doc/models/chat-scheduled-messages-list-error-schema-exception.md) |

