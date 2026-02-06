
# Admin Conversations Delete Error Schema Exception

Schema for error response from admin.conversations.delete

*This model accepts additional fields of type object.*

## Structure

`AdminConversationsDeleteErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Error` | [`Error3`](../../doc/models/error-3.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "could_not_delete_channel",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

