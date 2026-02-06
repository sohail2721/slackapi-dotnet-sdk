
# Prefs

*This model accepts additional fields of type object.*

## Structure

`Prefs`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Channels` | `List<string>` | Required | **Constraints**: *Pattern*: `^[C][A-Z0-9]{2,}$` |
| `Groups` | `List<string>` | Required | **Constraints**: *Pattern*: `^[G][A-Z0-9]{8,}$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "channels": [
    "channels3",
    "channels4",
    "channels5"
  ],
  "groups": [
    "groups6",
    "groups7"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

