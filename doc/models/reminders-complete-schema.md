
# Reminders Complete Schema

Schema for successful response from reminders.complete method

*This model accepts additional fields of type object.*

## Structure

`RemindersCompleteSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

