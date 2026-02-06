# Api

```csharp
ApiController apiController = client.ApiController;
```

## Class Name

`ApiController`


# Api Test

Checks API calling code.

API method documentation: [https://api.slack.com/methods/api.test](https://api.slack.com/methods/api.test)

```csharp
ApiTestAsync(
    string error = null,
    string foo = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | `string` | Query, Optional | Error response to return |
| `foo` | `string` | Query, Optional | example property to return |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ApiTestSuccessSchema](../../doc/models/api-test-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<ApiTestSuccessSchema> result = await apiController.ApiTestAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ApiTestErrorSchemaException)
    {
       // TODO: Handle ApiTestErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Artificial error response | [`ApiTestErrorSchemaException`](../../doc/models/api-test-error-schema-exception.md) |

