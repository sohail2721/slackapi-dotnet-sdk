# Admin Conversations Ekm

```csharp
AdminConversationsEkmController adminConversationsEkmController = client.AdminConversationsEkmController;
```

## Class Name

`AdminConversationsEkmController`


# Admin Conversations Ekm List Original Connected Channel Info

List all disconnected channels—i.e., channels that were once connected to other workspaces and then disconnected—and the corresponding original channel IDs for key revocation with EKM.

API method documentation: [https://api.slack.com/methods/admin.conversations.ekm.listOriginalConnectedChannelInfo](https://api.slack.com/methods/admin.conversations.ekm.listOriginalConnectedChannelInfo)

```csharp
AdminConversationsEkmListOriginalConnectedChannelInfoAsync(
    string token,
    string channelIds = null,
    string teamIds = null,
    int? limit = null,
    string cursor = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channelIds` | `string` | Query, Optional | A comma-separated list of channels to filter to. |
| `teamIds` | `string` | Query, Optional | A comma-separated list of the workspaces to which the channels you would like returned belong. |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |
| `cursor` | `string` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminConversationsEkmController.AdminConversationsEkmListOriginalConnectedChannelInfoAsync(token);
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

