
# Response Metadata

*This model accepts additional fields of type object.*

## Structure

`ResponseMetadata`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `NextCursor` | `string` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "next_cursor": "next_cursor0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

