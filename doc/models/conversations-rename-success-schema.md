
# Conversations Rename Success Schema

Schema for successful response from conversations.rename method

*This model accepts additional fields of type object.*

## Structure

`ConversationsRenameSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Channel` | `object` | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "channel": {
    "key1": "val1",
    "key2": "val2"
  },
  "ok": "True",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

