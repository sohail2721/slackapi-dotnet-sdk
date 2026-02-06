# Admin Conversations

```csharp
AdminConversationsController adminConversationsController = client.AdminConversationsController;
```

## Class Name

`AdminConversationsController`

## Methods

* [Admin Conversations Archive](../../doc/controllers/admin-conversations.md#admin-conversations-archive)
* [Admin Conversations Convert to Private](../../doc/controllers/admin-conversations.md#admin-conversations-convert-to-private)
* [Admin Conversations Create](../../doc/controllers/admin-conversations.md#admin-conversations-create)
* [Admin Conversations Delete](../../doc/controllers/admin-conversations.md#admin-conversations-delete)
* [Admin Conversations Disconnect Shared](../../doc/controllers/admin-conversations.md#admin-conversations-disconnect-shared)
* [Admin Conversations Get Conversation Prefs](../../doc/controllers/admin-conversations.md#admin-conversations-get-conversation-prefs)
* [Admin Conversations Get Teams](../../doc/controllers/admin-conversations.md#admin-conversations-get-teams)
* [Admin Conversations Invite](../../doc/controllers/admin-conversations.md#admin-conversations-invite)
* [Admin Conversations Rename](../../doc/controllers/admin-conversations.md#admin-conversations-rename)
* [Admin Conversations Search](../../doc/controllers/admin-conversations.md#admin-conversations-search)
* [Admin Conversations Set Conversation Prefs](../../doc/controllers/admin-conversations.md#admin-conversations-set-conversation-prefs)
* [Admin Conversations Set Teams](../../doc/controllers/admin-conversations.md#admin-conversations-set-teams)
* [Admin Conversations Unarchive](../../doc/controllers/admin-conversations.md#admin-conversations-unarchive)


# Admin Conversations Archive

Archive a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.archive](https://api.slack.com/methods/admin.conversations.archive)

```csharp
AdminConversationsArchiveAsync(
    string token,
    string channelId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The channel to archive. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AdminConversationsArchiveSchema](../../doc/models/admin-conversations-archive-schema.md).

## Example Usage

```csharp
string token = "token6";
string channelId = "channel_id4";
try
{
    ApiResponse<AdminConversationsArchiveSchema> result = await adminConversationsController.AdminConversationsArchiveAsync(
        token,
        channelId
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AdminConversationsArchiveErrorSchemaException)
    {
       // TODO: Handle AdminConversationsArchiveErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsArchiveErrorSchemaException`](../../doc/models/admin-conversations-archive-error-schema-exception.md) |


# Admin Conversations Convert to Private

Convert a public channel to a private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.convertToPrivate](https://api.slack.com/methods/admin.conversations.convertToPrivate)

```csharp
AdminConversationsConvertToPrivateAsync(
    string token,
    string channelId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The channel to convert to private. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AdminConversationsConvertToPrivateSchema](../../doc/models/admin-conversations-convert-to-private-schema.md).

## Example Usage

```csharp
string token = "token6";
string channelId = "channel_id4";
try
{
    ApiResponse<AdminConversationsConvertToPrivateSchema> result = await adminConversationsController.AdminConversationsConvertToPrivateAsync(
        token,
        channelId
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AdminConversationsConvertToPrivateErrorSchemaException)
    {
       // TODO: Handle AdminConversationsConvertToPrivateErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsConvertToPrivateErrorSchemaException`](../../doc/models/admin-conversations-convert-to-private-error-schema-exception.md) |


# Admin Conversations Create

Create a public or private channel-based conversation.

API method documentation: [https://api.slack.com/methods/admin.conversations.create](https://api.slack.com/methods/admin.conversations.create)

```csharp
AdminConversationsCreateAsync(
    string token,
    string name,
    bool isPrivate,
    string description = null,
    bool? orgWide = null,
    string teamId = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `name` | `string` | Form, Required | Name of the public or private channel to create. |
| `isPrivate` | `bool` | Form, Required | When `true`, creates a private channel instead of a public channel |
| `description` | `string` | Form, Optional | Description of the public or private channel to create. |
| `orgWide` | `bool?` | Form, Optional | When `true`, the channel will be available org-wide. Note: if the channel is not `org_wide=true`, you must specify a `team_id` for this channel |
| `teamId` | `string` | Form, Optional | The workspace to create the channel in. Note: this argument is required unless you set `org_wide=true`. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AdminConversationsCreateSchema](../../doc/models/admin-conversations-create-schema.md).

## Example Usage

```csharp
string token = "token6";
string name = "name0";
bool isPrivate = false;
try
{
    ApiResponse<AdminConversationsCreateSchema> result = await adminConversationsController.AdminConversationsCreateAsync(
        token,
        name,
        isPrivate
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AdminConversationsCreateErrorSchemaException)
    {
       // TODO: Handle AdminConversationsCreateErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsCreateErrorSchemaException`](../../doc/models/admin-conversations-create-error-schema-exception.md) |


# Admin Conversations Delete

Delete a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.delete](https://api.slack.com/methods/admin.conversations.delete)

```csharp
AdminConversationsDeleteAsync(
    string token,
    string channelId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The channel to delete. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AdminConversationsDeleteSchema](../../doc/models/admin-conversations-delete-schema.md).

## Example Usage

```csharp
string token = "token6";
string channelId = "channel_id4";
try
{
    ApiResponse<AdminConversationsDeleteSchema> result = await adminConversationsController.AdminConversationsDeleteAsync(
        token,
        channelId
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AdminConversationsDeleteErrorSchemaException)
    {
       // TODO: Handle AdminConversationsDeleteErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsDeleteErrorSchemaException`](../../doc/models/admin-conversations-delete-error-schema-exception.md) |


# Admin Conversations Disconnect Shared

Disconnect a connected channel from one or more workspaces.

API method documentation: [https://api.slack.com/methods/admin.conversations.disconnectShared](https://api.slack.com/methods/admin.conversations.disconnectShared)

```csharp
AdminConversationsDisconnectSharedAsync(
    string token,
    string channelId,
    string leavingTeamIds = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The channel to be disconnected from some workspaces. |
| `leavingTeamIds` | `string` | Form, Optional | The team to be removed from the channel. Currently only a single team id can be specified. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AdminConversationsRenameSchema](../../doc/models/admin-conversations-rename-schema.md).

## Example Usage

```csharp
string token = "token6";
string channelId = "channel_id4";
try
{
    ApiResponse<AdminConversationsRenameSchema> result = await adminConversationsController.AdminConversationsDisconnectSharedAsync(
        token,
        channelId
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AdminConversationsDisconnectSharedErrorSchemaException)
    {
       // TODO: Handle AdminConversationsDisconnectSharedErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsDisconnectSharedErrorSchemaException`](../../doc/models/admin-conversations-disconnect-shared-error-schema-exception.md) |


# Admin Conversations Get Conversation Prefs

Get conversation preferences for a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.getConversationPrefs](https://api.slack.com/methods/admin.conversations.getConversationPrefs)

```csharp
AdminConversationsGetConversationPrefsAsync(
    string token,
    string channelId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channelId` | `string` | Query, Required | The channel to get preferences for. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AdminConversationsGetConversationPrefsSchema](../../doc/models/admin-conversations-get-conversation-prefs-schema.md).

## Example Usage

```csharp
string token = "token6";
string channelId = "channel_id4";
try
{
    ApiResponse<AdminConversationsGetConversationPrefsSchema> result = await adminConversationsController.AdminConversationsGetConversationPrefsAsync(
        token,
        channelId
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AdminConversationsUnarchiveErrorSchemaException)
    {
       // TODO: Handle AdminConversationsUnarchiveErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsUnarchiveErrorSchemaException`](../../doc/models/admin-conversations-unarchive-error-schema-exception.md) |


# Admin Conversations Get Teams

Get all the workspaces a given public or private channel is connected to within this Enterprise org.

API method documentation: [https://api.slack.com/methods/admin.conversations.getTeams](https://api.slack.com/methods/admin.conversations.getTeams)

```csharp
AdminConversationsGetTeamsAsync(
    string token,
    string channelId,
    string cursor = null,
    int? limit = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channelId` | `string` | Query, Required | The channel to determine connected workspaces within the organization for. |
| `cursor` | `string` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AdminConversationsGetTeamsSchema](../../doc/models/admin-conversations-get-teams-schema.md).

## Example Usage

```csharp
string token = "token6";
string channelId = "channel_id4";
try
{
    ApiResponse<AdminConversationsGetTeamsSchema> result = await adminConversationsController.AdminConversationsGetTeamsAsync(
        token,
        channelId
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AdminConversationsGetTeamsErrorSchemaException)
    {
       // TODO: Handle AdminConversationsGetTeamsErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsGetTeamsErrorSchemaException`](../../doc/models/admin-conversations-get-teams-error-schema-exception.md) |


# Admin Conversations Invite

Invite a user to a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.invite](https://api.slack.com/methods/admin.conversations.invite)

```csharp
AdminConversationsInviteAsync(
    string token,
    string userIds,
    string channelId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `userIds` | `string` | Form, Required | The users to invite. |
| `channelId` | `string` | Form, Required | The channel that the users will be invited to. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AdminConversationsInviteSchema](../../doc/models/admin-conversations-invite-schema.md).

## Example Usage

```csharp
string token = "token6";
string userIds = "user_ids4";
string channelId = "channel_id4";
try
{
    ApiResponse<AdminConversationsInviteSchema> result = await adminConversationsController.AdminConversationsInviteAsync(
        token,
        userIds,
        channelId
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AdminConversationsInviteErrorSchemaException)
    {
       // TODO: Handle AdminConversationsInviteErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsInviteErrorSchemaException`](../../doc/models/admin-conversations-invite-error-schema-exception.md) |


# Admin Conversations Rename

Rename a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.rename](https://api.slack.com/methods/admin.conversations.rename)

```csharp
AdminConversationsRenameAsync(
    string token,
    string channelId,
    string name)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The channel to rename. |
| `name` | `string` | Form, Required | - |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AdminConversationsRenameSchema1](../../doc/models/admin-conversations-rename-schema-1.md).

## Example Usage

```csharp
string token = "token6";
string channelId = "channel_id4";
string name = "name0";
try
{
    ApiResponse<AdminConversationsRenameSchema1> result = await adminConversationsController.AdminConversationsRenameAsync(
        token,
        channelId,
        name
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AdminConversationsUnarchiveErrorSchema2Exception)
    {
       // TODO: Handle AdminConversationsUnarchiveErrorSchema2Exception exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsUnarchiveErrorSchema2Exception`](../../doc/models/admin-conversations-unarchive-error-schema-2-exception.md) |


# Admin Conversations Search

Search for public or private channels in an Enterprise organization.

API method documentation: [https://api.slack.com/methods/admin.conversations.search](https://api.slack.com/methods/admin.conversations.search)

```csharp
AdminConversationsSearchAsync(
    string token,
    string teamIds = null,
    string query = null,
    int? limit = null,
    string cursor = null,
    string searchChannelTypes = null,
    string sort = null,
    string sortDir = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `teamIds` | `string` | Query, Optional | Comma separated string of team IDs, signifying the workspaces to search through. |
| `query` | `string` | Query, Optional | Name of the the channel to query by. |
| `limit` | `int?` | Query, Optional | Maximum number of items to be returned. Must be between 1 - 20 both inclusive. Default is 10. |
| `cursor` | `string` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |
| `searchChannelTypes` | `string` | Query, Optional | The type of channel to include or exclude in the search. For example `private` will search private channels, while `private_exclude` will exclude them. For a full list of types, check the [Types section](#types). |
| `sort` | `string` | Query, Optional | Possible values are `relevant` (search ranking based on what we think is closest), `name` (alphabetical), `member_count` (number of users in the channel), and `created` (date channel was created). You can optionally pair this with the `sort_dir` arg to change how it is sorted |
| `sortDir` | `string` | Query, Optional | Sort direction. Possible values are `asc` for ascending order like (1, 2, 3) or (a, b, c), and `desc` for descending order like (3, 2, 1) or (c, b, a) |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AdminConversationsSearchSchema](../../doc/models/admin-conversations-search-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<AdminConversationsSearchSchema> result = await adminConversationsController.AdminConversationsSearchAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AdminConversationsSearchErrorSchemaException)
    {
       // TODO: Handle AdminConversationsSearchErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsSearchErrorSchemaException`](../../doc/models/admin-conversations-search-error-schema-exception.md) |


# Admin Conversations Set Conversation Prefs

Set the posting permissions for a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.setConversationPrefs](https://api.slack.com/methods/admin.conversations.setConversationPrefs)

```csharp
AdminConversationsSetConversationPrefsAsync(
    string token,
    string channelId,
    string prefs)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The channel to set the prefs for |
| `prefs` | `string` | Form, Required | The prefs for this channel in a stringified JSON format. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AdminConversationsSetConversationPrefsSchema](../../doc/models/admin-conversations-set-conversation-prefs-schema.md).

## Example Usage

```csharp
string token = "token6";
string channelId = "channel_id4";
string prefs = "prefs0";
try
{
    ApiResponse<AdminConversationsSetConversationPrefsSchema> result = await adminConversationsController.AdminConversationsSetConversationPrefsAsync(
        token,
        channelId,
        prefs
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AdminConversationsSetConversationPrefsErrorSchemaException)
    {
       // TODO: Handle AdminConversationsSetConversationPrefsErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsSetConversationPrefsErrorSchemaException`](../../doc/models/admin-conversations-set-conversation-prefs-error-schema-exception.md) |


# Admin Conversations Set Teams

Set the workspaces in an Enterprise grid org that connect to a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.setTeams](https://api.slack.com/methods/admin.conversations.setTeams)

```csharp
AdminConversationsSetTeamsAsync(
    string token,
    string channelId,
    string teamId = null,
    string targetTeamIds = null,
    bool? orgChannel = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The encoded `channel_id` to add or remove to workspaces. |
| `teamId` | `string` | Form, Optional | The workspace to which the channel belongs. Omit this argument if the channel is a cross-workspace shared channel. |
| `targetTeamIds` | `string` | Form, Optional | A comma-separated list of workspaces to which the channel should be shared. Not required if the channel is being shared org-wide. |
| `orgChannel` | `bool?` | Form, Optional | True if channel has to be converted to an org channel |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string channelId = "channel_id4";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminConversationsController.AdminConversationsSetTeamsAsync(
        token,
        channelId
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


# Admin Conversations Unarchive

Unarchive a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.unarchive](https://api.slack.com/methods/admin.conversations.unarchive)

```csharp
AdminConversationsUnarchiveAsync(
    string token,
    string channelId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The channel to unarchive. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AdminConversationsUnarchiveSchema](../../doc/models/admin-conversations-unarchive-schema.md).

## Example Usage

```csharp
string token = "token6";
string channelId = "channel_id4";
try
{
    ApiResponse<AdminConversationsUnarchiveSchema> result = await adminConversationsController.AdminConversationsUnarchiveAsync(
        token,
        channelId
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AdminConversationsUnarchiveErrorSchema3Exception)
    {
       // TODO: Handle AdminConversationsUnarchiveErrorSchema3Exception exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsUnarchiveErrorSchema3Exception`](../../doc/models/admin-conversations-unarchive-error-schema-3-exception.md) |

