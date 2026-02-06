
# Objs Team Profile Field

*This model accepts additional fields of type object.*

## Structure

`ObjsTeamProfileField`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `FieldName` | `string` | Optional | - |
| `Hint` | `string` | Required | - |
| `Id` | `string` | Required | **Constraints**: *Pattern*: `^X[a-zA-Z0-9]{9,}$` |
| `IsHidden` | `bool?` | Optional | - |
| `Label` | `string` | Required | - |
| `Options` | `object` | Optional | - |
| `Ordering` | `double` | Required | - |
| `PossibleValues` | `List<string>` | Optional | - |
| `Type` | [`Type`](../../doc/models/type.md) | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "field_name": "field_name4",
  "hint": "hint0",
  "id": "id0",
  "is_hidden": false,
  "label": "label0",
  "options": {
    "key1": "val1",
    "key2": "val2"
  },
  "ordering": 211.1,
  "possible_values": [
    "possible_values1",
    "possible_values2"
  ],
  "type": "options_list",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

