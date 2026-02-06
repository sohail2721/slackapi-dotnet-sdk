
# Admin Conversations Convert to Private Error Schema Exception

Schema for error response from admin.conversations.convertToPrivate

*This model accepts additional fields of type object.*

## Structure

`AdminConversationsConvertToPrivateErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Error` | [`Error1`](../../doc/models/error-1.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"False"` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "default_org_wide_channel",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

