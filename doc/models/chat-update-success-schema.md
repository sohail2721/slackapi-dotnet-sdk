
# Chat Update Success Schema

Schema for successful response of chat.update method

*This model accepts additional fields of type object.*

## Structure

`ChatUpdateSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Channel` | `string` | Required | - |
| `Message` | [`MessageObject1`](../../doc/models/message-object-1.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Text` | `string` | Required | - |
| `Ts` | `string` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "channel": "channel8",
  "message": {
    "attachments": [
      {
        "key1": "val1",
        "key2": "val2"
      },
      {
        "key1": "val1",
        "key2": "val2"
      }
    ],
    "blocks": {
      "key1": "val1",
      "key2": "val2"
    },
    "text": "text0",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "ok": "True",
  "text": "text6",
  "ts": "ts8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

