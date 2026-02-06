# Bots

```csharp
BotsController botsController = client.BotsController;
```

## Class Name

`BotsController`


# Bots Info

Gets information about a bot user.

API method documentation: [https://api.slack.com/methods/bots.info](https://api.slack.com/methods/bots.info)

```csharp
BotsInfoAsync(
    string token,
    string bot = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `users:read` |
| `bot` | `string` | Query, Optional | Bot user to get info on |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.BotsInfoSchema](../../doc/models/bots-info-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<BotsInfoSchema> result = await botsController.BotsInfoAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is BotsInfoErrorSchemaException)
    {
       // TODO: Handle BotsInfoErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | When no bot can be found, it returns an error. | [`BotsInfoErrorSchemaException`](../../doc/models/bots-info-error-schema-exception.md) |

