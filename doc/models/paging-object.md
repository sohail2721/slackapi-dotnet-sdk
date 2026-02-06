
# Paging Object

*This model accepts additional fields of type object.*

## Structure

`PagingObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Count` | `int?` | Optional | - |
| `Page` | `int` | Required | - |
| `Pages` | `int?` | Optional | - |
| `PerPage` | `int?` | Optional | - |
| `Spill` | `int?` | Optional | - |
| `Total` | `int` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "count": 190,
  "page": 160,
  "pages": 28,
  "per_page": 72,
  "spill": 132,
  "total": 140,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

