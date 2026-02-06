
# Profile 1

*This model accepts additional fields of type object.*

## Structure

`Profile1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AvatarHash` | `string` | Required | **Constraints**: *Pattern*: `^[0-9a-f]{12}$` |
| `Image1024` | `string` | Required | - |
| `Image192` | `string` | Required | - |
| `Image24` | `string` | Required | - |
| `Image32` | `string` | Required | - |
| `Image48` | `string` | Required | - |
| `Image512` | `string` | Required | - |
| `Image72` | `string` | Required | - |
| `ImageOriginal` | `string` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "avatar_hash": "avatar_hash6",
  "image_1024": "image_10242",
  "image_192": "image_1922",
  "image_24": "image_242",
  "image_32": "image_322",
  "image_48": "image_484",
  "image_512": "image_5128",
  "image_72": "image_720",
  "image_original": "image_original2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

