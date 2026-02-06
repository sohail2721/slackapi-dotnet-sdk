
# Admin Conversations Get Teams Error Schema Exception

Schema for error response from admin.conversations.getTeams

*This model accepts additional fields of type object.*

## Structure

`AdminConversationsGetTeamsErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Error` | [`Error6`](../../doc/models/error-6.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "channel_type_not_supported",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

