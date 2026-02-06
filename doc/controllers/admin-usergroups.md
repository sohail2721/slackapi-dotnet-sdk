# Admin Usergroups

```csharp
AdminUsergroupsController adminUsergroupsController = client.AdminUsergroupsController;
```

## Class Name

`AdminUsergroupsController`

## Methods

* [Admin Usergroups Add Channels](../../doc/controllers/admin-usergroups.md#admin-usergroups-add-channels)
* [Admin Usergroups Add Teams](../../doc/controllers/admin-usergroups.md#admin-usergroups-add-teams)
* [Admin Usergroups List Channels](../../doc/controllers/admin-usergroups.md#admin-usergroups-list-channels)
* [Admin Usergroups Remove Channels](../../doc/controllers/admin-usergroups.md#admin-usergroups-remove-channels)


# Admin Usergroups Add Channels

Add one or more default channels to an IDP group.

API method documentation: [https://api.slack.com/methods/admin.usergroups.addChannels](https://api.slack.com/methods/admin.usergroups.addChannels)

```csharp
AdminUsergroupsAddChannelsAsync(
    string token,
    string usergroupId,
    string channelIds,
    string teamId = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.usergroups:write` |
| `usergroupId` | `string` | Form, Required | ID of the IDP group to add default channels for. |
| `channelIds` | `string` | Form, Required | Comma separated string of channel IDs. |
| `teamId` | `string` | Form, Optional | The workspace to add default channels in. |

## Requires scope

### slackAuth

`admin.usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string usergroupId = "usergroup_id0";
string channelIds = "channel_ids8";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminUsergroupsController.AdminUsergroupsAddChannelsAsync(
        token,
        usergroupId,
        channelIds
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
| Default | Typical error response if the token provided is not associated with an Org Admin or Owner | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Admin Usergroups Add Teams

Associate one or more default workspaces with an organization-wide IDP group.

API method documentation: [https://api.slack.com/methods/admin.usergroups.addTeams](https://api.slack.com/methods/admin.usergroups.addTeams)

```csharp
AdminUsergroupsAddTeamsAsync(
    string token,
    string usergroupId,
    string teamIds,
    bool? autoProvision = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.teams:write` |
| `usergroupId` | `string` | Form, Required | An encoded usergroup (IDP Group) ID. |
| `teamIds` | `string` | Form, Required | A comma separated list of encoded team (workspace) IDs. Each workspace *MUST* belong to the organization associated with the token. |
| `autoProvision` | `bool?` | Form, Optional | When `true`, this method automatically creates new workspace accounts for the IDP group members. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string usergroupId = "usergroup_id0";
string teamIds = "team_ids2";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminUsergroupsController.AdminUsergroupsAddTeamsAsync(
        token,
        usergroupId,
        teamIds
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


# Admin Usergroups List Channels

List the channels linked to an org-level IDP group (user group).

API method documentation: [https://api.slack.com/methods/admin.usergroups.listChannels](https://api.slack.com/methods/admin.usergroups.listChannels)

```csharp
AdminUsergroupsListChannelsAsync(
    string token,
    string usergroupId,
    string teamId = null,
    bool? includeNumMembers = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.usergroups:read` |
| `usergroupId` | `string` | Query, Required | ID of the IDP group to list default channels for. |
| `teamId` | `string` | Query, Optional | ID of the the workspace. |
| `includeNumMembers` | `bool?` | Query, Optional | Flag to include or exclude the count of members per channel. |

## Requires scope

### slackAuth

`admin.usergroups:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string usergroupId = "usergroup_id0";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminUsergroupsController.AdminUsergroupsListChannelsAsync(
        token,
        usergroupId
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
| Default | Typical error response if the token provided is not associated with an Org Admin or Owner | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Admin Usergroups Remove Channels

Remove one or more default channels from an org-level IDP group (user group).

API method documentation: [https://api.slack.com/methods/admin.usergroups.removeChannels](https://api.slack.com/methods/admin.usergroups.removeChannels)

```csharp
AdminUsergroupsRemoveChannelsAsync(
    string token,
    string usergroupId,
    string channelIds)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.usergroups:write` |
| `usergroupId` | `string` | Form, Required | ID of the IDP Group |
| `channelIds` | `string` | Form, Required | Comma-separated string of channel IDs |

## Requires scope

### slackAuth

`admin.usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string usergroupId = "usergroup_id0";
string channelIds = "channel_ids8";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminUsergroupsController.AdminUsergroupsRemoveChannelsAsync(
        token,
        usergroupId,
        channelIds
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
| Default | Typical error response if the token provided is not associated with an Org Admin or Owner | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

