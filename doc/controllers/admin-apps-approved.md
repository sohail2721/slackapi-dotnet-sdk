# Admin Apps Approved

```csharp
AdminAppsApprovedController adminAppsApprovedController = client.AdminAppsApprovedController;
```

## Class Name

`AdminAppsApprovedController`


# Admin Apps Approved List

List approved apps for an org or workspace.

API method documentation: [https://api.slack.com/methods/admin.apps.approved.list](https://api.slack.com/methods/admin.apps.approved.list)

```csharp
AdminAppsApprovedListAsync(
    string token,
    int? limit = null,
    string cursor = null,
    string teamId = null,
    string enterpriseId = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `admin.apps:read` |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |
| `cursor` | `string` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page |
| `teamId` | `string` | Query, Optional | - |
| `enterpriseId` | `string` | Query, Optional | - |

## Requires scope

### slackAuth

`admin.apps:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminAppsApprovedController.AdminAppsApprovedListAsync(token);
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

