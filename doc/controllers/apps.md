# Apps

```csharp
AppsController appsController = client.AppsController;
```

## Class Name

`AppsController`


# Apps Uninstall

Uninstalls your app from a workspace.

API method documentation: [https://api.slack.com/methods/apps.uninstall](https://api.slack.com/methods/apps.uninstall)

```csharp
AppsUninstallAsync(
    string token = null,
    string clientId = null,
    string clientSecret = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `none` |
| `clientId` | `string` | Query, Optional | Issued when you created your application. |
| `clientSecret` | `string` | Query, Optional | Issued when you created your application. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AppsUninstallSchema](../../doc/models/apps-uninstall-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<AppsUninstallSchema> result = await appsController.AppsUninstallAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AppsUninstallErrorSchemaException)
    {
       // TODO: Handle AppsUninstallErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AppsUninstallErrorSchemaException`](../../doc/models/apps-uninstall-error-schema-exception.md) |

