
# Profile

*This model accepts additional fields of type object.*

## Structure

`Profile`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Fields` | [`List<ObjsTeamProfileField>`](../../doc/models/objs-team-profile-field.md) | Required | **Constraints**: *Unique Items Required* |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "fields": [
    {
      "field_name": "field_name2",
      "hint": "hint8",
      "id": "id8",
      "is_hidden": false,
      "label": "label8",
      "options": {
        "key1": "val1",
        "key2": "val2"
      },
      "ordering": 158.68,
      "possible_values": [
        "possible_values9",
        "possible_values0"
      ],
      "type": "options_list",
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

