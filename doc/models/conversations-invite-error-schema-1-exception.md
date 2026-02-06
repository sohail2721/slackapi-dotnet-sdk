
# Conversations Invite Error Schema 1 Exception

Schema for error response from conversations.invite method

*This model accepts additional fields of type object.*

## Structure

`ConversationsInviteErrorSchema1Exception`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Callstack` | `string` | Optional | Note: PHP callstack is only visible in dev/qa |
| `Error` | [`Error35?`](../../doc/models/error-35.md) | Optional | - |
| `Errors` | [`List<ErrorsIsReturnedWhenAnErrorAssociatesAnUser>`](../../doc/models/errors-is-returned-when-an-error-associates-an-user.md) | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `Needed` | `string` | Optional | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `Provided` | `string` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "False",
  "callstack": "callstack2",
  "error": "invalid_post_type",
  "errors": [
    {
      "error": "user_not_found",
      "ok": "ok6",
      "user": "user0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "error": "user_not_found",
      "ok": "ok6",
      "user": "user0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "error": "user_not_found",
      "ok": "ok6",
      "user": "user0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "needed": "needed6",
  "provided": "provided2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

