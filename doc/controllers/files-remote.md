# Files Remote

```csharp
FilesRemoteController filesRemoteController = client.FilesRemoteController;
```

## Class Name

`FilesRemoteController`

## Methods

* [Files Remote Add](../../doc/controllers/files-remote.md#files-remote-add)
* [Files Remote Info](../../doc/controllers/files-remote.md#files-remote-info)
* [Files Remote List](../../doc/controllers/files-remote.md#files-remote-list)
* [Files Remote Remove](../../doc/controllers/files-remote.md#files-remote-remove)
* [Files Remote Share](../../doc/controllers/files-remote.md#files-remote-share)
* [Files Remote Update](../../doc/controllers/files-remote.md#files-remote-update)


# Files Remote Add

Adds a file from a remote service

API method documentation: [https://api.slack.com/methods/files.remote.add](https://api.slack.com/methods/files.remote.add)

```csharp
FilesRemoteAddAsync(
    string token = null,
    string externalId = null,
    string title = null,
    string filetype = null,
    string externalUrl = null,
    string previewImage = null,
    string indexableFileContents = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Optional | Authentication token. Requires scope: `remote_files:write` |
| `externalId` | `string` | Form, Optional | Creator defined GUID for the file. |
| `title` | `string` | Form, Optional | Title of the file being shared. |
| `filetype` | `string` | Form, Optional | type of file |
| `externalUrl` | `string` | Form, Optional | URL of the remote file. |
| `previewImage` | `string` | Form, Optional | Preview of the document via `multipart/form-data`. |
| `indexableFileContents` | `string` | Form, Optional | A text file (txt, pdf, doc, etc.) containing textual search terms that are used to improve discovery of the remote file. |

## Requires scope

### slackAuth

`remote_files:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
try
{
    ApiResponse<DefaultSuccessTemplate> result = await filesRemoteController.FilesRemoteAddAsync();
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


# Files Remote Info

Retrieve information about a remote file added to Slack

API method documentation: [https://api.slack.com/methods/files.remote.info](https://api.slack.com/methods/files.remote.info)

```csharp
FilesRemoteInfoAsync(
    string token = null,
    string file = null,
    string externalId = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `remote_files:read` |
| `file` | `string` | Query, Optional | Specify a file by providing its ID. |
| `externalId` | `string` | Query, Optional | Creator defined GUID for the file. |

## Requires scope

### slackAuth

`remote_files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
try
{
    ApiResponse<DefaultSuccessTemplate> result = await filesRemoteController.FilesRemoteInfoAsync();
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


# Files Remote List

Retrieve information about a remote file added to Slack

API method documentation: [https://api.slack.com/methods/files.remote.list](https://api.slack.com/methods/files.remote.list)

```csharp
FilesRemoteListAsync(
    string token = null,
    string channel = null,
    double? tsFrom = null,
    double? tsTo = null,
    int? limit = null,
    string cursor = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `remote_files:read` |
| `channel` | `string` | Query, Optional | Filter files appearing in a specific channel, indicated by its ID. |
| `tsFrom` | `double?` | Query, Optional | Filter files created after this timestamp (inclusive). |
| `tsTo` | `double?` | Query, Optional | Filter files created before this timestamp (inclusive). |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. |
| `cursor` | `string` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |

## Requires scope

### slackAuth

`remote_files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
try
{
    ApiResponse<DefaultSuccessTemplate> result = await filesRemoteController.FilesRemoteListAsync();
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


# Files Remote Remove

Remove a remote file.

API method documentation: [https://api.slack.com/methods/files.remote.remove](https://api.slack.com/methods/files.remote.remove)

```csharp
FilesRemoteRemoveAsync(
    string token = null,
    string file = null,
    string externalId = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Optional | Authentication token. Requires scope: `remote_files:write` |
| `file` | `string` | Form, Optional | Specify a file by providing its ID. |
| `externalId` | `string` | Form, Optional | Creator defined GUID for the file. |

## Requires scope

### slackAuth

`remote_files:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
try
{
    ApiResponse<DefaultSuccessTemplate> result = await filesRemoteController.FilesRemoteRemoveAsync();
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


# Files Remote Share

Share a remote file into a channel.

API method documentation: [https://api.slack.com/methods/files.remote.share](https://api.slack.com/methods/files.remote.share)

```csharp
FilesRemoteShareAsync(
    string token = null,
    string file = null,
    string externalId = null,
    string channels = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `remote_files:share` |
| `file` | `string` | Query, Optional | Specify a file registered with Slack by providing its ID. Either this field or `external_id` or both are required. |
| `externalId` | `string` | Query, Optional | The globally unique identifier (GUID) for the file, as set by the app registering the file with Slack.  Either this field or `file` or both are required. |
| `channels` | `string` | Query, Optional | Comma-separated list of channel IDs where the file will be shared. |

## Requires scope

### slackAuth

`remote_files:share`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
try
{
    ApiResponse<DefaultSuccessTemplate> result = await filesRemoteController.FilesRemoteShareAsync();
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


# Files Remote Update

Updates an existing remote file.

API method documentation: [https://api.slack.com/methods/files.remote.update](https://api.slack.com/methods/files.remote.update)

```csharp
FilesRemoteUpdateAsync(
    string token = null,
    string file = null,
    string externalId = null,
    string title = null,
    string filetype = null,
    string externalUrl = null,
    string previewImage = null,
    string indexableFileContents = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Optional | Authentication token. Requires scope: `remote_files:write` |
| `file` | `string` | Form, Optional | Specify a file by providing its ID. |
| `externalId` | `string` | Form, Optional | Creator defined GUID for the file. |
| `title` | `string` | Form, Optional | Title of the file being shared. |
| `filetype` | `string` | Form, Optional | type of file |
| `externalUrl` | `string` | Form, Optional | URL of the remote file. |
| `previewImage` | `string` | Form, Optional | Preview of the document via `multipart/form-data`. |
| `indexableFileContents` | `string` | Form, Optional | File containing contents that can be used to improve searchability for the remote file. |

## Requires scope

### slackAuth

`remote_files:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
try
{
    ApiResponse<DefaultSuccessTemplate> result = await filesRemoteController.FilesRemoteUpdateAsync();
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

