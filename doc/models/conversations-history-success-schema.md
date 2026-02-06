
# Conversations History Success Schema

Schema for successful response from conversations.history method

*This model accepts additional fields of type object.*

## Structure

`ConversationsHistorySuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ChannelActionsCount` | `int` | Required | - |
| `ChannelActionsTs` | `object` | Required | - |
| `HasMore` | `bool` | Required | - |
| `Messages` | [`List<MessageObject>`](../../doc/models/message-object.md) | Required | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `PinCount` | `int` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "channel_actions_count": 90,
  "channel_actions_ts": {
    "key1": "val1",
    "key2": "val2"
  },
  "has_more": false,
  "messages": [
    {
      "attachments": [
        {
          "fallback": "fallback4",
          "id": 36,
          "image_bytes": 34,
          "image_height": 154,
          "image_url": "image_url6",
          "image_width": 24,
          "exampleAdditionalProperty": {
            "key1": "val1",
            "key2": "val2"
          }
        },
        {
          "fallback": "fallback4",
          "id": 36,
          "image_bytes": 34,
          "image_height": 154,
          "image_url": "image_url6",
          "image_width": 24,
          "exampleAdditionalProperty": {
            "key1": "val1",
            "key2": "val2"
          }
        }
      ],
      "blocks": [
        {
          "type": "type4",
          "exampleAdditionalProperty": {
            "key1": "val1",
            "key2": "val2"
          }
        },
        {
          "type": "type4",
          "exampleAdditionalProperty": {
            "key1": "val1",
            "key2": "val2"
          }
        }
      ],
      "bot_id": {
        "key1": "val1",
        "key2": "val2"
      },
      "bot_profile": {
        "app_id": "app_id8",
        "deleted": false,
        "icons": {
          "image_36": "image_362",
          "image_48": "image_488",
          "image_72": "image_722",
          "exampleAdditionalProperty": {
            "key1": "val1",
            "key2": "val2"
          }
        },
        "id": "id8",
        "name": "name8",
        "team_id": "team_id8",
        "updated": 44,
        "exampleAdditionalProperty": {
          "key1": "val1",
          "key2": "val2"
        }
      },
      "client_msg_id": "client_msg_id4",
      "text": "text8",
      "ts": "ts0",
      "type": "type8",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "ok": "True",
  "pin_count": 156,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

