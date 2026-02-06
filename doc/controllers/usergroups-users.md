# Usergroups Users

```csharp
UsergroupsUsersController usergroupsUsersController = client.UsergroupsUsersController;
```

## Class Name

`UsergroupsUsersController`

## Methods

* [Usergroups Users List](../../doc/controllers/usergroups-users.md#usergroups-users-list)
* [Usergroups Users Update](../../doc/controllers/usergroups-users.md#usergroups-users-update)


# Usergroups Users List

List all users in a User Group

API method documentation: [https://api.slack.com/methods/usergroups.users.list](https://api.slack.com/methods/usergroups.users.list)

```csharp
UsergroupsUsersListAsync(
    string token,
    string usergroup,
    bool? includeDisabled = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `usergroups:read` |
| `usergroup` | `string` | Query, Required | The encoded ID of the User Group to update. |
| `includeDisabled` | `bool?` | Query, Optional | Allow results that involve disabled User Groups. |

## Requires scope

### slackAuth

`usergroups:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsergroupsUsersListSchema](../../doc/models/usergroups-users-list-schema.md).

## Example Usage

```csharp
string token = "token6";
string usergroup = "usergroup2";
try
{
    ApiResponse<UsergroupsUsersListSchema> result = await usergroupsUsersController.UsergroupsUsersListAsync(
        token,
        usergroup
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsergroupsUsersListErrorSchemaException)
    {
       // TODO: Handle UsergroupsUsersListErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Standard failure response when used with an invalid token | [`UsergroupsUsersListErrorSchemaException`](../../doc/models/usergroups-users-list-error-schema-exception.md) |


# Usergroups Users Update

Update the list of users for a User Group

API method documentation: [https://api.slack.com/methods/usergroups.users.update](https://api.slack.com/methods/usergroups.users.update)

```csharp
UsergroupsUsersUpdateAsync(
    string token,
    string usergroup,
    string users,
    bool? includeCount = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `usergroup` | `string` | Form, Required | The encoded ID of the User Group to update. |
| `users` | `string` | Form, Required | A comma separated string of encoded user IDs that represent the entire list of users for the User Group. |
| `includeCount` | `bool?` | Form, Optional | Include the number of users in the User Group. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsergroupsUsersUpdateSchema](../../doc/models/usergroups-users-update-schema.md).

## Example Usage

```csharp
string token = "token6";
string usergroup = "usergroup2";
string users = "users6";
try
{
    ApiResponse<UsergroupsUsersUpdateSchema> result = await usergroupsUsersController.UsergroupsUsersUpdateAsync(
        token,
        usergroup,
        users
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsergroupsUsersUpdateErrorSchemaException)
    {
       // TODO: Handle UsergroupsUsersUpdateErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsUsersUpdateErrorSchemaException`](../../doc/models/usergroups-users-update-error-schema-exception.md) |

