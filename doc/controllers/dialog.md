# Dialog

```csharp
DialogController dialogController = client.DialogController;
```

## Class Name

`DialogController`


# Dialog Open

Open a dialog with a user

API method documentation: [https://api.slack.com/methods/dialog.open](https://api.slack.com/methods/dialog.open)

```csharp
DialogOpenAsync(
    string token,
    string dialog,
    string triggerId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `none` |
| `dialog` | `string` | Query, Required | The dialog definition. This must be a JSON-encoded string. |
| `triggerId` | `string` | Query, Required | Exchange a trigger to post to the user. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DialogOpenSchema](../../doc/models/dialog-open-schema.md).

## Example Usage

```csharp
string token = "token6";
string dialog = "dialog4";
string triggerId = "trigger_id6";
try
{
    ApiResponse<DialogOpenSchema> result = await dialogController.DialogOpenAsync(
        token,
        dialog,
        triggerId
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is DialogOpenErrorSchemaException)
    {
       // TODO: Handle DialogOpenErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response, before getting to any possible validation errors. | [`DialogOpenErrorSchemaException`](../../doc/models/dialog-open-error-schema-exception.md) |

