
# Users Info Error Schema Exception

Schema for error response from users.info method

*This model accepts additional fields of type object.*

## Structure

`UsersInfoErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Callstack` | `string` | Optional | - |
| `Error` | [`Error92`](../../doc/models/error-92.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "not_authed",
  "ok": "False",
  "callstack": "callstack4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

