
# Reminders List Schema

Schema for successful response from reminders.list method

*This model accepts additional fields of type object.*

## Structure

`RemindersListSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Reminders` | [`List<ObjsReminder>`](../../doc/models/objs-reminder.md) | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "reminders": [
    {
      "complete_ts": 28,
      "creator": "creator0",
      "id": "id2",
      "recurring": false,
      "text": "text2",
      "time": 186,
      "user": "user2",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

