
# Conversations Close Success Schema

Schema for successful response conversations.close method

*This model accepts additional fields of type object.*

## Structure

`ConversationsCloseSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AlreadyClosed` | `bool?` | Optional | - |
| `NoOp` | `bool?` | Optional | - |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "already_closed": false,
  "no_op": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

