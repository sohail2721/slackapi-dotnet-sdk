
# Users Set Active Error Schema Exception

Schema for error response from users.setActive method

*This model accepts additional fields of type object.*

## Structure

`UsersSetActiveErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Callstack` | `string` | Optional | Note: PHP callstack is only visible in dev/qa |
| `Error` | [`Error97`](../../doc/models/error-97.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "invalid_charset",
  "ok": "False",
  "callstack": "callstack2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

