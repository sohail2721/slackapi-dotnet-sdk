
# Admin Conversations Unarchive Error Schema 3 Exception

Schema for error response from admin.conversations.unarchive

*This model accepts additional fields of type object.*

## Structure

`AdminConversationsUnarchiveErrorSchema3Exception`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Error` | [`Error11`](../../doc/models/error-11.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "restricted_action",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

