
# Usergroups List Schema

Schema for successful response from usergroups.list method

*This model accepts additional fields of type object.*

## Structure

`UsergroupsListSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Usergroups` | [`List<SubteamUsergroupObject>`](../../doc/models/subteam-usergroup-object.md) | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "usergroups": [
    {
      "auto_provision": false,
      "auto_type": {
        "key1": "val1",
        "key2": "val2"
      },
      "channel_count": 222,
      "created_by": "created_by8",
      "date_create": 66,
      "date_delete": 114,
      "date_update": 100,
      "deleted_by": {
        "key1": "val1",
        "key2": "val2"
      },
      "description": "description6",
      "enterprise_subteam_id": "enterprise_subteam_id2",
      "handle": "handle0",
      "id": "id4",
      "is_external": false,
      "is_subteam": false,
      "is_usergroup": false,
      "name": "name4",
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
      "team_id": "team_id2",
      "updated_by": "updated_by8",
      "user_count": 28,
      "users": [
        "users9"
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

