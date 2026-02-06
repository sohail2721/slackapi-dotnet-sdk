
# Objs Enterprise User

*This model accepts additional fields of type object.*

## Structure

`ObjsEnterpriseUser`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `EnterpriseId` | `string` | Required | **Constraints**: *Pattern*: `^[E][A-Z0-9]{8,}$` |
| `EnterpriseName` | `string` | Required | - |
| `Id` | `string` | Required | **Constraints**: *Pattern*: `^[WU][A-Z0-9]{8,}$` |
| `IsAdmin` | `bool` | Required | - |
| `IsOwner` | `bool` | Required | - |
| `Teams` | `List<string>` | Required | **Constraints**: *Unique Items Required*, *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "enterprise_id": "enterprise_id0",
  "enterprise_name": "enterprise_name0",
  "id": "id0",
  "is_admin": false,
  "is_owner": false,
  "teams": [
    "teams3",
    "teams4",
    "teams5"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

