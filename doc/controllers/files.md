# Files

```csharp
FilesController filesController = client.FilesController;
```

## Class Name

`FilesController`

## Methods

* [Files Delete](../../doc/controllers/files.md#files-delete)
* [Files Info](../../doc/controllers/files.md#files-info)
* [Files List](../../doc/controllers/files.md#files-list)
* [Files Revoke Public URL](../../doc/controllers/files.md#files-revoke-public-url)
* [Files Shared Public URL](../../doc/controllers/files.md#files-shared-public-url)
* [Files Upload](../../doc/controllers/files.md#files-upload)


# Files Delete

Deletes a file.

API method documentation: [https://api.slack.com/methods/files.delete](https://api.slack.com/methods/files.delete)

```csharp
FilesDeleteAsync(
    string token = null,
    string file = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `string` | Form, Optional | ID of file to delete. |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.FilesDeleteSchema](../../doc/models/files-delete-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<FilesDeleteSchema> result = await filesController.FilesDeleteAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is FilesDeleteErrorSchemaException)
    {
       // TODO: Handle FilesDeleteErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesDeleteErrorSchemaException`](../../doc/models/files-delete-error-schema-exception.md) |


# Files Info

Gets information about a file.

API method documentation: [https://api.slack.com/methods/files.info](https://api.slack.com/methods/files.info)

```csharp
FilesInfoAsync(
    string token = null,
    string file = null,
    string count = null,
    string page = null,
    int? limit = null,
    string cursor = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `files:read` |
| `file` | `string` | Query, Optional | Specify a file by providing its ID. |
| `count` | `string` | Query, Optional | - |
| `page` | `string` | Query, Optional | - |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. |
| `cursor` | `string` | Query, Optional | Parameter for pagination. File comments are paginated for a single file. Set `cursor` equal to the `next_cursor` attribute returned by the previous request's `response_metadata`. This parameter is optional, but pagination is mandatory: the default value simply fetches the first "page" of the collection of comments. See [pagination](/docs/pagination) for more details. |

## Requires scope

### slackAuth

`files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.FilesInfoSchema](../../doc/models/files-info-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<FilesInfoSchema> result = await filesController.FilesInfoAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is FilesInfoErrorSchemaException)
    {
       // TODO: Handle FilesInfoErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesInfoErrorSchemaException`](../../doc/models/files-info-error-schema-exception.md) |


# Files List

List for a team, in a channel, or from a user with applied filters.

API method documentation: [https://api.slack.com/methods/files.list](https://api.slack.com/methods/files.list)

```csharp
FilesListAsync(
    string token = null,
    string user = null,
    string channel = null,
    double? tsFrom = null,
    double? tsTo = null,
    string types = null,
    string count = null,
    string page = null,
    bool? showFilesHiddenByLimit = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `files:read` |
| `user` | `string` | Query, Optional | Filter files created by a single user. |
| `channel` | `string` | Query, Optional | Filter files appearing in a specific channel, indicated by its ID. |
| `tsFrom` | `double?` | Query, Optional | Filter files created after this timestamp (inclusive). |
| `tsTo` | `double?` | Query, Optional | Filter files created before this timestamp (inclusive). |
| `types` | `string` | Query, Optional | Filter files by type ([see below](#file_types)). You can pass multiple values in the types argument, like `types=spaces,snippets`.The default value is `all`, which does not filter the list. |
| `count` | `string` | Query, Optional | - |
| `page` | `string` | Query, Optional | - |
| `showFilesHiddenByLimit` | `bool?` | Query, Optional | Show truncated file info for files hidden due to being too old, and the team who owns the file being over the file limit. |

## Requires scope

### slackAuth

`files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.FilesListSchema](../../doc/models/files-list-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<FilesListSchema> result = await filesController.FilesListAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is FilesListErrorSchemaException)
    {
       // TODO: Handle FilesListErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesListErrorSchemaException`](../../doc/models/files-list-error-schema-exception.md) |


# Files Revoke Public URL

Revokes public/external sharing access for a file

API method documentation: [https://api.slack.com/methods/files.revokePublicURL](https://api.slack.com/methods/files.revokePublicURL)

```csharp
FilesRevokePublicUrlAsync(
    string token = null,
    string file = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `string` | Form, Optional | File to revoke |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.FilesRevokePublicUrlSchema](../../doc/models/files-revoke-public-url-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<FilesRevokePublicUrlSchema> result = await filesController.FilesRevokePublicUrlAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is FilesRevokePublicUrlErrorSchemaException)
    {
       // TODO: Handle FilesRevokePublicUrlErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesRevokePublicUrlErrorSchemaException`](../../doc/models/files-revoke-public-url-error-schema-exception.md) |


# Files Shared Public URL

Enables a file for public/external sharing.

API method documentation: [https://api.slack.com/methods/files.sharedPublicURL](https://api.slack.com/methods/files.sharedPublicURL)

```csharp
FilesSharedPublicUrlAsync(
    string token = null,
    string file = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `string` | Form, Optional | File to share |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.FilesSharedPublicUrlSchema](../../doc/models/files-shared-public-url-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<FilesSharedPublicUrlSchema> result = await filesController.FilesSharedPublicUrlAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is FilesSharedPublicUrlErrorSchemaException)
    {
       // TODO: Handle FilesSharedPublicUrlErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesSharedPublicUrlErrorSchemaException`](../../doc/models/files-shared-public-url-error-schema-exception.md) |


# Files Upload

Uploads or creates a file.

API method documentation: [https://api.slack.com/methods/files.upload](https://api.slack.com/methods/files.upload)

```csharp
FilesUploadAsync(
    string token = null,
    string file = null,
    string content = null,
    string filetype = null,
    string filename = null,
    string title = null,
    string initialComment = null,
    string channels = null,
    double? threadTs = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `string` | Form, Optional | File contents via `multipart/form-data`. If omitting this parameter, you must submit `content`. |
| `content` | `string` | Form, Optional | File contents via a POST variable. If omitting this parameter, you must provide a `file`. |
| `filetype` | `string` | Form, Optional | A [file type](/types/file#file_types) identifier. |
| `filename` | `string` | Form, Optional | Filename of file. |
| `title` | `string` | Form, Optional | Title of file. |
| `initialComment` | `string` | Form, Optional | The message text introducing the file in specified `channels`. |
| `channels` | `string` | Form, Optional | Comma-separated list of channel names or IDs where the file will be shared. |
| `threadTs` | `double?` | Form, Optional | Provide another message's `ts` value to upload this file as a reply. Never use a reply's `ts` value; use its parent instead. |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.FilesUploadSchema](../../doc/models/files-upload-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<FilesUploadSchema> result = await filesController.FilesUploadAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is FilesUploadErrorSchemaException)
    {
       // TODO: Handle FilesUploadErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesUploadErrorSchemaException`](../../doc/models/files-upload-error-schema-exception.md) |

