
# Chat Delete Success Schema

Schema for successful response of chat.delete method

*This model accepts additional fields of type object.*

## Structure

`ChatDeleteSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Channel` | `string` | Required | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Ts` | `string` | Required | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "channel": "channel4",
  "ok": "True",
  "ts": "ts2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

