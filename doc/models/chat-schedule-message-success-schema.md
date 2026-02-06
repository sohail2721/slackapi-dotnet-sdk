
# Chat Schedule Message Success Schema

Schema for successful response of chat.scheduleMessage method

*This model accepts additional fields of type object.*

## Structure

`ChatScheduleMessageSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Channel` | `string` | Required | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `Message` | [`Message`](../../doc/models/message.md) | Required | - |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `PostAt` | `int` | Required | - |
| `ScheduledMessageId` | `string` | Required | **Constraints**: *Pattern*: `^[Q][A-Z0-9]{8,}$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "channel": "channel4",
  "message": {
    "bot_id": "bot_id6",
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
    "team": "team0",
    "text": "text0",
    "type": "type0",
    "user": "user0",
    "username": "username0",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "ok": "True",
  "post_at": 128,
  "scheduled_message_id": "scheduled_message_id2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

