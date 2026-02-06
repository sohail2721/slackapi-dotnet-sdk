
# Topic

*This model accepts additional fields of type object.*

## Structure

`Topic`

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
  "creator": "creator8",
  "last_set": 254,
  "value": "value2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

