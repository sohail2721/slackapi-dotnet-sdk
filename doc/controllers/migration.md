# Migration

```csharp
MigrationController migrationController = client.MigrationController;
```

## Class Name

`MigrationController`


# Migration Exchange

For Enterprise Grid workspaces, map local user IDs to global user IDs

API method documentation: [https://api.slack.com/methods/migration.exchange](https://api.slack.com/methods/migration.exchange)

```csharp
MigrationExchangeAsync(
    string token,
    string users,
    string teamId = null,
    bool? toOld = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `tokens.basic` |
| `users` | `string` | Query, Required | A comma-separated list of user ids, up to 400 per request |
| `teamId` | `string` | Query, Optional | Specify team_id starts with `T` in case of Org Token |
| `toOld` | `bool?` | Query, Optional | Specify `true` to convert `W` global user IDs to workspace-specific `U` IDs. Defaults to `false`. |

## Requires scope

### slackAuth

`tokens.basic`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.MigrationExchangeSuccessSchema](../../doc/models/migration-exchange-success-schema.md).

## Example Usage

```csharp
string token = "token6";
string users = "users6";
try
{
    ApiResponse<MigrationExchangeSuccessSchema> result = await migrationController.MigrationExchangeAsync(
        token,
        users
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is MigrationExchangeErrorSchemaException)
    {
       // TODO: Handle MigrationExchangeErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when there are no mappings to provide | [`MigrationExchangeErrorSchemaException`](../../doc/models/migration-exchange-error-schema-exception.md) |

