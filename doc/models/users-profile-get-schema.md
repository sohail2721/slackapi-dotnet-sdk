
# Users Profile Get Schema

Schema for successful response from users.profile.get method

*This model accepts additional fields of type object.*

## Structure

`UsersProfileGetSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Profile` | [`UserProfileObject`](../../doc/models/user-profile-object.md) | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "profile": {
    "always_active": false,
    "api_app_id": "api_app_id0",
    "avatar_hash": "avatar_hash0",
    "bot_id": "bot_id6",
    "display_name": "display_name0",
    "display_name_normalized": "display_name_normalized0",
    "email": "email6",
    "fields": [
      {
        "key1": "val1",
        "key2": "val2"
      }
    ],
    "first_name": "first_name0",
    "phone": "phone0",
    "real_name": "real_name6",
    "real_name_normalized": "real_name_normalized6",
    "skype": "skype0",
    "status_emoji": "status_emoji4",
    "status_text": "status_text8",
    "title": "title6",
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

