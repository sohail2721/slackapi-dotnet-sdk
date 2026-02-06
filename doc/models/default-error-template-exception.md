
# Default Error Template Exception

This method either only returns a brief _not OK_ response or a verbose schema is not available for this method.

*This model accepts additional fields of type object.*

## Structure

`DefaultErrorTemplateException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

