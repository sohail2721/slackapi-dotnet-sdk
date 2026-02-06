# Admin Apps

```csharp
AdminAppsController adminAppsController = client.AdminAppsController;
```

## Class Name

`AdminAppsController`

## Methods

* [Admin Apps Approve](../../doc/controllers/admin-apps.md#admin-apps-approve)
* [Admin Apps Restrict](../../doc/controllers/admin-apps.md#admin-apps-restrict)


# Admin Apps Approve

Approve an app for installation on a workspace.

API method documentation: [https://api.slack.com/methods/admin.apps.approve](https://api.slack.com/methods/admin.apps.approve)

```csharp
AdminAppsApproveAsync(
    string token,
    string appId = null,
    string requestId = null,
    string teamId = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.apps:write` |
| `appId` | `string` | Form, Optional | The id of the app to approve. |
| `requestId` | `string` | Form, Optional | The id of the request to approve. |
| `teamId` | `string` | Form, Optional | - |

## Requires scope

### slackAuth

`admin.apps:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminAppsController.AdminAppsApproveAsync(token);
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


# Admin Apps Restrict

Restrict an app for installation on a workspace.

API method documentation: [https://api.slack.com/methods/admin.apps.restrict](https://api.slack.com/methods/admin.apps.restrict)

```csharp
AdminAppsRestrictAsync(
    string token,
    string appId = null,
    string requestId = null,
    string teamId = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.apps:write` |
| `appId` | `string` | Form, Optional | The id of the app to restrict. |
| `requestId` | `string` | Form, Optional | The id of the request to restrict. |
| `teamId` | `string` | Form, Optional | - |

## Requires scope

### slackAuth

`admin.apps:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminAppsController.AdminAppsRestrictAsync(token);
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

