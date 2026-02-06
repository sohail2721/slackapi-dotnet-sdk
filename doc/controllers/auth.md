# Auth

```csharp
AuthController authController = client.AuthController;
```

## Class Name

`AuthController`

## Methods

* [Auth Revoke](../../doc/controllers/auth.md#auth-revoke)
* [Auth Test](../../doc/controllers/auth.md#auth-test)


# Auth Revoke

Revokes a token.

API method documentation: [https://api.slack.com/methods/auth.revoke](https://api.slack.com/methods/auth.revoke)

```csharp
AuthRevokeAsync(
    string token,
    bool? test = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `none` |
| `test` | `bool?` | Query, Optional | Setting this parameter to `1` triggers a _testing mode_ where the specified token will not actually be revoked. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AuthRevokeSchema](../../doc/models/auth-revoke-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<AuthRevokeSchema> result = await authController.AuthRevokeAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AuthRevokeErrorSchemaException)
    {
       // TODO: Handle AuthRevokeErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AuthRevokeErrorSchemaException`](../../doc/models/auth-revoke-error-schema-exception.md) |


# Auth Test

Checks authentication & identity.

API method documentation: [https://api.slack.com/methods/auth.test](https://api.slack.com/methods/auth.test)

```csharp
AuthTestAsync(
    string token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `none` |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.AuthTestSuccessSchema](../../doc/models/auth-test-success-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<AuthTestSuccessSchema> result = await authController.AuthTestAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is AuthTestErrorSchemaException)
    {
       // TODO: Handle AuthTestErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Standard failure response when used with an invalid token | [`AuthTestErrorSchemaException`](../../doc/models/auth-test-error-schema-exception.md) |

