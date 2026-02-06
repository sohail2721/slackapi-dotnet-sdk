
# Conversations Set Topic Error Schema Exception

Schema for error response from conversations.setTopic method

*This model accepts additional fields of type object.*

## Structure

`ConversationsSetTopicErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Callstack` | `string` | Optional | Note: PHP callstack is only visible in dev/qa |
| `Error` | [`Error46`](../../doc/models/error-46.md) | Required | - |
| `Needed` | `string` | Optional | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `Provided` | `string` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "upgrade_required",
  "ok": "False",
  "callstack": "callstack6",
  "needed": "needed0",
  "provided": "provided6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

