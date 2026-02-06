
# Message

*This model accepts additional fields of type object.*

## Structure

`Message`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `BotId` | `string` | Required | **Constraints**: *Pattern*: `^B[A-Z0-9]{8,}$` |
| `BotProfile` | [`BotProfileObject`](../../doc/models/bot-profile-object.md) | Optional | - |
| `Team` | `string` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `Text` | `string` | Required | - |
| `Type` | `string` | Required | - |
| `User` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `Username` | `string` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "bot_id": "bot_id0",
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
  "team": "team4",
  "text": "text4",
  "type": "type4",
  "user": "user6",
  "username": "username4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

