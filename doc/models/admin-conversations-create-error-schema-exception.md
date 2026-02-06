
# Admin Conversations Create Error Schema Exception

Schema for error response from admin.conversations.create

*This model accepts additional fields of type object.*

## Structure

`AdminConversationsCreateErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Error` | [`Error2`](../../doc/models/error-2.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "could_not_create_channel",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

