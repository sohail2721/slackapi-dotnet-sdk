# Oauth

```csharp
OauthController oauthController = client.OauthController;
```

## Class Name

`OauthController`

## Methods

* [Oauth Access](../../doc/controllers/oauth.md#oauth-access)
* [Oauth Token](../../doc/controllers/oauth.md#oauth-token)


# Oauth Access

Exchanges a temporary OAuth verifier code for an access token.

API method documentation: [https://api.slack.com/methods/oauth.access](https://api.slack.com/methods/oauth.access)

```csharp
OauthAccessAsync(
    string clientId = null,
    string clientSecret = null,
    string code = null,
    string redirectUri = null,
    bool? singleChannel = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `clientId` | `string` | Query, Optional | Issued when you created your application. |
| `clientSecret` | `string` | Query, Optional | Issued when you created your application. |
| `code` | `string` | Query, Optional | The `code` param returned via the OAuth callback. |
| `redirectUri` | `string` | Query, Optional | This must match the originally submitted URI (if one was sent). |
| `singleChannel` | `bool?` | Query, Optional | Request the user to add your app only to a single channel. Only valid with a [legacy workspace app](https://api.slack.com/legacy-workspace-apps). |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
try
{
    ApiResponse<DefaultSuccessTemplate> result = await oauthController.OauthAccessAsync();
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


# Oauth Token

Exchanges a temporary OAuth verifier code for a workspace token.

API method documentation: [https://api.slack.com/methods/oauth.token](https://api.slack.com/methods/oauth.token)

```csharp
OauthTokenAsync(
    string clientId = null,
    string clientSecret = null,
    string code = null,
    string redirectUri = null,
    bool? singleChannel = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `clientId` | `string` | Query, Optional | Issued when you created your application. |
| `clientSecret` | `string` | Query, Optional | Issued when you created your application. |
| `code` | `string` | Query, Optional | The `code` param returned via the OAuth callback. |
| `redirectUri` | `string` | Query, Optional | This must match the originally submitted URI (if one was sent). |
| `singleChannel` | `bool?` | Query, Optional | Request the user to add your app only to a single channel. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
try
{
    ApiResponse<DefaultSuccessTemplate> result = await oauthController.OauthTokenAsync();
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

