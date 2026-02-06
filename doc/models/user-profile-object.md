
# User Profile Object

*This model accepts additional fields of type object.*

## Structure

`UserProfileObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AlwaysActive` | `bool?` | Optional | - |
| `ApiAppId` | `string` | Optional | **Constraints**: *Pattern*: `^(A[A-Z0-9]{1,})?$` |
| `AvatarHash` | `string` | Required | - |
| `BotId` | `string` | Optional | **Constraints**: *Pattern*: `^B[A-Z0-9]{8,}$` |
| `DisplayName` | `string` | Required | - |
| `DisplayNameNormalized` | `string` | Required | - |
| `Email` | `string` | Optional | - |
| `Fields` | `object` | Required | - |
| `FirstName` | `string` | Optional | - |
| `GuestExpirationTs` | `int?` | Optional | - |
| `GuestInvitedBy` | `string` | Optional | - |
| `Image1024` | `string` | Optional | - |
| `Image192` | `string` | Optional | - |
| `Image24` | `string` | Optional | - |
| `Image32` | `string` | Optional | - |
| `Image48` | `string` | Optional | - |
| `Image512` | `string` | Optional | - |
| `Image72` | `string` | Optional | - |
| `ImageOriginal` | `string` | Optional | - |
| `IsAppUser` | `bool?` | Optional | - |
| `IsCustomImage` | `bool?` | Optional | - |
| `IsRestricted` | `bool?` | Optional | - |
| `IsUltraRestricted` | `bool?` | Optional | - |
| `LastAvatarImageHash` | `string` | Optional | - |
| `LastName` | `string` | Optional | - |
| `MembershipsCount` | `int?` | Optional | - |
| `Name` | `string` | Optional | - |
| `Phone` | `string` | Required | - |
| `Pronouns` | `string` | Optional | - |
| `RealName` | `string` | Required | - |
| `RealNameNormalized` | `string` | Required | - |
| `Skype` | `string` | Required | - |
| `StatusDefaultEmoji` | `string` | Optional | - |
| `StatusDefaultText` | `string` | Optional | - |
| `StatusDefaultTextCanonical` | `string` | Optional | - |
| `StatusEmoji` | `string` | Required | - |
| `StatusExpiration` | `int?` | Optional | - |
| `StatusText` | `string` | Required | - |
| `StatusTextCanonical` | `string` | Optional | - |
| `Team` | `string` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `Title` | `string` | Required | - |
| `Updated` | `int?` | Optional | - |
| `UserId` | `string` | Optional | - |
| `Username` | `string` | Optional | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "always_active": false,
  "api_app_id": "api_app_id8",
  "avatar_hash": "avatar_hash8",
  "bot_id": "bot_id8",
  "display_name": "display_name8",
  "display_name_normalized": "display_name_normalized8",
  "email": "email8",
  "fields": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "first_name": "first_name8",
  "phone": "phone2",
  "real_name": "real_name6",
  "real_name_normalized": "real_name_normalized8",
  "skype": "skype8",
  "status_emoji": "status_emoji2",
  "status_text": "status_text0",
  "title": "title4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

