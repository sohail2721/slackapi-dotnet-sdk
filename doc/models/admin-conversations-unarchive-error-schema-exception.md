
# Admin Conversations Unarchive Error Schema Exception

Schema for error response from admin.conversations.getConversationPrefs

*This model accepts additional fields of type object.*

## Structure

`AdminConversationsUnarchiveErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Error` | [`Error5`](../../doc/models/error-5.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "missing_scope",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

