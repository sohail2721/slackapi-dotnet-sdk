
# Chat Me Message Schema

Schema for successful response from chat.meMessage method

*This model accepts additional fields of type object.*

## Structure

`ChatMeMessageSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Channel` | `string` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Ts` | `string` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "channel": "channel0",
  "ts": "ts6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

