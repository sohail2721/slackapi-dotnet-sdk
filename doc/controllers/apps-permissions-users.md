# Apps Permissions Users

```csharp
AppsPermissionsUsersController appsPermissionsUsersController = client.AppsPermissionsUsersController;
```

## Class Name

`AppsPermissionsUsersController`

## Methods

* [Apps Permissions Users List](../../doc/controllers/apps-permissions-users.md#apps-permissions-users-list)
* [Apps Permissions Users Request](../../doc/controllers/apps-permissions-users.md#apps-permissions-users-request)


# Apps Permissions Users List

Returns list of user grants and corresponding scopes this app has on a team.

API method documentation: [https://api.slack.com/methods/apps.permissions.users.list](https://api.slack.com/methods/apps.permissions.users.list)

```csharp
AppsPermissionsUsersListAsync(
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await appsPermissionsUsersController.AppsPermissionsUsersListAsync(token);
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


# Apps Permissions Users Request

Enables an app to trigger a permissions modal to grant an app access to a user access scope.

API method documentation: [https://api.slack.com/methods/apps.permissions.users.request](https://api.slack.com/methods/apps.permissions.users.request)

```csharp
AppsPermissionsUsersRequestAsync(
    string token,
    string scopes,
    string triggerId,
    string user)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `none` |
| `scopes` | `string` | Query, Required | A comma separated list of user scopes to request for |
| `triggerId` | `string` | Query, Required | Token used to trigger the request |
| `user` | `string` | Query, Required | The user this scope is being requested for |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string scopes = "scopes4";
string triggerId = "trigger_id6";
string user = "user0";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await appsPermissionsUsersController.AppsPermissionsUsersRequestAsync(
        token,
        scopes,
        triggerId,
        user
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
| Default | Standard failure response when trigger_id is invalid | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

