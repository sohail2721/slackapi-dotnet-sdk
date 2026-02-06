
# Chat Get Permalink Success Schema

Schema for successful response chat.getPermalink

*This model accepts additional fields of type object.*

## Structure

`ChatGetPermalinkSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Channel` | `string` | Required | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Permalink` | `string` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "channel": "channel8",
  "ok": "True",
  "permalink": "permalink4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

