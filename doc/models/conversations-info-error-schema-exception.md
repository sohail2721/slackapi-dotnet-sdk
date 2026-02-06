
# Conversations Info Error Schema Exception

Schema for error response from conversations.info method

*This model accepts additional fields of type object.*

## Structure

`ConversationsInfoErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Callstack` | `string` | Optional | Note: PHP callstack is only visible in dev/qa |
| `Error` | [`Error34`](../../doc/models/error-34.md) | Required | - |
| `Needed` | `string` | Optional | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `Provided` | `string` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "team_added_to_org",
  "ok": "False",
  "callstack": "callstack8",
  "needed": "needed8",
  "provided": "provided8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

