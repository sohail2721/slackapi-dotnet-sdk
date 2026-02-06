# Admin Invite Requests Denied

```csharp
AdminInviteRequestsDeniedController adminInviteRequestsDeniedController = client.AdminInviteRequestsDeniedController;
```

## Class Name

`AdminInviteRequestsDeniedController`


# Admin Invite Requests Denied List

List all denied workspace invite requests.

API method documentation: [https://api.slack.com/methods/admin.inviteRequests.denied.list](https://api.slack.com/methods/admin.inviteRequests.denied.list)

```csharp
AdminInviteRequestsDeniedListAsync(
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
| `cursor` | `string` | Query, Optional | Value of the `next_cursor` field sent as part of the previous api response |
| `limit` | `int?` | Query, Optional | The number of results that will be returned by the API on each invocation. Must be between 1 - 1000 both inclusive |

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
    ApiResponse<DefaultSuccessTemplate> result = await adminInviteRequestsDeniedController.AdminInviteRequestsDeniedListAsync(token);
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

