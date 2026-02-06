
# Admin Conversations Archive Error Schema Exception

Schema for error response from admin.conversations.archive

*This model accepts additional fields of type object.*

## Structure

`AdminConversationsArchiveErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Error` | [`Error`](../../doc/models/error.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "already_archived",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

