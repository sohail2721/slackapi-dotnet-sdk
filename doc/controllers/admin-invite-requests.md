# Admin Invite Requests

```csharp
AdminInviteRequestsController adminInviteRequestsController = client.AdminInviteRequestsController;
```

## Class Name

`AdminInviteRequestsController`

## Methods

* [Admin Invite Requests Approve](../../doc/controllers/admin-invite-requests.md#admin-invite-requests-approve)
* [Admin Invite Requests Deny](../../doc/controllers/admin-invite-requests.md#admin-invite-requests-deny)
* [Admin Invite Requests List](../../doc/controllers/admin-invite-requests.md#admin-invite-requests-list)


# Admin Invite Requests Approve

Approve a workspace invite request.

API method documentation: [https://api.slack.com/methods/admin.inviteRequests.approve](https://api.slack.com/methods/admin.inviteRequests.approve)

```csharp
AdminInviteRequestsApproveAsync(
    string token,
    string inviteRequestId,
    string teamId = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.invites:write` |
| `inviteRequestId` | `string` | Form, Required | ID of the request to invite. |
| `teamId` | `string` | Form, Optional | ID for the workspace where the invite request was made. |

## Requires scope

### slackAuth

`admin.invites:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string inviteRequestId = "invite_request_id4";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminInviteRequestsController.AdminInviteRequestsApproveAsync(
        token,
        inviteRequestId
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


# Admin Invite Requests Deny

Deny a workspace invite request.

API method documentation: [https://api.slack.com/methods/admin.inviteRequests.deny](https://api.slack.com/methods/admin.inviteRequests.deny)

```csharp
AdminInviteRequestsDenyAsync(
    string token,
    string inviteRequestId,
    string teamId = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.invites:write` |
| `inviteRequestId` | `string` | Form, Required | ID of the request to invite. |
| `teamId` | `string` | Form, Optional | ID for the workspace where the invite request was made. |

## Requires scope

### slackAuth

`admin.invites:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string inviteRequestId = "invite_request_id4";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminInviteRequestsController.AdminInviteRequestsDenyAsync(
        token,
        inviteRequestId
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


# Admin Invite Requests List

List all pending workspace invite requests.

API method documentation: [https://api.slack.com/methods/admin.inviteRequests.list](https://api.slack.com/methods/admin.inviteRequests.list)

```csharp
AdminInviteRequestsListAsync(
    string token,
    string teamId = null,
    string cursor = null,
    int? limit = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.invites:read` |
| `teamId` | `string` | Query, Optional | ID for the workspace where the invite requests were made. |
| `cursor` | `string` | Query, Optional | Value of the `next_cursor` field sent as part of the previous API response |
| `limit` | `int?` | Query, Optional | The number of results that will be returned by the API on each invocation. Must be between 1 - 1000, both inclusive |

## Requires scope

### slackAuth

`admin.invites:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminInviteRequestsController.AdminInviteRequestsListAsync(token);
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

