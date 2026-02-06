
# Team 1

*This model accepts additional fields of type object.*

## Structure

`Team1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Domain` | `string` | Required | - |
| `Id` | `string` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `Name` | `string` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "domain": "domain0",
  "id": "id4",
  "name": "name4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

