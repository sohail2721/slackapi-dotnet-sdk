# Search

```csharp
SearchController searchController = client.SearchController;
```

## Class Name

`SearchController`


# Search Messages

Searches for messages matching a query.

API method documentation: [https://api.slack.com/methods/search.messages](https://api.slack.com/methods/search.messages)

```csharp
SearchMessagesAsync(
    string token,
    string query,
    int? count = null,
    bool? highlight = null,
    int? page = null,
    string sort = null,
    string sortDir = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `search:read` |
| `query` | `string` | Query, Required | Search query. |
| `count` | `int?` | Query, Optional | Pass the number of results you want per "page". Maximum of `100`. |
| `highlight` | `bool?` | Query, Optional | Pass a value of `true` to enable query highlight markers (see below). |
| `page` | `int?` | Query, Optional | - |
| `sort` | `string` | Query, Optional | Return matches sorted by either `score` or `timestamp`. |
| `sortDir` | `string` | Query, Optional | Change sort direction to ascending (`asc`) or descending (`desc`). |

## Requires scope

### slackAuth

`search:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.DefaultSuccessTemplate](../../doc/models/default-success-template.md).

## Example Usage

```csharp
string token = "token6";
string query = "query0";
try
{
    ApiResponse<DefaultSuccessTemplate> result = await searchController.SearchMessagesAsync(
        token,
        query
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

