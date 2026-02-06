# Admin Users

```csharp
AdminUsersController adminUsersController = client.AdminUsersController;
```

## Class Name

`AdminUsersController`

## Methods

* [Admin Users Assign](../../doc/controllers/admin-users.md#admin-users-assign)
* [Admin Users Invite](../../doc/controllers/admin-users.md#admin-users-invite)
* [Admin Users List](../../doc/controllers/admin-users.md#admin-users-list)
* [Admin Users Remove](../../doc/controllers/admin-users.md#admin-users-remove)
* [Admin Users Set Admin](../../doc/controllers/admin-users.md#admin-users-set-admin)
* [Admin Users Set Expiration](../../doc/controllers/admin-users.md#admin-users-set-expiration)
* [Admin Users Set Owner](../../doc/controllers/admin-users.md#admin-users-set-owner)
* [Admin Users Set Regular](../../doc/controllers/admin-users.md#admin-users-set-regular)


# Admin Users Assign

Add an Enterprise user to a workspace.

API method documentation: [https://api.slack.com/methods/admin.users.assign](https://api.slack.com/methods/admin.users.assign)

```csharp
AdminUsersAssignAsync(
    string token,
    string teamId,
    string userId,
    bool? isRestricted = null,
    bool? isUltraRestricted = null,
    string channelIds = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `string` | Form, Required | The ID (`T1234`) of the workspace. |
| `userId` | `string` | Form, Required | The ID of the user to add to the workspace. |
| `isRestricted` | `bool?` | Form, Optional | True if user should be added to the workspace as a guest. |
| `isUltraRestricted` | `bool?` | Form, Optional | True if user should be added to the workspace as a single-channel guest. |
| `channelIds` | `string` | Form, Optional | Comma separated values of channel IDs to add user in the new workspace. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamId = "team_id6";
string userId = "user_id8";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminUsersController.AdminUsersAssignAsync(
        token,
        teamId,
        userId
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


# Admin Users Invite

Invite a user to a workspace.

API method documentation: [https://api.slack.com/methods/admin.users.invite](https://api.slack.com/methods/admin.users.invite)

```csharp
AdminUsersInviteAsync(
    string token,
    string teamId,
    string email,
    string channelIds,
    string customMessage = null,
    string realName = null,
    bool? resend = null,
    bool? isRestricted = null,
    bool? isUltraRestricted = null,
    string guestExpirationTs = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `string` | Form, Required | The ID (`T1234`) of the workspace. |
| `email` | `string` | Form, Required | The email address of the person to invite. |
| `channelIds` | `string` | Form, Required | A comma-separated list of `channel_id`s for this user to join. At least one channel is required. |
| `customMessage` | `string` | Form, Optional | An optional message to send to the user in the invite email. |
| `realName` | `string` | Form, Optional | Full name of the user. |
| `resend` | `bool?` | Form, Optional | Allow this invite to be resent in the future if a user has not signed up yet. (default: false) |
| `isRestricted` | `bool?` | Form, Optional | Is this user a multi-channel guest user? (default: false) |
| `isUltraRestricted` | `bool?` | Form, Optional | Is this user a single channel guest user? (default: false) |
| `guestExpirationTs` | `string` | Form, Optional | Timestamp when guest account should be disabled. Only include this timestamp if you are inviting a guest user and you want their account to expire on a certain date. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamId = "team_id6";
string email = "email6";
string channelIds = "channel_ids8";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminUsersController.AdminUsersInviteAsync(
        token,
        teamId,
        email,
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


# Admin Users List

List users on a workspace

API method documentation: [https://api.slack.com/methods/admin.users.list](https://api.slack.com/methods/admin.users.list)

```csharp
AdminUsersListAsync(
    string token,
    string teamId,
    string cursor = null,
    int? limit = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.users:read` |
| `teamId` | `string` | Query, Required | The ID (`T1234`) of the workspace. |
| `cursor` | `string` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |
| `limit` | `int?` | Query, Optional | Limit for how many users to be retrieved per page |

## Requires scope

### slackAuth

`admin.users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamId = "team_id6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminUsersController.AdminUsersListAsync(
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


# Admin Users Remove

Remove a user from a workspace.

API method documentation: [https://api.slack.com/methods/admin.users.remove](https://api.slack.com/methods/admin.users.remove)

```csharp
AdminUsersRemoveAsync(
    string token,
    string teamId,
    string userId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `string` | Form, Required | The ID (`T1234`) of the workspace. |
| `userId` | `string` | Form, Required | The ID of the user to remove. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamId = "team_id6";
string userId = "user_id8";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminUsersController.AdminUsersRemoveAsync(
        token,
        teamId,
        userId
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


# Admin Users Set Admin

Set an existing guest, regular user, or owner to be an admin user.

API method documentation: [https://api.slack.com/methods/admin.users.setAdmin](https://api.slack.com/methods/admin.users.setAdmin)

```csharp
AdminUsersSetAdminAsync(
    string token,
    string teamId,
    string userId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `string` | Form, Required | The ID (`T1234`) of the workspace. |
| `userId` | `string` | Form, Required | The ID of the user to designate as an admin. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamId = "team_id6";
string userId = "user_id8";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminUsersController.AdminUsersSetAdminAsync(
        token,
        teamId,
        userId
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


# Admin Users Set Expiration

Set an expiration for a guest user

API method documentation: [https://api.slack.com/methods/admin.users.setExpiration](https://api.slack.com/methods/admin.users.setExpiration)

```csharp
AdminUsersSetExpirationAsync(
    string token,
    string teamId,
    string userId,
    int expirationTs)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `string` | Form, Required | The ID (`T1234`) of the workspace. |
| `userId` | `string` | Form, Required | The ID of the user to set an expiration for. |
| `expirationTs` | `int` | Form, Required | Timestamp when guest account should be disabled. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamId = "team_id6";
string userId = "user_id8";
int expirationTs = 186;
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminUsersController.AdminUsersSetExpirationAsync(
        token,
        teamId,
        userId,
        expirationTs
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


# Admin Users Set Owner

Set an existing guest, regular user, or admin user to be a workspace owner.

API method documentation: [https://api.slack.com/methods/admin.users.setOwner](https://api.slack.com/methods/admin.users.setOwner)

```csharp
AdminUsersSetOwnerAsync(
    string token,
    string teamId,
    string userId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `string` | Form, Required | The ID (`T1234`) of the workspace. |
| `userId` | `string` | Form, Required | Id of the user to promote to owner. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamId = "team_id6";
string userId = "user_id8";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminUsersController.AdminUsersSetOwnerAsync(
        token,
        teamId,
        userId
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


# Admin Users Set Regular

Set an existing guest user, admin user, or owner to be a regular user.

API method documentation: [https://api.slack.com/methods/admin.users.setRegular](https://api.slack.com/methods/admin.users.setRegular)

```csharp
AdminUsersSetRegularAsync(
    string token,
    string teamId,
    string userId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `string` | Form, Required | The ID (`T1234`) of the workspace. |
| `userId` | `string` | Form, Required | The ID of the user to designate as a regular user. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamId = "team_id6";
string userId = "user_id8";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminUsersController.AdminUsersSetRegularAsync(
        token,
        teamId,
        userId
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

