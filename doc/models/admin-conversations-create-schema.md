
# Admin Conversations Create Schema

Schema for successful response of admin.conversations.create

*This model accepts additional fields of type object.*

## Structure

`AdminConversationsCreateSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ChannelId` | `string` | Optional | **Constraints**: *Pattern*: `^[C][A-Z0-9]{2,}$` |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "channel_id": "channel_id6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

