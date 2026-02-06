
# Admin Conversations Search Schema

Schema for successful response of admin.conversations.search

*This model accepts additional fields of type object.*

## Structure

`AdminConversationsSearchSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Channels` | [`List<ChannelObject>`](../../doc/models/channel-object.md) | Required | - |
| `NextCursor` | `string` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "channels": [
    {
      "accepted_user": "accepted_user8",
      "created": 90,
      "creator": "creator8",
      "id": "id0",
      "is_archived": false,
      "is_channel": false,
      "is_frozen": false,
      "is_general": false,
      "is_member": false,
      "is_mpim": false,
      "is_org_shared": false,
      "is_private": false,
      "is_shared": false,
      "members": [
        "members8"
      ],
      "name": "name0",
      "name_normalized": "name_normalized8",
      "purpose": {
        "creator": "creator4",
        "last_set": 30,
        "value": "value8",
        "exampleAdditionalProperty": {
          "key1": "val1",
          "key2": "val2"
        }
      },
      "topic": {
        "creator": "creator6",
        "last_set": 242,
        "value": "value0",
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
  ],
  "next_cursor": "next_cursor6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

