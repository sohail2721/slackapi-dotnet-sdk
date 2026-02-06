
# Shares

*This model accepts additional fields of type object.*

## Structure

`Shares`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Private` | `object` | Optional | - |
| `Public` | `object` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "private": {
    "key1": "val1",
    "key2": "val2"
  },
  "public": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

