
# Auth Test Success Schema

Schema for successful response auth.test method

*This model accepts additional fields of type object.*

## Structure

`AuthTestSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `BotId` | `string` | Optional | **Constraints**: *Pattern*: `^B[A-Z0-9]{8,}$` |
| `IsEnterpriseInstall` | `bool?` | Optional | - |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Team` | `string` | Required | - |
| `TeamId` | `string` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `Url` | `string` | Required | - |
| `User` | `string` | Required | - |
| `UserId` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "team": "team0",
  "team_id": "team_id4",
  "url": "url4",
  "user": "user0",
  "user_id": "user_id8",
  "bot_id": "bot_id6",
  "is_enterprise_install": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

