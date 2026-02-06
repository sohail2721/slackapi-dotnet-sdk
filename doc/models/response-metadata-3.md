
# Response Metadata 3

*This model accepts additional fields of type object.*

## Structure

`ResponseMetadata3`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Warnings` | `List<string>` | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "warnings": [
    "warnings4",
    "warnings5"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

