
# Admin Conversations Disconnect Shared Error Schema Exception

Schema for error response from admin.conversations.disconnectShared

*This model accepts additional fields of type object.*

## Structure

`AdminConversationsDisconnectSharedErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Error` | [`Error4`](../../doc/models/error-4.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "leaving_team_not_in_channel",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

