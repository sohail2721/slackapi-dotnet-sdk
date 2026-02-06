# Views

```csharp
ViewsController viewsController = client.ViewsController;
```

## Class Name

`ViewsController`

## Methods

* [Views Open](../../doc/controllers/views.md#views-open)
* [Views Publish](../../doc/controllers/views.md#views-publish)
* [Views Push](../../doc/controllers/views.md#views-push)
* [Views Update](../../doc/controllers/views.md#views-update)


# Views Open

Open a view for a user.

API method documentation: [https://api.slack.com/methods/views.open](https://api.slack.com/methods/views.open)

```csharp
ViewsOpenAsync(
    string token,
    string triggerId,
    string view)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `none` |
| `triggerId` | `string` | Query, Required | Exchange a trigger to post to the user. |
| `view` | `string` | Query, Required | A [view payload](/reference/surfaces/views). This must be a JSON-encoded string. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string triggerId = "trigger_id6";
string view = "view2";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await viewsController.ViewsOpenAsync(
        token,
        triggerId,
        view
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
| Default | Typical error response, before getting to any possible validation errors. | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Views Publish

Publish a static view for a User.

API method documentation: [https://api.slack.com/methods/views.publish](https://api.slack.com/methods/views.publish)

```csharp
ViewsPublishAsync(
    string token,
    string userId,
    string view,
    string hash = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `none` |
| `userId` | `string` | Query, Required | `id` of the user you want publish a view to. |
| `view` | `string` | Query, Required | A [view payload](/reference/surfaces/views). This must be a JSON-encoded string. |
| `hash` | `string` | Query, Optional | A string that represents view state to protect against possible race conditions. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string userId = "user_id8";
string view = "view2";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await viewsController.ViewsPublishAsync(
        token,
        userId,
        view
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
| Default | Typical error response, before getting to any possible validation errors. | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Views Push

Push a view onto the stack of a root view.

API method documentation: [https://api.slack.com/methods/views.push](https://api.slack.com/methods/views.push)

```csharp
ViewsPushAsync(
    string token,
    string triggerId,
    string view)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `none` |
| `triggerId` | `string` | Query, Required | Exchange a trigger to post to the user. |
| `view` | `string` | Query, Required | A [view payload](/reference/surfaces/views). This must be a JSON-encoded string. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string triggerId = "trigger_id6";
string view = "view2";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await viewsController.ViewsPushAsync(
        token,
        triggerId,
        view
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
| Default | Typical error response. | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Views Update

Update an existing view.

API method documentation: [https://api.slack.com/methods/views.update](https://api.slack.com/methods/views.update)

```csharp
ViewsUpdateAsync(
    string token,
    string viewId = null,
    string externalId = null,
    string view = null,
    string hash = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `none` |
| `viewId` | `string` | Query, Optional | A unique identifier of the view to be updated. Either `view_id` or `external_id` is required. |
| `externalId` | `string` | Query, Optional | A unique identifier of the view set by the developer. Must be unique for all views on a team. Max length of 255 characters. Either `view_id` or `external_id` is required. |
| `view` | `string` | Query, Optional | A [view object](/reference/surfaces/views). This must be a JSON-encoded string. |
| `hash` | `string` | Query, Optional | A string that represents view state to protect against possible race conditions. |

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
    ApiResponse<DefaultSuccessTemplate> result = await viewsController.ViewsUpdateAsync(token);
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
| Default | Typical error response. | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

