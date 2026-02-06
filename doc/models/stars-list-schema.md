
# Stars List Schema

Schema for successful response from stars.list method

*This model accepts additional fields of type object.*

## Structure

`StarsListSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Items` | `object` | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Paging` | [`PagingObject`](../../doc/models/paging-object.md) | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "items": [
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
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

