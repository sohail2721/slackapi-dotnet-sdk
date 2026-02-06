# Users Profile

```csharp
UsersProfileController usersProfileController = client.UsersProfileController;
```

## Class Name

`UsersProfileController`

## Methods

* [Users Profile Get](../../doc/controllers/users-profile.md#users-profile-get)
* [Users Profile Set](../../doc/controllers/users-profile.md#users-profile-set)


# Users Profile Get

Retrieves a user's profile information.

API method documentation: [https://api.slack.com/methods/users.profile.get](https://api.slack.com/methods/users.profile.get)

```csharp
UsersProfileGetAsync(
    string token,
    bool? includeLabels = null,
    string user = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `users.profile:read` |
| `includeLabels` | `bool?` | Query, Optional | Include labels for each ID in custom profile fields |
| `user` | `string` | Query, Optional | User to retrieve profile info for |

## Requires scope

### slackAuth

`users.profile:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsersProfileGetSchema](../../doc/models/users-profile-get-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<UsersProfileGetSchema> result = await usersProfileController.UsersProfileGetAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsersProfileGetErrorSchemaException)
    {
       // TODO: Handle UsersProfileGetErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersProfileGetErrorSchemaException`](../../doc/models/users-profile-get-error-schema-exception.md) |


# Users Profile Set

Set the profile information for a user.

API method documentation: [https://api.slack.com/methods/users.profile.set](https://api.slack.com/methods/users.profile.set)

```csharp
UsersProfileSetAsync(
    string token,
    string name = null,
    string profile = null,
    string user = null,
    string mValue = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `users.profile:write` |
| `name` | `string` | Form, Optional | Name of a single key to set. Usable only if `profile` is not passed. |
| `profile` | `string` | Form, Optional | Collection of key:value pairs presented as a URL-encoded JSON hash. At most 50 fields may be set. Each field name is limited to 255 characters. |
| `user` | `string` | Form, Optional | ID of user to change. This argument may only be specified by team admins on paid teams. |
| `mValue` | `string` | Form, Optional | Value to set a single key to. Usable only if `profile` is not passed. |

## Requires scope

### slackAuth

`users.profile:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsersProfileSetSchema](../../doc/models/users-profile-set-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<UsersProfileSetSchema> result = await usersProfileController.UsersProfileSetAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsersProfileSetErrorSchemaException)
    {
       // TODO: Handle UsersProfileSetErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersProfileSetErrorSchemaException`](../../doc/models/users-profile-set-error-schema-exception.md) |

