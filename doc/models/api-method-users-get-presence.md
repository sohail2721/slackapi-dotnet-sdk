
# Api Method Users Get Presence

Generated from users.getPresence with shasum e7251aec575d8863f9e0eb38663ae9dc26655f65

*This model accepts additional fields of type object.*

## Structure

`ApiMethodUsersGetPresence`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AutoAway` | `bool?` | Optional | - |
| `ConnectionCount` | `int?` | Optional | - |
| `LastActivity` | `int?` | Optional | - |
| `ManualAway` | `bool?` | Optional | - |
| `Ok` | `string` | Required, Constant | **Value**: `"True"` |
| `Online` | `bool?` | Optional | - |
| `Presence` | `string` | Required | - |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "presence": "presence8",
  "auto_away": false,
  "connection_count": 42,
  "last_activity": 166,
  "manual_away": false,
  "online": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

