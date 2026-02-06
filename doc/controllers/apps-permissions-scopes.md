# Apps Permissions Scopes

```csharp
AppsPermissionsScopesController appsPermissionsScopesController = client.AppsPermissionsScopesController;
```

## Class Name

`AppsPermissionsScopesController`


# Apps Permissions Scopes List

Returns list of scopes this app has on a team.

API method documentation: [https://api.slack.com/methods/apps.permissions.scopes.list](https://api.slack.com/methods/apps.permissions.scopes.list)

```csharp
AppsPermissionsScopesListAsync(
    string token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `none` |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ApiPermissionsScopesListSuccessSchema](../../doc/models/api-permissions-scopes-list-success-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<ApiPermissionsScopesListSuccessSchema> result = await appsPermissionsScopesController.AppsPermissionsScopesListAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AppsPermissionsScopesListErrorSchemaException)
    {
       // TODO: Handle AppsPermissionsScopesListErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AppsPermissionsScopesListErrorSchemaException`](../../doc/models/apps-permissions-scopes-list-error-schema-exception.md) |

