
# Errors Is Returned When an Error Associates an User

*This model accepts additional fields of type object.*

## Structure

`ErrorsIsReturnedWhenAnErrorAssociatesAnUser`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Error` | [`Error35`](../../doc/models/error-35.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `User` | `string` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "cant_invite",
  "ok": "False",
  "user": "user8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

