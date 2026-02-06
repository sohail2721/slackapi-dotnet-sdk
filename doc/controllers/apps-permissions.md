# Apps Permissions

```csharp
AppsPermissionsController appsPermissionsController = client.AppsPermissionsController;
```

## Class Name

`AppsPermissionsController`

## Methods

* [Apps Permissions Info](../../doc/controllers/apps-permissions.md#apps-permissions-info)
* [Apps Permissions Request](../../doc/controllers/apps-permissions.md#apps-permissions-request)


# Apps Permissions Info

Returns list of permissions this app has on a team.

API method documentation: [https://api.slack.com/methods/apps.permissions.info](https://api.slack.com/methods/apps.permissions.info)

```csharp
AppsPermissionsInfoAsync(
    string token = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `none` |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AppsPermissionsInfoSchema](../../doc/models/apps-permissions-info-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<AppsPermissionsInfoSchema> result = await appsPermissionsController.AppsPermissionsInfoAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AppsPermissionsInfoErrorSchemaException)
    {
       // TODO: Handle AppsPermissionsInfoErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Standard failure response when used with an invalid token | [`AppsPermissionsInfoErrorSchemaException`](../../doc/models/apps-permissions-info-error-schema-exception.md) |


# Apps Permissions Request

Allows an app to request additional scopes

API method documentation: [https://api.slack.com/methods/apps.permissions.request](https://api.slack.com/methods/apps.permissions.request)

```csharp
AppsPermissionsRequestAsync(
    string token,
    string scopes,
    string triggerId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `none` |
| `scopes` | `string` | Query, Required | A comma separated list of scopes to request for |
| `triggerId` | `string` | Query, Required | Token used to trigger the permissions API |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AppsPermissionsRequestSchema](../../doc/models/apps-permissions-request-schema.md).

## Example Usage

```csharp
string token = "token6";
string scopes = "scopes4";
string triggerId = "trigger_id6";
try
{
    ApiResponse<AppsPermissionsRequestSchema> result = await appsPermissionsController.AppsPermissionsRequestAsync(
        token,
        scopes,
        triggerId
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AppsPermissionsRequestErrorSchemaException)
    {
       // TODO: Handle AppsPermissionsRequestErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Standard failure response when trigger_id is invalid | [`AppsPermissionsRequestErrorSchemaException`](../../doc/models/apps-permissions-request-error-schema-exception.md) |

