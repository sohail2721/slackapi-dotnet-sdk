
# Objs User Profile Short

*This model accepts additional fields of type object.*

## Structure

`ObjsUserProfileShort`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AvatarHash` | `string` | Required | - |
| `DisplayName` | `string` | Required | - |
| `DisplayNameNormalized` | `string` | Optional | - |
| `FirstName` | `string` | Required | - |
| `Image72` | `string` | Required | - |
| `IsRestricted` | `bool` | Required | - |
| `IsUltraRestricted` | `bool` | Required | - |
| `Name` | `string` | Required | - |
| `RealName` | `string` | Required | - |
| `RealNameNormalized` | `string` | Optional | - |
| `Team` | `string` | Required | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "avatar_hash": "avatar_hash2",
  "display_name": "display_name2",
  "display_name_normalized": "display_name_normalized2",
  "first_name": "first_name2",
  "image_72": "image_726",
  "is_restricted": false,
  "is_ultra_restricted": false,
  "name": "name2",
  "real_name": "real_name8",
  "real_name_normalized": "real_name_normalized4",
  "team": "team8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

