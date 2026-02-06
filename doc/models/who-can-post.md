
# Who Can Post

*This model accepts additional fields of type object.*

## Structure

`WhoCanPost`

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
    "type7",
    "type8"
  ],
  "user": [
    "user8",
    "user9"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

