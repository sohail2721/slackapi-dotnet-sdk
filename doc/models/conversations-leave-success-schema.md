
# Conversations Leave Success Schema

Schema for successful response from conversations.leave method

*This model accepts additional fields of type object.*

## Structure

`ConversationsLeaveSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `NotInChannel` | `bool?` | Optional | - |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "not_in_channel": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

