
# Conversations List Success Schema

Schema for successful response from conversations.list method

*This model accepts additional fields of type object.*

## Structure

`ConversationsListSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Channels` | `object` | Required | **Constraints**: *Unique Items Required* |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `ResponseMetadata` | [`ResponseMetadata`](../../doc/models/response-metadata.md) | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "channels": [
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "ok": "True",
  "response_metadata": {
    "next_cursor": "next_cursor2",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

