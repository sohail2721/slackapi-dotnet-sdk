
# Login

*This model accepts additional fields of type object.*

## Structure

`Login`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Count` | `int` | Required | - |
| `Country` | `string` | Required | - |
| `DateFirst` | `int` | Required | - |
| `DateLast` | `int` | Required | - |
| `Ip` | `string` | Required | - |
| `Isp` | `string` | Required | - |
| `Region` | `string` | Required | - |
| `UserAgent` | `string` | Required | - |
| `UserId` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `Username` | `string` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "count": 110,
  "country": "country6",
  "date_first": 14,
  "date_last": 2,
  "ip": "ip6",
  "isp": "isp2",
  "region": "region8",
  "user_agent": "user_agent4",
  "user_id": "user_id0",
  "username": "username8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

