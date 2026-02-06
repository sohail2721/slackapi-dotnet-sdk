
# Admin Conversations Set Conversation Prefs Error Schema Exception

Schema for error response from admin.conversations.setConversationPrefs

*This model accepts additional fields of type object.*

## Structure

`AdminConversationsSetConversationPrefsErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Error` | [`Error10`](../../doc/models/error-10.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "channel_not_found",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

