
# Dnd Set Snooze Schema

Schema for successful response from dnd.setSnooze method

*This model accepts additional fields of type object.*

## Structure

`DndSetSnoozeSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `SnoozeEnabled` | `bool` | Required | - |
| `SnoozeEndtime` | `int` | Required | - |
| `SnoozeRemaining` | `int` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "snooze_enabled": false,
  "snooze_endtime": 8,
  "snooze_remaining": 8,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

