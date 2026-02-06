
# Message Object 1

*This model accepts additional fields of type object.*

## Structure

`MessageObject1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Attachments` | `object` | Optional | - |
| `Blocks` | `object` | Optional | - |
| `Text` | `string` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "attachments": [
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "blocks": {
    "key1": "val1",
    "key2": "val2"
  },
  "text": "text4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

