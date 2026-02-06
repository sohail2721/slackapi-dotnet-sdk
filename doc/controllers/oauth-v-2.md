# Oauth V 2

```csharp
OauthV2Controller oauthV2Controller = client.OauthV2Controller;
```

## Class Name

`OauthV2Controller`


# Oauth V 2 Access

Exchanges a temporary OAuth verifier code for an access token.

API method documentation: [https://api.slack.com/methods/oauth.v2.access](https://api.slack.com/methods/oauth.v2.access)

```csharp
OauthV2AccessAsync(
    string code,
    string clientId = null,
    string clientSecret = null,
    string redirectUri = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `code` | `string` | Query, Required | The `code` param returned via the OAuth callback. |
| `clientId` | `string` | Query, Optional | Issued when you created your application. |
| `clientSecret` | `string` | Query, Optional | Issued when you created your application. |
| `redirectUri` | `string` | Query, Optional | This must match the originally submitted URI (if one was sent). |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string code = "code8";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await oauthV2Controller.OauthV2AccessAsync(code);
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

