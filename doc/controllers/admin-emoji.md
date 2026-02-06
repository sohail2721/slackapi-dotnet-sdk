# Admin Emoji

```csharp
AdminEmojiController adminEmojiController = client.AdminEmojiController;
```

## Class Name

`AdminEmojiController`

## Methods

* [Admin Emoji Add](../../doc/controllers/admin-emoji.md#admin-emoji-add)
* [Admin Emoji Add Alias](../../doc/controllers/admin-emoji.md#admin-emoji-add-alias)
* [Admin Emoji List](../../doc/controllers/admin-emoji.md#admin-emoji-list)
* [Admin Emoji Remove](../../doc/controllers/admin-emoji.md#admin-emoji-remove)
* [Admin Emoji Rename](../../doc/controllers/admin-emoji.md#admin-emoji-rename)


# Admin Emoji Add

Add an emoji.

API method documentation: [https://api.slack.com/methods/admin.emoji.add](https://api.slack.com/methods/admin.emoji.add)

```csharp
AdminEmojiAddAsync(
    string token,
    string name,
    string url)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `name` | `string` | Form, Required | The name of the emoji to be removed. Colons (`:myemoji:`) around the value are not required, although they may be included. |
| `url` | `string` | Form, Required | The URL of a file to use as an image for the emoji. Square images under 128KB and with transparent backgrounds work best. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string name = "name0";
string url = "url4";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminEmojiController.AdminEmojiAddAsync(
        token,
        name,
        url
    );
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


# Admin Emoji Add Alias

Add an emoji alias.

API method documentation: [https://api.slack.com/methods/admin.emoji.addAlias](https://api.slack.com/methods/admin.emoji.addAlias)

```csharp
AdminEmojiAddAliasAsync(
    string token,
    string name,
    string aliasFor)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `name` | `string` | Form, Required | The name of the emoji to be aliased. Colons (`:myemoji:`) around the value are not required, although they may be included. |
| `aliasFor` | `string` | Form, Required | The alias of the emoji. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string name = "name0";
string aliasFor = "alias_for4";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminEmojiController.AdminEmojiAddAliasAsync(
        token,
        name,
        aliasFor
    );
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


# Admin Emoji List

List emoji for an Enterprise Grid organization.

API method documentation: [https://api.slack.com/methods/admin.emoji.list](https://api.slack.com/methods/admin.emoji.list)

```csharp
AdminEmojiListAsync(
    string token,
    string cursor = null,
    int? limit = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `admin.teams:read` |
| `cursor` | `string` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |

## Requires scope

### slackAuth

`admin.teams:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminEmojiController.AdminEmojiListAsync(token);
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


# Admin Emoji Remove

Remove an emoji across an Enterprise Grid organization

API method documentation: [https://api.slack.com/methods/admin.emoji.remove](https://api.slack.com/methods/admin.emoji.remove)

```csharp
AdminEmojiRemoveAsync(
    string token,
    string name)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `name` | `string` | Form, Required | The name of the emoji to be removed. Colons (`:myemoji:`) around the value are not required, although they may be included. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string name = "name0";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminEmojiController.AdminEmojiRemoveAsync(
        token,
        name
    );
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


# Admin Emoji Rename

Rename an emoji.

API method documentation: [https://api.slack.com/methods/admin.emoji.rename](https://api.slack.com/methods/admin.emoji.rename)

```csharp
AdminEmojiRenameAsync(
    string token,
    string name,
    string newName)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `name` | `string` | Form, Required | The name of the emoji to be renamed. Colons (`:myemoji:`) around the value are not required, although they may be included. |
| `newName` | `string` | Form, Required | The new name of the emoji. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string name = "name0";
string newName = "new_name8";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminEmojiController.AdminEmojiRenameAsync(
        token,
        name,
        newName
    );
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

