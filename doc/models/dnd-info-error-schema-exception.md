
# Dnd Info Error Schema Exception

Schema for error response from dnd.info method

*This model accepts additional fields of type object.*

## Structure

`DndInfoErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Callstack` | `string` | Optional | Note: PHP callstack is only visible in dev/qa |
| `Error` | [`Error52`](../../doc/models/error-52.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "org_login_required",
  "ok": "False",
  "callstack": "callstack8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

