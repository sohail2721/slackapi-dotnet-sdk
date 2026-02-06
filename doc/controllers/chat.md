# Chat

```csharp
ChatController chatController = client.ChatController;
```

## Class Name

`ChatController`

## Methods

* [Chat Delete](../../doc/controllers/chat.md#chat-delete)
* [Chat Delete Scheduled Message](../../doc/controllers/chat.md#chat-delete-scheduled-message)
* [Chat Get Permalink](../../doc/controllers/chat.md#chat-get-permalink)
* [Chat Me Message](../../doc/controllers/chat.md#chat-me-message)
* [Chat Post Ephemeral](../../doc/controllers/chat.md#chat-post-ephemeral)
* [Chat Post Message](../../doc/controllers/chat.md#chat-post-message)
* [Chat Schedule Message](../../doc/controllers/chat.md#chat-schedule-message)
* [Chat Unfurl](../../doc/controllers/chat.md#chat-unfurl)
* [Chat Update](../../doc/controllers/chat.md#chat-update)


# Chat Delete

Deletes a message.

API method documentation: [https://api.slack.com/methods/chat.delete](https://api.slack.com/methods/chat.delete)

```csharp
ChatDeleteAsync(
    string token = null,
    double? ts = null,
    string channel = null,
    bool? asUser = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `chat:write` |
| `ts` | `double?` | Form, Optional | Timestamp of the message to be deleted. |
| `channel` | `string` | Form, Optional | Channel containing the message to be deleted. |
| `asUser` | `bool?` | Form, Optional | Pass true to delete the message as the authed user with `chat:write:user` scope. [Bot users](/bot-users) in this context are considered authed users. If unused or false, the message will be deleted with `chat:write:bot` scope. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ChatDeleteSuccessSchema](../../doc/models/chat-delete-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ChatDeleteSuccessSchema> result = await chatController.ChatDeleteAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ChatDeleteErrorSchemaException)
    {
       // TODO: Handle ChatDeleteErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ChatDeleteErrorSchemaException`](../../doc/models/chat-delete-error-schema-exception.md) |


# Chat Delete Scheduled Message

Deletes a pending scheduled message from the queue.

API method documentation: [https://api.slack.com/methods/chat.deleteScheduledMessage](https://api.slack.com/methods/chat.deleteScheduledMessage)

```csharp
ChatDeleteScheduledMessageAsync(
    string token,
    string channel,
    string scheduledMessageId,
    bool? asUser = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `string` | Form, Required | The channel the scheduled_message is posting to |
| `scheduledMessageId` | `string` | Form, Required | `scheduled_message_id` returned from call to chat.scheduleMessage |
| `asUser` | `bool?` | Form, Optional | Pass true to delete the message as the authed user with `chat:write:user` scope. [Bot users](/bot-users) in this context are considered authed users. If unused or false, the message will be deleted with `chat:write:bot` scope. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ChatDeleteScheduledMessageSchema](../../doc/models/chat-delete-scheduled-message-schema.md).

## Example Usage

```csharp
string token = "token6";
string channel = "channel4";
string scheduledMessageId = "scheduled_message_id8";
try
{
    ApiResponse<ChatDeleteScheduledMessageSchema> result = await chatController.ChatDeleteScheduledMessageAsync(
        token,
        channel,
        scheduledMessageId
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ChatDeleteScheduledMessageErrorSchemaException)
    {
       // TODO: Handle ChatDeleteScheduledMessageErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response if no message is found | [`ChatDeleteScheduledMessageErrorSchemaException`](../../doc/models/chat-delete-scheduled-message-error-schema-exception.md) |


# Chat Get Permalink

Retrieve a permalink URL for a specific extant message

API method documentation: [https://api.slack.com/methods/chat.getPermalink](https://api.slack.com/methods/chat.getPermalink)

```csharp
ChatGetPermalinkAsync(
    string token,
    string channel,
    string messageTs)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `none` |
| `channel` | `string` | Query, Required | The ID of the conversation or channel containing the message |
| `messageTs` | `string` | Query, Required | A message's `ts` value, uniquely identifying it within a channel |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ChatGetPermalinkSuccessSchema](../../doc/models/chat-get-permalink-success-schema.md).

## Example Usage

```csharp
string token = "token6";
string channel = "channel4";
string messageTs = "message_ts4";
try
{
    ApiResponse<ChatGetPermalinkSuccessSchema> result = await chatController.ChatGetPermalinkAsync(
        token,
        channel,
        messageTs
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ChatGetPermalinkErrorSchemaException)
    {
       // TODO: Handle ChatGetPermalinkErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Error response when channel cannot be found | [`ChatGetPermalinkErrorSchemaException`](../../doc/models/chat-get-permalink-error-schema-exception.md) |


# Chat Me Message

Share a me message into a channel.

API method documentation: [https://api.slack.com/methods/chat.meMessage](https://api.slack.com/methods/chat.meMessage)

```csharp
ChatMeMessageAsync(
    string token = null,
    string channel = null,
    string text = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `chat:write` |
| `channel` | `string` | Form, Optional | Channel to send message to. Can be a public channel, private group or IM channel. Can be an encoded ID, or a name. |
| `text` | `string` | Form, Optional | Text of the message to send. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ChatMeMessageSchema](../../doc/models/chat-me-message-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ChatMeMessageSchema> result = await chatController.ChatMeMessageAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ChatMeMessageErrorSchemaException)
    {
       // TODO: Handle ChatMeMessageErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ChatMeMessageErrorSchemaException`](../../doc/models/chat-me-message-error-schema-exception.md) |


# Chat Post Ephemeral

Sends an ephemeral message to a user in a channel.

API method documentation: [https://api.slack.com/methods/chat.postEphemeral](https://api.slack.com/methods/chat.postEphemeral)

```csharp
ChatPostEphemeralAsync(
    string token,
    string channel,
    string user,
    bool? asUser = null,
    string attachments = null,
    string blocks = null,
    string iconEmoji = null,
    string iconUrl = null,
    bool? linkNames = null,
    string parse = null,
    string text = null,
    string threadTs = null,
    string username = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `string` | Form, Required | Channel, private group, or IM channel to send message to. Can be an encoded ID, or a name. |
| `user` | `string` | Form, Required | `id` of the user who will receive the ephemeral message. The user should be in the channel specified by the `channel` argument. |
| `asUser` | `bool?` | Form, Optional | Pass true to post the message as the authed user. Defaults to true if the chat:write:bot scope is not included. Otherwise, defaults to false. |
| `attachments` | `string` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. |
| `blocks` | `string` | Form, Optional | A JSON-based array of structured blocks, presented as a URL-encoded string. |
| `iconEmoji` | `string` | Form, Optional | Emoji to use as the icon for this message. Overrides `icon_url`. Must be used in conjunction with `as_user` set to `false`, otherwise ignored. See [authorship](#authorship) below. |
| `iconUrl` | `string` | Form, Optional | URL to an image to use as the icon for this message. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |
| `linkNames` | `bool?` | Form, Optional | Find and link channel names and usernames. |
| `parse` | `string` | Form, Optional | Change how messages are treated. Defaults to `none`. See [below](#formatting). |
| `text` | `string` | Form, Optional | How this field works and whether it is required depends on other fields you use in your API call. [See below](#text_usage) for more detail. |
| `threadTs` | `string` | Form, Optional | Provide another message's `ts` value to post this message in a thread. Avoid using a reply's `ts` value; use its parent's value instead. Ephemeral messages in threads are only shown if there is already an active thread. |
| `username` | `string` | Form, Optional | Set your bot's user name. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ChatPostEphemeralSuccessSchema](../../doc/models/chat-post-ephemeral-success-schema.md).

## Example Usage

```csharp
string token = "token6";
string channel = "channel4";
string user = "user0";
try
{
    ApiResponse<ChatPostEphemeralSuccessSchema> result = await chatController.ChatPostEphemeralAsync(
        token,
        channel,
        user
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ChatPostEphemeralErrorSchemaException)
    {
       // TODO: Handle ChatPostEphemeralErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ChatPostEphemeralErrorSchemaException`](../../doc/models/chat-post-ephemeral-error-schema-exception.md) |


# Chat Post Message

Sends a message to a channel.

API method documentation: [https://api.slack.com/methods/chat.postMessage](https://api.slack.com/methods/chat.postMessage)

```csharp
ChatPostMessageAsync(
    string token,
    string channel,
    string asUser = null,
    string attachments = null,
    string blocks = null,
    string iconEmoji = null,
    string iconUrl = null,
    bool? linkNames = null,
    bool? mrkdwn = null,
    string parse = null,
    bool? replyBroadcast = null,
    string text = null,
    string threadTs = null,
    bool? unfurlLinks = null,
    bool? unfurlMedia = null,
    string username = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `string` | Form, Required | Channel, private group, or IM channel to send message to. Can be an encoded ID, or a name. See [below](#channels) for more details. |
| `asUser` | `string` | Form, Optional | Pass true to post the message as the authed user, instead of as a bot. Defaults to false. See [authorship](#authorship) below. |
| `attachments` | `string` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. |
| `blocks` | `string` | Form, Optional | A JSON-based array of structured blocks, presented as a URL-encoded string. |
| `iconEmoji` | `string` | Form, Optional | Emoji to use as the icon for this message. Overrides `icon_url`. Must be used in conjunction with `as_user` set to `false`, otherwise ignored. See [authorship](#authorship) below. |
| `iconUrl` | `string` | Form, Optional | URL to an image to use as the icon for this message. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |
| `linkNames` | `bool?` | Form, Optional | Find and link channel names and usernames. |
| `mrkdwn` | `bool?` | Form, Optional | Disable Slack markup parsing by setting to `false`. Enabled by default. |
| `parse` | `string` | Form, Optional | Change how messages are treated. Defaults to `none`. See [below](#formatting). |
| `replyBroadcast` | `bool?` | Form, Optional | Used in conjunction with `thread_ts` and indicates whether reply should be made visible to everyone in the channel or conversation. Defaults to `false`. |
| `text` | `string` | Form, Optional | How this field works and whether it is required depends on other fields you use in your API call. [See below](#text_usage) for more detail. |
| `threadTs` | `string` | Form, Optional | Provide another message's `ts` value to make this message a reply. Avoid using a reply's `ts` value; use its parent instead. |
| `unfurlLinks` | `bool?` | Form, Optional | Pass true to enable unfurling of primarily text-based content. |
| `unfurlMedia` | `bool?` | Form, Optional | Pass false to disable unfurling of media content. |
| `username` | `string` | Form, Optional | Set your bot's user name. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ChatPostMessageSuccessSchema](../../doc/models/chat-post-message-success-schema.md).

## Example Usage

```csharp
string token = "token6";
string channel = "channel4";
try
{
    ApiResponse<ChatPostMessageSuccessSchema> result = await chatController.ChatPostMessageAsync(
        token,
        channel
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ChatPostMessageErrorSchemaException)
    {
       // TODO: Handle ChatPostMessageErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response if too many attachments are included | [`ChatPostMessageErrorSchemaException`](../../doc/models/chat-post-message-error-schema-exception.md) |


# Chat Schedule Message

Schedules a message to be sent to a channel.

API method documentation: [https://api.slack.com/methods/chat.scheduleMessage](https://api.slack.com/methods/chat.scheduleMessage)

```csharp
ChatScheduleMessageAsync(
    string token = null,
    string channel = null,
    string text = null,
    string postAt = null,
    string parse = null,
    bool? asUser = null,
    bool? linkNames = null,
    string attachments = null,
    string blocks = null,
    bool? unfurlLinks = null,
    bool? unfurlMedia = null,
    double? threadTs = null,
    bool? replyBroadcast = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `chat:write` |
| `channel` | `string` | Form, Optional | Channel, private group, or DM channel to send message to. Can be an encoded ID, or a name. See [below](#channels) for more details. |
| `text` | `string` | Form, Optional | How this field works and whether it is required depends on other fields you use in your API call. [See below](#text_usage) for more detail. |
| `postAt` | `string` | Form, Optional | Unix EPOCH timestamp of time in future to send the message. |
| `parse` | `string` | Form, Optional | Change how messages are treated. Defaults to `none`. See [chat.postMessage](chat.postMessage#formatting). |
| `asUser` | `bool?` | Form, Optional | Pass true to post the message as the authed user, instead of as a bot. Defaults to false. See [chat.postMessage](chat.postMessage#authorship). |
| `linkNames` | `bool?` | Form, Optional | Find and link channel names and usernames. |
| `attachments` | `string` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. |
| `blocks` | `string` | Form, Optional | A JSON-based array of structured blocks, presented as a URL-encoded string. |
| `unfurlLinks` | `bool?` | Form, Optional | Pass true to enable unfurling of primarily text-based content. |
| `unfurlMedia` | `bool?` | Form, Optional | Pass false to disable unfurling of media content. |
| `threadTs` | `double?` | Form, Optional | Provide another message's `ts` value to make this message a reply. Avoid using a reply's `ts` value; use its parent instead. |
| `replyBroadcast` | `bool?` | Form, Optional | Used in conjunction with `thread_ts` and indicates whether reply should be made visible to everyone in the channel or conversation. Defaults to `false`. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ChatScheduleMessageSuccessSchema](../../doc/models/chat-schedule-message-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ChatScheduleMessageSuccessSchema> result = await chatController.ChatScheduleMessageAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ChatScheduleMessageErrorSchemaException)
    {
       // TODO: Handle ChatScheduleMessageErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response if the `post_at` is invalid (ex. in the past or too far into the future) | [`ChatScheduleMessageErrorSchemaException`](../../doc/models/chat-schedule-message-error-schema-exception.md) |


# Chat Unfurl

Provide custom unfurl behavior for user-posted URLs

API method documentation: [https://api.slack.com/methods/chat.unfurl](https://api.slack.com/methods/chat.unfurl)

```csharp
ChatUnfurlAsync(
    string token,
    string channel,
    string ts,
    string unfurls = null,
    string userAuthMessage = null,
    bool? userAuthRequired = null,
    string userAuthUrl = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `links:write` |
| `channel` | `string` | Form, Required | Channel ID of the message |
| `ts` | `string` | Form, Required | Timestamp of the message to add unfurl behavior to. |
| `unfurls` | `string` | Form, Optional | URL-encoded JSON map with keys set to URLs featured in the the message, pointing to their unfurl blocks or message attachments. |
| `userAuthMessage` | `string` | Form, Optional | Provide a simply-formatted string to send as an ephemeral message to the user as invitation to authenticate further and enable full unfurling behavior |
| `userAuthRequired` | `bool?` | Form, Optional | Set to `true` or `1` to indicate the user must install your Slack app to trigger unfurls for this domain |
| `userAuthUrl` | `string` | Form, Optional | Send users to this custom URL where they will complete authentication in your app to fully trigger unfurling. Value should be properly URL-encoded. |

## Requires scope

### slackAuth

`links:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ChatUnfurlSuccessSchema](../../doc/models/chat-unfurl-success-schema.md).

## Example Usage

```csharp
string token = "token6";
string channel = "channel4";
string ts = "ts2";
try
{
    ApiResponse<ChatUnfurlSuccessSchema> result = await chatController.ChatUnfurlAsync(
        token,
        channel,
        ts
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ChatUnfurlErrorSchemaException)
    {
       // TODO: Handle ChatUnfurlErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ChatUnfurlErrorSchemaException`](../../doc/models/chat-unfurl-error-schema-exception.md) |


# Chat Update

Updates a message.

API method documentation: [https://api.slack.com/methods/chat.update](https://api.slack.com/methods/chat.update)

```csharp
ChatUpdateAsync(
    string token,
    string channel,
    string ts,
    string asUser = null,
    string attachments = null,
    string blocks = null,
    string linkNames = null,
    string parse = null,
    string text = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `string` | Form, Required | Channel containing the message to be updated. |
| `ts` | `string` | Form, Required | Timestamp of the message to be updated. |
| `asUser` | `string` | Form, Optional | Pass true to update the message as the authed user. [Bot users](/bot-users) in this context are considered authed users. |
| `attachments` | `string` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. This field is required when not presenting `text`. If you don't include this field, the message's previous `attachments` will be retained. To remove previous `attachments`, include an empty array for this field. |
| `blocks` | `string` | Form, Optional | A JSON-based array of [structured blocks](/block-kit/building), presented as a URL-encoded string. If you don't include this field, the message's previous `blocks` will be retained. To remove previous `blocks`, include an empty array for this field. |
| `linkNames` | `string` | Form, Optional | Find and link channel names and usernames. Defaults to `none`. If you do not specify a value for this field, the original value set for the message will be overwritten with the default, `none`. |
| `parse` | `string` | Form, Optional | Change how messages are treated. Defaults to `client`, unlike `chat.postMessage`. Accepts either `none` or `full`. If you do not specify a value for this field, the original value set for the message will be overwritten with the default, `client`. |
| `text` | `string` | Form, Optional | New text for the message, using the [default formatting rules](/reference/surfaces/formatting). It's not required when presenting `blocks` or `attachments`. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ChatUpdateSuccessSchema](../../doc/models/chat-update-success-schema.md).

## Example Usage

```csharp
string token = "token6";
string channel = "channel4";
string ts = "ts2";
try
{
    ApiResponse<ChatUpdateSuccessSchema> result = await chatController.ChatUpdateAsync(
        token,
        channel,
        ts
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ChatUpdateErrorSchemaException)
    {
       // TODO: Handle ChatUpdateErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ChatUpdateErrorSchemaException`](../../doc/models/chat-update-error-schema-exception.md) |

