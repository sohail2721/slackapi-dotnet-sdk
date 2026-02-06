
# Conversations Join Success Schema

Schema for successful response from conversations.join method

*This model accepts additional fields of type object.*

## Structure

`ConversationsJoinSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Channel` | `object` | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `ResponseMetadata` | [`ResponseMetadata3`](../../doc/models/response-metadata-3.md) | Optional | - |
| `Warning` | `string` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "channel": {
    "key1": "val1",
    "key2": "val2"
  },
  "ok": "True",
  "response_metadata": {
    "warnings": [
      "warnings8",
      "warnings9",
      "warnings0"
    ],
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "warning": "warning4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

