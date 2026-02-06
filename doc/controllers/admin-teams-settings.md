# Admin Teams Settings

```csharp
AdminTeamsSettingsController adminTeamsSettingsController = client.AdminTeamsSettingsController;
```

## Class Name

`AdminTeamsSettingsController`

## Methods

* [Admin Teams Settings Info](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-info)
* [Admin Teams Settings Set Default Channels](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-set-default-channels)
* [Admin Teams Settings Set Description](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-set-description)
* [Admin Teams Settings Set Discoverability](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-set-discoverability)
* [Admin Teams Settings Set Icon](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-set-icon)
* [Admin Teams Settings Set Name](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-set-name)


# Admin Teams Settings Info

Fetch information about settings in a workspace

API method documentation: [https://api.slack.com/methods/admin.teams.settings.info](https://api.slack.com/methods/admin.teams.settings.info)

```csharp
AdminTeamsSettingsInfoAsync(
    string token,
    string teamId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.teams:read` |
| `teamId` | `string` | Query, Required | - |

## Requires scope

### slackAuth

`admin.teams:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamId = "team_id6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminTeamsSettingsController.AdminTeamsSettingsInfoAsync(
        token,
        teamId
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


# Admin Teams Settings Set Default Channels

Set the default channels of a workspace.

API method documentation: [https://api.slack.com/methods/admin.teams.settings.setDefaultChannels](https://api.slack.com/methods/admin.teams.settings.setDefaultChannels)

```csharp
AdminTeamsSettingsSetDefaultChannelsAsync(
    string token,
    string teamId,
    string channelIds)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `teamId` | `string` | Form, Required | ID for the workspace to set the default channel for. |
| `channelIds` | `string` | Form, Required | An array of channel IDs. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamId = "team_id6";
string channelIds = "channel_ids8";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminTeamsSettingsController.AdminTeamsSettingsSetDefaultChannelsAsync(
        token,
        teamId,
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
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Admin Teams Settings Set Description

Set the description of a given workspace.

API method documentation: [https://api.slack.com/methods/admin.teams.settings.setDescription](https://api.slack.com/methods/admin.teams.settings.setDescription)

```csharp
AdminTeamsSettingsSetDescriptionAsync(
    string token,
    string teamId,
    string description)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.teams:write` |
| `teamId` | `string` | Form, Required | ID for the workspace to set the description for. |
| `description` | `string` | Form, Required | The new description for the workspace. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamId = "team_id6";
string description = "description0";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminTeamsSettingsController.AdminTeamsSettingsSetDescriptionAsync(
        token,
        teamId,
        description
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


# Admin Teams Settings Set Discoverability

An API method that allows admins to set the discoverability of a given workspace

API method documentation: [https://api.slack.com/methods/admin.teams.settings.setDiscoverability](https://api.slack.com/methods/admin.teams.settings.setDiscoverability)

```csharp
AdminTeamsSettingsSetDiscoverabilityAsync(
    string token,
    string teamId,
    string discoverability)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.teams:write` |
| `teamId` | `string` | Form, Required | The ID of the workspace to set discoverability on. |
| `discoverability` | `string` | Form, Required | This workspace's discovery setting. It must be set to one of `open`, `invite_only`, `closed`, or `unlisted`. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamId = "team_id6";
string discoverability = "discoverability0";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminTeamsSettingsController.AdminTeamsSettingsSetDiscoverabilityAsync(
        token,
        teamId,
        discoverability
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


# Admin Teams Settings Set Icon

Sets the icon of a workspace.

API method documentation: [https://api.slack.com/methods/admin.teams.settings.setIcon](https://api.slack.com/methods/admin.teams.settings.setIcon)

```csharp
AdminTeamsSettingsSetIconAsync(
    string token,
    string imageUrl,
    string teamId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `imageUrl` | `string` | Form, Required | Image URL for the icon |
| `teamId` | `string` | Form, Required | ID for the workspace to set the icon for. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string imageUrl = "image_url6";
string teamId = "team_id6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminTeamsSettingsController.AdminTeamsSettingsSetIconAsync(
        token,
        imageUrl,
        teamId
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


# Admin Teams Settings Set Name

Set the name of a given workspace.

API method documentation: [https://api.slack.com/methods/admin.teams.settings.setName](https://api.slack.com/methods/admin.teams.settings.setName)

```csharp
AdminTeamsSettingsSetNameAsync(
    string token,
    string teamId,
    string name)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.teams:write` |
| `teamId` | `string` | Form, Required | ID for the workspace to set the name for. |
| `name` | `string` | Form, Required | The new name of the workspace. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamId = "team_id6";
string name = "name0";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminTeamsSettingsController.AdminTeamsSettingsSetNameAsync(
        token,
        teamId,
        name
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

