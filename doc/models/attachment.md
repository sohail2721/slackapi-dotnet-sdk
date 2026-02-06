
# Attachment

*This model accepts additional fields of type object.*

## Structure

`Attachment`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Fallback` | `string` | Optional | - |
| `Id` | `int` | Required | - |
| `ImageBytes` | `int?` | Optional | - |
| `ImageHeight` | `int?` | Optional | - |
| `ImageUrl` | `string` | Optional | - |
| `ImageWidth` | `int?` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "fallback": "fallback4",
  "id": 158,
  "image_bytes": 168,
  "image_height": 20,
  "image_url": "image_url6",
  "image_width": 146,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

