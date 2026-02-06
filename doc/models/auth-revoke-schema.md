
# Auth Revoke Schema

Schema for successful response from auth.revoke method

*This model accepts additional fields of type object.*

## Structure

`AuthRevokeSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Revoked` | `bool` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "revoked": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

