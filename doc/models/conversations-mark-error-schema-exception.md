
# Conversations Mark Error Schema Exception

Schema for error response from conversations.mark method

*This model accepts additional fields of type object.*

## Structure

`ConversationsMarkErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Callstack` | `string` | Optional | Note: PHP callstack is only visible in dev/qa |
| `Error` | [`Error41`](../../doc/models/error-41.md) | Required | - |
| `Needed` | `string` | Optional | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `Provided` | `string` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "not_allowed_token_type",
  "ok": "False",
  "callstack": "callstack4",
  "needed": "needed2",
  "provided": "provided4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

