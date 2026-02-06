# Conversations

```csharp
ConversationsController conversationsController = client.ConversationsController;
```

## Class Name

`ConversationsController`

## Methods

* [Conversations Archive](../../doc/controllers/conversations.md#conversations-archive)
* [Conversations Close](../../doc/controllers/conversations.md#conversations-close)
* [Conversations Create](../../doc/controllers/conversations.md#conversations-create)
* [Conversations History](../../doc/controllers/conversations.md#conversations-history)
* [Conversations Info](../../doc/controllers/conversations.md#conversations-info)
* [Conversations Invite](../../doc/controllers/conversations.md#conversations-invite)
* [Conversations Join](../../doc/controllers/conversations.md#conversations-join)
* [Conversations Kick](../../doc/controllers/conversations.md#conversations-kick)
* [Conversations Leave](../../doc/controllers/conversations.md#conversations-leave)
* [Conversations List](../../doc/controllers/conversations.md#conversations-list)
* [Conversations Mark](../../doc/controllers/conversations.md#conversations-mark)
* [Conversations Members](../../doc/controllers/conversations.md#conversations-members)
* [Conversations Open](../../doc/controllers/conversations.md#conversations-open)
* [Conversations Rename](../../doc/controllers/conversations.md#conversations-rename)
* [Conversations Replies](../../doc/controllers/conversations.md#conversations-replies)
* [Conversations Set Purpose](../../doc/controllers/conversations.md#conversations-set-purpose)
* [Conversations Set Topic](../../doc/controllers/conversations.md#conversations-set-topic)
* [Conversations Unarchive](../../doc/controllers/conversations.md#conversations-unarchive)


# Conversations Archive

Archives a conversation.

API method documentation: [https://api.slack.com/methods/conversations.archive](https://api.slack.com/methods/conversations.archive)

```csharp
ConversationsArchiveAsync(
    string token = null,
    string channel = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string` | Form, Optional | ID of conversation to archive |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsArchiveSuccessSchema](../../doc/models/conversations-archive-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsArchiveSuccessSchema> result = await conversationsController.ConversationsArchiveAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsArchiveErrorSchemaException)
    {
       // TODO: Handle ConversationsArchiveErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsArchiveErrorSchemaException`](../../doc/models/conversations-archive-error-schema-exception.md) |


# Conversations Close

Closes a direct message or multi-person direct message.

API method documentation: [https://api.slack.com/methods/conversations.close](https://api.slack.com/methods/conversations.close)

```csharp
ConversationsCloseAsync(
    string token = null,
    string channel = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string` | Form, Optional | Conversation to close. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsCloseSuccessSchema](../../doc/models/conversations-close-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsCloseSuccessSchema> result = await conversationsController.ConversationsCloseAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsCloseErrorSchemaException)
    {
       // TODO: Handle ConversationsCloseErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsCloseErrorSchemaException`](../../doc/models/conversations-close-error-schema-exception.md) |


# Conversations Create

Initiates a public or private channel-based conversation

API method documentation: [https://api.slack.com/methods/conversations.create](https://api.slack.com/methods/conversations.create)

```csharp
ConversationsCreateAsync(
    string token = null,
    string name = null,
    bool? isPrivate = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `name` | `string` | Form, Optional | Name of the public or private channel to create |
| `isPrivate` | `bool?` | Form, Optional | Create a private channel instead of a public one |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsCreateSuccessSchema](../../doc/models/conversations-create-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsCreateSuccessSchema> result = await conversationsController.ConversationsCreateAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsCreateErrorSchemaException)
    {
       // TODO: Handle ConversationsCreateErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when name already in use | [`ConversationsCreateErrorSchemaException`](../../doc/models/conversations-create-error-schema-exception.md) |


# Conversations History

Fetches a conversation's history of messages and events.

API method documentation: [https://api.slack.com/methods/conversations.history](https://api.slack.com/methods/conversations.history)

```csharp
ConversationsHistoryAsync(
    string token = null,
    string channel = null,
    double? latest = null,
    double? oldest = null,
    bool? inclusive = null,
    int? limit = null,
    string cursor = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `conversations:history` |
| `channel` | `string` | Query, Optional | Conversation ID to fetch history for. |
| `latest` | `double?` | Query, Optional | End of time range of messages to include in results. |
| `oldest` | `double?` | Query, Optional | Start of time range of messages to include in results. |
| `inclusive` | `bool?` | Query, Optional | Include messages with latest or oldest timestamp in results only when either timestamp is specified. |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. |
| `cursor` | `string` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |

## Requires scope

### slackAuth

`channels:history`, `groups:history`, `im:history`, `mpim:history`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsHistorySuccessSchema](../../doc/models/conversations-history-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsHistorySuccessSchema> result = await conversationsController.ConversationsHistoryAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsHistoryErrorSchemaException)
    {
       // TODO: Handle ConversationsHistoryErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsHistoryErrorSchemaException`](../../doc/models/conversations-history-error-schema-exception.md) |


# Conversations Info

Retrieve information about a conversation.

API method documentation: [https://api.slack.com/methods/conversations.info](https://api.slack.com/methods/conversations.info)

```csharp
ConversationsInfoAsync(
    string token = null,
    string channel = null,
    bool? includeLocale = null,
    bool? includeNumMembers = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `channel` | `string` | Query, Optional | Conversation ID to learn more about |
| `includeLocale` | `bool?` | Query, Optional | Set this to `true` to receive the locale for this conversation. Defaults to `false` |
| `includeNumMembers` | `bool?` | Query, Optional | Set to `true` to include the member count for the specified conversation. Defaults to `false` |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsInfoSuccessSchema](../../doc/models/conversations-info-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsInfoSuccessSchema> result = await conversationsController.ConversationsInfoAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsInfoErrorSchemaException)
    {
       // TODO: Handle ConversationsInfoErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when a channel cannot be found | [`ConversationsInfoErrorSchemaException`](../../doc/models/conversations-info-error-schema-exception.md) |


# Conversations Invite

Invites users to a channel.

API method documentation: [https://api.slack.com/methods/conversations.invite](https://api.slack.com/methods/conversations.invite)

```csharp
ConversationsInviteAsync(
    string token = null,
    string channel = null,
    string users = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string` | Form, Optional | The ID of the public or private channel to invite user(s) to. |
| `users` | `string` | Form, Optional | A comma separated list of user IDs. Up to 1000 users may be listed. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsInviteErrorSchema](../../doc/models/conversations-invite-error-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsInviteErrorSchema> result = await conversationsController.ConversationsInviteAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsInviteErrorSchema1Exception)
    {
       // TODO: Handle ConversationsInviteErrorSchema1Exception exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when an invite is attempted on a conversation type that does not support it | [`ConversationsInviteErrorSchema1Exception`](../../doc/models/conversations-invite-error-schema-1-exception.md) |


# Conversations Join

Joins an existing conversation.

API method documentation: [https://api.slack.com/methods/conversations.join](https://api.slack.com/methods/conversations.join)

```csharp
ConversationsJoinAsync(
    string token = null,
    string channel = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `channels:write` |
| `channel` | `string` | Form, Optional | ID of conversation to join |

## Requires scope

### slackAuth

`channels:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsJoinSuccessSchema](../../doc/models/conversations-join-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsJoinSuccessSchema> result = await conversationsController.ConversationsJoinAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsJoinErrorSchemaException)
    {
       // TODO: Handle ConversationsJoinErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response if the conversation is archived and cannot be joined | [`ConversationsJoinErrorSchemaException`](../../doc/models/conversations-join-error-schema-exception.md) |


# Conversations Kick

Removes a user from a conversation.

API method documentation: [https://api.slack.com/methods/conversations.kick](https://api.slack.com/methods/conversations.kick)

```csharp
ConversationsKickAsync(
    string token = null,
    string channel = null,
    string user = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string` | Form, Optional | ID of conversation to remove user from. |
| `user` | `string` | Form, Optional | User ID to be removed. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsKickSuccessSchema](../../doc/models/conversations-kick-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsKickSuccessSchema> result = await conversationsController.ConversationsKickAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsKickErrorSchemaException)
    {
       // TODO: Handle ConversationsKickErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when you attempt to kick yourself from a channel | [`ConversationsKickErrorSchemaException`](../../doc/models/conversations-kick-error-schema-exception.md) |


# Conversations Leave

Leaves a conversation.

API method documentation: [https://api.slack.com/methods/conversations.leave](https://api.slack.com/methods/conversations.leave)

```csharp
ConversationsLeaveAsync(
    string token = null,
    string channel = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string` | Form, Optional | Conversation to leave |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsLeaveSuccessSchema](../../doc/models/conversations-leave-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsLeaveSuccessSchema> result = await conversationsController.ConversationsLeaveAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsLeaveErrorSchemaException)
    {
       // TODO: Handle ConversationsLeaveErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when attempting to leave a workspace's "general" channel | [`ConversationsLeaveErrorSchemaException`](../../doc/models/conversations-leave-error-schema-exception.md) |


# Conversations List

Lists all channels in a Slack team.

API method documentation: [https://api.slack.com/methods/conversations.list](https://api.slack.com/methods/conversations.list)

```csharp
ConversationsListAsync(
    string token = null,
    bool? excludeArchived = null,
    string types = null,
    int? limit = null,
    string cursor = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `excludeArchived` | `bool?` | Query, Optional | Set to `true` to exclude archived channels from the list |
| `types` | `string` | Query, Optional | Mix and match channel types by providing a comma-separated list of any combination of `public_channel`, `private_channel`, `mpim`, `im` |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. Must be an integer no larger than 1000. |
| `cursor` | `string` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsListSuccessSchema](../../doc/models/conversations-list-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsListSuccessSchema> result = await conversationsController.ConversationsListAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsListErrorSchemaException)
    {
       // TODO: Handle ConversationsListErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsListErrorSchemaException`](../../doc/models/conversations-list-error-schema-exception.md) |


# Conversations Mark

Sets the read cursor in a channel.

API method documentation: [https://api.slack.com/methods/conversations.mark](https://api.slack.com/methods/conversations.mark)

```csharp
ConversationsMarkAsync(
    string token = null,
    string channel = null,
    double? ts = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string` | Form, Optional | Channel or conversation to set the read cursor for. |
| `ts` | `double?` | Form, Optional | Unique identifier of message you want marked as most recently seen in this conversation. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsMarkSuccessSchema](../../doc/models/conversations-mark-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsMarkSuccessSchema> result = await conversationsController.ConversationsMarkAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsMarkErrorSchemaException)
    {
       // TODO: Handle ConversationsMarkErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsMarkErrorSchemaException`](../../doc/models/conversations-mark-error-schema-exception.md) |


# Conversations Members

Retrieve members of a conversation.

API method documentation: [https://api.slack.com/methods/conversations.members](https://api.slack.com/methods/conversations.members)

```csharp
ConversationsMembersAsync(
    string token = null,
    string channel = null,
    int? limit = null,
    string cursor = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `channel` | `string` | Query, Optional | ID of the conversation to retrieve members for |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. |
| `cursor` | `string` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsMembersSuccessSchema](../../doc/models/conversations-members-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsMembersSuccessSchema> result = await conversationsController.ConversationsMembersAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsMembersErrorSchemaException)
    {
       // TODO: Handle ConversationsMembersErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when an invalid cursor is provided | [`ConversationsMembersErrorSchemaException`](../../doc/models/conversations-members-error-schema-exception.md) |


# Conversations Open

Opens or resumes a direct message or multi-person direct message.

API method documentation: [https://api.slack.com/methods/conversations.open](https://api.slack.com/methods/conversations.open)

```csharp
ConversationsOpenAsync(
    string token = null,
    string channel = null,
    string users = null,
    bool? returnIm = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string` | Form, Optional | Resume a conversation by supplying an `im` or `mpim`'s ID. Or provide the `users` field instead. |
| `users` | `string` | Form, Optional | Comma separated lists of users. If only one user is included, this creates a 1:1 DM.  The ordering of the users is preserved whenever a multi-person direct message is returned. Supply a `channel` when not supplying `users`. |
| `returnIm` | `bool?` | Form, Optional | Boolean, indicates you want the full IM channel definition in the response. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsOpenSuccessSchema](../../doc/models/conversations-open-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsOpenSuccessSchema> result = await conversationsController.ConversationsOpenAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsOpenErrorSchemaException)
    {
       // TODO: Handle ConversationsOpenErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsOpenErrorSchemaException`](../../doc/models/conversations-open-error-schema-exception.md) |


# Conversations Rename

Renames a conversation.

API method documentation: [https://api.slack.com/methods/conversations.rename](https://api.slack.com/methods/conversations.rename)

```csharp
ConversationsRenameAsync(
    string token = null,
    string channel = null,
    string name = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string` | Form, Optional | ID of conversation to rename |
| `name` | `string` | Form, Optional | New name for conversation. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsRenameSuccessSchema](../../doc/models/conversations-rename-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsRenameSuccessSchema> result = await conversationsController.ConversationsRenameAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsRenameErrorSchemaException)
    {
       // TODO: Handle ConversationsRenameErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when the calling user is not a member of the conversation | [`ConversationsRenameErrorSchemaException`](../../doc/models/conversations-rename-error-schema-exception.md) |


# Conversations Replies

Retrieve a thread of messages posted to a conversation

API method documentation: [https://api.slack.com/methods/conversations.replies](https://api.slack.com/methods/conversations.replies)

```csharp
ConversationsRepliesAsync(
    string token = null,
    string channel = null,
    double? ts = null,
    double? latest = null,
    double? oldest = null,
    bool? inclusive = null,
    int? limit = null,
    string cursor = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `conversations:history` |
| `channel` | `string` | Query, Optional | Conversation ID to fetch thread from. |
| `ts` | `double?` | Query, Optional | Unique identifier of a thread's parent message. `ts` must be the timestamp of an existing message with 0 or more replies. If there are no replies then just the single message referenced by `ts` will return - it is just an ordinary, unthreaded message. |
| `latest` | `double?` | Query, Optional | End of time range of messages to include in results. |
| `oldest` | `double?` | Query, Optional | Start of time range of messages to include in results. |
| `inclusive` | `bool?` | Query, Optional | Include messages with latest or oldest timestamp in results only when either timestamp is specified. |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. |
| `cursor` | `string` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |

## Requires scope

### slackAuth

`channels:history`, `groups:history`, `im:history`, `mpim:history`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsRepliesSuccessSchema](../../doc/models/conversations-replies-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsRepliesSuccessSchema> result = await conversationsController.ConversationsRepliesAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsRepliesErrorSchemaException)
    {
       // TODO: Handle ConversationsRepliesErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsRepliesErrorSchemaException`](../../doc/models/conversations-replies-error-schema-exception.md) |


# Conversations Set Purpose

Sets the purpose for a conversation.

API method documentation: [https://api.slack.com/methods/conversations.setPurpose](https://api.slack.com/methods/conversations.setPurpose)

```csharp
ConversationsSetPurposeAsync(
    string token = null,
    string channel = null,
    string purpose = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string` | Form, Optional | Conversation to set the purpose of |
| `purpose` | `string` | Form, Optional | A new, specialer purpose |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsSetPurposeSuccessSchema](../../doc/models/conversations-set-purpose-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsSetPurposeSuccessSchema> result = await conversationsController.ConversationsSetPurposeAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsSetPurposeErrorSchemaException)
    {
       // TODO: Handle ConversationsSetPurposeErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsSetPurposeErrorSchemaException`](../../doc/models/conversations-set-purpose-error-schema-exception.md) |


# Conversations Set Topic

Sets the topic for a conversation.

API method documentation: [https://api.slack.com/methods/conversations.setTopic](https://api.slack.com/methods/conversations.setTopic)

```csharp
ConversationsSetTopicAsync(
    string token = null,
    string channel = null,
    string topic = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string` | Form, Optional | Conversation to set the topic of |
| `topic` | `string` | Form, Optional | The new topic string. Does not support formatting or linkification. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsSetTopicSuccessSchema](../../doc/models/conversations-set-topic-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsSetTopicSuccessSchema> result = await conversationsController.ConversationsSetTopicAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsSetTopicErrorSchemaException)
    {
       // TODO: Handle ConversationsSetTopicErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsSetTopicErrorSchemaException`](../../doc/models/conversations-set-topic-error-schema-exception.md) |


# Conversations Unarchive

Reverses conversation archival.

API method documentation: [https://api.slack.com/methods/conversations.unarchive](https://api.slack.com/methods/conversations.unarchive)

```csharp
ConversationsUnarchiveAsync(
    string token = null,
    string channel = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string` | Form, Optional | ID of conversation to unarchive |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ConversationsUnarchiveSuccessSchema](../../doc/models/conversations-unarchive-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ConversationsUnarchiveSuccessSchema> result = await conversationsController.ConversationsUnarchiveAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ConversationsUnarchiveErrorSchemaException)
    {
       // TODO: Handle ConversationsUnarchiveErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsUnarchiveErrorSchemaException`](../../doc/models/conversations-unarchive-error-schema-exception.md) |

