
# Can Thread

*This model accepts additional fields of type object.*

## Structure

`CanThread`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Type` | `List<string>` | Optional | - |
| `User` | `List<string>` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "type": [
    "type7"
  ],
  "user": [
    "user2",
    "user3",
    "user4"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

