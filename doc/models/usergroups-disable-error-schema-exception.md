
# Usergroups Disable Error Schema Exception

Schema for error response from usergroups.disable method

*This model accepts additional fields of type object.*

## Structure

`UsergroupsDisableErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Callstack` | `string` | Optional | Note: PHP callstack is only visible in dev/qa |
| `Error` | [`Error82`](../../doc/models/error-82.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "org_login_required",
  "ok": "False",
  "callstack": "callstack0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

