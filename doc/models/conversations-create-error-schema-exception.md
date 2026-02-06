
# Conversations Create Error Schema Exception

Schema for error response from conversations.create method

*This model accepts additional fields of type object.*

## Structure

`ConversationsCreateErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Callstack` | `string` | Optional | Note: PHP callstack is only visible in dev/qa |
| `Detail` | `string` | Optional | - |
| `Error` | [`Error32`](../../doc/models/error-32.md) | Required | - |
| `Needed` | `string` | Optional | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `Provided` | `string` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "invalid_array_arg",
  "ok": "False",
  "callstack": "callstack0",
  "detail": "detail4",
  "needed": "needed4",
  "provided": "provided0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

