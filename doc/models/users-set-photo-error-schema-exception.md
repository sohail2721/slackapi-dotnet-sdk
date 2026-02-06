
# Users Set Photo Error Schema Exception

Schema for error response from users.setPhoto method

*This model accepts additional fields of type object.*

## Structure

`UsersSetPhotoErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Callstack` | `string` | Optional | Note: PHP callstack is only visible in dev/qa |
| `DebugStep` | `string` | Optional | possibly DEV/QA only |
| `Dims` | `string` | Optional | possibly DEV/QA only |
| `Error` | [`Error98`](../../doc/models/error-98.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `TimeIdent` | `int?` | Optional | possibly DEV/QA only |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "account_inactive",
  "ok": "False",
  "callstack": "callstack4",
  "debug_step": "debug_step0",
  "dims": "dims8",
  "time_ident": 18,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

