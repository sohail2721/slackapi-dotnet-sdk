# Admin Conversations Restrict Access

```csharp
AdminConversationsRestrictAccessController adminConversationsRestrictAccessController = client.AdminConversationsRestrictAccessController;
```

## Class Name

`AdminConversationsRestrictAccessController`

## Methods

* [Admin Conversations Restrict Access Add Group](../../doc/controllers/admin-conversations-restrict-access.md#admin-conversations-restrict-access-add-group)
* [Admin Conversations Restrict Access List Groups](../../doc/controllers/admin-conversations-restrict-access.md#admin-conversations-restrict-access-list-groups)
* [Admin Conversations Restrict Access Remove Group](../../doc/controllers/admin-conversations-restrict-access.md#admin-conversations-restrict-access-remove-group)


# Admin Conversations Restrict Access Add Group

Add an allowlist of IDP groups for accessing a channel

API method documentation: [https://api.slack.com/methods/admin.conversations.restrictAccess.addGroup](https://api.slack.com/methods/admin.conversations.restrictAccess.addGroup)

```csharp
AdminConversationsRestrictAccessAddGroupAsync(
    string token,
    string groupId,
    string channelId,
    string teamId = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `groupId` | `string` | Form, Required | The [IDP Group](https://slack.com/help/articles/115001435788-Connect-identity-provider-groups-to-your-Enterprise-Grid-org) ID to be an allowlist for the private channel. |
| `channelId` | `string` | Form, Required | The channel to link this group to. |
| `teamId` | `string` | Form, Optional | The workspace where the channel exists. This argument is required for channels only tied to one workspace, and optional for channels that are shared across an organization. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string groupId = "group_id0";
string channelId = "channel_id4";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminConversationsRestrictAccessController.AdminConversationsRestrictAccessAddGroupAsync(
        token,
        groupId,
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


# Admin Conversations Restrict Access List Groups

List all IDP Groups linked to a channel

API method documentation: [https://api.slack.com/methods/admin.conversations.restrictAccess.listGroups](https://api.slack.com/methods/admin.conversations.restrictAccess.listGroups)

```csharp
AdminConversationsRestrictAccessListGroupsAsync(
    string token,
    string channelId,
    string teamId = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channelId` | `string` | Query, Required | - |
| `teamId` | `string` | Query, Optional | The workspace where the channel exists. This argument is required for channels only tied to one workspace, and optional for channels that are shared across an organization. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string channelId = "channel_id4";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminConversationsRestrictAccessController.AdminConversationsRestrictAccessListGroupsAsync(
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


# Admin Conversations Restrict Access Remove Group

Remove a linked IDP group linked from a private channel

API method documentation: [https://api.slack.com/methods/admin.conversations.restrictAccess.removeGroup](https://api.slack.com/methods/admin.conversations.restrictAccess.removeGroup)

```csharp
AdminConversationsRestrictAccessRemoveGroupAsync(
    string token,
    string teamId,
    string groupId,
    string channelId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `teamId` | `string` | Form, Required | The workspace where the channel exists. This argument is required for channels only tied to one workspace, and optional for channels that are shared across an organization. |
| `groupId` | `string` | Form, Required | The [IDP Group](https://slack.com/help/articles/115001435788-Connect-identity-provider-groups-to-your-Enterprise-Grid-org) ID to remove from the private channel. |
| `channelId` | `string` | Form, Required | The channel to remove the linked group from. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamId = "team_id6";
string groupId = "group_id0";
string channelId = "channel_id4";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminConversationsRestrictAccessController.AdminConversationsRestrictAccessRemoveGroupAsync(
        token,
        teamId,
        groupId,
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

