
# Icons

*This model accepts additional fields of type object.*

## Structure

`Icons`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Image36` | `string` | Required | - |
| `Image48` | `string` | Required | - |
| `Image72` | `string` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "image_36": "image_360",
  "image_48": "image_480",
  "image_72": "image_726",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

