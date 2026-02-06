
# Purpose

*This model accepts additional fields of type object.*

## Structure

`Purpose`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Creator` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{8,}$\|^$` |
| `LastSet` | `int` | Required | - |
| `MValue` | `string` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "creator": "creator6",
  "last_set": 108,
  "value": "value0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

