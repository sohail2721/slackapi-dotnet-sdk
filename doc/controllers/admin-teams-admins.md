# Admin Teams Admins

```csharp
AdminTeamsAdminsController adminTeamsAdminsController = client.AdminTeamsAdminsController;
```

## Class Name

`AdminTeamsAdminsController`


# Admin Teams Admins List

List all of the admins on a given workspace.

API method documentation: [https://api.slack.com/methods/admin.teams.admins.list](https://api.slack.com/methods/admin.teams.admins.list)

```csharp
AdminTeamsAdminsListAsync(
    string token,
    string teamId,
    int? limit = null,
    string cursor = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `admin.teams:read` |
| `teamId` | `string` | Query, Required | - |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. |
| `cursor` | `string` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |

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
    ApiResponse<DefaultSuccessTemplate> result = await adminTeamsAdminsController.AdminTeamsAdminsListAsync(
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

