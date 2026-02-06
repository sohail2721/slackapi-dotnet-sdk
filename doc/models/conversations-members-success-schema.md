
# Conversations Members Success Schema

Schema for successful response conversations.members method

*This model accepts additional fields of type object.*

## Structure

`ConversationsMembersSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Members` | `List<string>` | Required | **Constraints**: *Minimum Items*: `1`, *Unique Items Required*, *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `ResponseMetadata` | [`ResponseMetadata`](../../doc/models/response-metadata.md) | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "members": [
    "members8",
    "members9"
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

