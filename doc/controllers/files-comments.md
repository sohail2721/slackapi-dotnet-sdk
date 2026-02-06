# Files Comments

```csharp
FilesCommentsController filesCommentsController = client.FilesCommentsController;
```

## Class Name

`FilesCommentsController`


# Files Comments Delete

Deletes an existing comment on a file.

API method documentation: [https://api.slack.com/methods/files.comments.delete](https://api.slack.com/methods/files.comments.delete)

```csharp
FilesCommentsDeleteAsync(
    string token = null,
    string file = null,
    string id = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `string` | Form, Optional | File to delete a comment from. |
| `id` | `string` | Form, Optional | The comment to delete. |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.FilesCommentsDeleteSchema](../../doc/models/files-comments-delete-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<FilesCommentsDeleteSchema> result = await filesCommentsController.FilesCommentsDeleteAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is FilesCommentsDeleteErrorSchemaException)
    {
       // TODO: Handle FilesCommentsDeleteErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Standard failure response when used with an invalid token | [`FilesCommentsDeleteErrorSchemaException`](../../doc/models/files-comments-delete-error-schema-exception.md) |

