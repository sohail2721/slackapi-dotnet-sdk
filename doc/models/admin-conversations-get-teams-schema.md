
# Admin Conversations Get Teams Schema

Schema for successful response of admin.conversations.getTeams

*This model accepts additional fields of type object.*

## Structure

`AdminConversationsGetTeamsSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `ResponseMetadata` | [`ResponseMetadata`](../../doc/models/response-metadata.md) | Optional | - |
| `TeamIds` | `List<string>` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "team_ids": [
    "team_ids9",
    "team_ids0"
  ],
  "response_metadata": {
    "next_cursor": "next_cursor2",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

