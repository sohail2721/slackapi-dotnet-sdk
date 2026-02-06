
# Log

*This model accepts additional fields of type object.*

## Structure

`Log`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AdminAppId` | `string` | Optional | **Constraints**: *Pattern*: `^A[A-Z0-9]{1,}$` |
| `AppId` | `string` | Required | **Constraints**: *Pattern*: `^A[A-Z0-9]{1,}$` |
| `AppType` | `string` | Required | - |
| `ChangeType` | `string` | Required | - |
| `Channel` | `string` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `Date` | `string` | Required | - |
| `Scope` | `string` | Required | - |
| `ServiceId` | `string` | Optional | - |
| `ServiceType` | `string` | Optional | - |
| `UserId` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `UserName` | `string` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "admin_app_id": "admin_app_id2",
  "app_id": "app_id2",
  "app_type": "app_type8",
  "change_type": "change_type2",
  "channel": "channel0",
  "date": "date0",
  "scope": "scope8",
  "service_id": "service_id6",
  "service_type": "service_type0",
  "user_id": "user_id2",
  "user_name": "user_name0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

