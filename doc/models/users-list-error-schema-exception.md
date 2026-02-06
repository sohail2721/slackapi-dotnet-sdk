
# Users List Error Schema Exception

Schema for error response from users.list method

*This model accepts additional fields of type object.*

## Structure

`UsersListErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Callstack` | `string` | Optional | Note: PHP callstack is only visible in dev/qa |
| `Error` | [`Error93`](../../doc/models/error-93.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "invalid_arg_name",
  "ok": "False",
  "callstack": "callstack6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

