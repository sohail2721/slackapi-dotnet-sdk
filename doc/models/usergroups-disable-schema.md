
# Usergroups Disable Schema

Schema for successful response from usergroups.disable method

*This model accepts additional fields of type object.*

## Structure

`UsergroupsDisableSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Usergroup` | [`SubteamUsergroupObject`](../../doc/models/subteam-usergroup-object.md) | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "usergroup": {
    "auto_provision": false,
    "auto_type": {
      "key1": "val1",
      "key2": "val2"
    },
    "channel_count": 64,
    "created_by": "created_by0",
    "date_create": 164,
    "date_delete": 212,
    "date_update": 198,
    "deleted_by": {
      "key1": "val1",
      "key2": "val2"
    },
    "description": "description2",
    "enterprise_subteam_id": "enterprise_subteam_id0",
    "handle": "handle8",
    "id": "id2",
    "is_external": false,
    "is_subteam": false,
    "is_usergroup": false,
    "name": "name2",
    "prefs": {
      "channels": [
        "channels5",
        "channels4"
      ],
      "groups": [
        "groups4",
        "groups5",
        "groups6"
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    "team_id": "team_id6",
    "updated_by": "updated_by6",
    "user_count": 70,
    "users": [
      "users3",
      "users4",
      "users5"
    ],
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

