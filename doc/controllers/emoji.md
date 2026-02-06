# Emoji

```csharp
EmojiController emojiController = client.EmojiController;
```

## Class Name

`EmojiController`


# Emoji List

Lists custom emoji for a team.

API method documentation: [https://api.slack.com/methods/emoji.list](https://api.slack.com/methods/emoji.list)

```csharp
EmojiListAsync(
    string token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `emoji:read` |

## Requires scope

### slackAuth

`emoji:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await emojiController.EmojiListAsync(token);
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

