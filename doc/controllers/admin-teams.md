# Admin Teams

```csharp
AdminTeamsController adminTeamsController = client.AdminTeamsController;
```

## Class Name

`AdminTeamsController`

## Methods

* [Admin Teams Create](../../doc/controllers/admin-teams.md#admin-teams-create)
* [Admin Teams List](../../doc/controllers/admin-teams.md#admin-teams-list)


# Admin Teams Create

Create an Enterprise team.

API method documentation: [https://api.slack.com/methods/admin.teams.create](https://api.slack.com/methods/admin.teams.create)

```csharp
AdminTeamsCreateAsync(
    string token,
    string teamDomain,
    string teamName,
    string teamDescription = null,
    string teamDiscoverability = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.teams:write` |
| `teamDomain` | `string` | Form, Required | Team domain (for example, slacksoftballteam). |
| `teamName` | `string` | Form, Required | Team name (for example, Slack Softball Team). |
| `teamDescription` | `string` | Form, Optional | Description for the team. |
| `teamDiscoverability` | `string` | Form, Optional | Who can join the team. A team's discoverability can be `open`, `closed`, `invite_only`, or `unlisted`. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string teamDomain = "team_domain2";
string teamName = "team_name6";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await adminTeamsController.AdminTeamsCreateAsync(
        token,
        teamDomain,
        teamName
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


# Admin Teams List

List all teams on an Enterprise organization

API method documentation: [https://api.slack.com/methods/admin.teams.list](https://api.slack.com/methods/admin.teams.list)

```csharp
AdminTeamsListAsync(
    string token,
    int? limit = null,
    string cursor = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.teams:read` |
| `limit` | `int?` | Query, Optional | The maximum number of items to return. Must be between 1 - 100 both inclusive. |
| `cursor` | `string` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |

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
    ApiResponse<DefaultSuccessTemplate> result = await adminTeamsController.AdminTeamsListAsync(token);
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

