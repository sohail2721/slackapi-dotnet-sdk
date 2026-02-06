# Apps Permissions Resources

```csharp
AppsPermissionsResourcesController appsPermissionsResourcesController = client.AppsPermissionsResourcesController;
```

## Class Name

`AppsPermissionsResourcesController`


# Apps Permissions Resources List

Returns list of resource grants this app has on a team.

API method documentation: [https://api.slack.com/methods/apps.permissions.resources.list](https://api.slack.com/methods/apps.permissions.resources.list)

```csharp
AppsPermissionsResourcesListAsync(
    string token,
    string cursor = null,
    int? limit = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `none` |
| `cursor` | `string` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AppsPermissionsResourcesListSuccessSchema](../../doc/models/apps-permissions-resources-list-success-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<AppsPermissionsResourcesListSuccessSchema> result = await appsPermissionsResourcesController.AppsPermissionsResourcesListAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AppsPermissionsResourcesListErrorSchemaException)
    {
       // TODO: Handle AppsPermissionsResourcesListErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AppsPermissionsResourcesListErrorSchemaException`](../../doc/models/apps-permissions-resources-list-error-schema-exception.md) |

