
# Files Shared Public Url Schema

Schema for successful response from files.sharedPublicURL method

*This model accepts additional fields of type object.*

## Structure

`FilesSharedPublicUrlSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `File` | [`FileObject`](../../doc/models/file-object.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "file": {
    "channels": [
      "channels5",
      "channels4"
    ],
    "comments_count": 56,
    "created": 220,
    "date_delete": 118,
    "display_as_bot": false,
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "ok": "True",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

