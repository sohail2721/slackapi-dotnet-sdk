
# Message Object

*This model accepts additional fields of type object.*

## Structure

`MessageObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Attachments` | [`List<Attachment>`](../../doc/models/attachment.md) | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `Blocks` | [`List<BlockKitBlock>`](../../doc/models/block-kit-block.md) | Optional | This is a very loose definition, in the future, we'll populate this with deeper schema in this definition namespace. |
| `BotId` | `object` | Optional | - |
| `BotProfile` | [`BotProfileObject`](../../doc/models/bot-profile-object.md) | Optional | - |
| `ClientMsgId` | `string` | Optional | - |
| `Comment` | [`FileCommentObject`](../../doc/models/file-comment-object.md) | Optional | - |
| `DisplayAsBot` | `bool?` | Optional | - |
| `File` | [`FileObject`](../../doc/models/file-object.md) | Optional | - |
| `Files` | [`List<FileObject>`](../../doc/models/file-object.md) | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `Icons` | [`Icons1`](../../doc/models/icons-1.md) | Optional | - |
| `Inviter` | `string` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `IsDelayedMessage` | `bool?` | Optional | - |
| `IsIntro` | `bool?` | Optional | - |
| `IsStarred` | `bool?` | Optional | - |
| `LastRead` | `string` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `LatestReply` | `string` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `Name` | `string` | Optional | - |
| `OldName` | `string` | Optional | - |
| `ParentUserId` | `string` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `Permalink` | `string` | Optional | - |
| `PinnedTo` | `List<string>` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `Purpose` | `string` | Optional | - |
| `Reactions` | [`List<ReactionObject>`](../../doc/models/reaction-object.md) | Optional | - |
| `ReplyCount` | `int?` | Optional | - |
| `ReplyUsers` | `List<string>` | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required*, *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `ReplyUsersCount` | `int?` | Optional | - |
| `SourceTeam` | `string` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `Subscribed` | `bool?` | Optional | - |
| `Subtype` | `string` | Optional | - |
| `Team` | `string` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `Text` | `string` | Required | - |
| `ThreadTs` | `string` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `Topic` | `string` | Optional | - |
| `Ts` | `string` | Required | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `Type` | `string` | Required | - |
| `UnreadCount` | `int?` | Optional | - |
| `Upload` | `bool?` | Optional | - |
| `User` | `string` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `UserProfile` | [`ObjsUserProfileShort`](../../doc/models/objs-user-profile-short.md) | Optional | - |
| `UserTeam` | `string` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `Username` | `string` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
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
```

