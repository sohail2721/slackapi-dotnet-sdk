# Users

```csharp
UsersController usersController = client.UsersController;
```

## Class Name

`UsersController`

## Methods

* [Users Conversations](../../doc/controllers/users.md#users-conversations)
* [Users Delete Photo](../../doc/controllers/users.md#users-delete-photo)
* [Users Get Presence](../../doc/controllers/users.md#users-get-presence)
* [Users Identity](../../doc/controllers/users.md#users-identity)
* [Users Info](../../doc/controllers/users.md#users-info)
* [Users List](../../doc/controllers/users.md#users-list)
* [Users Lookup by Email](../../doc/controllers/users.md#users-lookup-by-email)
* [Users Set Active](../../doc/controllers/users.md#users-set-active)
* [Users Set Photo](../../doc/controllers/users.md#users-set-photo)
* [Users Set Presence](../../doc/controllers/users.md#users-set-presence)


# Users Conversations

List conversations the calling user may access.

API method documentation: [https://api.slack.com/methods/users.conversations](https://api.slack.com/methods/users.conversations)

```csharp
UsersConversationsAsync(
    string token = null,
    string user = null,
    string types = null,
    bool? excludeArchived = null,
    int? limit = null,
    string cursor = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `user` | `string` | Query, Optional | Browse conversations by a specific user ID's membership. Non-public channels are restricted to those where the calling user shares membership. |
| `types` | `string` | Query, Optional | Mix and match channel types by providing a comma-separated list of any combination of `public_channel`, `private_channel`, `mpim`, `im` |
| `excludeArchived` | `bool?` | Query, Optional | Set to `true` to exclude archived channels from the list |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. Must be an integer no larger than 1000. |
| `cursor` | `string` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsersConversationsSuccessSchema](../../doc/models/users-conversations-success-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<UsersConversationsSuccessSchema> result = await usersController.UsersConversationsAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsersConversationsErrorSchemaException)
    {
       // TODO: Handle UsersConversationsErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersConversationsErrorSchemaException`](../../doc/models/users-conversations-error-schema-exception.md) |


# Users Delete Photo

Delete the user profile photo

API method documentation: [https://api.slack.com/methods/users.deletePhoto](https://api.slack.com/methods/users.deletePhoto)

```csharp
UsersDeletePhotoAsync(
    string token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `users.profile:write` |

## Requires scope

### slackAuth

`users.profile:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsersDeletePhotoSchema](../../doc/models/users-delete-photo-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<UsersDeletePhotoSchema> result = await usersController.UsersDeletePhotoAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsersDeletePhotoErrorSchemaException)
    {
       // TODO: Handle UsersDeletePhotoErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersDeletePhotoErrorSchemaException`](../../doc/models/users-delete-photo-error-schema-exception.md) |


# Users Get Presence

Gets user presence information.

API method documentation: [https://api.slack.com/methods/users.getPresence](https://api.slack.com/methods/users.getPresence)

```csharp
UsersGetPresenceAsync(
    string token,
    string user = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `users:read` |
| `user` | `string` | Query, Optional | User to get presence info on. Defaults to the authed user. |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.ApiMethodUsersGetPresence](../../doc/models/api-method-users-get-presence.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<ApiMethodUsersGetPresence> result = await usersController.UsersGetPresenceAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsersCountsErrorSchemaException)
    {
       // TODO: Handle UsersCountsErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersCountsErrorSchemaException`](../../doc/models/users-counts-error-schema-exception.md) |


# Users Identity

Get a user's identity.

API method documentation: [https://api.slack.com/methods/users.identity](https://api.slack.com/methods/users.identity)

```csharp
UsersIdentityAsync(
    string token = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `identity.basic` |

## Requires scope

### slackAuth

`identity.basic`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type dynamic.

## Example Usage

```csharp
try
{
    ApiResponse<dynamic> result = await usersController.UsersIdentityAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsersIdentityErrorSchemaException)
    {
       // TODO: Handle UsersIdentityErrorSchemaException exception here
    }
}
```

## Example Response

```
{
  "ok": true,
  "team": {
    "id": "T0G9PQBBK"
  },
  "user": {
    "id": "U0G9QF9C6",
    "name": "Sonny Whether"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersIdentityErrorSchemaException`](../../doc/models/users-identity-error-schema-exception.md) |


# Users Info

Gets information about a user.

API method documentation: [https://api.slack.com/methods/users.info](https://api.slack.com/methods/users.info)

```csharp
UsersInfoAsync(
    string token,
    bool? includeLocale = null,
    string user = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `users:read` |
| `includeLocale` | `bool?` | Query, Optional | Set this to `true` to receive the locale for this user. Defaults to `false` |
| `user` | `string` | Query, Optional | User to get info on |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsersInfoSuccessSchema](../../doc/models/users-info-success-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<UsersInfoSuccessSchema> result = await usersController.UsersInfoAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsersInfoErrorSchemaException)
    {
       // TODO: Handle UsersInfoErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersInfoErrorSchemaException`](../../doc/models/users-info-error-schema-exception.md) |


# Users List

Lists all users in a Slack team.

API method documentation: [https://api.slack.com/methods/users.list](https://api.slack.com/methods/users.list)

```csharp
UsersListAsync(
    string token = null,
    int? limit = null,
    string cursor = null,
    bool? includeLocale = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Optional | Authentication token. Requires scope: `users:read` |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. Providing no `limit` value will result in Slack attempting to deliver you the entire result set. If the collection is too large you may experience `limit_required` or HTTP 500 errors. |
| `cursor` | `string` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |
| `includeLocale` | `bool?` | Query, Optional | Set this to `true` to receive the locale for users. Defaults to `false` |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsersListSchema](../../doc/models/users-list-schema.md).

## Example Usage

```csharp
try
{
    ApiResponse<UsersListSchema> result = await usersController.UsersListAsync();
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsersListErrorSchemaException)
    {
       // TODO: Handle UsersListErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersListErrorSchemaException`](../../doc/models/users-list-error-schema-exception.md) |


# Users Lookup by Email

Find a user with an email address.

API method documentation: [https://api.slack.com/methods/users.lookupByEmail](https://api.slack.com/methods/users.lookupByEmail)

```csharp
UsersLookupByEmailAsync(
    string token,
    string email)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `users:read.email` |
| `email` | `string` | Query, Required | An email address belonging to a user in the workspace |

## Requires scope

### slackAuth

`users:read.email`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsersLookupByEmailSuccessSchema](../../doc/models/users-lookup-by-email-success-schema.md).

## Example Usage

```csharp
string token = "token6";
string email = "email6";
try
{
    ApiResponse<UsersLookupByEmailSuccessSchema> result = await usersController.UsersLookupByEmailAsync(
        token,
        email
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsersLookupByEmailErrorSchemaException)
    {
       // TODO: Handle UsersLookupByEmailErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersLookupByEmailErrorSchemaException`](../../doc/models/users-lookup-by-email-error-schema-exception.md) |


# Users Set Active

Marked a user as active. Deprecated and non-functional.

API method documentation: [https://api.slack.com/methods/users.setActive](https://api.slack.com/methods/users.setActive)

```csharp
UsersSetActiveAsync(
    string token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `users:write` |

## Requires scope

### slackAuth

`users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsersSetActiveSchema](../../doc/models/users-set-active-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<UsersSetActiveSchema> result = await usersController.UsersSetActiveAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsersSetActiveErrorSchemaException)
    {
       // TODO: Handle UsersSetActiveErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersSetActiveErrorSchemaException`](../../doc/models/users-set-active-error-schema-exception.md) |


# Users Set Photo

Set the user profile photo

API method documentation: [https://api.slack.com/methods/users.setPhoto](https://api.slack.com/methods/users.setPhoto)

```csharp
UsersSetPhotoAsync(
    string token,
    string cropW = null,
    string cropX = null,
    string cropY = null,
    string image = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `users.profile:write` |
| `cropW` | `string` | Form, Optional | Width/height of crop box (always square) |
| `cropX` | `string` | Form, Optional | X coordinate of top-left corner of crop box |
| `cropY` | `string` | Form, Optional | Y coordinate of top-left corner of crop box |
| `image` | `string` | Form, Optional | File contents via `multipart/form-data`. |

## Requires scope

### slackAuth

`users.profile:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsersSetPhotoSchema](../../doc/models/users-set-photo-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<UsersSetPhotoSchema> result = await usersController.UsersSetPhotoAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsersSetPhotoErrorSchemaException)
    {
       // TODO: Handle UsersSetPhotoErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersSetPhotoErrorSchemaException`](../../doc/models/users-set-photo-error-schema-exception.md) |


# Users Set Presence

Manually sets user presence.

API method documentation: [https://api.slack.com/methods/users.setPresence](https://api.slack.com/methods/users.setPresence)

```csharp
UsersSetPresenceAsync(
    string token,
    string presence)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `users:write` |
| `presence` | `string` | Form, Required | Either `auto` or `away` |

## Requires scope

### slackAuth

`users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsersSetPresenceSchema](../../doc/models/users-set-presence-schema.md).

## Example Usage

```csharp
string token = "token6";
string presence = "presence4";
try
{
    ApiResponse<UsersSetPresenceSchema> result = await usersController.UsersSetPresenceAsync(
        token,
        presence
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsersSetPresenceErrorSchemaException)
    {
       // TODO: Handle UsersSetPresenceErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersSetPresenceErrorSchemaException`](../../doc/models/users-set-presence-error-schema-exception.md) |

