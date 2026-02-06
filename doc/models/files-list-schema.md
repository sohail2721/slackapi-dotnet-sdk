
# Files List Schema

Schema for successful response from files.list method

*This model accepts additional fields of type object.*

## Structure

`FilesListSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Files` | [`List<FileObject>`](../../doc/models/file-object.md) | Required | **Constraints**: *Minimum Items*: `0`, *Unique Items Required* |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Paging` | [`PagingObject`](../../doc/models/paging-object.md) | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "files": [
    {
      "channels": [
        "channels9"
      ],
      "comments_count": 150,
      "created": 58,
      "date_delete": 212,
      "display_as_bot": false,
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "ok": "True",
  "paging": {
    "count": 56,
    "page": 26,
    "pages": 150,
    "per_page": 194,
    "spill": 246,
    "total": 6,
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

