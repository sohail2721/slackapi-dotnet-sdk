
# Admin Conversations Unarchive Error Schema 2 Exception

Schema for error response from admin.conversations.rename

*This model accepts additional fields of type object.*

## Structure

`AdminConversationsUnarchiveErrorSchema2Exception`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Error` | [`Error8`](../../doc/models/error-8.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "name_taken",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

