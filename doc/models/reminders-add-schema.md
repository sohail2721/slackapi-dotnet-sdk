
# Reminders Add Schema

Schema for successful response from reminders.add method

*This model accepts additional fields of type object.*

## Structure

`RemindersAddSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Reminder` | [`ObjsReminder`](../../doc/models/objs-reminder.md) | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "reminder": {
    "complete_ts": 136,
    "creator": "creator8",
    "id": "id0",
    "recurring": false,
    "text": "text0",
    "time": 38,
    "user": "user0",
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

