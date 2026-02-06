
# Channel Object

*This model accepts additional fields of type object.*

## Structure

`ChannelObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AcceptedUser` | `string` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `Created` | `int` | Required | - |
| `Creator` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `Id` | `string` | Required | **Constraints**: *Pattern*: `^[C][A-Z0-9]{2,}$` |
| `IsArchived` | `bool?` | Optional | - |
| `IsChannel` | `bool` | Required | - |
| `IsFrozen` | `bool?` | Optional | - |
| `IsGeneral` | `bool?` | Optional | - |
| `IsMember` | `bool?` | Optional | - |
| `IsMoved` | `int?` | Optional | - |
| `IsMpim` | `bool` | Required | - |
| `IsNonThreadable` | `bool?` | Optional | - |
| `IsOrgShared` | `bool` | Required | - |
| `IsPendingExtShared` | `bool?` | Optional | - |
| `IsPrivate` | `bool` | Required | - |
| `IsReadOnly` | `bool?` | Optional | - |
| `IsShared` | `bool` | Required | - |
| `IsThreadOnly` | `bool?` | Optional | - |
| `LastRead` | `string` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `Latest` | `object` | Optional | - |
| `Members` | `List<string>` | Required | **Constraints**: *Minimum Items*: `0`, *Unique Items Required*, *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `Name` | `string` | Required | - |
| `NameNormalized` | `string` | Required | - |
| `NumMembers` | `int?` | Optional | - |
| `PendingShared` | `List<string>` | Optional | **Constraints**: *Minimum Items*: `0`, *Unique Items Required*, *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `PreviousNames` | `List<string>` | Optional | **Constraints**: *Minimum Items*: `0`, *Unique Items Required* |
| `Priority` | `double?` | Optional | - |
| `Purpose` | [`Purpose`](../../doc/models/purpose.md) | Required | - |
| `Topic` | [`Topic`](../../doc/models/topic.md) | Required | - |
| `Unlinked` | `int?` | Optional | - |
| `UnreadCount` | `int?` | Optional | - |
| `UnreadCountDisplay` | `int?` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "accepted_user": "accepted_user4",
  "created": 68,
  "creator": "creator4",
  "id": "id6",
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
    "members4",
    "members5",
    "members6"
  ],
  "name": "name6",
  "name_normalized": "name_normalized4",
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
```

