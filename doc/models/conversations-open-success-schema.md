
# Conversations Open Success Schema

Schema for successful response from conversations.open method when opening channels, ims, mpims

*This model accepts additional fields of type object.*

## Structure

`ConversationsOpenSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AlreadyOpen` | `bool?` | Optional | - |
| `Channel` | `object` | Required | - |
| `NoOp` | `bool?` | Optional | - |
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
  "already_open": false,
  "no_op": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

