
# Subteam Usergroup Object

*This model accepts additional fields of type object.*

## Structure

`SubteamUsergroupObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AutoProvision` | `bool` | Required | - |
| `AutoType` | `object` | Required | - |
| `ChannelCount` | `int?` | Optional | - |
| `CreatedBy` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `DateCreate` | `int` | Required | - |
| `DateDelete` | `int` | Required | - |
| `DateUpdate` | `int` | Required | - |
| `DeletedBy` | `object` | Required | - |
| `Description` | `string` | Required | - |
| `EnterpriseSubteamId` | `string` | Required | - |
| `Handle` | `string` | Required | - |
| `Id` | `string` | Required | **Constraints**: *Pattern*: `^S[A-Z0-9]{2,}$` |
| `IsExternal` | `bool` | Required | - |
| `IsSubteam` | `bool` | Required | - |
| `IsUsergroup` | `bool` | Required | - |
| `Name` | `string` | Required | - |
| `Prefs` | [`Prefs`](../../doc/models/prefs.md) | Required | - |
| `TeamId` | `string` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `UpdatedBy` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `UserCount` | `int?` | Optional | - |
| `Users` | `List<string>` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "auto_provision": false,
  "auto_type": {
    "key1": "val1",
    "key2": "val2"
  },
  "channel_count": 140,
  "created_by": "created_by4",
  "date_create": 240,
  "date_delete": 32,
  "date_update": 18,
  "deleted_by": {
    "key1": "val1",
    "key2": "val2"
  },
  "description": "description2",
  "enterprise_subteam_id": "enterprise_subteam_id6",
  "handle": "handle4",
  "id": "id8",
  "is_external": false,
  "is_subteam": false,
  "is_usergroup": false,
  "name": "name8",
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
  "team_id": "team_id8",
  "updated_by": "updated_by2",
  "user_count": 110,
  "users": [
    "users5",
    "users4"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

