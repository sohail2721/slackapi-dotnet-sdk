
# Conversations Set Purpose Error Schema Exception

Schema for error response from conversations.setPurpose method

*This model accepts additional fields of type object.*

## Structure

`ConversationsSetPurposeErrorSchemaException`

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
  "error": "request_timeout",
  "ok": "False",
  "callstack": "callstack0",
  "needed": "needed4",
  "provided": "provided0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

