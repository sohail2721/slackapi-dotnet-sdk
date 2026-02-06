
# Reaction Object

*This model accepts additional fields of type object.*

## Structure

`ReactionObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Count` | `int` | Required | - |
| `Name` | `string` | Required | - |
| `Users` | `List<string>` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "count": 186,
  "name": "name6",
  "users": [
    "users3",
    "users2"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

