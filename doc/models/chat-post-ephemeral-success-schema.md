
# Chat Post Ephemeral Success Schema

Schema for successful response from chat.postEphemeral method

*This model accepts additional fields of type object.*

## Structure

`ChatPostEphemeralSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `MessageTs` | `string` | Required | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "message_ts": "message_ts0",
  "ok": "True",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

