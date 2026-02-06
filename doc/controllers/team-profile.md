# Team Profile

```csharp
TeamProfileController teamProfileController = client.TeamProfileController;
```

## Class Name

`TeamProfileController`


# Team Profile Get

Retrieve a team's profile.

API method documentation: [https://api.slack.com/methods/team.profile.get](https://api.slack.com/methods/team.profile.get)

```csharp
TeamProfileGetAsync(
    string token,
    string visibility = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `users.profile:read` |
| `visibility` | `string` | Query, Optional | Filter by visibility. |

## Requires scope

### slackAuth

`users.profile:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.TeamProfileGetSuccessSchema](../../doc/models/team-profile-get-success-schema.md).

## Example Usage

```csharp
string token = "token6";
try
{
    ApiResponse<TeamProfileGetSuccessSchema> result = await teamProfileController.TeamProfileGetAsync(token);
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is TeamProfileGetErrorSchemaException)
    {
       // TODO: Handle TeamProfileGetErrorSchemaException exception here
    }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`TeamProfileGetErrorSchemaException`](../../doc/models/team-profile-get-error-schema-exception.md) |

