# Usergroups

```csharp
UsergroupsController usergroupsController = client.UsergroupsController;
```

## Class Name

`UsergroupsController`

## Methods

* [Usergroups Create](../../doc/controllers/usergroups.md#usergroups-create)
* [Usergroups Disable](../../doc/controllers/usergroups.md#usergroups-disable)
* [Usergroups Enable](../../doc/controllers/usergroups.md#usergroups-enable)
* [Usergroups List](../../doc/controllers/usergroups.md#usergroups-list)
* [Usergroups Update](../../doc/controllers/usergroups.md#usergroups-update)


# Usergroups Create

Create a User Group

API method documentation: [https://api.slack.com/methods/usergroups.create](https://api.slack.com/methods/usergroups.create)

```csharp
UsergroupsCreateAsync(
    string token,
    string name,
    string channels = null,
    string description = null,
    string handle = null,
    bool? includeCount = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `name` | `string` | Form, Required | A name for the User Group. Must be unique among User Groups. |
| `channels` | `string` | Form, Optional | A comma separated string of encoded channel IDs for which the User Group uses as a default. |
| `description` | `string` | Form, Optional | A short description of the User Group. |
| `handle` | `string` | Form, Optional | A mention handle. Must be unique among channels, users and User Groups. |
| `includeCount` | `bool?` | Form, Optional | Include the number of users in each User Group. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsergroupsCreateSchema](../../doc/models/usergroups-create-schema.md).

## Example Usage

```csharp
string token = "token6";
string name = "name0";
try
{
    ApiResponse<UsergroupsCreateSchema> result = await usergroupsController.UsergroupsCreateAsync(
        token,
        name
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsergroupsCreateErrorSchemaException)
    {
       // TODO: Handle UsergroupsCreateErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsCreateErrorSchemaException`](../../doc/models/usergroups-create-error-schema-exception.md) |


# Usergroups Disable

Disable an existing User Group

API method documentation: [https://api.slack.com/methods/usergroups.disable](https://api.slack.com/methods/usergroups.disable)

```csharp
UsergroupsDisableAsync(
    string token,
    string usergroup,
    bool? includeCount = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `usergroup` | `string` | Form, Required | The encoded ID of the User Group to disable. |
| `includeCount` | `bool?` | Form, Optional | Include the number of users in the User Group. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsergroupsDisableSchema](../../doc/models/usergroups-disable-schema.md).

## Example Usage

```csharp
string token = "token6";
string usergroup = "usergroup2";
try
{
    ApiResponse<UsergroupsDisableSchema> result = await usergroupsController.UsergroupsDisableAsync(
        token,
        usergroup
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsergroupsDisableErrorSchemaException)
    {
       // TODO: Handle UsergroupsDisableErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsDisableErrorSchemaException`](../../doc/models/usergroups-disable-error-schema-exception.md) |


# Usergroups Enable

Enable a User Group

API method documentation: [https://api.slack.com/methods/usergroups.enable](https://api.slack.com/methods/usergroups.enable)

```csharp
UsergroupsEnableAsync(
    string token,
    string usergroup,
    bool? includeCount = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `usergroup` | `string` | Form, Required | The encoded ID of the User Group to enable. |
| `includeCount` | `bool?` | Form, Optional | Include the number of users in the User Group. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsergroupsEnableSchema](../../doc/models/usergroups-enable-schema.md).

## Example Usage

```csharp
string token = "token6";
string usergroup = "usergroup2";
try
{
    ApiResponse<UsergroupsEnableSchema> result = await usergroupsController.UsergroupsEnableAsync(
        token,
        usergroup
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsergroupsEnableErrorSchemaException)
    {
       // TODO: Handle UsergroupsEnableErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsEnableErrorSchemaException`](../../doc/models/usergroups-enable-error-schema-exception.md) |


# Usergroups List

List all User Groups for a team

API method documentation: [https://api.slack.com/methods/usergroups.list](https://api.slack.com/methods/usergroups.list)

```csharp
UsergroupsListAsync(
    string token,
    bool? includeUsers = null,
    bool? includeCount = null,
    bool? includeDisabled = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `usergroups:read` |
| `includeUsers` | `bool?` | Query, Optional | Include the list of users for each User Group. |
| `includeCount` | `bool?` | Query, Optional | Include the number of users in each User Group. |
| `includeDisabled` | `bool?` | Query, Optional | Include disabled User Groups. |

## Requires scope

### slackAuth

`usergroups:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsergroupsListSchema](../../doc/models/usergroups-list-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<UsergroupsListSchema> result = await usergroupsController.UsergroupsListAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsergroupsListErrorSchemaException)
    {
       // TODO: Handle UsergroupsListErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsListErrorSchemaException`](../../doc/models/usergroups-list-error-schema-exception.md) |


# Usergroups Update

Update an existing User Group

API method documentation: [https://api.slack.com/methods/usergroups.update](https://api.slack.com/methods/usergroups.update)

```csharp
UsergroupsUpdateAsync(
    string token,
    string usergroup,
    string handle = null,
    string description = null,
    string channels = null,
    bool? includeCount = null,
    string name = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `usergroup` | `string` | Form, Required | The encoded ID of the User Group to update. |
| `handle` | `string` | Form, Optional | A mention handle. Must be unique among channels, users and User Groups. |
| `description` | `string` | Form, Optional | A short description of the User Group. |
| `channels` | `string` | Form, Optional | A comma separated string of encoded channel IDs for which the User Group uses as a default. |
| `includeCount` | `bool?` | Form, Optional | Include the number of users in the User Group. |
| `name` | `string` | Form, Optional | A name for the User Group. Must be unique among User Groups. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.UsergroupsUpdateSchema](../../doc/models/usergroups-update-schema.md).

## Example Usage

```csharp
string token = "token6";
string usergroup = "usergroup2";
try
{
    ApiResponse<UsergroupsUpdateSchema> result = await usergroupsController.UsergroupsUpdateAsync(
        token,
        usergroup
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is UsergroupsUpdateErrorSchemaException)
    {
       // TODO: Handle UsergroupsUpdateErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsUpdateErrorSchemaException`](../../doc/models/usergroups-update-error-schema-exception.md) |

