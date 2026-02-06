
# Dnd Info Schema

Schema for successful response from dnd.info method

*This model accepts additional fields of type object.*

## Structure

`DndInfoSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `DndEnabled` | `bool` | Required | - |
| `NextDndEndTs` | `int` | Required | - |
| `NextDndStartTs` | `int` | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `SnoozeEnabled` | `bool?` | Optional | - |
| `SnoozeEndtime` | `int?` | Optional | - |
| `SnoozeRemaining` | `int?` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "dnd_enabled": false,
  "next_dnd_end_ts": 138,
  "next_dnd_start_ts": 198,
  "ok": "True",
  "snooze_enabled": false,
  "snooze_endtime": 96,
  "snooze_remaining": 96,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

