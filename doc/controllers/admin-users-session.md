# Admin Users Session

```csharp
AdminUsersSessionController adminUsersSessionController = client.AdminUsersSessionController;
```

## Class Name

`AdminUsersSessionController`

## Methods

* [Admin Users Session Invalidate](../../doc/controllers/admin-users-session.md#admin-users-session-invalidate)
* [Admin Users Session Reset](../../doc/controllers/admin-users-session.md#admin-users-session-reset)


# Admin Users Session Invalidate

Invalidate a single session for a user by session_id

API method documentation: [https://api.slack.com/methods/admin.users.session.invalidate](https://api.slack.com/methods/admin.users.session.invalidate)

```csharp
AdminUsersSessionInvalidateAsync(
    string token,
    string teamId,
    int sessionId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `string` | Form, Required | ID of the team that the session belongs to |
| `sessionId` | `int` | Form, Required | - |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamId = "team_id6";
int sessionId = 2;
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminUsersSessionController.AdminUsersSessionInvalidateAsync(
        token,
        teamId,
        sessionId
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


# Admin Users Session Reset

Wipes all valid sessions on all devices for a given user

API method documentation: [https://api.slack.com/methods/admin.users.session.reset](https://api.slack.com/methods/admin.users.session.reset)

```csharp
AdminUsersSessionResetAsync(
    string token,
    string userId,
    bool? mobileOnly = null,
    bool? webOnly = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `userId` | `string` | Form, Required | The ID of the user to wipe sessions for |
| `mobileOnly` | `bool?` | Form, Optional | Only expire mobile sessions (default: false) |
| `webOnly` | `bool?` | Form, Optional | Only expire web sessions (default: false) |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string userId = "user_id8";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminUsersSessionController.AdminUsersSessionResetAsync(
        token,
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

