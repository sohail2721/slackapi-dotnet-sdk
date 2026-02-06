# Apps Event Authorizations

```csharp
AppsEventAuthorizationsController appsEventAuthorizationsController = client.AppsEventAuthorizationsController;
```

## Class Name

`AppsEventAuthorizationsController`


# Apps Event Authorizations List

Get a list of authorizations for the given event context. Each authorization represents an app installation that the event is visible to.

API method documentation: [https://api.slack.com/methods/apps.event.authorizations.list](https://api.slack.com/methods/apps.event.authorizations.list)

```csharp
AppsEventAuthorizationsListAsync(
    string token,
    string eventContext,
    string cursor = null,
    int? limit = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `authorizations:read` |
| `eventContext` | `string` | Query, Required | - |
| `cursor` | `string` | Query, Optional | - |
| `limit` | `int?` | Query, Optional | - |

## Requires scope

### slackAuth

`authorizations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string eventContext = "event_context0";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await appsEventAuthorizationsController.AppsEventAuthorizationsListAsync(
        token,
        eventContext
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

