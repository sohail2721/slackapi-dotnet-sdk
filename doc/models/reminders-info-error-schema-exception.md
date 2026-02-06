
# Reminders Info Error Schema Exception

Schema for error response from reminders.info method

*This model accepts additional fields of type object.*

## Structure

`RemindersInfoErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Callstack` | `string` | Optional | Note: PHP callstack is only visible in dev/qa |
| `Error` | [`Error71`](../../doc/models/error-71.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "invalid_auth",
  "ok": "False",
  "callstack": "callstack0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

