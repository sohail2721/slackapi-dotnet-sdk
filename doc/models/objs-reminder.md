
# Objs Reminder

*This model accepts additional fields of type object.*

## Structure

`ObjsReminder`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `CompleteTs` | `int?` | Optional | - |
| `Creator` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `Id` | `string` | Required | **Constraints**: *Pattern*: `^Rm[A-Z0-9]{8,}$` |
| `Recurring` | `bool` | Required | - |
| `Text` | `string` | Required | - |
| `Time` | `int?` | Optional | - |
| `User` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "complete_ts": 102,
  "creator": "creator4",
  "id": "id6",
  "recurring": false,
  "text": "text4",
  "time": 252,
  "user": "user6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

